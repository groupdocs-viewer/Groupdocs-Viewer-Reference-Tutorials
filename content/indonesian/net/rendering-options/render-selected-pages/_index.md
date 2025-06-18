---
"description": "Pelajari cara merender halaman terpilih dari dokumen menggunakan Groupdocs.Viewer untuk .NET. Tutorial langkah demi langkah dengan contoh kode disertakan."
"linktitle": "Render Halaman Terpilih"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Halaman Terpilih"
"url": "/id/net/rendering-options/render-selected-pages/"
"weight": 17
---

# Render Halaman Terpilih

## Perkenalan

Dalam tutorial ini, kita akan mempelajari cara menggunakan Groupdocs.Viewer for .NET untuk merender halaman tertentu dari sebuah dokumen. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan langkah demi langkah ini akan memandu Anda melalui proses ini dengan mudah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

### 1. Instalasi

Pastikan Anda telah menginstal Groupdocs.Viewer for .NET di lingkungan pengembangan Anda. Jika belum, Anda dapat mengunduhnya dari [Tautan unduhan](https://releases.groupdocs.com/viewer/net/).

## Mengimpor Ruang Nama

Dalam berkas kode C# Anda, impor namespace yang diperlukan untuk mengakses kelas dan metode yang diperlukan. Anda dapat melakukannya dengan menggunakan `using` direktif:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang mari kita uraikan contoh kode yang diberikan menjadi beberapa langkah:

## Langkah 1: Atur Direktori Output

Tentukan direktori tempat Anda ingin menyimpan halaman yang dirender. Ganti `"Your Document Directory"` dengan jalur direktori yang diinginkan.

```csharp
string outputDirectory = "Your Document Directory";
```

## Langkah 2: Tentukan Format Jalur File Halaman

Tentukan format untuk jalur berkas halaman yang dirender. Format ini akan digunakan untuk menyimpan setiap halaman sebagai berkas HTML di direktori keluaran.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Langkah 3: Buat Instansiasi Objek Viewer

Buat contoh kelas Viewer, berikan jalur dokumen yang ingin Anda tampilkan sebagai argumen.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Langkah 4: Konfigurasikan Opsi Tampilan HTML

Siapkan opsi tampilan HTML untuk rendering. Dalam contoh ini, kami mengonfigurasi opsi untuk menanamkan sumber daya dalam output HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Langkah 5: Render Halaman yang Dipilih

Tentukan nomor halaman yang ingin Anda tampilkan. Dalam kasus ini, kita akan menampilkan halaman 1 hingga 3. Kemudian, panggil metode View pada objek Viewer, dengan meneruskan opsi dan nomor halaman sebagai argumen.

```csharp
viewer.View(options, 1, 3);
```

## Langkah 6: Hasil Output

Terakhir, tampilkan pesan yang menunjukkan keberhasilan pemrosesan dokumen dan lokasi penyimpanan berkas keluaran.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara merender halaman terpilih dari sebuah dokumen menggunakan Groupdocs.Viewer untuk .NET. Dengan pengetahuan ini, kini Anda dapat mengintegrasikan kemampuan merender dokumen ke dalam aplikasi .NET Anda dengan mudah.

## Pertanyaan yang Sering Diajukan

### T: Dapatkah saya merender halaman dari berbagai jenis dokumen, seperti PDF atau gambar?

A: Ya, Groupdocs.Viewer untuk .NET mendukung rendering halaman dari berbagai format dokumen, termasuk PDF, dokumen Microsoft Office, dan file gambar.

### T: Apakah ada versi uji coba yang tersedia untuk pengujian sebelum membeli?

A: Ya, Anda dapat mengakses versi uji coba gratis Groupdocs.Viewer untuk .NET dari [situs web](https://releases.groupdocs.com/).

### T: Dapatkah saya menyesuaikan format keluaran selain HTML?

A: Tentu saja, Groupdocs.Viewer untuk .NET menyediakan opsi untuk menampilkan halaman sebagai gambar, PDF, dan lainnya, selain HTML.

### T: Bagaimana saya bisa mendapatkan lisensi sementara untuk tujuan pengujian?

A: Lisensi sementara dapat diperoleh dari [halaman lisensi sementara](https://purchase.groupdocs.com/temporary-license/) di situs web Groupdocs.

### T: Di mana saya bisa mencari bantuan atau mendapatkan bantuan untuk masalah yang saya hadapi?

A: Kamu bisa mengunjungi [Forum Penampil Groupdocs](https://forum.groupdocs.com/c/viewer/9) untuk dukungan dan panduan dari komunitas dan pengembang.