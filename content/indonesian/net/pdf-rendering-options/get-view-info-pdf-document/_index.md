---
title: Dapatkan Lihat Info untuk Dokumen PDF
linktitle: Dapatkan Lihat Info untuk Dokumen PDF
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengekstrak informasi tampilan dari dokumen PDF menggunakan GroupDocs.Viewer untuk .NET dalam tutorial komprehensif ini.
weight: 16
url: /id/net/pdf-rendering-options/get-view-info-pdf-document/
---
## Perkenalan
GroupDocs.Viewer untuk .NET adalah alat canggih yang dirancang untuk menyederhanakan tampilan dokumen dalam aplikasi .NET. Baik Anda menangani PDF, dokumen Word, spreadsheet Excel, atau presentasi PowerPoint, pustaka ini menyederhanakan proses rendering dan interaksi dengan berbagai format file. Dalam tutorial ini, kami akan fokus memanfaatkan kemampuan GroupDocs.Viewer khusus untuk mengekstrak informasi tampilan dari dokumen PDF.
## Prasyarat
Sebelum masuk ke tutorial, pastikan Anda memiliki prasyarat berikut:
1.  Instalasi GroupDocs.Viewer untuk .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan GroupDocs.Viewer. Anda dapat memperolehnya dari[tautan unduhan](https://releases.groupdocs.com/viewer/net/).   
2. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# sangat penting untuk memahami dan mengimplementasikan contoh kode yang diberikan.
3. Akses ke Dokumen PDF: Siapkan dokumen PDF yang akan Anda gunakan untuk mengekstrak informasi tampilan.

## Impor Namespace
Dalam proyek C# Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Sekarang, mari kita uraikan proses mengambil informasi tampilan dari dokumen PDF menggunakan GroupDocs.Viewer untuk .NET.
## Langkah 1: Inisialisasi Objek Penampil
Buat objek Viewer dan berikan jalur ke dokumen PDF sebagai parameter.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Langkah 2: Tentukan ViewInfoOptions
Tentukan opsi tampilan, seperti tampilan HTML, untuk mengambil informasi tampilan.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Langkah 3: Dapatkan Lihat Informasi
Panggil metode GetViewInfo untuk mengekstrak informasi tampilan dari dokumen PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Langkah 4: Informasi Tampilan Keluaran
Menampilkan informasi tampilan yang diekstraksi, seperti jenis dokumen, jumlah halaman, dan izin pencetakan.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara memanfaatkan GroupDocs.Viewer untuk .NET untuk mengekstrak informasi tampilan dari dokumen PDF. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi .NET Anda, meningkatkan kemampuan manajemen dan tampilan dokumen.
## FAQ
### Apakah GroupDocs.Viewer kompatibel dengan format file lain selain PDF?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk Word, Excel, PowerPoint, dan banyak lagi.
### Bisakah saya menyesuaikan opsi tampilan sesuai dengan kebutuhan aplikasi saya?
Tentu saja, GroupDocs.Viewer menawarkan berbagai opsi untuk menyesuaikan pengalaman menonton berdasarkan kebutuhan spesifik Anda.
### Apakah GroupDocs.Viewer cocok untuk aplikasi desktop dan web?
Ya, GroupDocs.Viewer serbaguna dan dapat diintegrasikan ke dalam aplikasi .NET desktop dan berbasis web dengan mulus.
### Apakah GroupDocs.Viewer memberikan dukungan dan bantuan jika saya mengalami masalah apa pun selama penerapan?
Tentu saja, Anda dapat mencari bantuan dari forum komunitas GroupDocs.Viewer atau mengakses layanan dukungan profesional untuk penyelesaian masalah apa pun dengan cepat.
### Bisakah saya mencoba GroupDocs.Viewer sebelum melakukan pembelian?
 Ya, Anda dapat menjelajahi fitur GroupDocs.Viewer dengan mengakses versi uji coba gratis yang tersedia di[situs web](https://purchase.groupdocs.com/buy).