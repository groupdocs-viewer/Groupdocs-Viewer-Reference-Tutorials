---
"description": "Jelajahi proses rendering file XML SpreadSheetML yang lancar dalam berbagai format menggunakan GroupDocs.Viewer untuk .NET. Integrasikan dengan mudah ke dalam aplikasi Anda."
"linktitle": "Merender SpreadSheetML XML"
"second_title": "API Penampil GroupDocs.NET"
"title": "Merender SpreadSheetML XML"
"url": "/id/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# Merender SpreadSheetML XML

## Perkenalan
Selamat datang di dunia GroupDocs.Viewer untuk .NET! Dalam tutorial ini, kami akan memandu Anda merender file XML SpreadSheetML dengan mudah menggunakan GroupDocs.Viewer, pustaka .NET yang canggih. Baik Anda pengembang berpengalaman atau baru memulai, panduan langkah demi langkah ini akan membantu Anda mengintegrasikan rendering XML SpreadSheetML ke dalam aplikasi Anda dengan mudah.
## Prasyarat
Sebelum memulai tutorial, pastikan Anda telah menyiapkan prasyarat berikut:
- Lingkungan pengembangan dengan dukungan .NET.
- GroupDocs.Viewer untuk pustaka .NET telah terinstal. Anda dapat mengunduhnya [Di Sini](https://releases.groupdocs.com/viewer/net/).
- Pemahaman dasar tentang pemrograman C#.
## Mengimpor Ruang Nama
Mulailah dengan mengimpor namespace yang diperlukan ke dalam proyek C# Anda. Ini memastikan bahwa Anda memiliki akses ke fungsi yang disediakan oleh GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Langkah 1: Siapkan Direktori Dokumen Anda
Tentukan jalur ke direktori dokumen Anda di mana output akan disimpan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Langkah 2: Tentukan Jalur File Output
Siapkan jalur lengkap untuk file keluaran HTML, JPG, PNG, dan PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Langkah 3: Tentukan Opsi Muatan
Tentukan secara eksplisit jenis file sebagai Excel 2003 XML SpreadSheetML untuk menyajikannya secara akurat.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Langkah 4: Render ke HTML Multi-Halaman
Manfaatkan opsi tampilan HTML untuk menyajikan file XML SpreadSheetML menjadi dokumen HTML multi-halaman.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 5: Render ke JPG
Render file XML SpreadSheetML menjadi gambar JPG menggunakan opsi yang ditentukan.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 6: Render ke PNG
Demikian pula, render file menjadi gambar PNG dengan opsi yang ditentukan.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Langkah 7: Render ke PDF
Terakhir, render file XML SpreadSheetML menjadi dokumen PDF menggunakan opsi yang ditentukan.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara merender file XML SpreadSheetML menggunakan GroupDocs.Viewer untuk .NET. Tingkatkan kemampuan tampilan dokumen Anda dengan menjelajahi lebih banyak fitur dan opsi yang disediakan oleh pustaka serbaguna ini.
## Tanya Jawab Umum
### Apakah GroupDocs.Viewer kompatibel dengan format file lain?
Ya, GroupDocs.Viewer mendukung berbagai format dokumen, termasuk PDF, Word, Excel, dan banyak lagi.
### Bisakah saya menyesuaikan tampilan dokumen yang ditampilkan?
Tentu saja! GroupDocs.Viewer menawarkan berbagai opsi penyesuaian, yang memungkinkan Anda menyesuaikan output dengan kebutuhan spesifik Anda.
### Di mana saya dapat menemukan dukungan dan sumber daya tambahan?
Kunjungi [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk dukungan komunitas dan mengeksplorasi [dokumentasi](https://tutorials.groupdocs.com/viewer/net/) untuk informasi lebih rinci.
### Apakah ada uji coba gratis yang tersedia?
Ya, Anda dapat mengakses uji coba gratis [Di Sini](https://releases.groupdocs.com/).
### Bagaimana cara memperoleh lisensi sementara?
Anda bisa mendapatkan lisensi sementara [Di Sini](https://purchase.groupdocs.com/temporary-license/).