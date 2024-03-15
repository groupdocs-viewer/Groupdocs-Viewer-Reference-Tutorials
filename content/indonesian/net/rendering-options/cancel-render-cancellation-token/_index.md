---
title: Batalkan Render dengan Token Pembatalan
linktitle: Batalkan Render dengan Token Pembatalan
second_title: GroupDocs.Viewer .NET API
description: Integrasikan Groupdocs.Viewer untuk .NET dengan lancar ke dalam proyek .NET Anda untuk tampilan dokumen yang efisien.
type: docs
weight: 11
url: /id/net/rendering-options/cancel-render-cancellation-token/
---
## Perkenalan
Groupdocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk menyederhanakan tampilan dan pemrosesan dokumen dalam aplikasi .NET. Baik Anda berurusan dengan PDF, dokumen Microsoft Office, atau format umum lainnya, perpustakaan ini menawarkan fungsionalitas yang kuat untuk mengintegrasikan kemampuan melihat dokumen dengan lancar ke dalam proyek .NET Anda.
## Prasyarat
Sebelum mendalami integrasi Groupdocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi: Unduh dan instal perpustakaan Groupdocs.Viewer untuk .NET dari yang disediakan[tautan unduhan](https://releases.groupdocs.com/viewer/net/).
   
2.  Lisensi: Dapatkan lisensi dari[dokumen grup](https://purchase.groupdocs.com/buy) untuk membuka seluruh potensi perpustakaan. Alternatifnya, Anda dapat memulai dengan uji coba gratis menggunakan[izin sementara](https://purchase.groupdocs.com/temporary-license/).
   
3. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan yang kompatibel, termasuk Visual Studio atau .NET IDE lainnya pilihan Anda.

## Impor Namespace
Untuk memanfaatkan Groupdocs.Viewer untuk .NET secara efektif, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ikuti langkah ini:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Sekarang, mari kita bagi contoh yang diberikan menjadi beberapa langkah untuk pemahaman dan penerapan yang lebih baik:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Langkah ini menetapkan direktori tempat halaman dokumen yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Di sini, kami menentukan format jalur file masing-masing halaman dokumen.
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
Di sini, kami memulai rendering halaman dokumen secara asinkron menggunakan Task.Run(). Instance Viewer dibuat dengan file dokumen tertentu (SAMPLE_DOCX), dan opsi rendering dikonfigurasi. Proses rendering kemudian dimulai menggunakan metode View dari kelas Viewer.
## Langkah 6: Tetapkan Batas Waktu Render
```csharp
cancellationTokenSource.CancelAfter(10);
```
Langkah ini menetapkan batas waktu 10 milidetik untuk operasi rendering. Jika operasi melebihi batas waktu ini, operasi akan dibatalkan secara otomatis.
## Langkah 7: Tampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Terakhir, pesan sukses ditampilkan yang menunjukkan bahwa dokumen telah berhasil dirender.

## Kesimpulan
Dalam tutorial ini, kami telah membahas dasar-dasar pengintegrasian Groupdocs.Viewer untuk .NET ke dalam proyek Anda. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat dengan mudah menggabungkan kemampuan melihat dokumen ke dalam aplikasi .NET Anda, sehingga meningkatkan pengalaman pengguna dan produktivitas.
## FAQ
### Apakah Groupdocs.Viewer untuk .NET kompatibel dengan semua format dokumen?
Groupdocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk PDF, dokumen Microsoft Office, gambar, dan banyak lagi.
### Bisakah saya menyesuaikan tampilan halaman dokumen yang dirender?
Ya, Anda dapat menyesuaikan berbagai aspek proses rendering, termasuk ukuran halaman, kualitas, watermarking, dan banyak lagi.
### Apakah Groupdocs.Viewer untuk .NET memerlukan konektivitas internet?
Tidak, Groupdocs.Viewer untuk .NET beroperasi secara lokal dalam lingkungan .NET Anda dan tidak memerlukan konektivitas internet untuk melihat dokumen.
### Apakah dukungan teknis tersedia untuk Groupdocs.Viewer untuk .NET?
 Ya, dukungan teknis tersedia melalui[Forum Grupdocs](https://forum.groupdocs.com/c/viewer/9), tempat Anda dapat mengajukan pertanyaan, melaporkan masalah, dan berinteraksi dengan komunitas.
### Bisakah saya mencoba Groupdocs.Viewer untuk .NET sebelum membeli?
 Ya, Anda bisa memulai dengan uji coba gratis menggunakan yang disediakan[versi percobaan](https://releases.groupdocs.com/).