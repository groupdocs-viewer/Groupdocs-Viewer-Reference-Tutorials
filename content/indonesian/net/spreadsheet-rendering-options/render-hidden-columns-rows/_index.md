---
"description": "Buka data tersembunyi di spreadsheet dengan mudah menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengungkap kolom dan baris tersembunyi."
"linktitle": "Render Kolom dan Baris Tersembunyi"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Kolom dan Baris Tersembunyi"
"url": "/id/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
---

# Render Kolom dan Baris Tersembunyi

## Perkenalan
Dalam bidang visualisasi dokumen, GroupDocs.Viewer for .NET merupakan alat yang tangguh yang memfasilitasi rendering berbagai format dokumen dengan lancar. Salah satu kemampuan yang menarik adalah kemampuan untuk menampilkan kolom dan baris tersembunyi dalam spreadsheet. Dalam tutorial ini, kita akan membahas langkah-langkah untuk membuka fitur ini dan memaksimalkan potensi data Anda.
## Prasyarat
Sebelum memulai perjalanan ini, pastikan Anda memiliki prasyarat berikut:
- GroupDocs.Viewer untuk .NET: Pastikan Anda telah menginstal versi terbaru. Jika belum, Anda dapat mengunduhnya dari [situs web resmi](https://releases.groupdocs.com/viewer/net/).
- Berkas Dokumen: Siapkan dokumen contoh dalam format spreadsheet (misalnya, SAMPLE.XLSX) untuk bereksperimen dengan kolom dan baris tersembunyi.
- Lingkungan Pengembangan: Siapkan lingkungan kerja, sebaiknya menggunakan Visual Studio atau IDE lain yang sesuai untuk pengembangan .NET.
## Mengimpor Ruang Nama
Dalam proyek .NET Anda, impor namespace yang diperlukan untuk memanfaatkan fungsionalitas GroupDocs.Viewer secara efektif:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Siapkan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Tentukan direktori keluaran tempat halaman HTML yang dirender akan disimpan. Sesuaikan format jalur file sebagaimana mestinya.
## Langkah 2: Inisialisasi Penampil dan Konfigurasikan Opsi
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Buat instance Viewer dengan memberikan jalur ke dokumen spreadsheet Anda. Konfigurasikan opsi tampilan HTML untuk menyematkan sumber daya dan mengaktifkan rendering kolom dan baris tersembunyi.
## Langkah 3: Jalankan Proses Rendering
```csharp
    viewer.View(options);
}
```
Panggil metode View pada objek penampil, dengan meneruskan opsi yang dikonfigurasi. Ini akan memulai proses rendering.
## Langkah 4: Periksa Outputnya
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verifikasi keberhasilan rendering dokumen sumber dan cari output dalam direktori yang ditentukan.
## Kesimpulan
Membuka kolom dan baris tersembunyi di lembar kerja Anda menjadi mudah dengan GroupDocs.Viewer untuk .NET. Tutorial ini telah membekali Anda dengan langkah-langkah penting untuk mengungkap data tersembunyi, sehingga memberikan tampilan dokumen Anda yang lebih komprehensif.
## Pertanyaan yang Sering Diajukan
### Bisakah saya merender kolom dan baris tersembunyi dalam format dokumen lain selain spreadsheet?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk Word, PDF, dan PowerPoint, selain spreadsheet.
### Apakah ada batasan jumlah kolom dan baris tersembunyi yang dapat dirender?
GroupDocs.Viewer menangani rendering secara efisien untuk berbagai kolom dan baris tersembunyi. Namun, kasus ekstrem dengan sejumlah besar data tersembunyi dapat memengaruhi kinerja.
### Bisakah saya menyesuaikan format keluaran dari data yang ditampilkan?
Tentu saja! GroupDocs.Viewer menyediakan opsi fleksibel untuk menyesuaikan output, yang memungkinkan Anda menyesuaikan data yang ditampilkan dengan kebutuhan spesifik Anda.
### Apakah ada pertimbangan lisensi untuk menggunakan GroupDocs.Viewer?
Ya, pastikan Anda memiliki lisensi yang sesuai untuk penggunaan Anda. Jelajahi opsi lisensi di [Pembelian GroupDocs](https://purchase.groupdocs.com/buy) atau mendapatkan [lisensi sementara](https://purchase.groupdocs.com/temporary-license/) untuk pengujian.
### Di mana saya dapat mencari bantuan atau menghubungi komunitas GroupDocs untuk mendapatkan dukungan?
Kunjungi [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk dukungan, diskusi, dan interaksi komunitas.