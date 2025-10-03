---
"description": "Pelajari cara menampilkan folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET. Sederhanakan pengelolaan dokumen dalam aplikasi .NET."
"linktitle": "Menampilkan Folder Tertentu dan Memfilter Pesan (Outlook)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Menampilkan Folder Tertentu dan Memfilter Pesan (Outlook)"
"url": "/id/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/"
"weight": 11
type: docs
---
# Menampilkan Folder Tertentu dan Memfilter Pesan (Outlook)

## Perkenalan
Dalam dunia pengembangan .NET, mengelola dan menampilkan dokumen secara efisien sangatlah penting. GroupDocs.Viewer untuk .NET menyederhanakan tugas ini dengan menyediakan fungsionalitas yang canggih untuk merender berbagai format dokumen dengan lancar. Dalam tutorial ini, kita akan mempelajari cara merender folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda memiliki hal berikut:
1. GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal GroupDocs.Viewer untuk .NET. Anda dapat mengunduhnya dari [situs web](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Anda perlu menginstal .NET Framework di komputer Anda.
3. Pemahaman dasar tentang C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat untuk mengikuti tutorial.

## Mengimpor Ruang Nama
Pertama, mari impor namespace yang diperlukan ke kode C# kita:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur direktori tempat Anda ingin menyimpan dokumen yang dirender.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Baris ini mendefinisikan format untuk jalur file dari setiap halaman yang ditampilkan. Dalam contoh ini, ini akan menghasilkan file HTML bernama `page_1.html`Bahasa Indonesia: `page_2.html`, dan seterusnya.
## Langkah 3: Inisialisasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Di sini, kita menginisialisasi `Viewer` objek dengan jalur ke folder contoh Outlook.
## Langkah 4: Tentukan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
Kami membuat sebuah contoh dari `HtmlViewOptions` dan menentukan format untuk sumber daya yang disematkan. Selain itu, kami mengatur folder Outlook untuk ditampilkan sebagai `"Входящие"` (Masuk).
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
Baris ini memicu proses rendering dengan opsi yang ditentukan.
## Langkah 6: Menampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Setelah rendering, pesan ini ditampilkan yang menunjukkan keberhasilan penyelesaian proses rendering dan mengarahkan pengguna ke direktori output.

## Kesimpulan
Dalam tutorial ini, kami mempelajari cara merender folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat mengelola dan menampilkan dokumen secara efisien dalam aplikasi .NET Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya merender dokumen selain pesan Outlook dengan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung berbagai format dokumen termasuk PDF, DOCX, XLSX, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan format keluaran rendering?
Tentu saja, GroupDocs.Viewer untuk .NET menyediakan berbagai opsi untuk menyesuaikan keluaran rendering termasuk format HTML, gambar, dan PDF.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengunduh uji coba gratis dari [situs web](https://releases.groupdocs.com/).
### Di mana saya dapat mencari bantuan atau dukungan untuk GroupDocs.Viewer untuk .NET?
Anda dapat mengunjungi [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk bantuan atau pertanyaan apa pun.