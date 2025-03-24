---
title: Render Halaman yang Dipilih
linktitle: Render Halaman yang Dipilih
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender halaman yang dipilih dari dokumen menggunakan Groupdocs.Viewer untuk .NET. Tutorial langkah demi langkah dengan contoh kode disertakan.
weight: 17
url: /id/net/rendering-options/render-selected-pages/
---
## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara memanfaatkan Groupdocs.Viewer untuk .NET untuk merender halaman yang dipilih dari dokumen. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan langkah demi langkah ini akan memandu Anda melalui prosesnya dengan mudah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

### 1. Instalasi

 Pastikan Anda telah menginstal Groupdocs.Viewer untuk .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mendownloadnya dari[Tautan unduhan](https://releases.groupdocs.com/viewer/net/).

## Mengimpor Namespace

Dalam file kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang diperlukan. Anda dapat melakukan ini menggunakan`using` pengarahan:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang mari kita uraikan kode contoh yang diberikan menjadi beberapa langkah:

## Langkah 1: Tetapkan Direktori Output

 Tentukan direktori tempat Anda ingin menyimpan halaman yang dirender. Mengganti`"Your Document Directory"` dengan jalur direktori yang diinginkan.

```csharp
string outputDirectory = "Your Document Directory";
```

## Langkah 2: Tentukan Format Jalur File Halaman

Tentukan format jalur file dari halaman yang dirender. Ini akan digunakan untuk menyimpan setiap halaman sebagai file HTML di direktori keluaran.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Langkah 3: Buat Instansiasi Objek Penampil

Buat instance kelas Viewer, lewati jalur dokumen yang ingin Anda render sebagai argumen.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Langkah 4: Konfigurasikan Opsi Tampilan HTML

Siapkan opsi tampilan HTML untuk rendering. Dalam contoh ini, kami mengonfigurasi opsi untuk menyematkan sumber daya dalam keluaran HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Langkah 5: Render Halaman yang Dipilih

Tentukan nomor halaman yang ingin Anda render. Dalam hal ini, kita merender halaman 1 hingga 3. Kemudian, panggil metode View pada objek Viewer, dengan meneruskan opsi dan nomor halaman sebagai argumen.

```csharp
viewer.View(options, 1, 3);
```

## Langkah 6: Hasil Keluaran

Terakhir, tampilkan pesan yang menunjukkan keberhasilan rendering dokumen dan lokasi penyimpanan file keluaran.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara merender halaman yang dipilih dari dokumen menggunakan Groupdocs.Viewer untuk .NET. Dengan pengetahuan ini, kini Anda dapat mengintegrasikan kemampuan rendering dokumen ke dalam aplikasi .NET Anda dengan mudah.

## FAQ

### T: Dapatkah saya merender halaman dari berbagai jenis dokumen, seperti PDF atau gambar?

J: Ya, Groupdocs.Viewer untuk .NET mendukung rendering halaman dari berbagai format dokumen, termasuk PDF, dokumen Microsoft Office, dan file gambar.

### T: Apakah ada versi uji coba yang tersedia untuk pengujian sebelum membeli?

 J: Ya, Anda dapat mengakses versi uji coba gratis Groupdocs.Viewer untuk .NET dari[situs web](https://releases.groupdocs.com/).

### T: Bisakah saya menyesuaikan format keluaran selain HTML?

J: Tentu saja, Groupdocs.Viewer untuk .NET menyediakan opsi untuk merender halaman sebagai gambar, PDF, dan lainnya, selain HTML.

### T: Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?

J: Lisensi sementara dapat diperoleh dari[halaman lisensi sementara](https://purchase.groupdocs.com/temporary-license/) di situs web Groupdocs.

### T: Di mana saya bisa mencari bantuan atau mendapatkan bantuan untuk masalah apa pun yang saya temui?

 A: Anda dapat mengunjungi[Groupdocs. Forum penampil](https://forum.groupdocs.com/c/viewer/9) atas dukungan dan bimbingan dari masyarakat dan pengembang.