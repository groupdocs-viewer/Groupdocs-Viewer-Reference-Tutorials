---
"date": "2025-04-25"
"description": "Pelajari cara mengekstrak informasi arsip secara efisien menggunakan GroupDocs.Viewer untuk .NET. Panduan ini mencakup pengaturan, contoh kode, dan aplikasi praktis."
"title": "Cara Mengambil Informasi Arsip Menggunakan GroupDocs.Viewer untuk .NET&#58; Panduan Lengkap"
"url": "/id/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
---

# Cara Mengambil Informasi Arsip Menggunakan GroupDocs.Viewer untuk .NET: Panduan Lengkap

## Perkenalan

Apakah Anda ingin mengekstrak informasi terperinci secara efisien dari file arsip seperti ZIP? Memahami strukturnya dapat menjadi hal penting untuk manajemen dokumen. Panduan ini akan menunjukkan kepada Anda cara menggunakannya **GroupDocs.Viewer untuk .NET** untuk mengambil dan menampilkan rincian lengkap tentang berkas arsip.

![Ambil Informasi Arsip dengan GroupDocs.Viewer untuk .NET](/viewer/metadata-properties/retrieve-archive-information.png)

Dalam tutorial ini, kita akan membahas:
- Menyiapkan GroupDocs.Viewer di aplikasi .NET Anda
- Mengambil informasi tampilan dari file arsip
- Menampilkan struktur folder dalam arsip

Di akhir panduan ini, Anda akan memiliki pemahaman yang kuat tentang penerapan fungsi-fungsi ini. Mari kita mulai dengan apa yang Anda butuhkan sebelum menyelami kodenya.

### Prasyarat

Pastikan Anda telah menyiapkan hal-hal berikut:

- **Perpustakaan dan Versi**: Instal GroupDocs.Viewer untuk .NET (versi 25.3.0).
- **Pengaturan Lingkungan**: Gunakan lingkungan pengembangan .NET yang sesuai seperti Visual Studio.
- **Prasyarat Pengetahuan**: Pemahaman dasar tentang C# dan penanganan file dalam aplikasi .NET.

## Menyiapkan GroupDocs.Viewer untuk .NET

Untuk menggunakan GroupDocs.Viewer untuk .NET, instal melalui NuGet Package Manager:

### Petunjuk Instalasi

**Konsol Pengelola Paket NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.KLIK NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Mendapatkan Lisensi

GroupDocs.Viewer menawarkan beberapa opsi lisensi:
- **Uji Coba Gratis**Jelajahi fungsionalitas dasar.
- **Lisensi Sementara**: Akses fitur lengkap selama evaluasi.
- **Pembelian**:Untuk penggunaan jangka panjang, pertimbangkan untuk membeli lisensi.

Setelah menginstal dan menyiapkan lisensi Anda, inisialisasi GroupDocs.Viewer di aplikasi Anda. Berikut contoh penyiapannya:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Gunakan fungsi Penampil di sini.
}
```

## Panduan Implementasi

Kami akan memecah implementasi menjadi fitur-fitur utama untuk pendekatan yang terstruktur.

### Ambil Informasi Tampilan untuk File Arsip

Memahami struktur arsip Anda sangatlah penting. Berikut cara untuk mencapainya:

#### Inisialisasi Objek Penampil

Buat contoh dari `Viewer` kelas dengan jalur file arsip Anda:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // Kode Anda untuk pemrosesan akan diletakkan di sini.
}
```

#### Dapatkan Informasi Tampilan

Ambil informasi tampilan, diformat sebagai gambar JPG:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Menampilkan Informasi Folder Root

Untuk ikhtisar yang komprehensif, cetak detail folder root:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Membaca dan Mencetak Nama Subfolder Secara Rekursif

Untuk menjelajahi subfolder dalam arsip Anda, gunakan metode rekursif ini:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Aplikasi Praktis

GroupDocs.Viewer untuk .NET dapat digunakan dalam berbagai skenario:
- **Sistem Manajemen Dokumen**: Secara otomatis mengekstrak dan menampilkan struktur arsip.
- **Platform Pengiriman Konten**: Memberikan pratinjau konten yang diarsipkan kepada pengguna.
- **Alat Analisis Data**: Menganalisis hierarki folder dalam arsip untuk wawasan bisnis.

Integrasi dengan kerangka kerja lain seperti ASP.NET atau WPF sangatlah mudah, memungkinkan penggabungan yang mulus ke dalam sistem yang sudah ada.

## Pertimbangan Kinerja

Untuk kinerja optimal:
- **Mengoptimalkan Penggunaan Sumber Daya**: Mengelola memori secara efisien dan menangani file besar.
- **Praktik Terbaik Manajemen Memori**: Buang `Viewer` objek dengan benar untuk segera membebaskan sumber daya.

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara memanfaatkan GroupDocs.Viewer for .NET untuk mengambil informasi terperinci dari berkas arsip. Menerapkan fitur-fitur ini dapat meningkatkan kemampuan pengelolaan dokumen Anda secara signifikan.

### Langkah Berikutnya

Pertimbangkan untuk menjelajahi fitur-fitur yang lebih canggih yang ditawarkan oleh GroupDocs.Viewer atau mengintegrasikannya dengan komponen lain dari aplikasi Anda. Bereksperimenlah dengan berbagai jenis file dan struktur folder yang kompleks untuk memperdalam pemahaman Anda.

## Bagian FAQ

1. **Apa tujuan dari `ViewInfoOptions`....**
   - Mengonfigurasi bagaimana Anda ingin melihat dokumen, seperti merender format tertentu seperti JPG.

2. **Bagaimana cara menangani arsip besar secara efisien?**
   - Gunakan teknik manajemen memori dan buang sumber daya dengan benar.

3. **Bisakah GroupDocs.Viewer memproses file yang dilindungi kata sandi?**
   - Ya, dengan lisensi dan konfigurasi yang benar, ia dapat menangani dokumen terenkripsi.

4. **Apakah ada batasan ukuran file arsip yang dapat diproses?**
   - Batasannya bergantung pada kapasitas memori sistem Anda; file yang lebih besar memerlukan lebih banyak sumber daya.

5. **Bagaimana cara mengintegrasikan GroupDocs.Viewer dengan aplikasi ASP.NET?**
   - Gunakan kelas Viewer dalam tindakan atau layanan pengontrol Anda, mirip dengan yang Anda lakukan dalam aplikasi konsol.

## Sumber daya

- [Dokumentasi](https://docs.groupdocs.com/viewer/net/)
- [Referensi API](https://reference.groupdocs.com/viewer/net/)
- [Unduh GroupDocs.Viewer untuk .NET](https://releases.groupdocs.com/viewer/net/)
- [Beli Lisensi](https://purchase.groupdocs.com/buy)
- [Versi Uji Coba Gratis](https://releases.groupdocs.com/viewer/net/)
- [Aplikasi Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)
- [Forum Dukungan](https://forum.groupdocs.com/c/viewer/9)