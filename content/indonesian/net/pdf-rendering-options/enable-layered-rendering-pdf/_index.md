---
title: Aktifkan Rendering Berlapis dalam PDF
linktitle: Aktifkan Rendering Berlapis dalam PDF
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengaktifkan rendering berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan pengalaman melihat dokumen dengan mudah.
weight: 15
url: /id/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Perkenalan
Dalam tutorial ini, kita akan mempelajari proses mengaktifkan rendering berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET. Render berlapis memungkinkan tampilan dan manipulasi dokumen yang ditingkatkan, memberikan pengalaman menonton yang lebih interaktif kepada pengguna.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal paket atau pustaka yang diperlukan untuk menggunakan GroupDocs.Viewer untuk .NET di proyek Anda.
2. Visual Studio: Anda harus menginstal Visual Studio di sistem Anda untuk mengkode dan mengeksekusi contoh yang diberikan.
3. Pemahaman Dasar C#: Tutorial ini mengasumsikan keakraban dengan sintaks dan konsep bahasa pemrograman C#.

## Impor Namespace
Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek Anda:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Pastikan untuk menentukan jalur direktori tempat Anda ingin menyimpan keluaran yang dirender.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Langkah ini menetapkan format jalur file masing-masing halaman dalam output yang dirender.`{0}` adalah pengganti nomor halaman.
## Langkah 3: Aktifkan Rendering Berlapis
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Di sini, kami membuat a`Viewer` objek dan tentukan dokumen PDF yang akan diproses. Kami kemudian mengkonfigurasi`HtmlViewOptions` dengan format jalur file halaman yang ditentukan. Dengan mengatur`EnableLayeredRendering` properti ke`true` di dalam`PdfOptions`, kami mengaktifkan rendering berlapis untuk dokumen PDF.
## Langkah 4: Tampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Terakhir, kami mencetak pesan yang menunjukkan keberhasilan rendering dokumen sumber dan meminta pengguna untuk memeriksa output di direktori yang ditentukan.

## Kesimpulan
Mengaktifkan rendering berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET meningkatkan kemampuan melihat dokumen, memberikan pengalaman yang lebih kaya dan interaktif kepada pengguna. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fitur ini ke dalam aplikasi .NET Anda dengan lancar.
## FAQ
### Apa itu rendering berlapis dalam dokumen PDF?
Render berlapis memungkinkan pemisahan dan manipulasi berbagai komponen dalam dokumen PDF, memungkinkan tampilan interaktif dan pengalaman pengguna yang lebih baik.
### Bisakah saya menyesuaikan direktori keluaran untuk dokumen yang dirender?
Ya, Anda dapat menentukan jalur direktori mana pun untuk keluaran sesuai kebutuhan Anda.
### Apakah GroupDocs.Viewer mendukung format file lain selain PDF?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk Word, Excel, PowerPoint, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer kompatibel dengan lingkungan .NET Framework dan .NET Core.
### Di mana saya bisa mendapatkan dukungan atau bantuan tambahan?
Anda dapat mengunjungi forum GroupDocs.Viewer untuk pertanyaan atau bantuan apa pun terkait perpustakaan penampil.