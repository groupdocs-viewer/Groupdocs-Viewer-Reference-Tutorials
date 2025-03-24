---
title: Render Arsip ke Satu atau Beberapa Halaman HTML
linktitle: Render Arsip ke Satu atau Beberapa Halaman HTML
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender arsip ke halaman HTML menggunakan GroupDocs.Viewer untuk .NET. Integrasikan kemampuan melihat dokumen dengan mudah ke dalam aplikasi .NET Anda.
weight: 12
url: /id/net/rendering-archive-files/render-archives-html/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah pustaka rendering dokumen canggih yang memungkinkan pengembang dengan mudah mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET mereka. Apakah Anda perlu merender arsip ke satu atau beberapa halaman HTML, tutorial ini akan memandu Anda melalui proses langkah demi langkah.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal perpustakaan di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan yang berfungsi untuk pengembangan .NET.
3. Direktori Dokumen: Siapkan direktori tempat dokumen Anda disimpan.
4. Pemahaman Dasar C#: Biasakan diri Anda dengan dasar-dasar bahasa pemrograman C#.

## Impor Namespace
Dalam kode C# Anda, pastikan untuk mengimpor namespace yang diperlukan:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Ikuti langkah-langkah berikut untuk merender arsip ke satu atau beberapa halaman HTML menggunakan GroupDocs.Viewer untuk .NET:
## Langkah 1: Tetapkan Direktori Output
Tentukan direktori tempat Anda ingin menyimpan halaman HTML yang dirender:
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File
Tentukan format jalur file untuk halaman HTML. Untuk rendering satu halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Untuk rendering multi-halaman:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Langkah 3: Render ke HTML Satu Halaman
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Langkah 4: Render ke Beberapa Halaman HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Tetapkan item per halaman
    viewer.View(options);
}
```
## Langkah 5: Periksa Keluaran
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Merender arsip ke halaman HTML menggunakan GroupDocs.Viewer untuk .NET adalah proses yang mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET Anda.
## FAQ
### Bisakah saya merender format dokumen lain selain arsip?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, DOCX, XLSX, PPTX, dan banyak lagi.
### Apakah GroupDocs.Viewer cocok untuk aplikasi desktop dan web?
Tentu saja, GroupDocs.Viewer dapat digunakan di aplikasi desktop dan web dengan lancar.
### Apakah GroupDocs.Viewer menawarkan opsi penyesuaian untuk antarmuka penampil?
Ya, Anda dapat menyesuaikan antarmuka penampil sesuai kebutuhan Anda.
### Bisakah saya merender dokumen secara asinkron dengan GroupDocs.Viewer?
Ya, GroupDocs.Viewer menyediakan kemampuan rendering asinkron untuk meningkatkan kinerja.
### Apakah GroupDocs.Viewer mendukung anotasi dokumen?
Ya, GroupDocs.Viewer memungkinkan pengguna melihat dan mengelola anotasi dokumen secara efisien.