---
title: Render Tata Letak Tunggal dalam Gambar CAD
linktitle: Render Tata Letak Tunggal dalam Gambar CAD
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender tata letak tunggal dalam gambar CAD menggunakan GroupDocs.Viewer untuk .NET. Langkah mudah untuk integrasi yang lancar dalam aplikasi .NET Anda.
weight: 14
url: /id/net/rendering-cad-drawings/render-single-layout-cad/
---

# Render Tata Letak Tunggal dalam Gambar CAD

## Perkenalan
Dalam bidang pengembangan .NET, menangani dan melihat gambar CAD merupakan persyaratan umum. GroupDocs.Viewer untuk .NET menyederhanakan tugas ini dengan menyediakan solusi komprehensif untuk merender gambar CAD dalam aplikasi .NET. Dalam tutorial ini, kita akan mempelajari rendering tata letak tunggal dalam gambar CAD menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
- Pemahaman dasar bahasa pemrograman C# dan framework .NET.
- Visual Studio diinstal pada sistem Anda.
-  GroupDocs.Viewer untuk perpustakaan .NET diunduh dan direferensikan dalam proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
- Keakraban dengan format file CAD dan strukturnya.

## Impor Namespace
Pertama, impor namespace yang diperlukan ke dalam kode C# Anda untuk mengakses fungsionalitas GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Tentukan direktori tempat Anda ingin menyimpan keluaran yang dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format jalur file setiap halaman yang dirender.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Buat Instansiasi Objek Penampil
Buat instance kelas Viewer yang disediakan oleh GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi untuk merender keluaran HTML dengan sumber daya yang disematkan.
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
## Langkah 7: Tampilkan Pesan Sukses
Beri tahu pengguna tentang keberhasilan rendering dokumen sumber.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Merender gambar CAD, terutama saat menangani tata letak, bisa menjadi tugas yang menakutkan. Namun, dengan GroupDocs.Viewer untuk .NET, prosesnya menjadi lancar dan efisien. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah merender satu tata letak dalam gambar CAD dalam aplikasi .NET Anda.
## FAQ
### Bisakah saya merender beberapa tata letak secara bersamaan menggunakan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung rendering beberapa tata letak dari gambar CAD.
### Apakah GroupDocs.Viewer kompatibel dengan format file CAD yang berbeda?
Tentu saja, GroupDocs.Viewer mendukung berbagai format file CAD, termasuk DWG, DXF, DGN, dan banyak lagi.
### Bisakah saya menyesuaikan opsi rendering untuk gambar CAD?
Ya, GroupDocs.Viewer menyediakan opsi ekstensif untuk menyesuaikan pengaturan rendering sesuai kebutuhan Anda.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat menjelajahi fitur GroupDocs.Viewer dengan uji coba gratis yang tersedia[Di Sini](https://releases.groupdocs.com/).
### Di mana saya bisa mendapatkan dukungan untuk GroupDocs.Viewer untuk .NET?
 Untuk pertanyaan atau bantuan apa pun, Anda dapat mengunjungi forum GroupDocs.Viewer[Di Sini](https://forum.groupdocs.com/c/viewer/9).