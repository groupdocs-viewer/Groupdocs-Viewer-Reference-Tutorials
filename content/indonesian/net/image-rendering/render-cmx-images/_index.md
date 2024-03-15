---
title: Render Gambar CMX
linktitle: Render Gambar CMX
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender gambar CMX dengan mudah ke dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan manajemen dokumen Anda.
type: docs
weight: 13
url: /id/net/image-rendering/render-cmx-images/
---
## Perkenalan
Dalam bidang manajemen dan manipulasi dokumen, rendering gambar dari berbagai format adalah tugas yang sangat penting. GroupDocs.Viewer untuk .NET menyederhanakan proses ini dengan menyediakan fungsionalitas komprehensif untuk merender gambar CMX ke dalam format berbeda seperti HTML, JPG, PNG, dan PDF. Tutorial ini akan memandu Anda melalui proses langkah demi langkah merender gambar CMX menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET Library: Unduh dan instal perpustakaan GroupDocs.Viewer untuk .NET dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang berfungsi dengan kerangka .NET.
3. File Gambar CMX: Dapatkan file gambar CMX yang ingin Anda render.

## Mengimpor Namespace
Sebelum melanjutkan, pastikan untuk mengimpor namespace yang diperlukan untuk mengakses fungsionalitas GroupDocs.Viewer di aplikasi .NET Anda:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Merender ke HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Tentukan Direktori Output: Tetapkan direktori tempat Anda ingin menyimpan file HTML yang dirender.
- Tentukan Format Jalur File: Tentukan format untuk file HTML keluaran.
- Instantiate Viewer Object: Buat instance kelas Viewer dengan file gambar CMX.
- Opsi Rendering HTML: Konfigurasikan opsi rendering HTML, seperti menyematkan sumber daya.
- Render CMX ke HTML: Panggil metode View pada objek penampil untuk merender gambar CMX ke HTML.
## Merender ke JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Tentukan Direktori Output: Mengatur direktori untuk menyimpan file JPG yang dirender.
- Tentukan Format Jalur File: Tentukan format untuk file JPG keluaran.
- Instantiate Viewer Object: Buat instance kelas Viewer dengan file gambar CMX.
- Opsi Rendering JPG: Konfigurasikan opsi rendering JPG.
- Render CMX ke JPG: Aktifkan metode View pada objek penampil untuk merender gambar CMX ke JPG.
## Merender ke PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Tentukan Direktori Output: Mengatur direktori untuk menyimpan file PNG yang dirender.
- Tentukan Format Jalur File: Tentukan format untuk file PNG keluaran.
- Instantiate Viewer Object: Buat instance kelas Viewer dengan file gambar CMX.
- Opsi Rendering PNG: Konfigurasikan opsi rendering PNG.
- Render CMX ke PNG: Aktifkan metode View pada objek penampil untuk merender gambar CMX ke PNG.
## Merender ke PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Tentukan Direktori Output: Mengatur direktori untuk menyimpan file PDF yang dirender.
- Tentukan Format Jalur File: Tentukan format untuk file PDF keluaran.
- Instantiate Viewer Object: Buat instance kelas Viewer dengan file gambar CMX.
- Opsi Rendering PDF: Konfigurasikan opsi rendering PDF.
- Render CMX ke PDF: Aktifkan metode View pada objek penampil untuk merender gambar CMX ke PDF.

## Kesimpulan
Kesimpulannya, GroupDocs.Viewer untuk .NET menawarkan solusi tangguh untuk merender gambar CMX ke dalam berbagai format dengan mulus. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan kemampuan rendering gambar CMX ke dalam aplikasi .NET Anda, sehingga meningkatkan efisiensi manajemen dokumen.
## FAQ
### Bisakah saya merender halaman tertentu dari gambar CMX?
Ya, Anda dapat merender halaman tertentu dengan menentukan nomor halaman di opsi rendering.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua kerangka .NET?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan beberapa kerangka .NET, termasuk .NET Core dan .NET Framework.
### Apakah GroupDocs.Viewer mendukung rendering gambar CMX terenkripsi?
Ya, GroupDocs.Viewer mendukung rendering gambar CMX terenkripsi dengan kunci dekripsi yang sesuai.
### Bisakah saya menyesuaikan opsi rendering untuk format output yang berbeda?
Tentu saja, GroupDocs.Viewer menyediakan opsi ekstensif untuk menyesuaikan parameter rendering berdasarkan kebutuhan Anda.
### Apakah ada forum komunitas untuk dukungan GroupDocs.Viewer?
 Ya, Anda dapat mencari bantuan dan terlibat dengan komunitas GroupDocs.Viewer di forum dukungan[Di Sini](https://forum.groupdocs.com/c/viewer/9).