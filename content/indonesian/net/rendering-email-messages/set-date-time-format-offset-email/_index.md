---
title: Atur Format TanggalWaktu dan Offset Zona Waktu (Email)
linktitle: Atur Format TanggalWaktu dan Offset Zona Waktu (Email)
second_title: GroupDocs.Viewer .NET API
description: Integrasikan GroupDocs.Viewer untuk .NET dengan lancar ke dalam aplikasi Anda untuk kemampuan melihat dokumen yang canggih. Tingkatkan pengalaman pengguna dengan opsi yang dapat disesuaikan.
weight: 11
url: /id/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Perkenalan
GroupDocs.Viewer untuk .NET adalah alat canggih yang memungkinkan pengembang mengintegrasikan kemampuan melihat dokumen dengan lancar ke dalam aplikasi .NET mereka. Dengan GroupDocs.Viewer, Anda dapat menampilkan berbagai format dokumen termasuk PDF, dokumen Microsoft Office, gambar, dan lainnya langsung dalam aplikasi Anda, tanpa memerlukan plugin atau penampil eksternal apa pun. Dalam tutorial komprehensif ini, kami akan memandu Anda melalui proses pengaturan GroupDocs.Viewer untuk .NET, menjelajahi fitur-fiturnya, dan mendemonstrasikan cara menggunakannya secara efektif untuk meningkatkan kemampuan melihat dokumen aplikasi Anda.
## Prasyarat
Sebelum mendalami tutorial ini, pastikan Anda telah menyiapkan prasyarat berikut:
1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda. GroupDocs.Viewer untuk .NET sepenuhnya kompatibel dengan Visual Studio, memungkinkan integrasi tanpa batas ke dalam proyek .NET Anda.
2.  GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/). Ikuti petunjuk instalasi yang diberikan untuk menyiapkan perpustakaan dalam lingkungan pengembangan Anda.
3. .NET Framework: Pastikan Anda menginstal versi .NET Framework yang sesuai. GroupDocs.Viewer untuk .NET mendukung berbagai versi .NET Framework, termasuk .NET Core dan .NET Standard.

## Impor Namespace
Untuk memanfaatkan GroupDocs.Viewer untuk .NET secara efektif, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah-langkah berikut untuk mengimpor namespace yang diperlukan:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk memahami setiap komponen dan fungsinya.
## Langkah 1: Tetapkan Direktori Output dan Jalur File
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Pada langkah ini, kita menentukan direktori keluaran tempat dokumen yang dirender akan disimpan dan menentukan jalur file untuk file HTML keluaran.
## Langkah 2: Buat Instansiasi Objek Penampil
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Di sini, kami membuat instance baru dari`Viewer` kelas, meneruskan jalur dokumen yang akan dilihat (dalam hal ini, contoh file EML) sebagai parameter.
## Langkah 3: Tentukan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Pada langkah ini, kami mengonfigurasi opsi tampilan HTML untuk rendering dokumen, menentukan jalur file output untuk dokumen HTML yang dirender.
## Langkah 4: Atur Format TanggalWaktu dan Offset Zona Waktu
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Di sini, kami menyesuaikan format tanggal dan waktu untuk pesan email dan mengatur offset zona waktu sesuai zona waktu yang diinginkan.
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
 Akhirnya, kami menelepon`View` metode`Viewer` objek, meneruskan opsi tampilan HTML yang dikonfigurasi untuk merender dokumen ke dalam format HTML.
## Langkah 6: Tampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Langkah ini hanya menampilkan pesan yang menunjukkan keberhasilan rendering dokumen dan menyediakan jalur ke direktori keluaran tempat dokumen HTML yang dirender berada.

## Kesimpulan
GroupDocs.Viewer untuk .NET menawarkan solusi tangguh untuk mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah mengatur GroupDocs.Viewer, mengimpor namespace yang diperlukan, dan memanfaatkan fitur-fiturnya untuk merender dokumen dengan opsi yang dapat disesuaikan. Baik Anda bekerja dengan PDF, dokumen Microsoft Office, atau format lainnya, GroupDocs.Viewer menyederhanakan proses tampilan dokumen, meningkatkan pengalaman pengguna aplikasi Anda.
## FAQ
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET mendukung .NET Core, memungkinkan kompatibilitas lintas platform untuk aplikasi Anda.
### Bisakah saya menyesuaikan tampilan dokumen yang dirender?
Sangat! GroupDocs.Viewer menyediakan berbagai opsi penyesuaian termasuk tingkat zoom, rotasi halaman, dan lainnya untuk menyesuaikan pengalaman menonton sesuai preferensi Anda.
### Apakah ada versi uji coba yang tersedia untuk tujuan pengujian?
 Ya, Anda dapat mengunduh GroupDocs.Viewer versi uji coba gratis untuk .NET dari[tautan situs web](https://releases.groupdocs.com/viewer/net/) untuk mengevaluasi fitur-fiturnya sebelum melakukan pembelian.
### Apakah GroupDocs.Viewer mendukung rendering dokumen yang dilindungi kata sandi?
Ya, GroupDocs.Viewer memiliki dukungan bawaan untuk merender dokumen yang dilindungi kata sandi, memastikan tampilan dokumen aman dalam aplikasi Anda.
### Di mana saya dapat menemukan dukungan atau bantuan tambahan dengan GroupDocs.Viewer?
 Untuk pertanyaan atau bantuan teknis apa pun, Anda dapat mengunjungi GroupDocs.Viewer[forum](https://forum.groupdocs.com/c/viewer/9) atau hubungi tim dukungan mereka untuk mendapatkan bantuan dan bimbingan segera.