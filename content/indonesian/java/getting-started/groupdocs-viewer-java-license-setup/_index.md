---
date: '2026-03-08'
description: Pelajari cara mendapatkan lisensi sementara, menyiapkan GroupDocs.Viewer
  untuk Java menggunakan file lokal atau URL, dan memverifikasi ketersediaan jalur
  lisensi.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Cara mendapatkan lisensi sementara dan mengatur lisensi di GroupDocs.Viewer
  Java
type: docs
url: /id/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

# Cara mendapatkan lisensi sementara dan mengatur lisensi di GroupDocs.Viewer Java

Mengelola lisensi secara efisien sangat penting saat mengintegrasikan pustaka pihak ketiga seperti **GroupDocs.Viewer for Java** ke dalam aplikasi Anda. Panduan ini menunjukkan **cara mendapatkan lisensi sementara**, mengaturnya dari file lokal atau URL HTTP, dan memverifikasi bahwa jalur lisensi benar. Pada akhir tutorial ini Anda akan memiliki pengaturan lisensi yang andal dan siap produksi yang menjaga aplikasi Anda tetap sesuai dan berperforma.

![Pengaturan File dan URL dengan GroupDocs.Viewer untuk Java](/viewer/getting-started/file-and-url-setup-png.png)

## Jawaban Cepat
- **Bagaimana cara saya mendapatkan lisensi sementara?** Minta satu dari halaman lisensi sementara GroupDocs dan unduh file *.lic*.  
- **Apakah saya dapat memuat lisensi dari URL?** Ya – cukup arahkan `License.setLicense` ke alamat HTTP yang mengembalikan file lisensi yang valid.  
- **Apa yang terjadi jika jalur lisensi tidak ada?** Terapkan pemeriksaan untuk menampilkan panduan dan mencegah viewer berjalan.  
- **Apakah saya perlu memulai ulang aplikasi setelah mengubah lisensi?** Tidak, `License.setLicense` dapat dipanggil pada runtime.  
- **Versi Java apa yang diperlukan?** JDK 8 atau lebih tinggi disarankan.

## Apa itu lisensi sementara?
Sebuah **lisensi sementara** adalah kunci berjangka waktu yang dikeluarkan oleh GroupDocs yang memungkinkan Anda mengevaluasi produk tanpa membeli lisensi penuh. Lisensi ini berfungsi persis seperti lisensi permanen selama masih berlaku, memungkinkan Anda menguji semua fitur dalam lingkungan dunia nyata.

## Mengapa mendapatkan lisensi sementara?
- **Evaluasi cepat:** Dapatkan fungsionalitas penuh secara instan untuk proyek proof‑of‑concept.  
- **Tidak ada komitmen finansial:** Uji sebelum membeli.  
- **Integrasi mudah:** Bekerja dengan panggilan API yang sama seperti lisensi permanen.

## Prasyarat
1. **Java Development Kit (JDK):** Versi 8 atau lebih tinggi.  
2. **IDE:** IntelliJ IDEA, Eclipse, atau IDE kompatibel Java apa pun.  
3. **Pustaka GroupDocs.Viewer untuk Java:** Ditambahkan ke proyek Anda (lihat pengaturan Maven di bawah).  
4. **Pengetahuan dasar Java:** Familiaritas dengan kelas, impor, dan penanganan pengecualian.

## Menyiapkan GroupDocs.Viewer untuk Java
Untuk memulai, sertakan pustaka dalam proyek Maven Anda.

