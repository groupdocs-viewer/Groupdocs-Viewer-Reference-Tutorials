---
title: Tetapkan Batas Ukuran Gambar
linktitle: Tetapkan Batas Ukuran Gambar
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara menetapkan batas ukuran gambar dalam aplikasi .NET dengan mudah menggunakan GroupDocs.Viewer untuk .NET, sehingga meningkatkan pengalaman melihat dokumen.
type: docs
weight: 21
url: /id/net/rendering-options/set-image-size-limits/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk memfasilitasi tampilan dokumen tanpa hambatan dalam aplikasi .NET. Dengan fitur-fitur canggih dan antarmuka intuitif, pengembang dapat dengan mudah mengintegrasikan kemampuan melihat dokumen ke dalam proyek mereka, sehingga meningkatkan pengalaman pengguna dan produktivitas. Dalam tutorial ini, kita akan mempelajari cara menetapkan batas ukuran gambar menggunakan GroupDocs.Viewer untuk .NET, memastikan tampilan dokumen yang optimal dengan tetap menjaga kinerja dan efisiensi.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  GroupDocs.Viewer untuk .NET: Pastikan Anda memiliki perpustakaan GroupDocs.Viewer untuk .NET yang diperlukan yang diinstal di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[situs web](https://releases.groupdocs.com/viewer/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan .NET pilihan Anda, seperti Visual Studio, dengan konfigurasi yang diperlukan.
3. Direktori Dokumen: Miliki direktori khusus tempat dokumen Anda disimpan, dan pastikan jalur direktori dapat diakses dalam aplikasi Anda.

## Impor Namespace
Sebelum melanjutkan implementasi, penting untuk mengimpor namespace yang diperlukan untuk mengakses fungsionalitas GroupDocs.Viewer untuk .NET secara efektif.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Tentukan Direktori Output dan Jalur File
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 Pastikan untuk mengganti`"Your Document Directory"` dengan jalur sebenarnya ke direktori dokumen Anda.
## Langkah 2: Inisialisasi Objek Penampil dan Tentukan Jalur Dokumen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX mewakili jalur ke dokumen sampel.
    // Ganti dengan jalur ke dokumen yang Anda inginkan.
```
 Mengganti`TestFiles.SAMPLE_DOCX` dengan jalur ke dokumen Anda. Ini bisa berupa DOCX, PDF, atau format file lain yang didukung.
## Langkah 3: Konfigurasikan Opsi Tampilan JPEG
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 Sesuaikan`MaxWidth` properti untuk mengatur lebar maksimum gambar yang dirender sesuai kebutuhan Anda. Hal ini memastikan bahwa gambar tidak melebihi lebar yang ditentukan, menjaga tampilan tetap optimal.
## Langkah 4: Render Dokumen dengan Opsi Tertentu
```csharp
viewer.View(options);
```
Baris kode ini memicu proses rendering, menghasilkan gambar keluaran dengan batas ukuran yang ditentukan.
## Langkah 5: Tampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Setelah rendering berhasil, pesan yang menunjukkan penyelesaian berhasil bersama dengan jalur direktori keluaran ditampilkan.

## Kesimpulan
Kesimpulannya, menguasai seni menetapkan batas ukuran gambar menggunakan GroupDocs.Viewer untuk .NET dapat meningkatkan pengalaman melihat dokumen secara signifikan dalam aplikasi .NET Anda. Dengan mengikuti panduan langkah demi langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengoptimalkan tampilan gambar sekaligus memastikan kinerja dan efisiensi.
## FAQ
### Bisakah saya mengatur lebar dan tinggi maksimum untuk gambar yang dirender?
Ya, Anda dapat mengatur lebar dan tinggi maksimum menggunakan properti yang sesuai di opsi tampilan.
### Format dokumen apa yang didukung oleh GroupDocs.Viewer untuk .NET?
GroupDocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk DOCX, PDF, PPT, XLS, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET menawarkan kompatibilitas dengan .NET Core, memungkinkan integrasi tanpa batas ke dalam aplikasi .NET modern.
### Bisakah saya menyesuaikan format gambar keluaran selain JPEG?
Ya, GroupDocs.Viewer untuk .NET menyediakan dukungan untuk berbagai format keluaran, termasuk PNG, TIFF, dan PDF.
### Apakah ada versi uji coba yang tersedia untuk pengujian sebelum membeli?
 Ya, Anda dapat memanfaatkan versi uji coba gratis dari[situs web](https://releases.groupdocs.com/viewer/net/). untuk menjelajahi fitur dan fungsi GroupDocs.Viewer untuk .NET sebelum melakukan pembelian.