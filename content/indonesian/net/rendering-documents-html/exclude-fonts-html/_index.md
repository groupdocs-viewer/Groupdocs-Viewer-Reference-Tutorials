---
title: Kecualikan Font dari HTML yang Dirender
linktitle: Kecualikan Font dari HTML yang Dirender
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengecualikan font dari HTML yang dirender menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah ini untuk tampilan dokumen yang lancar.
weight: 10
url: /id/net/rendering-documents-html/exclude-fonts-html/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah pustaka rendering dokumen canggih yang memungkinkan pengembang menampilkan lebih dari 50 format dokumen dalam aplikasi .NET mereka tanpa memerlukan ketergantungan eksternal. Dalam tutorial ini, kita akan fokus pada fitur spesifik GroupDocs.Viewer: mengecualikan font dari keluaran HTML yang dirender. 
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Pemahaman dasar tentang pengembangan C# dan .NET.
2.  GroupDocs.Viewer untuk .NET diinstal. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio atau IDE lainnya untuk pengembangan C#.

## Impor Namespace
Dalam kode C# Anda, pastikan untuk menyertakan namespace yang diperlukan:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Siapkan direktori tempat Anda ingin menyimpan file HTML yang dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format jalur file dari masing-masing halaman dokumen yang dirender.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Inisialisasi Objek Penampil
Buat instance objek Viewer dengan dokumen yang ingin Anda render.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Kode Anda ada di sini
}
```
## Langkah 4: Atur Opsi Tampilan HTML
Tentukan opsi untuk rendering HTML, termasuk format sumber daya yang disematkan dan font yang akan dikecualikan.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Langkah 5: Render Dokumen
Berikan opsi tampilan HTML ke objek Viewer untuk merender dokumen.
```csharp
viewer.View(options);
```
## Langkah 6: Keluaran Lokasi Dokumen yang Dirender
Memberi tahu pengguna tentang lokasi penyimpanan file HTML yang dirender.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menggunakan GroupDocs.Viewer untuk .NET untuk mengecualikan font dari keluaran HTML yang dirender. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat menyesuaikan proses rendering untuk memenuhi kebutuhan spesifik Anda, memastikan tampilan dokumen yang optimal dalam aplikasi Anda.
## FAQ
### Bisakah saya mengecualikan beberapa font dari HTML yang dirender?
 Ya, Anda dapat menambahkan beberapa nama font ke`FontsToExclude` daftar dalam opsi tampilan HTML.
### Apakah GroupDocs.Viewer kompatibel dengan semua kerangka .NET?
Ya, GroupDocs.Viewer mendukung .NET Framework 4.6.1 dan lebih tinggi.
### Bisakah saya merender dokumen dari lokasi penyimpanan jarak jauh?
Ya, GroupDocs.Viewer mendukung rendering dokumen dari penyimpanan lokal serta lokasi dan aliran penyimpanan jarak jauh.
### Apakah GroupDocs.Viewer mendukung desain responsif untuk keluaran HTML?
Ya, Anda dapat mengaktifkan rendering responsif dengan menyesuaikan opsi tampilan HTML.
### Apakah dukungan teknis tersedia untuk GroupDocs.Viewer?
 Ya, Anda dapat mencari bantuan dan berpartisipasi dalam diskusi mengenai[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).