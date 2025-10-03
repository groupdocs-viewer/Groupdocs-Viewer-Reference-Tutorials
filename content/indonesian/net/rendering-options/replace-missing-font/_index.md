---
"description": "Pelajari cara mengganti font yang hilang dalam dokumen .NET dengan mudah menggunakan GroupDocs.Viewer. Pastikan rendering akurat dengan langkah-langkah sederhana."
"linktitle": "Ganti Font yang Hilang"
"second_title": "API Penampil GroupDocs.NET"
"title": "Ganti Font yang Hilang"
"url": "/id/net/rendering-options/replace-missing-font/"
"weight": 20
type: docs
---
# Ganti Font yang Hilang

## Perkenalan
Dalam dunia pengembangan .NET, penanganan dokumen yang efisien sangatlah penting. GroupDocs.Viewer untuk .NET menyediakan solusi yang hebat untuk melihat berbagai format dokumen dalam aplikasi .NET Anda. Dalam tutorial ini, kita akan membahas cara menggunakan GroupDocs.Viewer untuk .NET untuk mengganti font yang hilang dalam dokumen. Baik Anda menangani PDF, presentasi PowerPoint, atau dokumen Word, GroupDocs.Viewer menyederhanakan prosesnya, memastikan bahwa dokumen Anda ditampilkan secara akurat, bahkan saat font hilang.
## Prasyarat
Sebelum menyelami tutorial ini, pastikan Anda memiliki hal berikut:
1. GroupDocs.Viewer untuk .NET: Unduh dan instal pustaka GroupDocs.Viewer dari situs web](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan kerangka kerja .NET.

## Mengimpor Ruang Nama
Dalam kode C# Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita telusuri proses penggantian font yang hilang dalam dokumen menggunakan GroupDocs.Viewer untuk .NET.
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tetapkan direktori tempat halaman dokumen yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tentukan format penamaan file HTML keluaran. Dalam contoh ini, setiap halaman akan disimpan sebagai file HTML dengan konvensi penamaan "page_{page_number}.html".
## Langkah 3: Inisialisasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inisialisasi instance baru kelas Viewer, berikan path ke file dokumen (dalam kasus ini, presentasi PowerPoint dengan font yang hilang) sebagai parameter.
## Langkah 4: Mengatur Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Buat contoh HtmlViewOptions dan konfigurasikan untuk menanamkan sumber daya dalam keluaran HTML. Tentukan nama font default untuk digunakan sebagai pengganti font yang hilang.
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
Panggil metode View dari objek Viewer, dengan meneruskan opsi tampilan HTML. Ini akan merender halaman dokumen menggunakan opsi yang ditentukan.
## Langkah 6: Menampilkan Jalur Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cetak pesan yang menunjukkan keberhasilan pemrosesan dokumen dan berikan jalur penyimpanan file HTML keluaran.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menggunakan GroupDocs.Viewer untuk .NET guna mengganti font yang hilang dalam dokumen. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen Anda ditampilkan secara akurat, bahkan saat font tertentu tidak tersedia. GroupDocs.Viewer menyederhanakan proses, sehingga Anda dapat fokus membangun aplikasi .NET yang tangguh tanpa perlu khawatir tentang masalah kompatibilitas font.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer menangani jenis masalah terkait font lainnya?
Ya, GroupDocs.Viewer menyediakan berbagai fungsi terkait font, termasuk substitusi font dan deteksi font.
### Apakah GroupDocs.Viewer kompatibel dengan semua kerangka kerja .NET?
GroupDocs.Viewer mendukung berbagai kerangka kerja .NET, termasuk .NET Core dan .NET Standard.
### Bisakah saya menyesuaikan penggantian font default di GroupDocs.Viewer?
Tentu saja, Anda dapat menentukan font apa pun pilihan Anda sebagai pengganti default untuk font yang hilang.
### Apakah GroupDocs.Viewer mendukung pemrosesan dokumen secara batch?
Ya, GroupDocs.Viewer memungkinkan Anda memproses beberapa dokumen secara bersamaan, menjadikannya ideal untuk skenario pemrosesan batch.
### Di mana saya dapat menemukan bantuan atau dukungan lebih lanjut untuk GroupDocs.Viewer?
Anda dapat mengunjungi forum GroupDocs.Viewer [Di Sini](https://forum.groupdocs.com/c/viewer/9) untuk pertanyaan bantuan atau dukungan apa pun.