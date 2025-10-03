---
"description": "Pelajari cara menentukan jenis file saat memuat dokumen menggunakan GroupDocs.Viewer untuk .NET. Render berbagai format secara akurat di aplikasi .NET Anda."
"linktitle": "Tentukan Jenis File Saat Memuat Dokumen"
"second_title": "API Penampil GroupDocs.NET"
"title": "Tentukan Jenis File Saat Memuat Dokumen"
"url": "/id/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Tentukan Jenis File Saat Memuat Dokumen

## Perkenalan
GroupDocs.Viewer untuk .NET adalah API rendering dokumen serbaguna yang mendukung berbagai format file, termasuk DOCX, PDF, PPTX, dan banyak lagi. Dengan menentukan jenis file saat memuat dokumen, Anda dapat memastikan rendering yang akurat dan pengalaman menonton yang lancar bagi pengguna Anda.

![Tentukan Jenis File Saat Memuat Dokumen di GroupDocs.Viewer untuk .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Prasyarat
Sebelum memulai, pastikan Anda memiliki prasyarat berikut:
- Pengetahuan dasar tentang C# dan kerangka kerja .NET.
- Visual Studio terinstal di sistem Anda.
- GroupDocs.Viewer untuk .NET terpasang di proyek Anda. Anda dapat mengunduhnya dari [Di Sini](https://releases.groupdocs.com/viewer/net/).
##
## Mengimpor Ruang Nama
Pertama, Anda perlu mengimpor namespace yang diperlukan ke dalam kode C# Anda. Namespace ini menyediakan akses ke kelas dan metode yang diperlukan untuk rendering dokumen.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Langkah 1: Siapkan Direktori Output
Tentukan direktori tempat Anda ingin menyimpan halaman dokumen yang telah dirender.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format untuk penamaan file HTML keluaran untuk setiap halaman dokumen.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Langkah 3: Tentukan Opsi Muatan
Buat contoh dari `LoadOptions` kelas dan mengatur jenis file yang diinginkan.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Langkah 4: Muat Dokumen dan Render
Gunakan `Viewer` kelas untuk memuat dokumen dan menyajikannya ke dalam format HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Langkah 5: Menampilkan Pesan Sukses
Beritahukan pengguna bahwa dokumen telah berhasil ditampilkan dan tentukan lokasi file keluaran.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dalam tutorial ini, kita telah mempelajari cara menggunakan GroupDocs.Viewer untuk .NET guna menentukan jenis berkas saat memuat dokumen. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat memastikan rendering berbagai format dokumen yang akurat dalam aplikasi .NET Anda.
## Pertanyaan yang Sering Diajukan
### Bisakah saya merender dokumen selain DOCX menggunakan GroupDocs.Viewer untuk .NET?
Ya, GroupDocs.Viewer mendukung berbagai format file, termasuk PDF, PPTX, XLSX, dan banyak lagi.
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer untuk .NET kompatibel dengan .NET Framework dan .NET Core.
### Dapatkah saya menyesuaikan keluaran file HTML yang dihasilkan oleh GroupDocs.Viewer?
Ya, Anda dapat menyesuaikan keluaran HTML menggunakan berbagai opsi yang disediakan oleh API.
### Apakah GroupDocs.Viewer untuk .NET memerlukan dependensi eksternal?
Tidak, GroupDocs.Viewer untuk .NET adalah pustaka mandiri dan tidak memerlukan dependensi eksternal apa pun.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengunduh versi uji coba gratis dari [Di Sini](https://releases.groupdocs.com/viewer/net/).