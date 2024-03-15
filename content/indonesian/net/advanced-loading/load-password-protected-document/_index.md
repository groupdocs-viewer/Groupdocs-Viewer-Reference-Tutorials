---
title: Muat Dokumen yang Dilindungi Kata Sandi
linktitle: Muat Dokumen yang Dilindungi Kata Sandi
second_title: GroupDocs.Viewer .NET API
description: Integrasikan tampilan dokumen yang dilindungi kata sandi dengan mudah ke dalam aplikasi .NET menggunakan GroupDocs.Viewer untuk .NET. Ikuti tutorial langkah demi langkah kami agar lancar.
type: docs
weight: 12
url: /id/net/advanced-loading/load-password-protected-document/
---
## Perkenalan
Di era digital saat ini, mengelola dan melihat berbagai format dokumen dengan lancar merupakan kebutuhan bagi banyak bisnis dan individu. Untungnya, GroupDocs.Viewer untuk .NET memberikan solusi komprehensif bagi pengembang .NET untuk dengan mudah mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi mereka. Dalam tutorial ini, kita akan mempelajari salah satu fungsi penting GroupDocs.Viewer: memuat dokumen yang dilindungi kata sandi. Kami akan menguraikan prosesnya langkah demi langkah, memastikan bahwa pengembang dapat dengan mudah mengikuti dan menerapkan fitur ini ke dalam proyek mereka.
## Prasyarat
Sebelum kita mendalami tutorialnya, pastikan Anda telah menyiapkan prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
 Pastikan Anda telah menginstal GroupDocs.Viewer untuk .NET di lingkungan pengembangan Anda. Anda dapat mengunduhnya dari[situs web](https://releases.groupdocs.com/viewer/net/).
### 2. Dapatkan Dokumen yang Dilindungi Kata Sandi
Untuk tujuan pengujian, sediakan dokumen yang dilindungi kata sandi. Ini akan memungkinkan kami mendemonstrasikan proses pemuatan secara efektif.

## Impor Namespace
Sebelum kita melanjutkan tutorial, mari impor namespace yang diperlukan ke proyek kita:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Pertama, tentukan direktori tempat Anda ingin menyimpan keluaran yang dirender:
```csharp
string outputDirectory = "Your Document Directory";
```
 Mengganti`"Your Document Directory"` dengan jalur direktori yang Anda inginkan.
## Langkah 2: Tentukan Format Jalur File Halaman
Selanjutnya, tentukan format jalur file setiap halaman yang dirender:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Format ini akan menghasilkan jalur file seperti`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, dan seterusnya.
## Langkah 3: Konfigurasikan Opsi Pemuatan
Konfigurasikan opsi pemuatan untuk dokumen yang dilindungi kata sandi, termasuk kata sandi:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
 Mengganti`"12345"` dengan kata sandi sebenarnya dari dokumen Anda.
## Langkah 4: Inisialisasi Penampil
Inisialisasi GroupDocs.Viewer dengan opsi dokumen dan muat:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Kode untuk opsi tampilan akan ditambahkan pada langkah berikutnya.
}
```
 Mengganti`"Path_to_your_document"` dengan jalur ke dokumen Anda yang dilindungi kata sandi.
## Langkah 5: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML untuk merender dokumen dengan sumber daya yang disematkan:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Langkah 6: Render Dokumen
Render dokumen menggunakan penampil dan opsi tampilan yang dikonfigurasi:
```csharp
viewer.View(options);
```
## Langkah 7: Tampilkan Pesan Sukses
Beri tahu pengguna bahwa dokumen telah berhasil dirender:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Dalam tutorial ini, kita telah menjelajahi cara memuat dokumen yang dilindungi kata sandi menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan langkah demi langkah, pengembang dapat dengan mudah mengintegrasikan fungsi ini ke dalam aplikasi .NET mereka, memungkinkan pengguna untuk melihat dokumen yang dilindungi dengan mudah.
## FAQ
### Bisakah GroupDocs.Viewer menangani format dokumen lain selain dokumen yang dilindungi kata sandi?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, DOCX, XLSX, PPTX, dan banyak lagi.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer menawarkan kompatibilitas dengan lingkungan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan opsi rendering dokumen?
Sangat! GroupDocs.Viewer menyediakan berbagai opsi rendering, memungkinkan pengembang untuk menyesuaikan pengalaman menonton sesuai dengan kebutuhan mereka.
### Apakah GroupDocs.Viewer mendukung anotasi dokumen?
Ya, GroupDocs.Viewer mendukung anotasi dokumen, memungkinkan pengguna menambahkan komentar, sorotan, dan anotasi lainnya ke dokumen.
### Apakah ada versi uji coba yang tersedia untuk GroupDocs.Viewer?
 Ya, Anda dapat memperoleh uji coba gratis GroupDocs.Viewer dari[situs web](https://releases.groupdocs.com/).