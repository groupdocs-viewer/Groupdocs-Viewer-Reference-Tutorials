---
"description": "Temukan cara merender dokumen ke JPG/PNG di .NET dengan mudah menggunakan GroupDocs.Viewer untuk meningkatkan pengalaman pengguna dan produktivitas."
"linktitle": "Render Dokumen ke JPGPNG"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Dokumen ke JPGPNG"
"url": "/id/net/rendering-documents-images/render-jpg-png/"
"weight": 10
---

# Render Dokumen ke JPGPNG

## Perkenalan

Dalam dunia pengembangan .NET, penanganan dokumen secara efisien sangat penting untuk berbagai aplikasi. Baik Anda sedang membangun sistem manajemen dokumen, platform e-commerce, atau aplikasi yang kaya konten, kemampuan untuk melihat dokumen dengan lancar sangatlah penting. Di sinilah GroupDocs.Viewer untuk .NET berperan, menawarkan solusi komprehensif untuk merender dokumen ke berbagai format seperti JPG dan PNG.

## Prasyarat

Sebelum mulai menggunakan GroupDocs.Viewer untuk .NET, ada beberapa prasyarat yang perlu Anda pastikan:

1. Lingkungan Pengembangan .NET: Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi di komputer Anda. Ini termasuk menginstal .NET SDK.

2. Lisensi GroupDocs.Viewer: Dapatkan lisensi yang valid untuk GroupDocs.Viewer. Anda dapat membeli lisensi atau menggunakan lisensi sementara untuk tujuan evaluasi.

3. Instalasi: Unduh dan instal GroupDocs.Viewer untuk .NET dari sumber yang disediakan. [tautan unduhan](https://releases.groupdocs.com/viewer/net/).

4. Berkas Dokumen: Siapkan berkas dokumen yang ingin Anda tampilkan. GroupDocs.Viewer mendukung berbagai format termasuk DOCX, PDF, PPT, dan banyak lagi.

## Mengimpor Ruang Nama

Untuk memulai rendering dokumen menggunakan GroupDocs.Viewer for .NET, Anda perlu mengimpor namespace yang diperlukan ke dalam proyek Anda. Ini memungkinkan Anda untuk mengakses fungsionalitas yang disediakan oleh pustaka.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Mengubah dokumen ke format JPG atau PNG merupakan proses yang mudah dengan GroupDocs.Viewer untuk .NET. Berikut adalah panduan langkah demi langkah untuk membantu Anda mencapainya:

## Langkah 1: Tentukan Direktori Output

Pertama, tentukan direktori tempat Anda ingin menyimpan halaman yang telah dirender. Direktori ini harus ada dan dapat diakses oleh aplikasi.

```csharp
string outputDirectory = "Your Document Directory";
```

## Langkah 2: Tentukan Format Jalur File Halaman

Tentukan format untuk jalur file setiap halaman yang ditampilkan. GroupDocs.Viewer akan menggantikan `{0}` dengan nomor halaman saat menyimpan file.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Langkah 3: Buat Instansiasi Objek Viewer

Buat contoh dari `Viewer` kelas dengan menyediakan jalur ke berkas dokumen yang ingin Anda render.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Kode untuk rendering ada di sini
}
```

## Langkah 4: Tentukan Opsi Rendering

Tentukan opsi rendering sesuai dengan kebutuhan Anda. Untuk rendering JPG/PNG, Anda akan menggunakan `JpgViewOptions` atau `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Langkah 5: Render Dokumen

Memanggil `View` metode dari `Viewer` objek dan meneruskan opsi rendering yang dibuat sebelumnya.

```csharp
viewer.View(options);
```

## Langkah 6: Hasil Keluaran

Setelah proses rendering selesai, Anda dapat memberi tahu pengguna tentang keberhasilan rendering dan memberikan direktori tempat halaman yang dirender disimpan.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan

Sebagai kesimpulan, GroupDocs.Viewer untuk .NET menawarkan solusi yang hebat untuk merender dokumen ke berbagai format, termasuk JPG dan PNG. Dengan mengikuti langkah-langkah yang diuraikan dalam tutorial ini, Anda dapat mengintegrasikan fungsionalitas rendering dokumen ke dalam aplikasi .NET Anda dengan lancar, sehingga meningkatkan pengalaman pengguna dan produktivitas.

## Pertanyaan yang Sering Diajukan

### T: Dapatkah saya merender dokumen selain DOCX menggunakan GroupDocs.Viewer untuk .NET?

A: Ya, GroupDocs.Viewer mendukung berbagai format dokumen termasuk PDF, PPT, XLS, dan banyak lagi.

### T: Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?

A: Ya, Anda dapat mengunduh uji coba gratis dari [Di Sini](https://releases.groupdocs.com/).

### T: Bagaimana saya bisa mendapatkan lisensi sementara untuk tujuan evaluasi?

A: Anda dapat meminta lisensi sementara dari [Di Sini](https://purchase.groupdocs.com/temporary-license/).

### T: Di mana saya dapat menemukan dokumentasi untuk GroupDocs.Viewer untuk .NET?

A: Dokumentasi terperinci tersedia [Di Sini](https://tutorials.groupdocs.com/viewer/net/).

### T: Di mana saya bisa mendapatkan dukungan atau mengajukan pertanyaan terkait GroupDocs.Viewer untuk .NET?

A: Anda dapat mengunjungi forum dukungan [Di Sini](https://forum.groupdocs.com/c/viewer/9) untuk bantuan.