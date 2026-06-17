---
date: '2026-04-01'
description: Pelajari cara memecah gambar CAD menjadi ubin menggunakan GroupDocs Viewer
  untuk Java, meningkatkan kinerja rendering dan menyederhanakan penanganan file besar.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Cara Membagi Gambar CAD menjadi Ubin dengan GroupDocs Viewer
type: docs
url: /id/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Cara Membagi Gambar CAD menjadi Tile dengan GroupDocs Viewer

Jika Anda bertanya-tanya **how to split CAD** file menjadi bagian yang lebih kecil dan lebih mudah dikelola, Anda berada di tempat yang tepat. Dalam tutorial ini kami akan menjelaskan langkah‑langkah tepat untuk membagi gambar CAD besar menjadi tile menggunakan **GroupDocs Viewer for Java**. Pada akhir tutorial Anda akan memiliki solusi siap pakai yang meningkatkan kecepatan rendering, mengurangi konsumsi memori, dan memudahkan penampilan gambar dalam aplikasi web atau seluler.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Jawaban Cepat
- **Apa yang dicapai dengan “splitting CAD”?** Itu memecah gambar besar menjadi gambar‑gambar kecil (tile) yang dimuat lebih cepat dan menggunakan memori lebih sedikit.  
- **Format apa yang digunakan untuk tile?** File PNG dihasilkan secara default, namun format lain didukung melalui opsi Viewer.  
- **Apakah saya memerlukan lisensi?** Versi percobaan gratis dapat digunakan untuk pengembangan; lisensi berbayar diperlukan untuk produksi.  
- **Bisakah saya mengubah ukuran tile?** Ya – sesuaikan perhitungan `tileWidth` dan `tileHeight` sesuai kebutuhan Anda.  
- **Apakah pendekatan ini thread‑safe?** Merender setiap tile dalam instance `Viewer` terpisah dengan try‑with‑resources aman untuk eksekusi bersamaan.

## Apa itu “splitting CAD”?
Splitting CAD mengacu pada pembagian satu gambar CAD yang sering kali sangat besar menjadi beberapa bagian persegi panjang (tile). Setiap tile dirender secara independen, memungkinkan Anda memuat hanya bagian yang benar‑benar dibutuhkan pengguna—sempurna untuk peta web, portal dokumen, dan penampil seluler.

## Mengapa Menggunakan GroupDocs Viewer untuk Java?
GroupDocs Viewer menyediakan dukungan out‑of‑the‑box untuk lebih dari 100 format file, termasuk DWG, DXF, dan DWF. API tile‑nya memungkinkan Anda menentukan koordinat tepat, sehingga Anda dapat merender area yang Anda inginkan tanpa harus memproses seluruh file terlebih dahulu. Ini menghemat siklus CPU, mengurangi bandwidth, dan memberikan pengalaman pengguna yang lebih mulus.

