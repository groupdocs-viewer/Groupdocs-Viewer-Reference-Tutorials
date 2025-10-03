---
"description": "Pelajari cara mengecualikan font dari HTML yang ditampilkan menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah ini untuk tampilan dokumen yang lancar."
"linktitle": "Kecualikan Font dari HTML yang Dirender"
"second_title": "API Penampil GroupDocs.NET"
"title": "Kecualikan Font dari HTML yang Dirender"
"url": "/id/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Kecualikan Font dari HTML yang Dirender

## Perkenalan
GroupDocs.Viewer untuk .NET adalah pustaka rendering dokumen canggih yang memungkinkan pengembang untuk menampilkan lebih dari 50 format dokumen dalam aplikasi .NET mereka tanpa memerlukan dependensi eksternal. Dalam tutorial ini, kita akan fokus pada fitur khusus GroupDocs.Viewer: mengecualikan font dari output HTML yang dirender. 
## Prasyarat
Sebelum memulai, pastikan Anda memiliki hal berikut:
1. Pemahaman dasar tentang pengembangan C# dan .NET.
2. GroupDocs.Viewer untuk .NET terinstal. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio atau IDE lain untuk pengembangan C#.

## Mengimpor Ruang Nama
Dalam kode C# Anda, pastikan untuk menyertakan namespace yang diperlukan:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Siapkan direktori tempat Anda ingin menyimpan file HTML yang telah dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format untuk jalur berkas setiap halaman dokumen yang dirender.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Inisialisasi Objek Penampil
Buat objek Viewer dengan dokumen yang ingin Anda render.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Kode Anda ada di sini
}
```
## Langkah 4: Mengatur Opsi Tampilan HTML
Tentukan opsi untuk rendering HTML, termasuk format sumber daya yang disematkan dan font yang akan dikecualikan.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Langkah 5: Render Dokumen
Lewatkan opsi tampilan HTML ke objek Viewer untuk merender dokumen.
```csharp
viewer.View(options);
```
## Langkah 6: Output Lokasi Dokumen yang Dirender
Memberi tahu pengguna tentang lokasi penyimpanan berkas HTML yang telah dirender.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menggunakan GroupDocs.Viewer for .NET untuk mengecualikan font dari hasil HTML yang dirender. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat menyesuaikan proses rendering untuk memenuhi persyaratan khusus Anda, memastikan tampilan dokumen yang optimal dalam aplikasi Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya mengecualikan beberapa font dari HTML yang ditampilkan?
Ya, Anda dapat menambahkan beberapa nama font ke `FontsToExclude` daftar dalam opsi tampilan HTML.
### Apakah GroupDocs.Viewer kompatibel dengan semua kerangka kerja .NET?
Ya, GroupDocs.Viewer mendukung .NET Framework 4.6.1 dan yang lebih tinggi.
### Bisakah saya merender dokumen dari lokasi penyimpanan jarak jauh?
Ya, GroupDocs.Viewer mendukung penyajian dokumen dari penyimpanan lokal maupun lokasi dan aliran penyimpanan jarak jauh.
### Apakah GroupDocs.Viewer mendukung desain responsif untuk keluaran HTML?
Ya, Anda dapat mengaktifkan rendering responsif dengan menyesuaikan opsi tampilan HTML sebagaimana mestinya.
### Apakah dukungan teknis tersedia untuk GroupDocs.Viewer?
Ya, Anda dapat mencari bantuan dan berpartisipasi dalam diskusi di [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9).