---
"description": "Pelajari cara menonaktifkan pemilihan teks dalam PDF menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami untuk integrasi yang lancar."
"linktitle": "Nonaktifkan Pemilihan Teks dalam PDF"
"second_title": "API Penampil GroupDocs.NET"
"title": "Nonaktifkan Pemilihan Teks dalam PDF"
"url": "/id/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# Nonaktifkan Pemilihan Teks dalam PDF

## Perkenalan
GroupDocs.Viewer untuk .NET adalah API rendering dokumen yang canggih yang memungkinkan pengembang untuk mengintegrasikan kemampuan tampilan dokumen ke dalam aplikasi .NET mereka dengan mudah. Salah satu fungsi utama yang disediakan oleh GroupDocs.Viewer adalah kemampuan untuk menonaktifkan pemilihan teks dalam dokumen PDF. Fitur ini sangat berguna dalam skenario di mana Anda perlu mencegah pengguna menyalin teks dari dokumen sensitif, memastikan keamanan dan integritas dokumen.

![Nonaktifkan Pemilihan Teks dalam PDF dengan GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Prasyarat
Sebelum kita menyelami panduan langkah demi langkah tentang cara menonaktifkan pemilihan teks dalam PDF menggunakan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
1. Pemasangan GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan memasang GroupDocs.Viewer untuk .NET dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/).
2. Direktori Dokumen: Siapkan direktori tempat dokumen Anda akan disimpan. Anda perlu menentukan direktori ini dalam cuplikan kode untuk merender dokumen PDF.

## Mengimpor Ruang Nama
Pertama, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsi yang disediakan oleh GroupDocs.Viewer untuk .NET. Berikut cara melakukannya:

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
Pada langkah ini, ganti `"Your Document Directory"` dengan jalur direktori tempat dokumen PDF Anda berada.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Langkah ini menentukan format untuk jalur berkas halaman HTML yang dirender. Setiap halaman dokumen PDF akan dikonversi menjadi berkas HTML dengan nomor halaman berurutan.
## Langkah 3: Render Dokumen PDF dengan Pemilihan Teks Dinonaktifkan
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Mengganti `"Path to Your PDF Document"` dengan jalur sebenarnya ke file PDF Anda. Potongan kode ini menginisialisasi `Viewer` objek, mengonfigurasi opsi tampilan HTML untuk menanamkan sumber daya, dan menonaktifkan pemilihan teks dengan menyetel `RenderTextAsImage` properti untuk `true`.
## Langkah 4: Menampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Setelah merender dokumen PDF, langkah ini menampilkan pesan berhasil beserta direktori tempat halaman HTML yang dirender disimpan.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menonaktifkan pemilihan teks dalam dokumen PDF menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, Anda dapat mengintegrasikan fitur ini dengan lancar ke dalam aplikasi .NET Anda, memastikan keamanan dokumen dan meningkatkan pengalaman pengguna.
## Pertanyaan yang Sering Diajukan
### Dapatkah saya menyesuaikan direktori keluaran untuk halaman HTML yang ditampilkan?
Ya, Anda dapat menentukan jalur direktori mana saja di mana Anda ingin menyimpan halaman HTML yang telah dirender.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi kerangka kerja .NET?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan berbagai versi kerangka kerja .NET, termasuk .NET Core dan .NET Framework.
### Apakah menonaktifkan pemilihan teks memengaruhi fungsi lain pada dokumen PDF?
Tidak, menonaktifkan pemilihan teks hanya akan mencegah pengguna memilih dan menyalin teks dari dokumen. Fungsionalitas lainnya tetap utuh.
### Bisakah saya mengaktifkan kembali pemilihan teks setelah merender dokumen?
Ya, Anda dapat mengaktifkan pemilihan teks hanya dengan mengatur `RenderTextAsImage` properti untuk `false` dalam opsi tampilan HTML.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengakses uji coba gratis GroupDocs.Viewer untuk .NET dari [situs web](https://releases.groupdocs.com/).