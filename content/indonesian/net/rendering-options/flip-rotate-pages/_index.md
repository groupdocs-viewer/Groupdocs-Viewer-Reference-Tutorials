---
title: Balik dan Putar Halaman
linktitle: Balik dan Putar Halaman
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengintegrasikan Groupdocs.Viewer untuk .NET ke dalam aplikasi Anda untuk rendering, pembalikan, dan rotasi dokumen yang lancar.
weight: 12
url: /id/net/rendering-options/flip-rotate-pages/
---

# Balik dan Putar Halaman

## Perkenalan
Dalam tutorial ini, kita akan mempelajari fungsi Groupdocs.Viewer untuk .NET, khususnya berfokus pada membalik dan memutar halaman. Groupdocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk merender dokumen dalam berbagai format dalam aplikasi .NET. Baik Anda sedang mengembangkan sistem manajemen dokumen atau perlu mengintegrasikan kemampuan melihat dokumen ke dalam perangkat lunak Anda, Groupdocs.Viewer untuk .NET memberikan solusi yang efisien.
## Prasyarat
Sebelum kita mulai, pastikan Anda telah menyiapkan prasyarat berikut:
### Menginstal Groupdocs.Viewer untuk .NET
 Untuk menggunakan Groupdocs.Viewer untuk .NET, Anda perlu menginstal paket melalui NuGet Package Manager. Anda dapat menemukan petunjuk instalasi terperinci di[dokumentasi](https://tutorials.groupdocs.com/viewer/net/).

## Impor Namespace
Pastikan Anda memiliki namespace yang diperlukan yang diimpor ke proyek Anda untuk memanfaatkan Groupdocs.Viewer untuk .NET secara efektif.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Mari kita uraikan proses membalik dan memutar halaman menggunakan Groupdocs.Viewer untuk .NET menjadi langkah-langkah sederhana:
## Langkah 1: Tetapkan Direktori Output dan Jalur File
Tentukan direktori tempat Anda ingin menyimpan file keluaran dan tentukan jalur file keluaran.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Langkah 2: Inisialisasi Objek Penampil
Buat instance kelas Viewer dengan meneruskan jalur ke dokumen yang ingin Anda lihat.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Langkah 3: Konfigurasikan Opsi Tampilan
Atur opsi tampilan, seperti menentukan format file keluaran dan pengaturan tambahan apa pun seperti rotasi halaman.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Langkah 4: Render Dokumen
Panggil metode View pada objek Viewer dan teruskan opsi tampilan.
```csharp
viewer.View(viewOptions);
```
## Langkah 5: Tampilkan Pesan Sukses
Beri tahu pengguna bahwa dokumen telah berhasil dirender dan tentukan direktori keluaran untuk verifikasi.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Kesimpulannya, Groupdocs.Viewer untuk .NET menawarkan kemampuan canggih untuk merender dokumen, termasuk membalik dan memutar halaman. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengintegrasikan fitur-fitur ini ke dalam aplikasi .NET Anda, sehingga meningkatkan pengalaman melihat dokumen bagi pengguna Anda.
## FAQ
### Apakah Groupdocs.Viewer untuk .NET kompatibel dengan semua format dokumen?
Ya, Groupdocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk DOCX, PDF, PPTX, dan banyak lagi.
### Bisakah saya menyesuaikan opsi tampilan selain membalik dan memutar halaman?
Tentu saja, Groupdocs.Viewer untuk .NET menyediakan berbagai opsi penyesuaian untuk melihat dokumen, memungkinkan Anda menyesuaikan pengalaman sesuai dengan kebutuhan Anda.
### Apakah ada uji coba gratis yang tersedia untuk Groupdocs.Viewer untuk .NET?
 Ya, Anda dapat memanfaatkan uji coba gratis Groupdocs.Viewer untuk .NET dengan mengunjungi[situs web](https://releases.groupdocs.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Groupdocs.Viewer untuk .NET?
 Anda dapat mencari bantuan dan terlibat dengan komunitas melalui[Groupdocs. Forum penampil](https://forum.groupdocs.com/c/viewer/9).
### Di mana saya bisa mendapatkan lisensi sementara untuk Groupdocs.Viewer untuk .NET?
 Lisensi sementara untuk Groupdocs.Viewer untuk .NET dapat diperoleh dari[halaman pembelian](https://purchase.groupdocs.com/temporary-license/).