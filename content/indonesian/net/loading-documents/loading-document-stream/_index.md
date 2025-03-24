---
title: Muat Dokumen dari Stream
linktitle: Muat Dokumen dari Stream
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara memuat dokumen dari aliran dengan lancar menggunakan GroupDocs.Viewer untuk .NET. Sempurnakan aplikasi .NET Anda dengan kemampuan melihat dokumen yang canggih.
weight: 12
url: /id/net/loading-documents/loading-document-stream/
---
## Perkenalan
Dalam bidang pengembangan .NET, mengelola dan melihat dokumen secara efisien adalah hal yang terpenting. Dengan munculnya alat dan perpustakaan canggih, tugas-tugas yang dulunya tampak menakutkan kini menjadi lebih sederhana. Di antara alat-alat ini, GroupDocs.Viewer untuk .NET menonjol sebagai solusi serbaguna untuk menangani berbagai format dokumen dengan lancar. Dalam panduan komprehensif ini, kami mempelajari seluk-beluk penggunaan GroupDocs.Viewer untuk .NET untuk memuat dokumen dari aliran. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan membekali Anda dengan pengetahuan untuk memanfaatkan kekuatan GroupDocs.Viewer secara efektif.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1. Pemahaman Dasar C# dan .NET Framework: Keakraban dengan bahasa pemrograman C# dan .NET framework akan membantu dalam memahami konsep yang dibahas.
   
2.  Instalasi GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari[situs web](https://releases.groupdocs.com/viewer/net/).
3. IDE: Memiliki Lingkungan Pengembangan Terpadu (IDE) seperti Visual Studio yang diinstal untuk pengkodean dan pengujian.
4. Aliran Dokumen: Siapkan aliran dokumen untuk dimuat. Ini bisa berupa aliran file atau sumber aliran lain yang kompatibel.

## Impor Namespace
Sebelum menerapkan kode untuk memuat dokumen dari aliran, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tetapkan jalur direktori tempat dokumen yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tentukan format jalur file setiap halaman. Di sini, "{0}" akan diganti dengan nomor halaman.
## Langkah 3: Dapatkan Aliran Dokumen
```csharp
Stream stream = GetFileStream();
```
Dapatkan aliran dokumen dari sumber yang Anda inginkan. Ini bisa berupa aliran file, aliran memori, atau aliran lain yang kompatibel.
## Langkah 4: Muat Dokumen Menggunakan Penampil
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Inisialisasi instance baru kelas Viewer dengan aliran dokumen. Kemudian, konfigurasikan opsi tampilan HTML dan render dokumen.
## Langkah 5: Tampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Beri tahu pengguna tentang keberhasilan rendering dokumen dan berikan lokasi penyimpanan keluaran.

## Kesimpulan
Kesimpulannya, GroupDocs.Viewer untuk .NET menawarkan solusi tangguh untuk memuat dan melihat dokumen dari aliran dengan mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET Anda, sehingga meningkatkan pengalaman pengguna dan produktivitas.
## FAQ
### Bisakah GroupDocs.Viewer untuk .NET menangani format dokumen yang berbeda?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, DOCX, XLSX, PPTX, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET cocok untuk aplikasi web dan desktop?
Sangat! GroupDocs.Viewer dapat diintegrasikan dengan mulus ke dalam aplikasi web dan desktop yang dikembangkan menggunakan .NET.
### Apakah GroupDocs.Viewer menawarkan opsi penyesuaian untuk rendering dokumen?
Ya, Anda dapat menyesuaikan berbagai aspek rendering dokumen, seperti watermarking, rotasi halaman, dan tingkat zoom, sesuai kebutuhan Anda.
### Bisakah saya menggunakan GroupDocs.Viewer untuk .NET dalam proyek komersial?
Ya, GroupDocs.Viewer menawarkan opsi lisensi yang sesuai untuk proyek komersial. Anda dapat membeli lisensi dari resminya[situs web](https://purchase.groupdocs.com/temporary-license/).
### Apakah dukungan teknis tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mencari bantuan dan bimbingan teknis dari forum dukungan khusus yang disediakan oleh[GroupDocs.Penampil](https://forum.groupdocs.com/c/viewer/9).