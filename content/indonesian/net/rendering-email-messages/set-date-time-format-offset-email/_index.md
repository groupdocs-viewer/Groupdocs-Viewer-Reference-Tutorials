---
"description": "Integrasikan GroupDocs.Viewer for .NET dengan lancar ke dalam aplikasi Anda untuk mendapatkan kemampuan tampilan dokumen yang canggih. Tingkatkan pengalaman pengguna dengan opsi yang dapat disesuaikan."
"linktitle": "Mengatur Format Tanggal dan Waktu dan Offset Zona Waktu (Email)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Mengatur Format Tanggal dan Waktu dan Offset Zona Waktu (Email)"
"url": "/id/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Mengatur Format Tanggal dan Waktu dan Offset Zona Waktu (Email)


## Perkenalan
GroupDocs.Viewer untuk .NET adalah alat canggih yang memungkinkan pengembang untuk mengintegrasikan kemampuan tampilan dokumen ke dalam aplikasi .NET mereka dengan lancar. Dengan GroupDocs.Viewer, Anda dapat menampilkan berbagai format dokumen termasuk PDF, dokumen Microsoft Office, gambar, dan lainnya secara langsung di dalam aplikasi Anda, tanpa memerlukan plugin atau penampil eksternal apa pun. Dalam tutorial komprehensif ini, kami akan memandu Anda melalui proses pengaturan GroupDocs.Viewer untuk .NET, menjelajahi fitur-fiturnya, dan menunjukkan cara memanfaatkannya secara efektif untuk meningkatkan kemampuan tampilan dokumen aplikasi Anda.
## Prasyarat
Sebelum menyelami tutorial ini, pastikan Anda telah menyiapkan prasyarat berikut:
1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di sistem Anda. GroupDocs.Viewer untuk .NET sepenuhnya kompatibel dengan Visual Studio, sehingga memungkinkan integrasi yang lancar ke dalam proyek .NET Anda.
2. GroupDocs.Viewer untuk .NET: Unduh dan instal GroupDocs.Viewer untuk .NET dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/)Ikuti petunjuk instalasi yang diberikan untuk menyiapkan pustaka dalam lingkungan pengembangan Anda.
3. .NET Framework: Pastikan Anda telah menginstal versi .NET Framework yang sesuai. GroupDocs.Viewer untuk .NET mendukung berbagai versi .NET Framework, termasuk .NET Core dan .NET Standard.

## Mengimpor Ruang Nama
Untuk memanfaatkan GroupDocs.Viewer for .NET secara efektif, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah-langkah berikut untuk mengimpor namespace yang diperlukan:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Mari kita uraikan contoh yang diberikan menjadi beberapa langkah untuk memahami setiap komponen dan fungsinya.
## Langkah 1: Tetapkan Direktori Output dan Jalur File
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Pada langkah ini, kita menentukan direktori keluaran di mana dokumen yang dirender akan disimpan dan menentukan jalur file untuk file HTML keluaran.
## Langkah 2: Buat Instansiasi Objek Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Di sini, kita membuat contoh baru dari `Viewer` kelas, yang meneruskan jalur dokumen yang akan dilihat (dalam kasus ini, contoh file EML) sebagai parameter.
## Langkah 3: Tentukan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Pada langkah ini, kami mengonfigurasi opsi tampilan HTML untuk rendering dokumen, menentukan jalur file keluaran untuk dokumen HTML yang dirender.
## Langkah 4: Atur Format Tanggal dan Waktu dan Offset Zona Waktu
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Di sini, kami menyesuaikan format tanggal dan waktu untuk pesan email dan mengatur zona waktu sesuai dengan zona waktu yang diinginkan.
## Langkah 5: Render Dokumen
```csharp
viewer.View(options);
```
Terakhir, kami memanggil `View` metode dari `Viewer` objek, meneruskan opsi tampilan HTML yang dikonfigurasi untuk menyajikan dokumen ke dalam format HTML.
## Langkah 6: Menampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Langkah ini hanya menampilkan pesan yang menunjukkan keberhasilan rendering dokumen dan menyediakan jalur ke direktori keluaran tempat dokumen HTML yang dirender berada.

## Kesimpulan
GroupDocs.Viewer untuk .NET menawarkan solusi yang tangguh untuk mengintegrasikan kemampuan tampilan dokumen ke dalam aplikasi .NET Anda. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat dengan mudah menyiapkan GroupDocs.Viewer, mengimpor namespace yang diperlukan, dan memanfaatkan fitur-fiturnya untuk merender dokumen dengan opsi yang dapat disesuaikan. Baik Anda bekerja dengan PDF, dokumen Microsoft Office, atau format lain, GroupDocs.Viewer menyederhanakan proses tampilan dokumen, sehingga meningkatkan pengalaman pengguna aplikasi Anda.
## Pertanyaan yang Sering Diajukan
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET mendukung .NET Core, memungkinkan kompatibilitas lintas-platform untuk aplikasi Anda.
### Bisakah saya menyesuaikan tampilan dokumen yang ditampilkan?
Tentu saja! GroupDocs.Viewer menyediakan berbagai opsi penyesuaian termasuk tingkat pembesaran, rotasi halaman, dan lainnya untuk menyesuaikan pengalaman menonton sesuai dengan tutorial Anda.
### Apakah ada versi uji coba yang tersedia untuk tujuan pengujian?
Ya, Anda dapat mengunduh versi uji coba gratis GroupDocs.Viewer untuk .NET dari [tautan situs web](https://releases.groupdocs.com/viewer/net/) untuk mengevaluasi fitur-fiturnya sebelum melakukan pembelian.
### Apakah GroupDocs.Viewer mendukung rendering dokumen yang dilindungi kata sandi?
Ya, GroupDocs.Viewer memiliki dukungan bawaan untuk merender dokumen yang dilindungi kata sandi, memastikan tampilan dokumen yang aman dalam aplikasi Anda.
### Di mana saya dapat menemukan dukungan atau bantuan tambahan dengan GroupDocs.Viewer?
Untuk pertanyaan teknis atau bantuan apa pun, Anda dapat mengunjungi GroupDocs.Viewer [forum](https://forum.groupdocs.com/c/viewer/9) atau menghubungi tim dukungan mereka untuk bantuan dan panduan segera.