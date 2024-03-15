---
title: Render File Teks (.txt)
linktitle: Render File Teks (.txt)
second_title: GroupDocs.Viewer .NET API
description: Jelajahi konversi file teks yang lancar ke dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan kemampuan manajemen dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/net/rendering-text-files/render-txt/
---
## Perkenalan
Dalam bidang manajemen dan manipulasi dokumen, GroupDocs.Viewer untuk .NET muncul sebagai alat yang ampuh, menawarkan banyak fungsi untuk merender berbagai format dokumen secara efisien. Artikel ini mempelajari seluk-beluk penggunaan GroupDocs.Viewer untuk .NET untuk merender file teks (.txt) ke dalam berbagai format. Baik Anda ingin mengonversi file teks menjadi HTML, JPG, PNG, atau PDF, GroupDocs.Viewer membekali Anda dengan alat yang diperlukan untuk menyelesaikan tugas ini dengan lancar.
## Prasyarat
Sebelum mempelajari proses konversi, pastikan Anda memiliki prasyarat berikut:
### 1. Instalasi GroupDocs.Viewer untuk .NET
 Pastikan Anda telah menginstal GroupDocs.Viewer untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduh file yang diperlukan dari[situs web](https://releases.groupdocs.com/viewer/net/).
### 2. Keakraban Dasar dengan .NET Framework
Biasakan diri Anda dengan dasar-dasar kerangka .NET, termasuk cara menyiapkan proyek dan memanfaatkan perpustakaan dalam basis kode Anda.
### 3. Contoh File Teks
Siapkan contoh file teks (.txt) yang ingin Anda konversi. File-file ini akan berfungsi sebagai masukan untuk proses konversi.

## Impor Namespace
Sebelum mendalami proses konversi, pastikan untuk mengimpor namespace yang diperlukan ke dalam proyek Anda. Ini memungkinkan Anda mengakses fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET dengan lancar.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Mari kita bagi setiap contoh menjadi beberapa langkah untuk memandu Anda melalui proses konversi secara efektif:

## Langkah 1: Tentukan Jalur Keluaran HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Tentukan jalur lengkap untuk file keluaran HTML.
## Langkah 2: Render File Teks ke HTML Multi-Halaman
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Buat contoh a`Viewer` objek dengan path ke file teks. Konfigurasikan`HtmlViewOptions` untuk sumber daya yang disematkan dan merender file teks menjadi HTML multi-halaman.
## Langkah 3: Tentukan Jalur Output HTML Satu Halaman
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Tentukan jalur lengkap untuk file keluaran HTML satu halaman.
## Langkah 4: Render File Teks ke HTML Satu Halaman
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Buat contoh a`Viewer` objek dengan path ke file teks. Konfigurasikan`HtmlViewOptions` untuk sumber daya tertanam dan set`RenderToSinglePage` menjadi benar. Render file teks menjadi HTML satu halaman.
## Langkah 5: Tentukan Jalur Keluaran JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Tentukan jalur lengkap untuk file keluaran JPG.
## Langkah 6: Render File Teks ke JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Buat contoh a`Viewer` objek dengan path ke file teks. Konfigurasikan`JpgViewOptions` untuk jalur keluaran dan merender file teks ke dalam format JPG.
## Langkah 7: Tentukan Jalur Keluaran PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Tentukan jalur lengkap untuk file keluaran PNG.
## Langkah 8: Render File Teks ke PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Buat contoh a`Viewer` objek dengan path ke file teks. Konfigurasikan`PngViewOptions` untuk jalur keluaran dan merender file teks ke dalam format PNG.
## Langkah 9: Tentukan Jalur Keluaran PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Tentukan jalur lengkap untuk file keluaran PDF.
## Langkah 10: Render File Teks ke PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Buat contoh a`Viewer` objek dengan path ke file teks. Konfigurasikan`PdfViewOptions` untuk jalur keluaran dan merender file teks ke dalam format PDF.

## Kesimpulan
Kesimpulannya, GroupDocs.Viewer untuk .NET memberdayakan pengembang untuk dengan mudah merender file teks ke dalam berbagai format, termasuk HTML, JPG, PNG, dan PDF. Dengan mengikuti panduan langkah demi langkah yang diuraikan dalam artikel ini, Anda dapat mengintegrasikan GroupDocs.Viewer dengan lancar ke dalam aplikasi .NET Anda, sehingga meningkatkan kemampuan manajemen dokumen.
## FAQ
### T: Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua versi kerangka .NET?
Ya, GroupDocs.Viewer untuk .NET dirancang agar kompatibel dengan berbagai versi kerangka .NET, memastikan keserbagunaan dan fleksibilitas dalam pengembangan.
### T: Dapatkah saya menyesuaikan tampilan keluaran dokumen yang dirender?
Sangat! GroupDocs.Viewer menawarkan opsi penyesuaian yang luas, memungkinkan pengembang menyesuaikan tampilan dokumen yang dirender sesuai dengan preferensi dan kebutuhan mereka.
### T: Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat menjelajahi fungsi GroupDocs.Viewer untuk .NET dengan mengakses uji coba gratis yang tersedia di[situs web]( https://releases.groupdocs.com/).
### T: Bagaimana cara mendapatkan dukungan atau mencari bantuan dengan GroupDocs.Viewer untuk .NET?
 Untuk pertanyaan, dukungan, atau bantuan apa pun mengenai GroupDocs.Viewer untuk .NET, Anda dapat mengunjungi forum dukungan khusus yang dapat diakses[Di Sini](https://forum.groupdocs.com/c/viewer/9).
### T: Bisakah saya membeli lisensi sementara GroupDocs.Viewer untuk .NET?
Ya, lisensi sementara tersedia untuk dibeli, memberikan fleksibilitas dan kenyamanan kepada pengguna dalam menggunakan GroupDocs.Viewer untuk .NET untuk jangka waktu tertentu.