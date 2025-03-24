---
title: Tetapkan Lisensi dari Stream
linktitle: Tetapkan Lisensi dari Stream
second_title: GroupDocs.Viewer .NET API
description: Tingkatkan aplikasi .NET Anda dengan GroupDocs.Viewer untuk tampilan dokumen yang lancar. Ikuti panduan langkah demi langkah kami dan integrasikan kemampuan melihat dokumen yang canggih dengan mudah.
weight: 11
url: /id/net/getting-started/set-license-from-stream/
---
## Perkenalan
Apakah Anda ingin memberdayakan aplikasi .NET Anda dengan kemampuan melihat dokumen tingkat lanjut? GroupDocs.Viewer untuk .NET menawarkan solusi komprehensif untuk mengintegrasikan fungsi tampilan dokumen ke dalam proyek Anda dengan lancar. Dalam tutorial ini, kita akan mempelajari proses memanfaatkan GroupDocs.Viewer untuk .NET untuk memperkaya aplikasi Anda dengan kemampuan melihat dokumen yang canggih. 
## Prasyarat
Sebelum kita mendalami proses integrasi, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar Pengembangan .NET: Keakraban dengan C# dan kerangka .NET sangat penting untuk mengikuti tutorial ini.
   
2.  Paket GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal paket GroupDocs.Viewer untuk .NET. Anda dapat memperolehnya dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/).
3.  Akses ke Dokumentasi GroupDocs: Simpan[dokumentasi](https://tutorials.groupdocs.com/viewer/net/) berguna untuk referensi selama proses integrasi.

## Impor Namespace
Untuk memulainya, impor namespace yang diperlukan ke dalam aplikasi .NET Anda. Ikuti langkah ini:
### Langkah 1: Buka proyek .NET Anda.
Pastikan proyek .NET Anda dibuka di lingkungan pengembangan pilihan Anda.
### Langkah 2: Tambahkan GroupDocs.Viewer Namespace.
Di file kode Anda, tambahkan namespace berikut untuk mengakses fungsionalitas GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Tetapkan Lisensi dari Stream
Langkah selanjutnya melibatkan pengaturan lisensi dari aliran. Ikuti langkah-langkah terperinci berikut:
### Langkah 1: Tentukan Direktori Output.
Tetapkan direktori tempat dokumen Anda akan disimpan dengan menentukan direktori keluaran:
```csharp
string outputDirectory = "Your Document Directory";
```
### Langkah 2: Periksa Keberadaan File Lisensi.
Periksa apakah file lisensi ada di direktori proyek Anda:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Langkah 3: Tetapkan Lisensi.
Jika file lisensi ada, setel lisensi menggunakan aliran yang disediakan:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Langkah 4: Tangani Ketidakhadiran Lisensi.
Jika file lisensi tidak ditemukan, berikan petunjuk untuk mendapatkan lisensi:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://pembelian.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengintegrasikan GroupDocs.Viewer untuk .NET ke dalam aplikasi Anda. Dengan alat canggih ini, kini Anda dapat dengan mudah melihat berbagai format dokumen dalam proyek .NET Anda, sehingga meningkatkan pengalaman pengguna dan produktivitas.
## FAQ
### Apakah saya memerlukan lisensi untuk menggunakan GroupDocs.Viewer untuk .NET?
Ya, Anda memerlukan lisensi untuk menggunakan GroupDocs.Viewer untuk .NET. Anda dapat memperoleh lisensi sementara atau permanen dari situs web GroupDocs.
### Bisakah saya mengintegrasikan GroupDocs.Viewer ke dalam aplikasi ASP.NET saya?
Sangat! GroupDocs.Viewer untuk .NET terintegrasi dengan mulus ke dalam aplikasi desktop dan web, termasuk ASP.NET.
### Format dokumen apa yang didukung oleh GroupDocs.Viewer?
GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Microsoft Office (Word, Excel, PowerPoint), gambar, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan antarmuka penampil sesuai dengan tema aplikasi saya?
Ya, GroupDocs.Viewer menyediakan opsi penyesuaian yang luas, memungkinkan Anda menyesuaikan antarmuka penampil agar sesuai dengan tema aplikasi Anda dengan lancar.