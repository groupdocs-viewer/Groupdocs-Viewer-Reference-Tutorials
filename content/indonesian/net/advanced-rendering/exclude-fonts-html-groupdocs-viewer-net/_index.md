---
"date": "2025-04-25"
"description": "Pelajari cara mengecualikan font seperti Arial dari konversi HTML menggunakan GroupDocs.Viewer untuk .NET, memastikan pencitraan merek yang konsisten di seluruh platform."
"title": "Cara Mengecualikan Font Tertentu dari Output HTML Menggunakan GroupDocs.Viewer untuk .NET"
"url": "/id/net/advanced-rendering/exclude-fonts-html-groupdocs-viewer-net/"
"weight": 1
---

# Cara Mengecualikan Font dari Output HTML Menggunakan GroupDocs.Viewer untuk .NET

## Perkenalan

Saat mengonversi dokumen ke format HTML, mempertahankan kontrol atas font yang digunakan sangatlah penting, terutama untuk konsistensi merek. Tutorial ini menunjukkan kepada Anda cara mengecualikan font tertentu, seperti Arial, menggunakan GroupDocs.Viewer untuk .NET. Dengan mengikuti panduan ini, Anda akan mempelajari cara-cara yang efisien untuk mengelola rendering font dalam transformasi dokumen ke HTML.

![Kecualikan Font Tertentu dari Output HTML di GroupDocs.Viewer untuk .NET](/viewer/advanced-rendering/exclude-specific-fonts-from-html-output-img.png)

### Apa yang Akan Anda Pelajari:
- Menyiapkan dan mengonfigurasi GroupDocs.Viewer untuk .NET
- Teknik untuk mengecualikan font tertentu dari output HTML
- Tips praktis untuk mengoptimalkan kinerja dan integrasi dengan sistem .NET lainnya
- Aplikasi nyata dari teknik ini

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:
- **Perpustakaan & Versi**: GroupDocs.Viewer versi 25.3.0 atau yang lebih baru.
- **Pengaturan Lingkungan**: Lingkungan pengembangan yang disiapkan dengan .NET Framework atau .NET Core.
- **Prasyarat Pengetahuan**Pemahaman dasar tentang pengembangan C# dan .NET.

## Menyiapkan GroupDocs.Viewer untuk .NET

### Petunjuk Instalasi:

**Menggunakan Konsol Manajer Paket NuGet:**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Menggunakan .NET CLI:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Akuisisi Lisensi:
Anda dapat memperoleh uji coba gratis atau membeli lisensi dari [Halaman pembelian GroupDocs](https://purchase.groupdocs.com/buy)Untuk akses sementara, pertimbangkan untuk mengajukan permohonan [lisensi sementara](https://purchase.groupdocs.com/temporary-license/).

### Inisialisasi dan Pengaturan Dasar:

Berikut cara menginisialisasi GroupDocs.Viewer di proyek .NET Anda:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}

using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Konfigurasi Anda akan berada di sini
}
```
Pengaturan ini memastikan Anda siap untuk memanipulasi rendering dokumen dengan GroupDocs.Viewer.

## Panduan Implementasi

### Mengecualikan Font dari Output HTML

Di bagian ini, kami akan fokus pada cara mengecualikan font tertentu dari keluaran HTML Anda menggunakan GroupDocs.Viewer untuk .NET. 

#### Langkah 1: Persiapkan Lingkungan Anda
Pastikan direktori keluaran ada dan diatur dengan benar:
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}
```
Langkah ini memastikan bahwa berkas yang Anda render memiliki lokasi yang ditentukan.

#### Langkah 2: Konfigurasikan Opsi Tampilan HTML
Berikut cara mengonfigurasi penampil untuk mengeluarkan file HTML sumber daya yang tertanam:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Itu `HtmlViewOptions` Objek sangat penting untuk menentukan bagaimana dokumen Anda ditampilkan dalam HTML.

#### Langkah 3: Kecualikan Font Tertentu
Untuk mengecualikan font Arial, ubah `options` konfigurasi:
```csharp
options.FontsToExclude.Add("Arial");
```
Baris ini memberitahu GroupDocs.Viewer untuk menghilangkan Arial dari font apa pun yang disematkan dalam HTML keluaran. Dengan menentukan `FontsToExclude`, Anda memperoleh kendali atas bagaimana gaya visual dokumen Anda dipertahankan di berbagai lingkungan.

