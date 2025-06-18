---
"description": "Pelajari cara mengaktifkan tampilan berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan pengalaman melihat dokumen dengan mudah."
"linktitle": "Aktifkan Rendering Berlapis dalam PDF"
"second_title": "API Penampil GroupDocs.NET"
"title": "Aktifkan Rendering Berlapis dalam PDF"
"url": "/id/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# Aktifkan Rendering Berlapis dalam PDF

## Perkenalan
Dalam tutorial ini, kita akan mempelajari proses pengaktifan tampilan berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer for .NET. Tampilan berlapis memungkinkan tampilan dan manipulasi dokumen yang lebih baik, sehingga memberikan pengalaman menonton yang lebih interaktif kepada pengguna.

![Aktifkan Rendering Berlapis dalam PDF dengan GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
1. GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal paket atau pustaka yang diperlukan untuk menggunakan GroupDocs.Viewer untuk .NET dalam proyek Anda.
2. Visual Studio: Anda harus menginstal Visual Studio di sistem Anda untuk membuat kode dan menjalankan contoh yang disediakan.
3. Pemahaman Dasar C#: Tutorial ini mengasumsikan pemahaman terhadap sintaksis dan konsep bahasa pemrograman C#.

## Mengimpor Ruang Nama
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
Pastikan untuk menentukan jalur direktori tempat Anda ingin menyimpan hasil render.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Langkah ini menetapkan format untuk jalur berkas setiap halaman dalam hasil render. `{0}` adalah tempat penampung nomor halaman.
## Langkah 3: Aktifkan Rendering Berlapis
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Di sini, kita membuat `Viewer` objek dan menentukan dokumen PDF yang akan diproses. Kami kemudian mengonfigurasi `HtmlViewOptions` dengan format jalur berkas halaman yang ditentukan. Dengan menyetel `EnableLayeredRendering` properti untuk `true` di dalam `PdfOptions`, kami mengaktifkan rendering berlapis untuk dokumen PDF.
## Langkah 4: Menampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Terakhir, kami mencetak pesan yang menunjukkan keberhasilan pemrosesan dokumen sumber dan meminta pengguna untuk memeriksa output di direktori yang ditentukan.

## Kesimpulan
Mengaktifkan tampilan berlapis dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET meningkatkan kemampuan tampilan dokumen, memberikan pengguna pengalaman yang lebih kaya dan lebih interaktif. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fitur ini dengan lancar ke dalam aplikasi .NET Anda.
## Pertanyaan yang Sering Diajukan
### Apa itu rendering berlapis dalam dokumen PDF?
Rendering berlapis memungkinkan pemisahan dan manipulasi berbagai komponen dalam dokumen PDF, memungkinkan tampilan interaktif dan pengalaman pengguna yang lebih baik.
### Dapatkah saya menyesuaikan direktori keluaran untuk dokumen yang dirender?
Ya, Anda dapat menentukan jalur direktori mana pun untuk output sesuai kebutuhan Anda.
### Apakah GroupDocs.Viewer mendukung format file lain selain PDF?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk Word, Excel, PowerPoint, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer kompatibel dengan lingkungan .NET Framework dan .NET Core.
### Di mana saya dapat menemukan dukungan atau bantuan tambahan?
Anda dapat mengunjungi forum GroupDocs.Viewer untuk pertanyaan atau bantuan apa pun mengenai pustaka penampil.