### Konfigurasi Maven
Tambahkan konfigurasi berikut ke file `pom.xml` Anda:
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Memperoleh Lisensi
Untuk menggunakan GroupDocs.Viewer, dapatkan lisensi:
- **Uji Coba Gratis:** Unduh dari [situs GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Lisensi Sementara:** Minta satu di [halaman lisensi sementara](https://purchase.groupdocs.com/temporary-license/).  
- **Pembelian:** Untuk solusi permanen, pertimbangkan membeli lisensi dari [halaman pembelian GroupDocs](https://purchase.groupdocs.com/buy).

### Inisialisasi Dasar
Setelah pustaka ditambahkan, Anda dapat menginisialisasi viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Cara mendapatkan lisensi sementara dan mengaturnya dari file
### Ikhtisar
Mengatur lisensi dari file lokal adalah pendekatan paling sederhana dan berfungsi bahkan ketika aplikasi berjalan offline.

### Langkah Implementasi
1. **Tentukan Jalur Lisensi** – arahkan ke file *.lic* yang Anda terima setelah meminta lisensi sementara:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Terapkan Lisensi** – gunakan kelas `License` untuk memuatnya:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Tips:**  
- Pastikan jalur file bersifat absolut atau relatif terhadap direktori kerja.  
- Pastikan file memiliki izin baca untuk pengguna yang menjalankan JVM.

## Cara menangani lisensi berbasis URL
### Ikhtisar
Lisensi berbasis URL berguna untuk penyebaran cloud di mana file lisensi berada di bucket penyimpanan yang aman.

### Langkah Implementasi
1. **Tentukan URL Lisensi** – ganti placeholder dengan endpoint aktual Anda:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Deteksi dan Catat Penggunaan URL** – contoh di bawah hanya memberi tahu bahwa URL telah disediakan:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Tips:**  
- Di produksi Anda akan mengunduh file (misalnya dengan `java.net.HttpURLConnection`) dan kemudian memanggil `license.setLicense(stream)`.  
- Tambahkan logika retry dan penanganan timeout untuk mengatasi masalah jaringan sementara.

## Cara memeriksa ketersediaan lisensi (memverifikasi jalur lisensi)
### Ikhtisar
Sebelum mencoba memuat lisensi, praktik yang baik adalah **memeriksa ketersediaan lisensi** sehingga Anda dapat membimbing pengembang atau pengguna untuk memperoleh lisensi sementara bila diperlukan.

### Langkah Implementasi
1. **Simulasikan jalur lisensi yang hilang**:
```java
final String licensePath = null;
```
2. **Berikan panduan jelas jika jalur tidak ada**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Tips:**  
- Catat pesan ini saat startup sehingga tim operasional mengetahui lisensi tidak ada.  
- Pertimbangkan untuk menghentikan aplikasi atau menonaktifkan fitur viewer hingga lisensi yang valid disediakan.

## Aplikasi Praktis
Memahami cara **mendapatkan lisensi sementara**, mengaturnya dari file atau URL, dan **memverifikasi jalur lisensi** membuka beberapa skenario dunia nyata:
1. **Sistem Manajemen Dokumen** – menyematkan viewer yang secara otomatis memvalidasi lisensinya pada setiap peluncuran.  
2. **Platform SaaS Cloud** – menyimpan lisensi di penyimpanan blob yang terlindungi dan memuatnya melalui URL untuk pembaruan tanpa downtime.  
3. **Deploymen Perusahaan** – menggunakan lisensi sementara selama fase pilot sebelum membeli lisensi skala penuh.

## Pertimbangan Kinerja
- **Penggunaan sumber daya:** Muat lisensi sekali saat aplikasi dimulai; pemanggilan berulang menambah I/O yang tidak perlu.  
- **Manajemen memori:** Objek `License` menyimpan state minimal, tetapi selalu tutup stream jika Anda mengunduh lisensi secara manual.

## Kesimpulan
Dengan mengikuti langkah‑langkah di atas Anda dapat **mendapatkan lisensi sementara**, mengonfigurasi GroupDocs.Viewer untuk Java menggunakan file lokal atau URL HTTP, dan **memeriksa ketersediaan lisensi** untuk menjaga aplikasi Anda tetap sesuai. Fondasi lisensi yang solid ini mencegah kesalahan runtime dan memberi Anda fleksibilitas untuk berpindah antara lingkungan pengembangan, pengujian, dan produksi dengan percaya diri.

### FAQ

1. **Bagaimana cara saya mengatur file lisensi lokal di GroupDocs.Viewer Java?**  

   Gunakan `license.setLicense("path/to/license.lic")` dengan jalur file yang benar untuk menerapkan lisensi lokal.

2. **Apakah saya dapat memuat lisensi langsung dari URL?**  

   Ya, tetapi pastikan kode Anda menangani akses URL, mungkin dengan mengunduh lisensi pada runtime atau mengelola masalah jaringan.

3. **Apa yang harus saya lakukan jika jalur lisensi tidak valid atau tidak ada?**  

   Terapkan pemeriksaan untuk nilai null atau jalur tidak valid dan berikan panduan atau prompt cadangan untuk memperoleh lisensi yang valid.

4. **Apakah memungkinkan beralih antara file lisensi dan URL secara dinamis?**  

   Tentu saja, dengan menambahkan logika kondisional untuk menangani kedua skenario berdasarkan lingkungan atau parameter runtime Anda.

5. **Apa praktik terbaik untuk manajemen lisensi di produksi?**  

   Simpan lisensi secara aman, verifikasi keabsahannya secara berkala, dan terapkan penanganan kesalahan untuk masalah lisensi guna memastikan layanan tetap berjalan tanpa gangguan.

## Pertanyaan yang Sering Diajukan

**T: Berapa lama lisensi sementara berlaku?**  
J: Biasanya 30 hari, setelah itu Anda dapat meminta perpanjangan atau meningkatkan ke lisensi permanen.

**T: Apakah saya memerlukan koneksi internet untuk menggunakan lisensi berbasis file?**  
J: Tidak. File *.lic* lokal berfungsi sepenuhnya offline setelah dimuat.

**T: Bisakah saya mengenkripsi file lisensi untuk keamanan tambahan?**  
J: File lisensi sudah ditandatangani oleh GroupDocs; enkripsi tambahan bersifat opsional tetapi tidak diperlukan.

**T: Apa yang terjadi jika lisensi kedaluwarsa saat aplikasi berjalan?**  
J: Operasi viewer akan mulai melempar pengecualian lisensi; disarankan untuk memeriksa kedaluwarsa saat startup.

**T: Apakah aman menyimpan URL lisensi di kontrol sumber?**  
J: Hindari meng-commit URL sensitif; gunakan variabel lingkungan atau penyimpanan konfigurasi yang aman sebagai gantinya.

---

**Last Updated:** 2026-03-08  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs