---
title: Render Folder Tertentu dan Pesan Filter (Outlook)
linktitle: Render Folder Tertentu dan Pesan Filter (Outlook)
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET. Sederhanakan manajemen dokumen dalam aplikasi .NET.
weight: 11
url: /id/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---

# Render Folder Tertentu dan Pesan Filter (Outlook)

## Perkenalan
Dalam dunia pengembangan .NET, mengelola dan menampilkan dokumen secara efisien sangatlah penting. GroupDocs.Viewer untuk .NET menyederhanakan tugas ini dengan menyediakan fungsionalitas canggih untuk merender berbagai format dokumen dengan mulus. Dalam tutorial ini, kita akan mempelajari cara merender folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum mendalami tutorial, pastikan Anda memiliki hal berikut:
1.  GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal GroupDocs.Viewer untuk .NET. Anda dapat mengunduhnya dari[situs web](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Anda harus menginstal .NET framework di mesin Anda.
3. Pemahaman dasar C#: Keakraban dengan bahasa pemrograman C# akan bermanfaat untuk mengikuti tutorialnya.

## Impor Namespace
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
 Mengganti`"Your Document Directory"` dengan jalur direktori tempat Anda ingin menyimpan dokumen yang dirender.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Baris ini mendefinisikan format jalur file dari setiap halaman yang dirender. Dalam contoh ini, ini akan menghasilkan file HTML bernama`page_1.html`, `page_2.html`, dan seterusnya.
## Langkah 3: Inisialisasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 Di sini, kami menginisialisasi a`Viewer` objek dengan jalur ke contoh folder Outlook.
## Langkah 4: Tentukan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 Kami membuat sebuah instance dari`HtmlViewOptions` dan tentukan format untuk sumber daya yang disematkan. Selain itu, kami mengatur folder Outlook untuk dirender sebagai`"Входящие"` (Masuk).
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
Baris ini memicu proses rendering dengan opsi yang ditentukan.
## Langkah 6: Tampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Setelah rendering, pesan ini ditampilkan yang menunjukkan keberhasilan penyelesaian proses rendering dan mengarahkan pengguna ke direktori keluaran.

## Kesimpulan
Dalam tutorial ini, kita menjelajahi cara merender folder tertentu dan memfilter pesan di Outlook menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat mengelola dan menampilkan dokumen dalam aplikasi .NET Anda secara efisien.
## FAQ
### Bisakah saya merender dokumen selain pesan Outlook dengan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer untuk .NET mendukung berbagai format dokumen termasuk PDF, DOCX, XLSX, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan format keluaran rendering?
Tentu saja, GroupDocs.Viewer untuk .NET menyediakan berbagai opsi untuk menyesuaikan keluaran rendering termasuk format HTML, gambar, dan PDF.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis dari[situs web](https://releases.groupdocs.com/).
### Di mana saya dapat mencari bantuan atau dukungan untuk GroupDocs.Viewer untuk .NET?
 Anda dapat mengunjungi[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) untuk bantuan atau pertanyaan apa pun.