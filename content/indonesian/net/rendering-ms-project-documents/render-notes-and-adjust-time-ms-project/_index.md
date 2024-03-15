---
title: Render Catatan dan Sesuaikan Satuan Waktu (Proyek MS)
linktitle: Render Catatan dan Sesuaikan Satuan Waktu (Proyek MS)
second_title: GroupDocs.Viewer .NET API
description: Master rendering dokumen MS Project dengan GroupDocs.Viewer untuk .NET. Render catatan, sesuaikan satuan waktu, dan jelajahi berbagai format keluaran dengan mudah.
type: docs
weight: 11
url: /id/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang melihat dan memanipulasi berbagai format dokumen dalam aplikasi .NET mereka. Dalam tutorial ini, kami akan fokus pada rendering catatan dan penyesuaian satuan waktu khusus untuk dokumen MS Project.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan GroupDocs.Viewer untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda dengan dukungan .NET.
3. Dokumen Proyek MS: Siapkan contoh dokumen Proyek MS untuk pengujian.
## Impor Namespace
Pertama, mari impor namespace yang diperlukan untuk mulai merender dokumen MS Project:
## Langkah 1: Impor Namespace
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Sekarang kita telah mengimpor namespace yang diperlukan, mari kita bagi setiap contoh menjadi beberapa langkah untuk pemahaman yang komprehensif.
## Merender Dokumen Proyek MS ke HTML
Untuk merender dokumen MS Project ke format HTML dengan catatan disertakan, ikuti langkah-langkah berikut:
### Langkah 2: Atur Direktori Output dan Format File
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Langkah 3: Inisialisasi Objek Penampil dan Atur Opsi
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Langkah 4: Render Dokumen ke HTML
```csharp
viewer.View(options);
```
## Merender Dokumen Proyek MS ke Format Gambar
Anda juga dapat merender dokumen MS Project ke format gambar seperti JPG dan PNG. Begini caranya:
### Langkah 5: Atur Direktori Output dan Format File untuk JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Langkah 6: Inisialisasi Objek Penampil dan Atur Opsi JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Langkah 7: Render Dokumen ke JPG
```csharp
viewer.View(options);
```
Ulangi langkah serupa untuk merender ke PNG dan format gambar lainnya.
## Merender Dokumen Proyek MS ke PDF
Untuk merender dokumen MS Project ke format PDF, lakukan sebagai berikut:
### Langkah 8: Atur Direktori Output dan Format File untuk PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Langkah 9: Inisialisasi Objek Penampil dan Atur Opsi PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Langkah 10: Render Dokumen ke PDF
```csharp
viewer.View(options);
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara merender dokumen MS Project dan menyesuaikan satuan waktu menggunakan GroupDocs.Viewer untuk .NET. Gabungkan pengetahuan ini ke dalam proyek Anda untuk meningkatkan kemampuan melihat dokumen.
## FAQ
### Bisakah saya merender dokumen MS Project ke format lain selain HTML, gambar, dan PDF?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering ke berbagai format seperti DOCX, XLSX, PPTX, dan banyak lagi.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda bisa mendapatkan uji coba gratis dari[Di Sini](https://releases.groupdocs.com/).
### Bagaimana saya bisa mendapatkan lisensi sementara untuk GroupDocs.Viewer untuk .NET?
 Mengunjungi[Link ini](https://purchase.groupdocs.com/temporary-license/) untuk mendapatkan izin sementara.
### Di mana saya dapat menemukan dokumentasi untuk GroupDocs.Viewer untuk .NET?
 Lihat dokumentasi[Di Sini](https://reference.groupdocs.com/viewer/net/).
### Di mana saya dapat mencari dukungan atau mengajukan pertanyaan terkait GroupDocs.Viewer untuk .NET?
 Anda dapat mengunjungi forum dukungan[Di Sini](https://forum.groupdocs.com/c/viewer/9).