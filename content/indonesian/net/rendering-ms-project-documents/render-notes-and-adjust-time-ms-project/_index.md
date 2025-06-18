---
"description": "Kuasai rendering dokumen MS Project dengan GroupDocs.Viewer untuk .NET. Render catatan, sesuaikan satuan waktu, dan jelajahi berbagai format output dengan mudah."
"linktitle": "Render Catatan dan Sesuaikan Satuan Waktu (MS Project)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Catatan dan Sesuaikan Satuan Waktu (MS Project)"
"url": "/id/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Render Catatan dan Sesuaikan Satuan Waktu (MS Project)

## Perkenalan
GroupDocs.Viewer untuk .NET adalah API rendering dokumen yang canggih yang memungkinkan pengembang untuk melihat dan memanipulasi berbagai format dokumen dalam aplikasi .NET mereka. Dalam tutorial ini, kita akan fokus pada rendering catatan dan penyesuaian unit waktu khusus untuk dokumen MS Project.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal pustaka GroupDocs.Viewer untuk .NET. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan pilihan Anda dengan dukungan .NET.
3. Dokumen MS Project: Siapkan contoh dokumen MS Project untuk pengujian.
## Mengimpor Ruang Nama
Pertama, mari impor namespace yang diperlukan untuk mulai merender dokumen MS Project:
## Langkah 1: Impor Namespace
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Sekarang setelah kita mengimpor namespace yang diperlukan, mari kita uraikan setiap contoh ke dalam beberapa langkah agar dapat dipahami secara komprehensif.
## Merender Dokumen MS Project ke HTML
Untuk merender dokumen MS Project ke format HTML dengan catatan yang disertakan, ikuti langkah-langkah berikut:
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
## Merender Dokumen MS Project ke Format Gambar
Anda juga dapat mengubah dokumen MS Project ke format gambar seperti JPG dan PNG. Berikut caranya:
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
## Merender Dokumen MS Project ke PDF
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
## Pertanyaan yang Sering Diajukan
### Bisakah saya menyajikan dokumen MS Project ke format lain selain HTML, gambar, dan PDF?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering ke berbagai format seperti DOCX, XLSX, PPTX, dan lainnya.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda bisa mendapatkan uji coba gratis dari [Di Sini](https://releases.groupdocs.com/).
### Bagaimana cara mendapatkan lisensi sementara untuk GroupDocs.Viewer untuk .NET?
Mengunjungi [tautan ini](https://purchase.groupdocs.com/temporary-license/) untuk mendapatkan lisensi sementara.
### Di mana saya dapat menemukan dokumentasi untuk GroupDocs.Viewer untuk .NET?
Lihat dokumentasi [Di Sini](https://tutorials.groupdocs.com/viewer/net/).
### Di mana saya dapat mencari dukungan atau mengajukan pertanyaan terkait GroupDocs.Viewer untuk .NET?
Anda dapat mengunjungi forum dukungan [Di Sini](https://forum.groupdocs.com/c/viewer/9).