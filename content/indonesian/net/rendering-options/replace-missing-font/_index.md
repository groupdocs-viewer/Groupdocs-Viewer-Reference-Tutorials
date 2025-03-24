---
title: Ganti Font yang Hilang
linktitle: Ganti Font yang Hilang
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengganti font yang hilang di dokumen .NET dengan mudah menggunakan GroupDocs.Viewer. Pastikan rendering akurat dengan langkah sederhana.
weight: 20
url: /id/net/rendering-options/replace-missing-font/
---

# Ganti Font yang Hilang

## Perkenalan
Dalam dunia pengembangan .NET, penanganan dokumen yang efisien sangatlah penting. GroupDocs.Viewer untuk .NET memberikan solusi ampuh untuk melihat berbagai format dokumen dalam aplikasi .NET Anda. Dalam tutorial ini, kita akan mempelajari cara menggunakan GroupDocs.Viewer untuk .NET untuk mengganti font yang hilang di dokumen. Baik Anda menangani PDF, presentasi PowerPoint, atau dokumen Word, GroupDocs.Viewer menyederhanakan prosesnya, memastikan bahwa dokumen Anda ditampilkan secara akurat, bahkan ketika font hilang.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda memiliki hal berikut:
1. GroupDocs.Viewer untuk .NET: Unduh dan instal perpustakaan GroupDocs.Viewer dari situs web](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET, seperti Visual Studio.
3. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# dan kerangka .NET.

## Impor Namespace
Dalam kode C# Anda, impor namespace yang diperlukan untuk mengakses fungsionalitas GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita lihat proses penggantian font yang hilang di dokumen menggunakan GroupDocs.Viewer untuk .NET.
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Atur direktori tempat halaman dokumen yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tentukan format untuk memberi nama file HTML keluaran. Dalam contoh ini, setiap halaman akan disimpan sebagai file HTML dengan konvensi penamaan "page_{page_number}.html".
## Langkah 3: Inisialisasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inisialisasi instance baru kelas Viewer, dengan meneruskan jalur ke file dokumen (dalam hal ini, presentasi PowerPoint dengan font yang hilang) sebagai parameter.
## Langkah 4: Atur Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Buat instance HtmlViewOptions dan konfigurasikan untuk menyematkan sumber daya dalam output HTML. Tentukan nama font default yang akan digunakan sebagai pengganti font yang hilang.
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
Panggil metode View pada objek Viewer, lewati opsi tampilan HTML. Ini akan merender halaman dokumen menggunakan opsi yang ditentukan.
## Langkah 6: Tampilkan Jalur Keluaran
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cetak pesan yang menunjukkan keberhasilan rendering dokumen dan berikan jalur penyimpanan file HTML keluaran.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menggunakan GroupDocs.Viewer untuk .NET untuk mengganti font yang hilang di dokumen. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen Anda dirender secara akurat, meskipun font tertentu tidak tersedia. GroupDocs.Viewer menyederhanakan proses, memungkinkan Anda fokus membangun aplikasi .NET yang tangguh tanpa mengkhawatirkan masalah kompatibilitas font.
## FAQ
### Bisakah GroupDocs.Viewer menangani jenis masalah terkait font lainnya?
Ya, GroupDocs.Viewer menyediakan berbagai fungsi terkait font, termasuk substitusi font dan deteksi font.
### Apakah GroupDocs.Viewer kompatibel dengan semua kerangka .NET?
GroupDocs.Viewer mendukung berbagai kerangka .NET, termasuk .NET Core dan .NET Standard.
### Bisakah saya menyesuaikan penggantian font default di GroupDocs.Viewer?
Tentu saja, Anda dapat menentukan font apa pun pilihan Anda sebagai pengganti default untuk font yang hilang.
### Apakah GroupDocs.Viewer mendukung pemrosesan dokumen secara batch?
Ya, GroupDocs.Viewer memungkinkan Anda memproses beberapa dokumen secara bersamaan, sehingga ideal untuk skenario pemrosesan batch.
### Di mana saya dapat menemukan bantuan atau dukungan lebih lanjut untuk GroupDocs.Viewer?
 Anda dapat mengunjungi forum GroupDocs.Viewer[Di Sini](https://forum.groupdocs.com/c/viewer/9) untuk bantuan atau pertanyaan dukungan apa pun.