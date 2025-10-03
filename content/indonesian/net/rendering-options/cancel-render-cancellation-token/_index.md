---
"description": "Integrasikan Groupdocs.Viewer untuk .NET dengan mulus ke dalam proyek .NET Anda untuk tampilan dokumen yang efisien."
"linktitle": "Batalkan Render dengan Token Pembatalan"
"second_title": "API Penampil GroupDocs.NET"
"title": "Batalkan Render dengan Token Pembatalan"
"url": "/id/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Batalkan Render dengan Token Pembatalan

## Perkenalan
Groupdocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk menyederhanakan tampilan dan pemrosesan dokumen dalam aplikasi .NET. Baik Anda menangani PDF, dokumen Microsoft Office, atau format umum lainnya, pustaka ini menawarkan fungsionalitas yang tangguh untuk mengintegrasikan kemampuan tampilan dokumen ke dalam proyek .NET Anda dengan lancar.
## Prasyarat
Sebelum menyelami integrasi Groupdocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
1. Instalasi: Unduh dan instal pustaka Groupdocs.Viewer untuk .NET dari sumber yang disediakan. [tautan unduhan](https://releases.groupdocs.com/viewer/net/).
   
2. Lisensi: Dapatkan lisensi dari [Grupdocs](https://purchase.groupdocs.com/buy) untuk membuka potensi penuh perpustakaan. Atau, Anda dapat memulai dengan uji coba gratis menggunakan [lisensi sementara](https://purchase.groupdocs.com/temporary-license/).
   
3. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan yang kompatibel, termasuk Visual Studio atau IDE .NET lain pilihan Anda.

## Mengimpor Ruang Nama
Untuk memanfaatkan Groupdocs.Viewer for .NET secara efektif, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah-langkah berikut:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Sekarang, mari kita uraikan contoh yang diberikan menjadi beberapa langkah agar lebih mudah dipahami dan diterapkan:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Langkah ini menetapkan direktori tempat halaman dokumen yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Di sini, kami menentukan format untuk jalur berkas setiap halaman dokumen individual.
## Langkah 3: Inisialisasi CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource digunakan untuk menghasilkan instance CancellationToken yang dapat digunakan untuk membatalkan operasi asinkron.
## Langkah 4: Dapatkan CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Langkah ini mengambil token dari CancellationTokenSource, yang akan digunakan untuk membatalkan operasi rendering.
## Langkah 5: Render Halaman Dokumen
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Di sini, kami memulai rendering halaman dokumen secara asinkron menggunakan Task.Run(). Instance Viewer dibuat dengan file dokumen yang ditentukan (SAMPLE_DOCX), dan opsi rendering dikonfigurasi. Proses rendering kemudian dimulai menggunakan metode View dari kelas Viewer.
## Langkah 6: Mengatur Batas Waktu Render
```csharp
cancellationTokenSource.CancelAfter(10);
```
Langkah ini menetapkan batas waktu 10 milidetik untuk operasi rendering. Jika operasi melampaui batas waktu ini, operasi akan dibatalkan secara otomatis.
## Langkah 7: Menampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Terakhir, pesan sukses ditampilkan yang menunjukkan dokumen telah berhasil dirender.

## Kesimpulan
Dalam tutorial ini, kami telah membahas dasar-dasar pengintegrasian Groupdocs.Viewer for .NET ke dalam proyek Anda. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah menggabungkan kemampuan tampilan dokumen ke dalam aplikasi .NET Anda, yang akan meningkatkan pengalaman pengguna dan produktivitas.
## Pertanyaan yang Sering Diajukan
### Apakah Groupdocs.Viewer untuk .NET kompatibel dengan semua format dokumen?
Groupdocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk PDF, dokumen Microsoft Office, gambar, dan banyak lagi.
### Bisakah saya menyesuaikan tampilan halaman dokumen yang ditampilkan?
Ya, Anda dapat menyesuaikan berbagai aspek proses rendering, termasuk ukuran halaman, kualitas, tanda air, dan banyak lagi.
### Apakah Groupdocs.Viewer untuk .NET memerlukan konektivitas internet?
Tidak, Groupdocs.Viewer untuk .NET beroperasi secara lokal dalam lingkungan .NET Anda dan tidak memerlukan konektivitas internet untuk melihat dokumen.
### Apakah dukungan teknis tersedia untuk Groupdocs.Viewer untuk .NET?
Ya, dukungan teknis tersedia melalui [Forum Groupdocs](https://forum.groupdocs.com/c/viewer/9), tempat Anda dapat mengajukan pertanyaan, melaporkan masalah, dan berinteraksi dengan komunitas.
### Dapatkah saya mencoba Groupdocs.Viewer untuk .NET sebelum membeli?
Ya, Anda dapat memulai dengan uji coba gratis menggunakan [versi percobaan](https://releases.groupdocs.com/).