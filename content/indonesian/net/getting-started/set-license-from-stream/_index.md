---
"description": "Tingkatkan aplikasi .NET Anda dengan GroupDocs.Viewer untuk tampilan dokumen yang lancar. Ikuti panduan langkah demi langkah kami dan integrasikan kemampuan tampilan dokumen yang canggih dengan mudah."
"linktitle": "Atur Lisensi dari Stream"
"second_title": "API Penampil GroupDocs.NET"
"title": "Atur Lisensi dari Stream"
"url": "/id/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Atur Lisensi dari Stream

## Perkenalan
Apakah Anda ingin memberdayakan aplikasi .NET Anda dengan kemampuan tampilan dokumen tingkat lanjut? GroupDocs.Viewer untuk .NET menawarkan solusi komprehensif untuk mengintegrasikan fungsionalitas tampilan dokumen ke dalam proyek Anda dengan lancar. Dalam tutorial ini, kita akan membahas proses pemanfaatan GroupDocs.Viewer untuk .NET guna memperkaya aplikasi Anda dengan kemampuan tampilan dokumen yang canggih. 

![Tetapkan Lisensi dari Stream dengan GroupDocs.Viewer untuk .NET](/viewer/getting-started/set-license-from-stream.png)

## Prasyarat
Sebelum kita masuk ke proses integrasi, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar Pengembangan .NET: Keakraban dengan C# dan kerangka kerja .NET sangat penting untuk mengikuti tutorial ini.
   
2. Paket GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal paket GroupDocs.Viewer untuk .NET. Anda dapat memperolehnya dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/).
3. Akses ke Dokumentasi GroupDocs: Simpan [dokumentasi](https://tutorials.groupdocs.com/viewer/net/) berguna untuk tutorial selama proses integrasi.

## Mengimpor Ruang Nama
Untuk memulai, impor namespace yang diperlukan ke aplikasi .NET Anda. Ikuti langkah-langkah berikut:
### Langkah 1: Buka proyek .NET Anda.
Pastikan Anda telah membuka proyek .NET di lingkungan pengembangan pilihan Anda.
### Langkah 2: Tambahkan Namespace GroupDocs.Viewer.
Dalam berkas kode Anda, tambahkan namespace berikut untuk mengakses fungsionalitas GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Atur Lisensi dari Stream
Langkah selanjutnya melibatkan pengaturan lisensi dari aliran. Ikuti langkah-langkah terperinci berikut:
### Langkah 1: Tentukan Direktori Output.
Tetapkan direktori tempat dokumen Anda akan disimpan dengan menentukan direktori keluaran:
```csharp
string outputDirectory = "Your Document Directory";
```
### Langkah 2: Periksa Keberadaan Berkas Lisensi.
Periksa apakah file lisensi ada di direktori proyek Anda:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Langkah 3: Tetapkan Lisensi.
Jika berkas lisensi ada, atur lisensi menggunakan aliran yang disediakan:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Langkah 4: Menangani Ketidakhadiran SIM.
Jika berkas lisensi tidak ditemukan, berikan petunjuk untuk mendapatkan lisensi:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/lisensi-sementara.");
}
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengintegrasikan GroupDocs.Viewer for .NET ke dalam aplikasi Anda. Dengan alat canggih ini, kini Anda dapat dengan mudah melihat berbagai format dokumen dalam proyek .NET Anda, sehingga meningkatkan pengalaman pengguna dan produktivitas.
## Pertanyaan yang Sering Diajukan
### Apakah saya memerlukan lisensi untuk menggunakan GroupDocs.Viewer untuk .NET?
Ya, Anda memerlukan lisensi untuk menggunakan GroupDocs.Viewer for .NET. Anda dapat memperoleh lisensi sementara atau permanen dari situs web GroupDocs.
### Dapatkah saya mengintegrasikan GroupDocs.Viewer ke dalam aplikasi ASP.NET saya?
Tentu saja! GroupDocs.Viewer untuk .NET terintegrasi dengan lancar ke dalam aplikasi desktop dan web, termasuk ASP.NET.
### Format dokumen apa yang didukung oleh GroupDocs.Viewer?
GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Microsoft Office (Word, Excel, PowerPoint), gambar, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan .NET Framework dan .NET Core.
### Dapatkah saya menyesuaikan antarmuka penampil menurut tema aplikasi saya?
Ya, GroupDocs.Viewer menyediakan opsi penyesuaian yang luas, yang memungkinkan Anda menyesuaikan antarmuka penampil agar sesuai dengan tema aplikasi Anda dengan mulus.