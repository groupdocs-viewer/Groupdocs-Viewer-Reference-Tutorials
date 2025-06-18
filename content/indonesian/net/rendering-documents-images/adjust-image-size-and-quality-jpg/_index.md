---
"description": "Pelajari cara mengoptimalkan ukuran dan kualitas gambar dalam format JPEG menggunakan Groupdocs.Viewer untuk .NET. Tingkatkan pengalaman melihat dokumen Anda."
"linktitle": "Sesuaikan Ukuran dan Kualitas Gambar (JPG)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Sesuaikan Ukuran dan Kualitas Gambar (JPG)"
"url": "/id/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Sesuaikan Ukuran dan Kualitas Gambar (JPG)

## Perkenalan
Groupdocs.Viewer untuk .NET adalah pustaka canggih yang memungkinkan pengembang untuk mengintegrasikan fungsionalitas tampilan dokumen ke dalam aplikasi .NET mereka dengan lancar. Salah satu persyaratan umum dalam aplikasi tampilan dokumen adalah kemampuan untuk menyesuaikan ukuran dan kualitas gambar, terutama saat menangani gambar JPEG (JPG). Dalam tutorial ini, kami akan memandu Anda melalui proses penyesuaian ukuran dan kualitas gambar menggunakan Groupdocs.Viewer untuk .NET.
## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1. Pemahaman dasar tentang bahasa pemrograman C#.
2. Visual Studio terinstal di sistem Anda.
3. Groupdocs.Viewer untuk pustaka .NET telah terinstal. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).

## Mengimpor Ruang Nama
Pertama, Anda perlu mengimpor namespace yang diperlukan ke dalam kode C# Anda. Namespace ini menyediakan akses ke kelas dan metode yang diperlukan untuk bekerja dengan Groupdocs.Viewer.
## Langkah 1: Impor Namespace
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang, mari kita uraikan contoh kode yang disediakan menjadi beberapa langkah agar lebih mudah dipahami.
## Langkah 2: Atur Direktori Output dan Format Jalur File Halaman
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Pada langkah ini, kami tentukan direktori keluaran tempat gambar yang dirender akan disimpan dan tentukan format untuk jalur file setiap gambar halaman.
## Langkah 3: Inisialisasi Penampil dan Konfigurasikan Opsi Tampilan JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Di sini, kita menginisialisasi objek Viewer dengan jalur ke dokumen yang akan dilihat. Kemudian, kita membuat contoh JpgViewOptions dan mengatur lebar dan tinggi yang diinginkan untuk gambar JPEG.
## Langkah 4: Render Dokumen Sumber
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Terakhir, kami mencetak pesan yang menunjukkan keberhasilan pemrosesan dokumen sumber dan lokasi penyimpanan gambar keluaran.

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menyesuaikan ukuran dan kualitas gambar JPEG menggunakan Groupdocs.Viewer untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah memasukkan fungsi ini ke dalam aplikasi .NET Anda, sehingga memberikan pengalaman menonton gambar yang optimal bagi pengguna.
## Pertanyaan yang Sering Diajukan
### Bisakah saya menyesuaikan kualitas gambar juga?
Ya, Anda dapat menyesuaikan kualitas gambar dengan menyetel properti Kualitas di JpgViewOptions.
### Format dokumen apa yang didukung oleh Groupdocs.Viewer untuk .NET?
Groupdocs.Viewer untuk .NET mendukung berbagai format dokumen termasuk DOCX, PDF, PPTX, XLSX, dan banyak lagi.
### Apakah Groupdocs.Viewer untuk .NET kompatibel dengan .NET Core?
Ya, Groupdocs.Viewer untuk .NET kompatibel dengan .NET Core dan .NET Framework tradisional.
### Bisakah saya menyesuaikan format penamaan berkas keluaran?
Ya, Anda dapat menyesuaikan format penamaan file keluaran dengan memodifikasi variabel pageFilePathFormat dalam kode.
### Apakah Groupdocs.Viewer untuk .NET mendukung anotasi dokumen?
Ya, Groupdocs.Viewer untuk .NET menyediakan dukungan komprehensif untuk anotasi dokumen termasuk penyorotan teks, garis bawah, dan komentar.