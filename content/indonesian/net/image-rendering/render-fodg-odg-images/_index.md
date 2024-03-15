---
title: Render Gambar FODG dan ODG
linktitle: Render Gambar FODG dan ODG
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar FODG dan ODG ke HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan penanganan dokumen Anda.
type: docs
weight: 15
url: /id/net/image-rendering/render-fodg-odg-images/
---
## Perkenalan
Dalam dunia pengembangan perangkat lunak, penanganan format dokumen yang efisien adalah yang terpenting. GroupDocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk menyederhanakan proses rendering gambar FODG dan ODG dalam aplikasi .NET. Tutorial ini akan memandu Anda melalui langkah-langkah yang diperlukan untuk merender gambar-gambar ini ke dalam berbagai format, seperti HTML, JPG, PNG, dan PDF, menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Pastikan Anda telah menginstal .NET Framework di sistem Anda.
3. Pengetahuan dasar C#: Keakraban dengan bahasa pemrograman C# akan sangat membantu.

## Impor Namespace
Sebelum memulai implementasi, impor namespace yang diperlukan:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Langkah 1: Tetapkan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
 Mengganti`"Your Document Directory"`dengan jalur direktori tempat Anda ingin menyimpan gambar yang dirender.
## Langkah 2: Render ke HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Langkah ini merender gambar FODG ke format HTML.
## Langkah 3: Render ke JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Di sini, gambar FODG dirender ke format JPG.
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
Dalam tutorial ini, kita telah mempelajari cara merender gambar FODG dan ODG ke dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengintegrasikan kemampuan rendering dokumen ke dalam aplikasi .NET Anda.
## FAQ
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua versi .NET Framework?
GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi .NET Framework, termasuk yang terbaru.
### Bisakah saya merender dokumen secara asinkron dengan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET menyediakan kemampuan rendering asinkron untuk meningkatkan kinerja.
### Apakah GroupDocs.Viewer untuk .NET mendukung rendering dokumen terenkripsi?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering dokumen terenkripsi dengan kunci dekripsi yang sesuai.
### Apakah mungkin untuk menyesuaikan keluaran rendering dengan GroupDocs.Viewer untuk .NET?
Tentu saja, GroupDocs.Viewer untuk .NET menawarkan berbagai opsi penyesuaian untuk menyesuaikan keluaran rendering sesuai dengan kebutuhan Anda.
### Bisakah saya merender dokumen dari lokasi penyimpanan jarak jauh menggunakan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering dokumen dari lokasi penyimpanan lokal dan jarak jauh.