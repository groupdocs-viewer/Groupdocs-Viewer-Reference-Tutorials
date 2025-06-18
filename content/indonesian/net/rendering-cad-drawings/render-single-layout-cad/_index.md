---
"description": "Pelajari cara merender tata letak tunggal dalam gambar CAD menggunakan GroupDocs.Viewer untuk .NET. Langkah mudah untuk integrasi yang lancar dalam aplikasi .NET Anda."
"linktitle": "Render Tata Letak Tunggal dalam Gambar CAD"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Tata Letak Tunggal dalam Gambar CAD"
"url": "/id/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# Render Tata Letak Tunggal dalam Gambar CAD

## Perkenalan
Dalam bidang pengembangan .NET, penanganan dan tampilan gambar CAD merupakan persyaratan umum. GroupDocs.Viewer untuk .NET menyederhanakan tugas ini dengan menyediakan solusi komprehensif untuk merender gambar CAD dalam aplikasi .NET. Dalam tutorial ini, kita akan mempelajari cara merender satu tata letak dalam gambar CAD menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar tentang bahasa pemrograman C# dan kerangka kerja .NET.
- Visual Studio terinstal di sistem Anda.
- GroupDocs.Viewer untuk pustaka .NET diunduh dan tutorialnya ada di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
- Keakraban dengan format file CAD dan strukturnya.

## Mengimpor Ruang Nama
Pertama, impor namespace yang diperlukan ke dalam kode C# Anda untuk mengakses fungsionalitas GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Tentukan direktori tempat Anda ingin menyimpan hasil render.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format untuk jalur berkas setiap halaman yang dirender.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Buat Instansiasi Objek Viewer
Buat contoh kelas Viewer yang disediakan oleh GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi untuk merender keluaran HTML dengan sumber daya tertanam.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 5: Tentukan Nama Tata Letak CAD
Tentukan nama tata letak CAD yang ingin Anda render.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Langkah 6: Render Gambar CAD
Panggil metode View dari objek Viewer dengan opsi yang ditentukan.
```csharp
viewer.View(options);
```
## Langkah 7: Menampilkan Pesan Sukses
Memberi tahu pengguna tentang keberhasilan rendering dokumen sumber.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Membuat gambar CAD, terutama saat berhadapan dengan tata letak, bisa menjadi tugas yang berat. Namun, dengan GroupDocs.Viewer untuk .NET, prosesnya menjadi lancar dan efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah membuat satu tata letak dalam gambar CAD dalam aplikasi .NET Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya membuat beberapa tata letak secara bersamaan menggunakan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering beberapa tata letak dari gambar CAD.
### Apakah GroupDocs.Viewer kompatibel dengan berbagai format file CAD?
Tentu saja, GroupDocs.Viewer mendukung berbagai format file CAD, termasuk DWG, DXF, DGN, dan banyak lagi.
### Dapatkah saya menyesuaikan opsi rendering untuk gambar CAD?
Ya, GroupDocs.Viewer menyediakan opsi luas untuk menyesuaikan pengaturan rendering menurut kebutuhan Anda.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat menjelajahi fitur GroupDocs.Viewer dengan uji coba gratis yang tersedia [Di Sini](https://releases.groupdocs.com/).
### Di mana saya bisa mendapatkan dukungan untuk GroupDocs.Viewer untuk .NET?
Untuk pertanyaan atau bantuan apa pun, Anda dapat mengunjungi forum GroupDocs.Viewer [Di Sini](https://forum.groupdocs.com/c/viewer/9).