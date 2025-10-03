---
"date": "2025-04-25"
"description": "Pelajari cara mengonversi file TXT ke berbagai format seperti HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET dengan panduan lengkap ini."
"title": "Konversi TXT ke HTML, JPG, PNG, PDF Menggunakan GroupDocs.Viewer .NET&#58; Panduan Lengkap"
"url": "/id/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# Konversi TXT ke Beberapa Format dengan GroupDocs.Viewer .NET

## Perkenalan

Ingin mengonversi dokumen teks ke berbagai format seperti HTML, JPG, PNG, atau PDF dengan mudah? Mengelola konversi dokumen bisa jadi sulit, terutama saat menangani beberapa halaman atau persyaratan format tertentu. **GroupDocs.Viewer untuk .NET** menyederhanakan proses rendering file TXT ke dalam beragam format keluaran, memastikan data Anda dapat diakses dan menarik secara visual.

![Konversi TXT ke HTML, JPG, PNG, PDF dengan GroupDocs.Viewer untuk .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Dalam panduan ini, kita akan membahas cara menggunakan GroupDocs.Viewer for .NET untuk mengubah dokumen TXT menjadi HTML multi-halaman, HTML satu halaman, JPG, PNG, dan PDF. Pada akhirnya, Anda akan menguasai:
- Mengonversi file TXT menggunakan C# dengan GroupDocs.Viewer
- Menerapkan berbagai opsi rendering sesuai kebutuhan Anda
- Mengoptimalkan kinerja selama konversi

Mari selami untuk memecahkan tantangan konversi dokumen Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan hal-hal berikut:
- **Lingkungan Pengembangan**: Visual Studio 2019 atau yang lebih baru.
- **Kerangka .NET**: Versi 4.6.1 atau lebih tinggi.
- **GroupDocs.Viewer untuk Pustaka .NET**:
  - Melalui Konsol Manajer Paket NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Menggunakan .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Disarankan untuk memahami pemrograman C# dan operasi file dasar dalam .NET agar mudah dipahami.

## Menyiapkan GroupDocs.Viewer untuk .NET

### Instalasi

Untuk memulai, instal **Penampil GroupDocs** perpustakaan menggunakan manajer paket pilihan Anda:

#### Konsol Pengelola Paket NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .KLIK NET
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Lisensi

Anda bisa memulai dengan **uji coba gratis** atau mendapatkan **lisensi sementara** untuk mengeksplorasi kemampuan penuh GroupDocs.Viewer untuk .NET tanpa batasan evaluasi:
- Uji Coba Gratis: [Unduh di sini](https://releases.groupdocs.com/viewer/net/)
- Lisensi Sementara: [Minta di sini](https://purchase.groupdocs.com/temporary-license/)

Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli lisensi langsung dari [GrupDocs](https://purchase.groupdocs.com/buy).

### Inisialisasi Dasar

Untuk menyiapkan GroupDocs.Viewer di proyek Anda:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Inisialisasi objek Viewer dengan jalur file TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Kode rendering Anda akan berada di sini.
}
```

## Panduan Implementasi

Sekarang, mari kita bahas setiap fitur dan lihat bagaimana Anda dapat mengimplementasikannya.

### Render Dokumen TXT ke HTML Multi-halaman

#### Ringkasan
Fitur ini menunjukkan cara mengonversi dokumen TXT ke format HTML multi-halaman. Setiap halaman file teks ditampilkan sebagai file HTML individual dengan sumber daya tertanam.

#### Langkah 1: Siapkan Penampil

Membuat sebuah `Viewer` objek untuk file TXT sumber Anda:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Inisialisasi Viewer dengan contoh berkas teks.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Lanjutkan ke langkah 2...
```

#### Langkah 2: Konfigurasikan Opsi Tampilan HTML

Mendirikan `HtmlViewOptions` untuk merender setiap halaman secara terpisah:

```csharp
// Siapkan opsi tampilan HTML untuk rendering multi-halaman.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Render dokumen sebagai HTML multi-halaman.
viewer.View(options);
}
```

**Penjelasan**: : Itu `ForEmbeddedResources()` Metode ini memastikan bahwa sumber daya seperti gambar dan gaya tertanam langsung dalam berkas HTML, sehingga memudahkan berbagi.

### Render Dokumen TXT ke HTML Satu Halaman

#### Ringkasan
Mengubah dokumen TXT menjadi satu halaman HTML, ideal untuk dokumen yang perlu ditampilkan sebagai satu halaman web berkelanjutan.

#### Langkah 1: Siapkan Penampil

Inisialisasi `Viewer` obyek:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Inisialisasi contoh Viewer baru untuk berkas teks yang berbeda.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Lanjutkan ke langkah 2...
```

#### Langkah 2: Konfigurasikan Opsi HTML Halaman Tunggal

Konfigurasi `HtmlViewOptions` dengan pengaturan satu halaman diaktifkan:

```csharp
// Siapkan pilihan untuk merender ke dalam satu halaman HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Render sebagai satu halaman HTML.
viewer.View(options);
}
```

**Penjelasan**: : Itu `RenderToSinglePage` Properti memastikan seluruh konten ditampilkan pada satu halaman.

### Render Dokumen TXT ke JPG

#### Ringkasan
Fitur ini memungkinkan Anda mengubah dokumen teks menjadi gambar JPEG, berguna untuk presentasi visual atau tujuan pengarsipan.

#### Langkah 1: Siapkan Penampil

Siapkan `Viewer` obyek:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Inisialisasi penampil dengan berkas contoh.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Lanjutkan ke langkah 2...
```

#### Langkah 2: Konfigurasikan Opsi Tampilan JPG

Mendirikan `JpgViewOptions` untuk rendering gambar:

```csharp
// Siapkan pilihan untuk merender sebagai gambar JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Render dokumen sebagai berkas JPEG.
viewer.View(options);
}
```

**Penjelasan**: : Itu `JpgViewOptions` Kelas ini menentukan cara merender dan menyimpan setiap halaman dokumen Anda dalam format JPEG.

### Render Dokumen TXT ke PNG

#### Ringkasan
Mengonversi dokumen teks ke format PNG, menawarkan keluaran gambar berkualitas tinggi dengan dukungan transparansi.

#### Langkah 1: Siapkan Penampil

Inisialisasi `Viewer` obyek:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Buat contoh penampil untuk berkas TXT Anda.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Lanjutkan ke langkah 2...
```

#### Langkah 2: Konfigurasikan Opsi Tampilan PNG

Mendirikan `PngViewOptions`:

```csharp
// Siapkan opsi tampilan untuk ditampilkan sebagai gambar PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Render dokumen dalam format PNG.
viewer.View(options);
}
```

**Penjelasan**: : Itu `PngViewOptions` kelas memungkinkan setiap halaman ditampilkan dengan transparansi, membuatnya cocok untuk grafik berlapis.

### Render Dokumen TXT ke PDF

#### Ringkasan
Fitur ini sempurna untuk mengubah dokumen teks menjadi format PDF yang dapat diakses secara universal.

#### Langkah 1: Siapkan Penampil

Siapkan `Viewer` obyek:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Inisialisasi contoh penampil untuk berkas teks contoh Anda.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Lanjutkan ke langkah 2...
```

#### Langkah 2: Konfigurasikan Opsi Tampilan PDF

Mendirikan `PdfViewOptions`:

```csharp
// Siapkan pilihan tampilan untuk ditampilkan sebagai dokumen PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Ubah dokumen menjadi berkas PDF.
viewer.View(options);
}
```

**Penjelasan**: : Itu `PdfViewOptions` kelas menentukan cara mengonversi dan menyimpan file TXT Anda sebagai dokumen PDF.

## Kesimpulan

Dengan GroupDocs.Viewer untuk .NET, mengonversi dokumen teks ke berbagai format menjadi mudah. Panduan ini membahas cara mengubah file TXT menjadi HTML multi-halaman, HTML satu halaman, JPG, PNG, dan PDF menggunakan C#. Baik Anda ingin meningkatkan aksesibilitas atau kompatibilitas dokumen, metode ini menyediakan solusi yang tangguh.

Untuk bantuan lebih lanjut atau fitur yang lebih canggih, lihat [dokumentasi resmi GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/)Selamat membuat kode!