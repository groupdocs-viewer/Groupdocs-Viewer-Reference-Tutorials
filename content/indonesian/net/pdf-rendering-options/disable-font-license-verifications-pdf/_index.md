---
title: Nonaktifkan Verifikasi Lisensi Font di PDF
linktitle: Nonaktifkan Verifikasi Lisensi Font di PDF
second_title: GroupDocs.Viewer .NET API
description: Buka kemampuan melihat dokumen tanpa hambatan di .NET Anda dengan GroupDocs.Viewer untuk .NET. Integrasikan dan sesuaikan rendering dokumen dengan mudah dengan ketergantungan minimal.
type: docs
weight: 12
url: /id/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## Perkenalan
Dalam bidang pengembangan .NET, pengelolaan dan manipulasi dokumen seringkali menjadi aspek penting dalam banyak aplikasi. Baik itu melihat PDF, dokumen Word, atau jenis file lainnya, memiliki alat canggih untuk menangani tugas-tugas ini secara efisien sangatlah penting. Di sinilah GroupDocs.Viewer untuk .NET berperan. Pustaka yang kuat ini memberi pengembang kemampuan untuk mengintegrasikan fungsionalitas tampilan dokumen dengan mulus ke dalam aplikasi .NET mereka.
## Prasyarat
Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET, ada beberapa prasyarat yang harus Anda miliki:
### 1. Instal Visual Studio
Pertama dan terpenting, pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda dapat mengunduhnya dari situs web Microsoft jika Anda belum melakukannya.
### 2. Unduh GroupDocs.Viewer untuk .NET
 Pergilah ke[tautan unduhan](https://releases.groupdocs.com/viewer/net/) untuk mendapatkan versi terbaru GroupDocs.Viewer untuk .NET. Ikuti petunjuk instalasi yang diberikan untuk mengaturnya dalam lingkungan pengembangan Anda.
### 3. Mendapatkan Lisensi Sementara
 Untuk membuka potensi penuh GroupDocs.Viewer untuk .NET selama pengembangan dan pengujian, disarankan untuk mendapatkan lisensi sementara. Anda dapat memintanya dari[Di Sini](https://purchase.groupdocs.com/temporary-license/).

## Impor Namespace
Setelah Anda menyelesaikan prasyarat, Anda siap untuk mulai menggunakan GroupDocs.Viewer untuk .NET dalam proyek Anda. Mulailah dengan mengimpor namespace yang diperlukan ke dalam basis kode Anda.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman yang lebih jelas:
## Langkah 1: Tentukan Direktori Output
Mulailah dengan menentukan direktori tempat Anda ingin menyimpan halaman dokumen yang dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tetapkan format jalur file untuk setiap halaman dokumen.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Langkah 3: Inisialisasi Objek Penampil
Buat sebuah instance dari kelas Viewer, meneruskan jalur ke dokumen yang ingin Anda lihat.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Tentukan pilihan untuk melihat dokumen sebagai HTML, tentukan format untuk sumber daya yang disematkan (misalnya gambar).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 5: Nonaktifkan Verifikasi Lisensi Font
Aktifkan opsi untuk menonaktifkan verifikasi lisensi font untuk memastikan kelancaran rendering.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Langkah 6: Lihat Dokumen
Panggil metode View dari objek Viewer, dengan meneruskan opsi yang dikonfigurasi.
```csharp
viewer.View(options);
```
## Langkah 7: Tampilkan Direktori Output
Memberi tahu pengguna tentang lokasi penyimpanan halaman dokumen yang dirender.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
GroupDocs.Viewer untuk .NET menawarkan kepada pengembang solusi komprehensif untuk mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET mereka dengan mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat memanfaatkan pustaka canggih ini secara efektif untuk meningkatkan alur kerja manajemen dokumen Anda.
## FAQ
### Bisakah GroupDocs.Viewer untuk .NET menangani berbagai format dokumen?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, Microsoft Word, Excel, PowerPoint, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET cocok untuk aplikasi web?
Tentu saja, GroupDocs.Viewer dapat diintegrasikan dengan mulus ke dalam aplikasi desktop dan web yang dikembangkan menggunakan teknologi .NET.
### Apakah GroupDocs.Viewer memerlukan ketergantungan tambahan?
Tidak, GroupDocs.Viewer untuk .NET memiliki ketergantungan minimal dan dapat dengan mudah diintegrasikan ke dalam proyek Anda yang sudah ada.
### Bisakah saya menyesuaikan tampilan dokumen yang dirender?
Ya, GroupDocs.Viewer menyediakan berbagai opsi untuk menyesuaikan tampilan dan perilaku dokumen yang dirender agar sesuai dengan kebutuhan spesifik Anda.
### Apakah dukungan teknis tersedia untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mencari bantuan dan bimbingan dari tim dukungan khusus melalui[forum](https://forum.groupdocs.com/c/viewer/9).