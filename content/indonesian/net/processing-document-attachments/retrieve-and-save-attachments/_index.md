---
"description": "Kelola lampiran dokumen secara efisien dalam aplikasi .NET menggunakan GroupDocs.Viewer. Ambil dan simpan lampiran tanpa repot."
"linktitle": "Ambil dan Simpan Lampiran Dokumen"
"second_title": "API Penampil GroupDocs.NET"
"title": "Ambil dan Simpan Lampiran Dokumen"
"url": "/id/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
---

# Ambil dan Simpan Lampiran Dokumen

## Perkenalan
Di era digital, penanganan dokumen yang efisien sangat penting bagi bisnis dan individu. Baik itu mengelola email, melihat kontrak, atau mengakses laporan, memiliki alat yang andal untuk visualisasi dokumen sangatlah penting. GroupDocs.Viewer untuk .NET muncul sebagai solusi yang tangguh, memberdayakan pengguna untuk dengan mudah melihat dan berinteraksi dengan berbagai format dokumen langsung dalam aplikasi .NET mereka.

![Ambil dan Simpan Lampiran Dokumen dengan GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Prasyarat
Sebelum mempelajari lebih lanjut tentang penggunaan GroupDocs.Viewer for .NET untuk pengambilan dan penyimpanan lampiran dokumen, pastikan Anda memiliki prasyarat berikut:
1. Lingkungan Operasi: Lingkungan kerja yang disiapkan dengan kerangka kerja .NET.
2. Instalasi: GroupDocs.Viewer untuk pustaka .NET diunduh dan diinstal. Anda dapat mengakses pustaka dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/).
3. Pemahaman Dasar: Keakraban dengan bahasa pemrograman C#.
4. Sumber Dokumen: Akses ke contoh dokumen dengan lampiran untuk tujuan demonstrasi.

## Mengimpor Ruang Nama
Untuk mulai menggunakan GroupDocs.Viewer untuk .NET untuk pengambilan dan penyimpanan lampiran dokumen, impor namespace yang diperlukan:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tentukan direktori tempat Anda ingin menyimpan lampiran yang diambil dari dokumen.
## Langkah 2: Buat Instansiasi Objek Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Buat objek Viewer dengan jalur ke dokumen yang berisi lampiran.
## Langkah 3: Ambil Lampiran
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Ambil daftar lampiran yang ada dalam dokumen.
## Langkah 4: Simpan Lampiran
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Ulangi setiap lampiran, tentukan jalur file, dan simpan lampiran ke direktori yang ditentukan.
## Langkah 5: Menampilkan Pesan Sukses
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Menampilkan pesan sukses yang menunjukkan keberhasilan penyimpanan lampiran beserta jalur direktori.

## Kesimpulan
Dengan menggabungkan GroupDocs.Viewer for .NET ke dalam alur kerja penanganan dokumen Anda, proses pengelolaan lampiran akan lebih mudah dan efisien. Dengan mengikuti panduan langkah demi langkah yang diuraikan di atas, pengguna dapat dengan mudah mengambil dan menyimpan lampiran dokumen dalam aplikasi .NET mereka.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer untuk .NET menangani berbagai format dokumen?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, dokumen Microsoft Office, gambar, dan banyak lagi.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengakses uji coba gratis dari [Di Sini](https://releases.groupdocs.com/).
### Bagaimana cara memperoleh lisensi sementara untuk GroupDocs.Viewer untuk .NET?
Lisensi sementara dapat diperoleh dari [tautan ini](https://purchase.groupdocs.com/temporary-license/).
### Di mana saya dapat menemukan dokumentasi untuk GroupDocs.Viewer untuk .NET?
Dokumentasi lengkap tersedia [Di Sini](https://tutorials.groupdocs.com/viewer/net/).
### Pilihan dukungan apa yang tersedia untuk GroupDocs.Viewer untuk .NET?
Anda dapat mencari bantuan dari forum komunitas [Di Sini](https://forum.groupdocs.com/c/viewer/9).