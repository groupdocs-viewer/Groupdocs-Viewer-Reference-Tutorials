---
"description": "Pelajari cara menyesuaikan ukuran gambar keluaran untuk gambar CAD menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan visibilitas dan kegunaan dengan mudah."
"linktitle": "Sesuaikan Ukuran Gambar Output untuk Gambar CAD"
"second_title": "API Penampil GroupDocs.NET"
"title": "Sesuaikan Ukuran Gambar Output untuk Gambar CAD"
"url": "/id/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# Sesuaikan Ukuran Gambar Output untuk Gambar CAD

## Perkenalan
Gambar CAD sering kali memerlukan penyesuaian khusus untuk tampilan dan presentasi yang optimal. GroupDocs.Viewer untuk .NET menyediakan seperangkat alat yang canggih untuk mengelola dan menyesuaikan keluaran gambar CAD. Dalam tutorial ini, kami akan memandu Anda melalui proses penyesuaian ukuran gambar keluaran untuk gambar CAD langkah demi langkah.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Direktori Dokumen: Siapkan direktori tempat dokumen Anda berada.
3. Pemahaman Dasar: Biasakan diri Anda dengan konsep dasar pemrograman .NET.

## Mengimpor Ruang Nama
Pertama, pastikan untuk mengimpor namespace yang diperlukan untuk mengakses fungsionalitas GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Atur Direktori Output
Tentukan direktori tempat Anda ingin menyimpan gambar keluaran gambar CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Mengatur format untuk jalur berkas halaman. Format ini akan digunakan untuk memberi nama dan menyimpan halaman individual sebagai berkas HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Sesuaikan Ukuran Gambar
Di dalam blok penggunaan untuk objek Viewer, sesuaikan ukuran gambar untuk gambar CAD dengan mengatur opsi yang sesuai:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Langkah 4: Menampilkan Direktori Output
Setelah merender dokumen, tampilkan pesan yang menunjukkan keberhasilan rendering dan berikan lokasi direktori output:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Menyesuaikan ukuran gambar keluaran untuk gambar CAD sangat penting untuk meningkatkan visibilitas dan kegunaannya. Dengan GroupDocs.Viewer untuk .NET, proses ini menjadi lebih efisien dan mudah, sehingga Anda dapat menyesuaikan keluaran sesuai dengan kebutuhan spesifik Anda.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menyesuaikan ukuran gambar keluaran untuk jenis dokumen lain selain gambar CAD?
Ya, GroupDocs.Viewer untuk .NET mendukung berbagai jenis dokumen, dan Anda dapat menyesuaikan ukuran gambar keluaran untuk sebagian besar format dokumen.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi kerangka kerja .NET?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan beberapa versi kerangka kerja .NET, memastikan fleksibilitas dan kegunaan di berbagai lingkungan.
### Apakah ada opsi lisensi yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat menjelajahi berbagai pilihan lisensi, termasuk lisensi sementara dan lisensi komersial, sesuai dengan kebutuhan Anda.
### Bisakah saya menyesuaikan format keluaran dokumen yang dirender?
Tentu saja, GroupDocs.Viewer untuk .NET menawarkan berbagai opsi penyesuaian, yang memungkinkan Anda menyesuaikan format keluaran sesuai dengan tutorial Anda.
### Di mana saya dapat menemukan dukungan atau bantuan tambahan dengan GroupDocs.Viewer untuk .NET?
Anda dapat mengunjungi forum GroupDocs.Viewer [Di Sini](https://forum.groupdocs.com/c/viewer/9) untuk mendapatkan dukungan, mengajukan pertanyaan, dan terlibat dengan komunitas.