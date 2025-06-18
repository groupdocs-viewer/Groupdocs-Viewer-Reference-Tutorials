---
"description": "Dapatkan kemampuan melihat dokumen tanpa hambatan di .NET Anda dengan GroupDocs.Viewer untuk .NET. Integrasikan dan sesuaikan tampilan dokumen dengan mudah dengan ketergantungan minimal."
"linktitle": "Nonaktifkan Verifikasi Lisensi Font dalam PDF"
"second_title": "API Penampil GroupDocs.NET"
"title": "Nonaktifkan Verifikasi Lisensi Font dalam PDF"
"url": "/id/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# Nonaktifkan Verifikasi Lisensi Font dalam PDF

## Perkenalan
Dalam bidang pengembangan .NET, mengelola dan memanipulasi dokumen sering kali merupakan aspek penting dari banyak aplikasi. Baik itu melihat PDF, dokumen Word, atau jenis file lainnya, memiliki alat yang tangguh untuk menangani tugas-tugas ini secara efisien sangatlah penting. Di sinilah GroupDocs.Viewer untuk .NET berperan. Pustaka yang hebat ini memberi pengembang kemampuan untuk mengintegrasikan fungsionalitas tampilan dokumen ke dalam aplikasi .NET mereka dengan lancar.

![Nonaktifkan Verifikasi Lisensi Font dalam PDF dengan GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Prasyarat
Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET, ada beberapa prasyarat yang perlu Anda penuhi:
### 1. Instal Visual Studio
Pertama dan terutama, pastikan Anda telah menginstal Visual Studio di sistem Anda. Anda dapat mengunduhnya dari situs web Microsoft jika belum melakukannya.
### 2. Unduh GroupDocs.Viewer untuk .NET
Kunjungi [tautan unduhan](https://releases.groupdocs.com/viewer/net/) untuk memperoleh versi terbaru GroupDocs.Viewer untuk .NET. Ikuti petunjuk instalasi yang diberikan untuk mengaturnya dalam lingkungan pengembangan Anda.
### 3. Dapatkan Lisensi Sementara
Untuk membuka potensi penuh GroupDocs.Viewer untuk .NET selama pengembangan dan pengujian, disarankan untuk mendapatkan lisensi sementara. Anda dapat meminta lisensi sementara dari [Di Sini](https://purchase.groupdocs.com/temporary-license/).

## Mengimpor Ruang Nama
Setelah Anda menyelesaikan prasyarat, Anda siap untuk mulai menggunakan GroupDocs.Viewer for .NET dalam proyek Anda. Mulailah dengan mengimpor namespace yang diperlukan ke dalam basis kode Anda.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Mari kita uraikan contoh yang diberikan menjadi beberapa langkah agar lebih mudah dipahami:
## Langkah 1: Tentukan Direktori Output
Mulailah dengan menentukan direktori di mana Anda ingin menyimpan halaman dokumen yang dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tetapkan format untuk jalur berkas di setiap halaman dokumen.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Langkah 3: Inisialisasi Objek Penampil
Buat contoh kelas Viewer dan teruskan jalur ke dokumen yang ingin Anda lihat.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
Tentukan pilihan untuk melihat dokumen sebagai HTML, tentukan format untuk sumber daya yang tertanam (misalnya, gambar).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 5: Nonaktifkan Verifikasi Lisensi Font
Aktifkan opsi untuk menonaktifkan verifikasi lisensi font guna memastikan proses rendering berjalan lancar.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Langkah 6: Lihat Dokumen
Panggil metode View dari objek Viewer dan berikan opsi yang dikonfigurasikan.
```csharp
viewer.View(options);
```
## Langkah 7: Menampilkan Direktori Output
Memberi tahu pengguna tentang lokasi penyimpanan halaman dokumen yang ditampilkan.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
GroupDocs.Viewer untuk .NET menawarkan solusi komprehensif bagi para pengembang untuk mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET mereka dengan mudah. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat secara efektif memanfaatkan pustaka canggih ini untuk meningkatkan alur kerja manajemen dokumen Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer untuk .NET menangani beberapa format dokumen?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, Microsoft Word, Excel, PowerPoint, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET cocok untuk aplikasi web?
Tentu saja, GroupDocs.Viewer dapat diintegrasikan dengan mulus ke dalam aplikasi desktop dan web yang dikembangkan menggunakan teknologi .NET.
### Apakah GroupDocs.Viewer memerlukan dependensi tambahan?
Tidak, GroupDocs.Viewer untuk .NET memiliki dependensi minimal dan dapat dengan mudah diintegrasikan ke dalam proyek Anda yang sudah ada.
### Bisakah saya menyesuaikan tampilan dokumen yang ditampilkan?
Ya, GroupDocs.Viewer menyediakan berbagai opsi untuk menyesuaikan tampilan dan perilaku dokumen yang dirender agar sesuai dengan kebutuhan spesifik Anda.
### Apakah dukungan teknis tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mencari bantuan dan panduan dari tim dukungan khusus melalui [forum](https://forum.groupdocs.com/c/viewer/9).