#### Langkah 4: Render Dokumen
Terakhir, render dokumen Anda dengan pengaturan berikut:
```csharp
viewer.View(options);
```
Dengan menyebut `View()`, GroupDocs.Viewer memproses dokumen Anda sesuai dengan opsi yang ditentukan dan mengeluarkannya ke dalam format HTML tanpa font yang dikecualikan.

### Tips Pemecahan Masalah
- Pastikan jalur berkas telah diatur dengan benar.
- Verifikasi bahwa Anda menggunakan versi GroupDocs.Viewer yang kompatibel untuk .NET.
- Periksa kembali nama font karena harus sama persis, termasuk pengaturan huruf besar/kecil.

## Aplikasi Praktis

### Kasus Penggunaan:
1. **Branding yang Konsisten**Kecualikan font yang tidak diinginkan untuk memastikan tipografi merek Anda tetap konsisten di semua platform.
2. **Integrasi Web**: Integrasikan dengan sistem CMS yang memerlukan font khusus untuk konsistensi desain web.
3. **Pengarsipan Dokumen**: Arsipkan dokumen dalam format HTML tanpa font yang asing, kurangi ukuran file.

### Kemungkinan Integrasi:
- Manfaatkan GroupDocs.Viewer dalam aplikasi .NET untuk membuat solusi tampilan dokumen kustom.
- Kombinasikan dengan kerangka kerja seperti ASP.NET MVC atau Blazor untuk rendering dokumen dinamis di web.

## Pertimbangan Kinerja

Mengoptimalkan kinerja sangat penting saat menangani dokumen berukuran besar. Berikut beberapa kiatnya:

- **Manajemen Sumber Daya**:Perhatikan penggunaan memori aplikasi Anda, terutama dengan file besar.
- **Pemrosesan Batch**: Jika berlaku, proses dokumen secara berkelompok untuk menghindari kewalahannya sumber daya sistem.
- **Caching yang Efisien**:Terapkan strategi caching untuk dokumen yang sering diakses.

## Kesimpulan

Dalam tutorial ini, kami mempelajari cara menggunakan GroupDocs.Viewer for .NET untuk mengecualikan font tertentu dari output HTML. Dengan mengikuti langkah-langkah ini, Anda dapat mempertahankan kontrol atas tampilan visual dokumen yang dikonversi. 

Untuk eksplorasi lebih lanjut, pertimbangkan untuk mengintegrasikan fitur-fitur lebih canggih yang disediakan oleh GroupDocs.Viewer atau menjelajahi kemampuan API lengkapnya.

## Bagian FAQ

**Q1: Bisakah saya mengecualikan beberapa font sekaligus?**
Ya, cukup telepon saja `options.FontsToExclude.Add("FontName")` untuk setiap font yang ingin Anda kecualikan.

**Q2: Apa yang terjadi jika font yang ditentukan tidak ditemukan dalam dokumen?**
GroupDocs.Viewer akan mengabaikannya dan melanjutkan rendering dengan font yang tersedia.

**Q3: Apakah ada batasan berapa banyak font yang dapat saya kecualikan?**
Tidak ada batasan khusus, tetapi pertimbangkan implikasi kinerja saat mengecualikan sejumlah besar font.

**Q4: Dapatkah fitur ini digunakan dengan format output lain seperti PDF atau gambar?**
GroupDocs.Viewer mendukung berbagai format, tetapi spesifikasi pengecualian font mungkin berbeda-beda. Lihat dokumentasi untuk detailnya.

**Q5: Bagaimana cara menangani berbagai jenis dokumen menggunakan GroupDocs.Viewer?**
Pustaka ini serbaguna dan mendukung berbagai format file secara native. Periksa referensi API untuk fitur yang didukung per format.

## Sumber daya
- **Dokumentasi**: [Dokumentasi Penampil GroupDocs .NET](https://docs.groupdocs.com/viewer/net/)
- **Referensi API**: [Referensi API GroupDocs](https://reference.groupdocs.com/viewer/net/)
- **Unduh**: [Unduhan GroupDocs](https://releases.groupdocs.com/viewer/net/)
- **Pembelian**: [Beli Lisensi GroupDocs](https://purchase.groupdocs.com/buy)
- **Uji Coba Gratis**: [Dapatkan Uji Coba Gratis](https://releases.groupdocs.com/viewer/net/)
- **Lisensi Sementara**: [Minta Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- **Mendukung**: [Forum Dukungan GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Siap untuk membawa proyek rendering dokumen Anda ke tingkat berikutnya? Cobalah menerapkan solusi ini hari ini!