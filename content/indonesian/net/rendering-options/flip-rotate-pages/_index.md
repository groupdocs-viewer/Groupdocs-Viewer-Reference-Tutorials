---
"description": "Pelajari cara mengintegrasikan Groupdocs.Viewer for .NET ke dalam aplikasi Anda untuk pemrosesan, pembalikan, dan rotasi dokumen yang lancar."
"linktitle": "Membalik dan Memutar Halaman"
"second_title": "API Penampil GroupDocs.NET"
"title": "Membalik dan Memutar Halaman"
"url": "/id/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Membalik dan Memutar Halaman

## Perkenalan
Dalam tutorial ini, kita akan mendalami fungsi Groupdocs.Viewer untuk .NET, khususnya berfokus pada membalik dan memutar halaman. Groupdocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk menyajikan dokumen dalam berbagai format dalam aplikasi .NET. Baik Anda sedang mengembangkan sistem manajemen dokumen atau perlu mengintegrasikan kemampuan tampilan dokumen ke dalam perangkat lunak Anda, Groupdocs.Viewer untuk .NET menyediakan solusi yang efisien.
## Prasyarat
Sebelum kita memulai, pastikan Anda telah menyiapkan prasyarat berikut:
### Menginstal Groupdocs.Viewer untuk .NET
Untuk menggunakan Groupdocs.Viewer untuk .NET, Anda perlu menginstal paket melalui NuGet Package Manager. Anda dapat menemukan petunjuk instalasi terperinci di [dokumentasi](https://tutorials.groupdocs.com/viewer/net/).

## Mengimpor Ruang Nama
Pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda untuk memanfaatkan Groupdocs.Viewer for .NET secara efektif.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Mari kita uraikan proses membalik dan memutar halaman menggunakan Groupdocs.Viewer untuk .NET menjadi beberapa langkah sederhana:
## Langkah 1: Tetapkan Direktori Output dan Jalur File
Tentukan direktori tempat Anda ingin menyimpan berkas keluaran dan tentukan jalur berkas keluaran.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Langkah 2: Inisialisasi Objek Penampil
Buat contoh kelas Viewer dengan meneruskan jalur ke dokumen yang ingin Anda lihat.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Langkah 3: Konfigurasikan Opsi Tampilan
Siapkan opsi tampilan, seperti menentukan format file keluaran dan pengaturan tambahan seperti rotasi halaman.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Langkah 4: Render Dokumen
Panggil metode View dari objek Viewer dan berikan opsi tampilan.
```csharp
viewer.View(viewOptions);
```
## Langkah 5: Menampilkan Pesan Sukses
Beritahukan pengguna bahwa dokumen telah berhasil ditampilkan dan tentukan direktori keluaran untuk verifikasi.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Sebagai kesimpulan, Groupdocs.Viewer untuk .NET menawarkan kemampuan hebat untuk merender dokumen, termasuk membalik dan memutar halaman. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fitur-fitur ini dengan lancar ke dalam aplikasi .NET Anda, yang akan meningkatkan pengalaman melihat dokumen bagi pengguna Anda.
## Pertanyaan yang Sering Diajukan
### Apakah Groupdocs.Viewer untuk .NET kompatibel dengan semua format dokumen?
Ya, Groupdocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk DOCX, PDF, PPTX, dan banyak lagi.
### Dapatkah saya menyesuaikan pilihan tampilan selain membalik dan memutar halaman?
Tentu saja, Groupdocs.Viewer untuk .NET menyediakan berbagai opsi penyesuaian untuk melihat dokumen, yang memungkinkan Anda menyesuaikan pengalaman sesuai dengan kebutuhan Anda.
### Apakah ada uji coba gratis yang tersedia untuk Groupdocs.Viewer untuk .NET?
Ya, Anda dapat memanfaatkan uji coba gratis Groupdocs.Viewer untuk .NET dengan mengunjungi [situs web](https://releases.groupdocs.com/).
### Bagaimana saya bisa mendapatkan dukungan untuk Groupdocs.Viewer untuk .NET?
Anda dapat mencari bantuan dan terlibat dengan komunitas melalui [Forum Penampil Groupdocs](https://forum.groupdocs.com/c/viewer/9).
### Di mana saya bisa mendapatkan lisensi sementara untuk Groupdocs.Viewer untuk .NET?
Lisensi sementara untuk Groupdocs.Viewer untuk .NET dapat diperoleh dari [halaman pembelian](https://purchase.groupdocs.com/temporary-license/).