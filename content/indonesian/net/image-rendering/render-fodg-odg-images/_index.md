---
"description": "Pelajari cara mengubah gambar FODG dan ODG menjadi HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan penanganan dokumen Anda."
"linktitle": "Render Gambar FODG dan ODG"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Gambar FODG dan ODG"
"url": "/id/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Render Gambar FODG dan ODG

## Perkenalan
Dalam dunia pengembangan perangkat lunak, penanganan format dokumen yang efisien adalah yang terpenting. GroupDocs.Viewer for .NET adalah alat canggih yang dirancang untuk menyederhanakan proses rendering gambar FODG dan ODG dalam aplikasi .NET. Tutorial ini akan memandu Anda melalui langkah-langkah yang diperlukan untuk merender gambar-gambar ini ke dalam berbagai format, seperti HTML, JPG, PNG, dan PDF, menggunakan GroupDocs.Viewer for .NET.

![Render Gambar FODG dan ODG dengan GroupDocs.Viewer untuk .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Pastikan Anda telah menginstal .NET Framework di sistem Anda.
3. Pengetahuan dasar C#: Keakraban dengan bahasa pemrograman C# akan sangat membantu.

## Mengimpor Ruang Nama
Sebelum memulai implementasi, impor namespace yang diperlukan:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Langkah 1: Atur Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur direktori tempat Anda ingin menyimpan gambar yang telah dirender.
## Langkah 2: Render ke HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Langkah ini menyajikan gambar FODG ke dalam format HTML.
## Langkah 3: Render ke JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Di sini, gambar FODG ditampilkan dalam format JPG.
## Langkah 4: Render ke PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Langkah ini mengubah gambar FODG ke format PNG.
## Langkah 5: Render ke PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Terakhir, gambar FODG dirender ke format PDF.

## Kesimpulan
Dalam tutorial ini, kami telah mempelajari cara merender gambar FODG dan ODG ke dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat mengintegrasikan kemampuan merender dokumen ke dalam aplikasi .NET Anda dengan lancar.
## Pertanyaan yang Sering Diajukan
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua versi .NET Framework?
GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi .NET Framework, termasuk yang terbaru.
### Bisakah saya menyajikan dokumen secara asinkron dengan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET menyediakan kemampuan rendering asinkron untuk meningkatkan kinerja.
### Apakah GroupDocs.Viewer untuk .NET mendukung rendering dokumen terenkripsi?
Ya, GroupDocs.Viewer untuk .NET mendukung penyajian dokumen terenkripsi dengan kunci dekripsi yang sesuai.
### Apakah mungkin untuk menyesuaikan keluaran rendering dengan GroupDocs.Viewer untuk .NET?
Tentu saja, GroupDocs.Viewer untuk .NET menawarkan berbagai opsi penyesuaian untuk menyesuaikan hasil rendering menurut kebutuhan Anda.
### Bisakah saya menyajikan dokumen dari lokasi penyimpanan jarak jauh menggunakan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung penyajian dokumen dari lokasi penyimpanan lokal dan jarak jauh.