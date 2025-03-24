---
title: Render Gambar CDR
linktitle: Render Gambar CDR
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar CDR ke HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET. Konversi file CorelDRAW dengan mudah menggunakan tutorial ini.
weight: 12
url: /id/net/image-rendering/render-cdr-images/
---
## Perkenalan
Dalam tutorial ini, kami akan memandu Anda melalui proses rendering gambar CDR (CorelDRAW) menggunakan GroupDocs.Viewer untuk .NET. CDR adalah format file yang terutama dikaitkan dengan CorelDRAW, editor grafis vektor. Dengan GroupDocs.Viewer, Anda dapat dengan mudah mengonversi file CDR ke berbagai format seperti HTML, JPG, PNG, dan PDF.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal GroupDocs.Viewer untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Direktori Dokumen: Siapkan direktori tempat Anda ingin menyimpan gambar yang dirender.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# diperlukan untuk memahami contoh kode.
## Impor Namespace
Sebelum mendalami contoh kode, impor namespace yang diperlukan dalam file C# Anda:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Sekarang, mari kita bagi setiap contoh menjadi beberapa langkah:
## Merender ke HTML
1. Tentukan direktori keluaran tempat Anda ingin menyimpan file HTML yang dirender:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Tentukan format jalur file untuk file HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Gunakan kelas Viewer untuk merender file CDR ke HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Merender ke JPG
1. Tentukan format jalur file untuk file JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Gunakan kelas Viewer untuk merender file CDR ke JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Merender ke PNG
1. Tentukan format jalur file untuk file PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Gunakan kelas Viewer untuk merender file CDR ke PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Merender ke PDF
1. Tentukan format jalur file untuk PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Gunakan kelas Viewer untuk merender file CDR ke PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Secara opsional, Anda dapat menentukan opsi rendering atau merender halaman tertentu dengan meneruskan parameter tambahan ke`viewer.View()` metode.
## Kesimpulan
Merender gambar CDR ke berbagai format seperti HTML, JPG, PNG, dan PDF menggunakan GroupDocs.Viewer untuk .NET adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efisien mengonversi file CDR ke format berbeda berdasarkan kebutuhan Anda.
## FAQ
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua versi file CDR?
GroupDocs.Viewer untuk .NET mendukung rendering file CDR yang dibuat oleh berbagai versi CorelDRAW.
### Bisakah saya menyesuaikan keluaran file yang dirender?
Ya, GroupDocs.Viewer untuk .NET menyediakan berbagai opsi untuk menyesuaikan keluaran, seperti menyesuaikan kualitas gambar, mengatur tanda air, dll.
### Apakah GroupDocs.Viewer untuk .NET memerlukan ketergantungan eksternal?
Tidak, GroupDocs.Viewer untuk .NET adalah perpustakaan mandiri dan tidak memerlukan ketergantungan eksternal apa pun untuk merender dokumen.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mengunduh GroupDocs.Viewer versi uji coba gratis untuk .NET dari[Di Sini](https://releases.groupdocs.com/).
### Di mana saya bisa mendapatkan dukungan untuk GroupDocs.Viewer untuk .NET?
 Anda bisa mendapatkan dukungan dari forum komunitas GroupDocs.Viewer[Di Sini](https://forum.groupdocs.com/c/viewer/9).