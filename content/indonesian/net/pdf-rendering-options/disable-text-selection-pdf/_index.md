---
title: Nonaktifkan Pemilihan Teks dalam PDF
linktitle: Nonaktifkan Pemilihan Teks dalam PDF
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara menonaktifkan pemilihan teks dalam PDF menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar.
type: docs
weight: 13
url: /id/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah API rendering dokumen canggih yang memungkinkan pengembang mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET mereka dengan mudah. Salah satu fungsi utama yang disediakan oleh GroupDocs.Viewer adalah kemampuan untuk menonaktifkan pemilihan teks dalam dokumen PDF. Fitur ini sangat berguna dalam skenario ketika Anda perlu mencegah pengguna menyalin teks dari dokumen sensitif, sehingga memastikan keamanan dan integritas dokumen.
## Prasyarat
Sebelum kita mendalami panduan langkah demi langkah tentang cara menonaktifkan pemilihan teks dalam PDF menggunakan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal GroupDocs.Viewer untuk .NET dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/).
2. Direktori Dokumen: Siapkan direktori tempat dokumen Anda akan disimpan. Anda harus menentukan direktori ini dalam cuplikan kode untuk merender dokumen PDF.

## Impor Namespace
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET. Inilah cara Anda melakukannya:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita uraikan proses menonaktifkan pemilihan teks dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET menjadi beberapa langkah:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
 Pada langkah ini, ganti`"Your Document Directory"` dengan jalur direktori tempat dokumen PDF Anda berada.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Langkah ini menentukan format jalur file halaman HTML yang dirender. Setiap halaman dokumen PDF akan diubah menjadi file HTML dengan nomor halaman berurutan.
## Langkah 3: Render Dokumen PDF dengan Pemilihan Teks Dinonaktifkan
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Mengganti`"Path to Your PDF Document"` dengan jalur sebenarnya ke file PDF Anda. Cuplikan kode ini menginisialisasi a`Viewer` objek, mengonfigurasi opsi tampilan HTML untuk menyematkan sumber daya, dan menonaktifkan pemilihan teks berdasarkan pengaturan`RenderTextAsImage` properti ke`true`.
## Langkah 4: Tampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Setelah merender dokumen PDF, langkah ini menampilkan pesan sukses beserta direktori tempat penyimpanan halaman HTML yang dirender.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menonaktifkan pemilihan teks dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat dengan mudah mengintegrasikan fitur ini ke dalam aplikasi .NET Anda, memastikan keamanan dokumen dan meningkatkan pengalaman pengguna.
## FAQ
### Bisakah saya menyesuaikan direktori keluaran untuk halaman HTML yang dirender?
Ya, Anda dapat menentukan jalur direktori mana pun yang Anda inginkan untuk menyimpan halaman HTML yang dirender.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi kerangka .NET?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi kerangka .NET, termasuk .NET Core dan .NET Framework.
### Apakah menonaktifkan pemilihan teks memengaruhi fungsi lain dari dokumen PDF?
Tidak, menonaktifkan pemilihan teks hanya mencegah pengguna memilih dan menyalin teks dari dokumen. Fungsi lainnya tetap utuh.
### Bisakah saya mengaktifkan kembali pemilihan teks setelah merender dokumen?
 Ya, Anda dapat mengaktifkan pemilihan teks hanya dengan mengatur`RenderTextAsImage` properti ke`false` dalam opsi tampilan HTML.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mengakses uji coba gratis GroupDocs.Viewer untuk .NET dari[situs web](https://releases.groupdocs.com/).