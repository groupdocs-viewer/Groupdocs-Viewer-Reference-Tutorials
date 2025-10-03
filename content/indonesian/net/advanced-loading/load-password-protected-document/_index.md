---
"description": "Integrasikan tampilan dokumen yang dilindungi kata sandi ke dalam aplikasi .NET dengan mudah menggunakan GroupDocs.Viewer untuk .NET. Ikuti tutorial langkah demi langkah kami untuk kemudahan."
"linktitle": "Muat Dokumen yang Dilindungi Kata Sandi"
"second_title": "API Penampil GroupDocs.NET"
"title": "Muat Dokumen yang Dilindungi Kata Sandi"
"url": "/id/net/advanced-loading/load-password-protected-document/"
"weight": 12
type: docs
---
# Muat Dokumen yang Dilindungi Kata Sandi

## Perkenalan
Di era digital saat ini, mengelola dan melihat berbagai format dokumen dengan mudah merupakan suatu keharusan bagi banyak bisnis dan individu. Untungnya, GroupDocs.Viewer untuk .NET menyediakan solusi komprehensif bagi pengembang .NET untuk mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi mereka dengan mudah. Dalam tutorial ini, kita akan membahas salah satu fungsi penting GroupDocs.Viewer: memuat dokumen yang dilindungi kata sandi. Kita akan menguraikan proses ini langkah demi langkah, memastikan bahwa pengembang dapat dengan mudah mengikuti dan menerapkan fitur ini ke dalam proyek mereka.

![Memuat Dokumen yang Dilindungi Kata Sandi di GroupDocs.Viewer untuk .NET](/viewer/advanced-loading/load-password-protected-documents-img.png)

## Prasyarat
Sebelum kita masuk ke tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
Pastikan Anda telah menginstal GroupDocs.Viewer for .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari [situs web](https://releases.groupdocs.com/viewer/net/).
### 2. Dapatkan Dokumen yang Dilindungi Kata Sandi
Untuk tujuan pengujian, sediakan dokumen yang dilindungi kata sandi. Ini akan memungkinkan kami untuk mendemonstrasikan proses pemuatan secara efektif.

## Mengimpor Ruang Nama
Sebelum kita melanjutkan tutorial, mari impor namespace yang diperlukan ke proyek kita:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Pertama, tentukan direktori tempat Anda ingin menyimpan hasil render:
```csharp
string outputDirectory = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur direktori yang Anda inginkan.
## Langkah 2: Tentukan Format Jalur File Halaman
Berikutnya, tentukan format untuk jalur file setiap halaman yang ditampilkan:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Format ini akan menghasilkan jalur file seperti `"Your Document Directory/page_1.html"`Bahasa Indonesia: `"Your Document Directory/page_2.html"`, dan seterusnya.
## Langkah 3: Konfigurasikan Opsi Muat
Konfigurasikan opsi muat untuk dokumen yang dilindungi kata sandi, termasuk kata sandinya:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
Mengganti `"12345"` dengan kata sandi sebenarnya dari dokumen Anda.
## Langkah 4: Inisialisasi Viewer
Inisialisasi GroupDocs.Viewer dengan opsi dokumen dan muat:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Kode untuk pilihan tampilan akan ditambahkan pada langkah berikutnya.
}
```
Mengganti `"Path_to_your_document"` dengan jalur ke dokumen Anda yang dilindungi kata sandi.
## Langkah 5: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML untuk merender dokumen dengan sumber daya tertanam:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 6: Render Dokumen
Render dokumen menggunakan penampil dan opsi tampilan yang dikonfigurasi:
```csharp
viewer.View(options);
```
## Langkah 7: Menampilkan Pesan Sukses
Beritahukan pengguna bahwa dokumen telah berhasil dirender:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dalam tutorial ini, kami telah mempelajari cara memuat dokumen yang dilindungi kata sandi menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, pengembang dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi .NET mereka, sehingga pengguna dapat melihat dokumen yang dilindungi dengan mudah.
## Pertanyaan yang Sering Diajukan
### Bisakah GroupDocs.Viewer menangani format dokumen lain selain dokumen yang dilindungi kata sandi?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, DOCX, XLSX, PPTX, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer menawarkan kompatibilitas dengan lingkungan .NET Framework dan .NET Core.
### Dapatkah saya menyesuaikan opsi rendering untuk dokumen?
Tentu saja! GroupDocs.Viewer menyediakan berbagai opsi rendering, yang memungkinkan pengembang untuk menyesuaikan pengalaman menonton sesuai dengan kebutuhan mereka.
### Apakah GroupDocs.Viewer mendukung anotasi dokumen?
Ya, GroupDocs.Viewer mendukung anotasi dokumen, yang memungkinkan pengguna untuk menambahkan komentar, sorotan, dan anotasi lainnya ke dokumen.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer?
Ya, Anda bisa mendapatkan uji coba gratis GroupDocs.Viewer dari [situs web](https://releases.groupdocs.com/).