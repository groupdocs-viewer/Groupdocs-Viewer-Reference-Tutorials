---
title: Render PDF dengan Ukuran Halaman Asli
linktitle: Render PDF dengan Ukuran Halaman Asli
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET. Ikuti panduan langkah demi langkah kami dan integrasikan fungsi ini dengan lancar.
type: docs
weight: 17
url: /id/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Perkenalan
Dalam bidang pengembangan .NET, GroupDocs.Viewer menonjol sebagai alat yang ampuh untuk merender berbagai format dokumen, termasuk PDF. Salah satu persyaratan umum dalam penanganan dokumen adalah merender PDF dengan tetap mempertahankan ukuran halaman aslinya. Untuk mencapai tugas ini dengan lancar memerlukan pemahaman komprehensif tentang GroupDocs.Viewer untuk .NET dan fungsinya.
## Prasyarat
Sebelum mendalami rendering PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
 Mulailah dengan mengunduh perpustakaan GroupDocs.Viewer dari situs web. Anda dapat memperoleh perpustakaan dari yang disediakan[tautan unduhan](https://releases.groupdocs.com/viewer/net/). Ikuti petunjuk instalasi yang disediakan dalam dokumentasi untuk mengintegrasikannya ke dalam proyek .NET Anda secara efektif.
### 2. Menyiapkan Lingkungan Pengembangan
Pastikan Anda memiliki lingkungan pengembangan yang disiapkan untuk pengembangan .NET. Ini termasuk menginstal IDE yang kompatibel, seperti Visual Studio, dan pemahaman dasar pemrograman C#.
### 3. Dapatkan Dokumen PDF
Anda memerlukan contoh dokumen PDF untuk dirender dengan GroupDocs.Viewer. Anda dapat menggunakan dokumen PDF apa pun untuk tujuan pengujian. Jika Anda tidak memilikinya, Anda dapat mengunduh contoh PDF dari berbagai sumber online.

## Impor Namespace
Sebelum melanjutkan rendering PDF, penting untuk mengimpor namespace yang diperlukan ke proyek C# Anda. Langkah ini memungkinkan Anda mengakses kelas dan metode yang diperlukan dari perpustakaan GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Sekarang setelah Anda memiliki prasyarat dan namespace yang diperlukan telah diimpor, mari kita uraikan proses rendering PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET menjadi langkah-langkah sederhana:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
 Pastikan Anda menentukan direktori tempat Anda ingin menyimpan halaman yang dirender. Mengganti`"Your Document Directory"` dengan jalur direktori yang Anda inginkan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Siapkan format untuk memberi nama file halaman yang dirender. Dalam contoh ini, halaman akan disimpan sebagai gambar PNG dengan nama file dalam format`"page_1.png"`, `"page_2.png"`, dan seterusnya.
## Langkah 3: Render PDF dengan Ukuran Halaman Asli
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Buat contoh a`Viewer` objek dengan jalur ke file PDF Anda. Lalu, buat`PngViewOptions` dengan format jalur file halaman yang ditentukan. Mengatur`RenderOriginalPageSize` properti ke`true` untuk mempertahankan ukuran halaman asli saat rendering.
## Langkah 4: Tampilkan Lokasi Dokumen yang Dirender
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Cetak pesan yang menunjukkan rendering berhasil dan berikan direktori tempat halaman yang dirender disimpan.

## Kesimpulan
Merender PDF dengan ukuran halaman asli menggunakan GroupDocs.Viewer untuk .NET adalah proses yang mudah jika Anda mengikuti langkah-langkah yang diuraikan dalam tutorial ini. Dengan mengimpor namespace yang diperlukan dan mengikuti panduan langkah demi langkah, Anda dapat mengintegrasikan fungsi ini dengan lancar ke dalam aplikasi .NET Anda.
## FAQ
### Bisakah GroupDocs.Viewer merender format dokumen lain selain PDF?
Ya, GroupDocs.Viewer mendukung rendering berbagai format dokumen, termasuk Word, Excel, PowerPoint, dan lainnya.
### Apakah GroupDocs.Viewer kompatibel dengan .NET Core?
Ya, GroupDocs.Viewer kompatibel dengan lingkungan .NET Framework dan .NET Core.
### Bisakah saya menyesuaikan format keluaran halaman yang dirender?
Ya, Anda dapat menyesuaikan format keluaran dengan menyesuaikan opsi yang disediakan oleh GroupDocs.Viewer, seperti mengatur format gambar yang berbeda atau menentukan opsi rendering khusus.
### Apakah GroupDocs.Viewer menawarkan dukungan untuk rendering dokumen berbasis cloud?
Ya, GroupDocs.Viewer menyediakan API untuk rendering dokumen berbasis cloud, memungkinkan Anda merender dokumen langsung dari penyedia penyimpanan cloud.
### Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer?
 Ya, Anda dapat menjelajahi GroupDocs.Viewer dengan uji coba gratis dengan mengunjungi yang disediakan[tautan](https://releases.groupdocs.com/).