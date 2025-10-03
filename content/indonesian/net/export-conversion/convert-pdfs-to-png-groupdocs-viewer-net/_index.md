---
"date": "2025-04-25"
"description": "Pelajari cara mengonversi halaman PDF ke gambar PNG sambil mempertahankan dimensi asli menggunakan GroupDocs.Viewer untuk .NET. Panduan ini mencakup penyiapan, konfigurasi, dan praktik terbaik."
"title": "Konversi PDF ke PNG dengan Ukuran Asli Menggunakan GroupDocs.Viewer untuk .NET"
"url": "/id/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# Konversi PDF ke PNG dengan Ukuran Asli Menggunakan GroupDocs.Viewer untuk .NET

## Perkenalan

Mengonversi file PDF menjadi gambar PNG sambil mempertahankan ukuran halaman asli sangat penting untuk digitalisasi dokumen berkualitas tinggi atau persiapan konten web. Tutorial ini akan memandu Anda menggunakan GroupDocs.Viewer for .NET untuk merender halaman PDF sebagai file PNG, dengan mempertahankan dimensi aslinya.

![Konversi PDF ke PNG dengan Ukuran Asli dengan GroupDocs.Viewer untuk .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Apa yang Akan Anda Pelajari:**
- Cara mengatur dan mengonfigurasi GroupDocs.Viewer untuk .NET di proyek Anda
- Proses langkah demi langkah untuk merender PDF ke gambar PNG sambil mempertahankan ukuran halaman
- Opsi konfigurasi utama dan praktik terbaik untuk kinerja optimal

Di akhir tutorial ini, Anda akan dapat mengintegrasikan fungsi ini ke dalam aplikasi Anda dengan lancar. Mari kita mulai dengan prasyarat yang diperlukan untuk memulai.

## Prasyarat

Sebelum menerapkan GroupDocs.Viewer untuk .NET di proyek Anda, pastikan Anda memiliki persyaratan berikut:

### Pustaka dan Versi yang Diperlukan
- **GroupDocs.Viewer untuk .NET**: Versi 25.3.0 atau lebih baru.

### Persyaratan Pengaturan Lingkungan
- Lingkungan pengembangan yang kompatibel seperti Visual Studio.
- Pemahaman dasar tentang pemrograman C#.

### Prasyarat Pengetahuan
- Keakraban dengan manajemen paket NuGet.
- Beberapa pengalaman bekerja dengan PDF dan pemrosesan gambar dalam aplikasi .NET.

Setelah Anda memiliki prasyarat ini, kita dapat melanjutkan untuk menyiapkan GroupDocs.Viewer untuk .NET.

## Menyiapkan GroupDocs.Viewer untuk .NET

Untuk mulai menggunakan GroupDocs.Viewer untuk .NET, ikuti langkah-langkah instalasi di bawah ini:

### Instalasi melalui Konsol Pengelola Paket NuGet
Buka proyek Anda di Visual Studio dan gunakan perintah berikut:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Instalasi melalui .NET CLI
Atau, Anda dapat menginstalnya menggunakan .NET CLI dengan perintah ini:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Langkah-langkah Memperoleh Lisensi
1. **Uji Coba Gratis**: Unduh versi uji coba dari [Unduhan GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Lisensi Sementara**: Dapatkan lisensi sementara untuk menjelajahi fitur lengkap di [Halaman Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/).
3. **Pembelian**:Untuk penggunaan jangka panjang, beli lisensi melalui [Halaman Pembelian](https://purchase.groupdocs.com/buy).

### Inisialisasi dan Pengaturan Dasar
Untuk menginisialisasi GroupDocs.Viewer untuk .NET di proyek C# Anda, ikuti langkah-langkah berikut:
1. Impor namespace yang diperlukan:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Siapkan jalur untuk PDF masukan dan direktori keluaran Anda.
3. Inisialisasi `Viewer` dengan jalur ke dokumen sumber Anda, seperti yang ditunjukkan dalam cuplikan ini:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Panduan Implementasi
Bagian ini mencakup penerapan rendering halaman PDF sebagai gambar PNG dengan tetap mempertahankan ukuran aslinya.

### Merender Halaman PDF ke PNG dengan Ukuran Halaman Asli
#### Ringkasan
Fitur ini memungkinkan Anda untuk merender setiap halaman dokumen PDF menjadi gambar PNG, dengan tetap mempertahankan dimensi aslinya. Fitur ini sangat berguna untuk aplikasi yang memerlukan representasi visual dokumen yang tepat.

##### Langkah 1: Siapkan Jalur dan Inisialisasi Penampil
Buat variabel untuk jalur PDF input dan direktori output Anda:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Inisialisasi `Viewer` kelas dengan jalur dokumen sumber Anda:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Blok kode akan dilanjutkan pada langkah berikutnya
}
```
##### Langkah 2: Konfigurasikan PngViewOptions
Buat contoh dari `PngViewOptions`, menentukan pola penamaan file untuk gambar keluaran:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Konfigurasikan opsi penampil untuk menampilkan setiap halaman pada ukuran aslinya:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Langkah 3: Render Halaman Dokumen
Telepon `View` metode pada Anda `Viewer` misalnya, dengan meneruskan opsi tampilan yang dikonfigurasi:
```csharp
viewer.View(viewOptions);
```
### Tips Pemecahan Masalah
- Pastikan jalur sudah benar dan direktori ada.
- Verifikasi bahwa Anda memiliki izin yang diperlukan untuk membaca dari direktori input dan menulis ke direktori output.

## Aplikasi Praktis
1. **Digitalisasi Dokumen**: Ubah dokumen PDF arsip menjadi gambar digital agar lebih mudah diakses dan didistribusikan.
2. **Portal Web**: Menampilkan pratinjau dokumen di situs web tanpa memerlukan pembaca PDF.
3. **Sistem Manajemen Konten (CMS)**: Integrasikan dengan platform CMS untuk mengelola dan menampilkan konten PDF dalam jumlah besar secara efisien.

## Pertimbangan Kinerja
Untuk mengoptimalkan kinerja aplikasi Anda menggunakan GroupDocs.Viewer untuk .NET:
- Batasi penggunaan memori dengan memproses dokumen dalam potongan-potongan jika berurusan dengan file besar.
- Gunakan metode asinkron jika memungkinkan untuk menghindari pemblokiran thread selama rendering.
- Buang `Viewer` contoh segera setelah digunakan untuk mengosongkan sumber daya.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara merender halaman PDF sebagai gambar PNG sambil mempertahankan ukuran aslinya menggunakan GroupDocs.Viewer untuk .NET. Kami membahas pengaturan lingkungan Anda, mengonfigurasi opsi yang diperlukan untuk hasil yang optimal, dan mengeksplorasi aplikasi praktis untuk fungsionalitas ini.

Langkah selanjutnya termasuk bereksperimen dengan opsi rendering lain yang tersedia di GroupDocs.Viewer atau mengintegrasikannya ke dalam proyek yang lebih besar untuk meningkatkan kemampuan manajemen dokumen.

## Bagian FAQ
1. **Apa cara terbaik untuk menangani file PDF besar dengan GroupDocs.Viewer?**
   - Memproses dokumen dalam potongan yang lebih kecil dan menggunakan metode asinkron untuk mempertahankan kinerja.
2. **Bisakah saya menyesuaikan nama file PNG keluaran?**
   - Ya, dengan menentukan pola penamaan di `PngViewOptions`.
3. **Bisakah hanya menampilkan halaman tertentu saja?**
   - Tentu saja, Anda dapat mengonfigurasinya `PageNumbers` di dalam `PngViewOptions` untuk menentukan halaman mana yang akan dirender.
4. **Bagaimana cara menangani perizinan untuk GroupDocs.Viewer?**
   - Pilihannya meliputi uji coba gratis, lisensi sementara, atau pembelian lisensi penuh.
5. **Bisakah pengaturan ini digunakan dalam aplikasi web?**
   - Ya, ini cocok untuk rendering PDF sisi server di ASP.NET Core dan kerangka kerja web berbasis .NET lainnya.

## Sumber daya
- [Dokumentasi](https://docs.groupdocs.com/viewer/net/)
- [Referensi API](https://reference.groupdocs.com/viewer/net/)
- [Unduh GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Beli Lisensi](https://purchase.groupdocs.com/buy)
- [Uji Coba Gratis](https://releases.groupdocs.com/viewer/net/)
- [Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- [Forum Dukungan](https://forum.groupdocs.com/c/viewer/9)