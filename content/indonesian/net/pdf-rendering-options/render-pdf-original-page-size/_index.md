---
"description": "Pelajari cara merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami dan integrasikan fungsionalitas ini dengan lancar."
"linktitle": "Render PDF dengan Ukuran Halaman Asli"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render PDF dengan Ukuran Halaman Asli"
"url": "/id/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# Render PDF dengan Ukuran Halaman Asli

## Perkenalan
Dalam bidang pengembangan .NET, GroupDocs.Viewer menonjol sebagai alat yang hebat untuk merender berbagai format dokumen, termasuk PDF. Salah satu persyaratan umum dalam penanganan dokumen adalah merender PDF sambil mempertahankan ukuran halaman aslinya. Untuk mencapai tugas ini dengan lancar, diperlukan pemahaman yang menyeluruh tentang GroupDocs.Viewer untuk .NET dan fungsinya.

![Render PDF dengan Ukuran Halaman Asli dengan GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Prasyarat
Sebelum mulai merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
Mulailah dengan mengunduh pustaka GroupDocs.Viewer dari situs web. Anda dapat memperoleh pustaka tersebut dari situs web yang disediakan. [tautan unduhan](https://releases.groupdocs.com/viewer/net/)Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk mengintegrasikannya ke dalam proyek .NET Anda secara efektif.
### 2. Siapkan Lingkungan Pengembangan
Pastikan Anda memiliki lingkungan pengembangan yang disiapkan untuk pengembangan .NET. Ini termasuk memasang IDE yang kompatibel, seperti Visual Studio, dan pemahaman dasar tentang pemrograman C#.
### 3. Dapatkan Dokumen PDF
Anda memerlukan contoh dokumen PDF untuk ditampilkan dengan GroupDocs.Viewer. Anda dapat menggunakan dokumen PDF apa pun untuk tujuan pengujian. Jika Anda tidak memilikinya, Anda dapat mengunduh contoh PDF dari berbagai sumber daring.

## Mengimpor Ruang Nama
Sebelum melanjutkan dengan merender PDF, penting untuk mengimpor namespace yang diperlukan ke dalam proyek C# Anda. Langkah ini memungkinkan Anda untuk mengakses kelas dan metode yang diperlukan dari pustaka GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang Anda telah menyiapkan prasyarat dan mengimpor namespace yang diperlukan, mari kita uraikan proses merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET ke dalam beberapa langkah sederhana:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Pastikan Anda menentukan direktori tempat Anda ingin menyimpan halaman yang dirender. Ganti `"Your Document Directory"` dengan jalur direktori yang Anda inginkan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Siapkan format untuk memberi nama berkas halaman yang dirender. Dalam contoh ini, halaman akan disimpan sebagai gambar PNG dengan nama berkas dalam format `"page_1.png"`Bahasa Indonesia: `"page_2.png"`, dan seterusnya.
## Langkah 3: Render PDF dengan Ukuran Halaman Asli
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Membuat contoh sebuah `Viewer` objek dengan jalur ke file PDF Anda. Kemudian, buat `PngViewOptions` dengan format jalur berkas halaman yang ditentukan. Atur `RenderOriginalPageSize` properti untuk `true` untuk mempertahankan ukuran halaman asli saat merender.
## Langkah 4: Menampilkan Lokasi Dokumen yang Dirender
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cetak pesan yang menunjukkan keberhasilan rendering dan berikan direktori tempat halaman yang dirender disimpan.

## Kesimpulan
Merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET merupakan proses yang mudah jika Anda mengikuti langkah-langkah yang diuraikan dalam tutorial ini. Dengan mengimpor namespace yang diperlukan dan mengikuti panduan langkah demi langkah, Anda dapat mengintegrasikan fungsionalitas ini ke dalam aplikasi .NET Anda dengan lancar.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer menyajikan format dokumen lain selain PDF?
Ya, GroupDocs.Viewer mendukung rendering berbagai format dokumen, termasuk Word, Excel, PowerPoint, dan lainnya.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer kompatibel dengan lingkungan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan format keluaran halaman yang ditampilkan?
Ya, Anda dapat menyesuaikan format keluaran dengan menyesuaikan opsi yang disediakan oleh GroupDocs.Viewer, seperti mengatur format gambar yang berbeda atau menentukan opsi rendering khusus.
### Apakah GroupDocs.Viewer menawarkan dukungan untuk rendering dokumen berbasis cloud?
Ya, GroupDocs.Viewer menyediakan API untuk penyajian dokumen berbasis cloud, yang memungkinkan Anda menyajikan dokumen langsung dari penyedia penyimpanan cloud.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer?
Ya, Anda dapat menjelajahi GroupDocs.Viewer dengan uji coba gratis dengan mengunjungi situs web yang disediakan [link](https://releases.groupdocs.com/).