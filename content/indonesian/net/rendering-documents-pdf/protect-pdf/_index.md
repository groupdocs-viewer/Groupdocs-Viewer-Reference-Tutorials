---
title: Lindungi PDF yang Dirender dengan Kata Sandi
linktitle: Lindungi PDF yang Dirender dengan Kata Sandi
second_title: GroupDocs.Viewer .NET API
description: Lindungi PDF Anda yang dirender dengan kata sandi dengan mudah menggunakan Groupdocs.Viewer untuk .NET. Jaga dokumen Anda tetap aman dan rahasia.
type: docs
weight: 12
url: /id/net/rendering-documents-pdf/protect-pdf/
---
## Perkenalan
Dalam tutorial ini, Anda akan mempelajari cara menggunakan Groupdocs.Viewer untuk .NET untuk melindungi PDF yang dirender dengan kata sandi. Dengan menambahkan langkah-langkah keamanan, Anda dapat mengontrol akses ke dokumen PDF Anda, memastikan kerahasiaan dan integritas.
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1.  Groupdocs.Viewer untuk .NET Library: Unduh dan instal perpustakaan dari[situs web](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang berfungsi untuk pengembangan .NET.

## Impor Namespace
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Tentukan Direktori Output dan Jalur File
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Langkah 2: Inisialisasi Objek Penampil dan Tetapkan Opsi Keamanan
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Langkah 3: Atur Opsi Tampilan PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Langkah 4: Render Dokumen dengan Opsi Keamanan
```csharp
    viewer.View(options);
}
```
## Langkah 5: Periksa Dokumen yang Dirender
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Dengan mengikuti langkah-langkah ini, Anda dapat melindungi PDF yang dirender dengan kata sandi menggunakan Groupdocs.Viewer untuk .NET. Hal ini memastikan dokumen Anda tetap aman dan hanya dapat diakses oleh pengguna yang berwenang.

## Kesimpulan
Mengamankan dokumen PDF sangat penting untuk menjaga kerahasiaan dan integritas. Dengan Groupdocs.Viewer untuk .NET, Anda dapat dengan mudah melindungi PDF yang dirender dengan kata sandi, mengontrol akses ke informasi sensitif.

## FAQ
### Bisakah saya melindungi PDF dengan tingkat izin berbeda?
Ya, Anda dapat menentukan izin berbeda untuk melihat, mencetak, menyalin, dan lainnya sambil melindungi PDF dengan kata sandi.
### Apakah Groupdocs.Viewer kompatibel dengan berbagai format file?
Sangat! Groupdocs.Viewer mendukung rendering berbagai format file, termasuk DOCX, XLSX, PPTX, PDF, dan banyak lagi.
### Bisakah saya mengintegrasikan Groupdocs.Viewer ke dalam aplikasi .NET saya yang sudah ada?
Tentu! Groupdocs.Viewer menyediakan API untuk integrasi tanpa batas ke dalam aplikasi .NET, menawarkan kemampuan melihat dokumen yang kuat.
### Apakah Groupdocs.Viewer menawarkan dukungan untuk layanan penyimpanan cloud?
Ya, Groupdocs.Viewer mendukung integrasi dengan layanan penyimpanan cloud populer seperti Dropbox, Google Drive, dan Amazon S3, memungkinkan Anda merender dokumen yang disimpan di cloud.
### Apakah ada versi uji coba yang tersedia untuk Groupdocs.Viewer?
 Ya, Anda dapat memulai Groupdocs.Viewer dengan mengakses versi uji coba gratis dari[situs web](https://releases.groupdocs.com/).