## Prasyarat
- **Perpustakaan**: GroupDocs.Viewer untuk Java ≥ 25.2.  
- **JDK**: Java Development Kit terbaru apa pun (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse, atau IDE lain yang kompatibel dengan Java.  
- **Alat Build**: Maven (alat build lain dapat digunakan selama dependensi ditambahkan).  

## Menyiapkan GroupDocs.Viewer untuk Java
Tambahkan repositori GroupDocs dan dependensi ke `pom.xml` Anda:

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

### Akuisisi Lisensi
GroupDocs.Viewer menawarkan lisensi percobaan gratis untuk evaluasi:

- **Free Trial**: Kunjungi [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) untuk mengunduh perpustakaan.  
- **Temporary License**: Ajukan di [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Full License**: Beli lisensi produksi pada [Purchase Page](https://purchase.groupdocs.com/buy).

### Inisialisasi Dasar
Buat instance `Viewer` sederhana untuk memverifikasi bahwa perpustakaan dimuat dengan benar:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Panduan Langkah‑ demi‑ Langkah Membagi Gambar CAD menjadi Tile

### Langkah 1: Tentukan Direktori Output
Kami akan menyimpan setiap tile sebagai file PNG terpisah. Menggunakan metode utilitas menjaga logika path tetap bersih dan dapat digunakan kembali.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Langkah 2: Konfigurasikan Opsi Tampilan
Setel format rendering ke PNG dan beri tahu viewer untuk tidak memuat pra‑semua halaman (yang menghemat memori).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Langkah 3: Hitung Dimensi Tile
Pertama kami memperoleh lebar dan tinggi asli gambar, kemudian membaginya menjadi empat kuadran yang sama besar.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Langkah 4: Render dan Simpan Tile
Tambahkan tile yang telah dihitung ke opsi rendering dan biarkan `Viewer` menghasilkan file PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Tips Pemecahan Masalah
- **Build path** – Pastikan file JAR GroupDocs berada di classpath.  
- **Permissions** – Folder output harus dapat ditulisi oleh proses Java.  
- **Exceptions** – Jika Anda melihat `ViewerException`, periksa kembali bahwa file DWG tidak rusak dan lisensi yang benar telah diterapkan.

## Kasus Penggunaan Umum untuk Membagi Tile CAD
1. **Web Mapping** – Muat hanya bagian yang terlihat dari denah saat pengguna menggeser/men‑zoom.  
2. **Document Management** – Simpan setiap tile secara terpisah untuk pembuatan pratinjau yang lebih cepat.  
3. **Mobile Viewing** – Kurangi bandwidth dengan mengunduh hanya tile yang diperlukan untuk layar saat ini.

## Pertimbangan Kinerja
- **Tile Size** – Tile yang lebih besar berarti lebih sedikit file tetapi rendering lebih lambat; temukan keseimbangan berdasarkan kebutuhan UI Anda.  
- **Memory Monitoring** – Gunakan alat profil Java (misalnya VisualVM) untuk memantau penggunaan heap saat memproses gambar sangat besar.  
- **Resource Cleanup** – Pola try‑with‑resources yang ditunjukkan di atas secara otomatis melepaskan sumber daya native.

## Pertanyaan yang Sering Diajukan

**Q: Bisakah saya membagi tipe file lain (PDF, gambar) menjadi tile menggunakan pendekatan yang sama?**  
A: Ya. GroupDocs Viewer mendukung banyak format; Anda hanya perlu menggunakan kelas opsi yang sesuai (misalnya `PdfViewOptions`).

**Q: Bagaimana cara mengubah kualitas gambar output?**  
A: Sesuaikan `viewOptions.setResolution(int dpi)` atau atur pengaturan kompresi pada objek `PngOptions`.

**Q: Aplikasi saya kehabisan memori pada file DWG yang sangat besar—apa yang dapat saya lakukan?**  
A: Kurangi dimensi tile, tingkatkan heap JVM (`-Xmx`), atau render tile secara berurutan dalam instance `Viewer` terpisah.

**Q: Apakah memungkinkan merender tile secara asynchronous?**  
A: Tentu saja. Bungkus setiap pemanggilan rendering tile dalam `CompletableFuture` atau gunakan layanan executor untuk memparallelkan beban kerja.

**Q: Apakah saya memerlukan lisensi terpisah untuk setiap tile?**  
A: Tidak. Satu lisensi GroupDocs Viewer yang valid mencakup semua operasi rendering dalam aplikasi Anda.

## Sumber Daya
- [Dokumentasi](https://docs.groupdocs.com/viewer/java/)
- [Referensi API](https://reference.groupdocs.com/viewer/java/)
- [Unduh GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Beli Lisensi](https://purchase.groupdocs.com/buy)
- [Trial Gratis](https://releases.groupdocs.com/viewer/java/)
- [Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- [Forum Dukungan](https://forum.groupdocs.com/c/viewer/9)

---

**Terakhir Diperbarui:** 2026-04-01  
**Diuji Dengan:** GroupDocs.Viewer 25.2 untuk Java  
**Penulis:** GroupDocs