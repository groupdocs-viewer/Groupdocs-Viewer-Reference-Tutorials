---
"description": "Pelajari cara mudah untuk merender gambar CMX ke dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan pengelolaan dokumen Anda."
"linktitle": "Render Gambar CMX"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Gambar CMX"
"url": "/id/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Render Gambar CMX

## Perkenalan
Dalam bidang manajemen dan manipulasi dokumen, merender gambar dari berbagai format merupakan tugas penting. GroupDocs.Viewer for .NET menyederhanakan proses ini dengan menyediakan fungsionalitas komprehensif untuk merender gambar CMX ke dalam berbagai format seperti HTML, JPG, PNG, dan PDF. Tutorial ini akan memandu Anda melalui proses langkah demi langkah merender gambar CMX menggunakan GroupDocs.Viewer for .NET.

![Render Gambar CMX dengan GroupDocs.Viewer untuk .NET](/viewer/image-rendering/render-cmx-images.png)

## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk Pustaka .NET: Unduh dan instal pustaka GroupDocs.Viewer untuk .NET dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang berfungsi dengan kerangka .NET.
3. Berkas Gambar CMX: Dapatkan berkas gambar CMX yang ingin Anda render.

## Mengimpor Ruang Nama
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
- Tentukan Direktori Keluaran: Tetapkan direktori di mana Anda ingin menyimpan file HTML yang telah dirender.
- Tentukan Format Jalur File: Tentukan format untuk file HTML keluaran.
- Buat Instansi Objek Viewer: Buat instans kelas Viewer dengan berkas gambar CMX.
- Opsi Rendering HTML: Konfigurasikan opsi rendering HTML, seperti penyematan sumber daya.
- Render CMX ke HTML: Panggil metode View dari objek penampil untuk merender gambar CMX ke HTML.
## Merender ke JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Tentukan Direktori Keluaran: Tetapkan direktori untuk menyimpan file JPG yang telah dirender.
- Tentukan Format Jalur File: Tentukan format untuk file JPG keluaran.
- Buat Instansi Objek Viewer: Buat instans kelas Viewer dengan berkas gambar CMX.
- Opsi Rendering JPG: Konfigurasikan opsi rendering JPG.
- Render CMX ke JPG: Panggil metode View dari objek penampil untuk merender gambar CMX ke JPG.
## Merender ke PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Tentukan Direktori Keluaran: Tetapkan direktori untuk menyimpan file PNG yang telah dirender.
- Tentukan Format Jalur File: Tentukan format untuk file PNG keluaran.
- Buat Instansi Objek Viewer: Buat instans kelas Viewer dengan berkas gambar CMX.
- Opsi Rendering PNG: Konfigurasikan opsi rendering PNG.
- Render CMX ke PNG: Panggil metode View dari objek penampil untuk merender gambar CMX ke PNG.
## Merender ke PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Tentukan Direktori Keluaran: Tetapkan direktori untuk menyimpan berkas PDF yang telah dirender.
- Tentukan Format Jalur File: Tentukan format untuk file PDF keluaran.
- Buat Instansi Objek Viewer: Buat instans kelas Viewer dengan berkas gambar CMX.
- Opsi Rendering PDF: Konfigurasikan opsi rendering PDF.
- Render CMX ke PDF: Panggil metode View dari objek penampil untuk merender gambar CMX ke PDF.

## Kesimpulan
Sebagai kesimpulan, GroupDocs.Viewer untuk .NET menawarkan solusi yang tangguh untuk merender gambar CMX ke dalam berbagai format dengan lancar. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan kemampuan merender gambar CMX ke dalam aplikasi .NET Anda, sehingga meningkatkan efisiensi pengelolaan dokumen.
## Pertanyaan yang Sering Diajukan
### Bisakah saya merender halaman tertentu dari gambar CMX?
Ya, Anda dapat merender halaman tertentu dengan menentukan nomor halaman dalam opsi rendering.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua kerangka kerja .NET?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan beberapa kerangka kerja .NET, termasuk .NET Core dan .NET Framework.
### Apakah GroupDocs.Viewer mendukung rendering gambar CMX yang terenkripsi?
Ya, GroupDocs.Viewer mendukung rendering gambar CMX terenkripsi dengan kunci dekripsi yang sesuai.
### Dapatkah saya menyesuaikan opsi rendering untuk format output yang berbeda?
Tentu saja, GroupDocs.Viewer menyediakan opsi yang luas untuk menyesuaikan parameter rendering berdasarkan kebutuhan Anda.
### Apakah ada forum komunitas untuk dukungan GroupDocs.Viewer?
Ya, Anda dapat mencari bantuan dan terlibat dengan komunitas GroupDocs.Viewer di forum dukungan [Di Sini](https://forum.groupdocs.com/c/viewer/9).