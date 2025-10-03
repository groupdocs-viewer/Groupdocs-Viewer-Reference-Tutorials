---
"date": "2025-04-25"
"description": "Pelajari cara membagi gambar CAD besar menjadi petak secara efisien menggunakan GroupDocs.Viewer .NET, yang akan meningkatkan alur kerja desain Anda."
"title": "Cara Membagi Gambar CAD Menjadi Petak Menggunakan GroupDocs.Viewer .NET untuk Rendering yang Efisien"
"url": "/id/net/advanced-rendering/split-cad-drawings-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# Cara Membagi Gambar CAD menjadi Beberapa Petak dengan GroupDocs.Viewer .NET

## Perkenalan

Menangani gambar CAD berskala besar dalam proyek arsitektur dan teknik bisa jadi menantang. File-file ini sering kali berisi terlalu banyak detail atau terlalu besar untuk dilihat dan dinavigasi dengan mudah. Tutorial ini menunjukkan cara membagi gambar CAD menjadi petak-petak yang mudah dikelola menggunakan GroupDocs.Viewer .NET, yang memudahkan pemeriksaan bagian-bagian tertentu tanpa kehilangan detail.

![Membagi Gambar CAD menjadi Ubin di GroupDocs.Viewer untuk .NET](/viewer/advanced-rendering/split-cad-drawings-tiles-img.png)

Di akhir panduan ini, Anda akan mempelajari:
- Cara menggunakan GroupDocs.Viewer untuk membagi gambar CAD secara efisien.
- Teknik untuk menyiapkan dan mengonfigurasi GroupDocs.Viewer di proyek .NET Anda.
- Langkah-langkah praktis untuk menerapkan fitur pemisahan ubin.

Mari kita bahas bagaimana alat-alat ini dapat memperlancar alur kerja Anda. Sebelum mulai menerapkannya, pastikan Anda memiliki prasyarat yang diperlukan.

## Prasyarat

Untuk membagi gambar CAD menggunakan GroupDocs.Viewer .NET, pastikan Anda memiliki:
- **Pustaka GroupDocs.Viewer**: Tutorial ini menggunakan versi 25.3.0.
- **Lingkungan Pengembangan**: Lingkungan pengembangan .NET yang cocok seperti Visual Studio.
- **Pengetahuan Dasar C#**: Diperlukan keakraban dengan sintaksis dan konsep C#.

### Menyiapkan GroupDocs.Viewer untuk .NET

Pertama, instal pustaka GroupDocs.Viewer di proyek Anda:

**Konsol Pengelola Paket NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.KLIK NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

#### Akuisisi Lisensi
GroupDocs menawarkan lisensi percobaan dan sementara untuk pengujian, dengan opsi untuk membeli lisensi penuh.
1. **Uji Coba Gratis**: Unduh versi uji coba dari [Unduhan GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Lisensi Sementara**:Lamar di [Halaman Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/) untuk menguji tanpa batasan.
3. **Pembelian**:Kunjungi [Halaman Pembelian](https://purchase.groupdocs.com/buy) untuk mendapatkan lisensi penuh.

Inisialisasi dan atur GroupDocs.Viewer di proyek Anda:
```csharp
using System;
using GroupDocs.Viewer;

class Program
{
    static void Main()
    {
        // Inisialisasi penampil dengan jalur berkas CAD.
        using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS"))
        {
            Console.WriteLine("GroupDocs.Viewer is ready.");
        }
    }
}
```

## Panduan Implementasi

### Menyiapkan Lingkungan
Pastikan lingkungan pengembangan Anda telah disiapkan dan GroupDocs.Viewer telah diinstal. Sekarang, bagi gambar CAD menjadi petak-petak.

#### Inisialisasi Penampil dengan File CAD
Muat file CAD Anda menggunakan `Viewer` kelas:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS"))
{
    // Kode Anda di sini...
}
```
### Dapatkan Informasi Tampilan
Dapatkan informasi tampilan untuk format PNG tanpa merendernya terlebih dahulu. Ini membantu menghitung dimensi petak.
```csharp
ViewInfoOptions infoOptions = ViewInfoOptions.ForPngView(false);
var viewInfo = viewer.GetViewInfo(infoOptions);
// Dapatkan lebar dan tinggi halaman pertama.
int width = viewInfo.Pages[0].Width;
int height = viewInfo.Pages[0].Height;
```
### Hitung Dimensi Ubin
Membagi gambar menjadi empat petak yang sama dengan mengatur dimensi menjadi setengah dari ukuran gambar total.
```csharp
int tileWidth = width / 2;
int tileHeight = height / 2;
```
### Tentukan dan Tambahkan Ubin
Tentukan setiap ubin dan tambahkan ke opsi CAD. Buat empat perempat dari gambar asli:
#### Ubin Kiri Atas
Inisialisasi koordinat awal dan tentukan petak pertama.
```csharp
int pointX = 0;
int pointY = 0;
Tile tile = new Tile(pointX, pointY, tileWidth, tileHeight);
PngViewOptions options = new PngViewOptions("YOUR_OUTPUT_DIRECTORY/page_{0}.png");
options.CadOptions.Tiles.Add(tile);
```
#### Ubin Kanan Atas
Pindahkan koordinat X untuk menentukan ubin kedua.
```csharp
pointX += tileWidth;
tile = new Tile(pointX, pointY, tileWidth, tileHeight);
options.CadOptions.Tiles.Add(tile);
```
#### Ubin Kiri Bawah
Setel ulang X dan pindahkan koordinat Y untuk ubin ketiga.
```csharp
pointX = 0;
pointY += tileHeight;
tile = new Tile(pointX, pointY, tileWidth, tileHeight);
options.CadOptions.Tiles.Add(tile);
```
#### Ubin Kanan Bawah
Pindahkan koordinat X untuk menentukan ubin keempat.
```csharp
pointX += tileWidth;
tile = new Tile(pointX, pointY, tileWidth, tileHeight);
options.CadOptions.Tiles.Add(tile);
// Render gambar dengan petak yang ditentukan.
viewer.View(options);
```
### Tips Pemecahan Masalah
- Pastikan jalur file diatur dengan benar untuk mencegah pengecualian terkait dengan file atau direktori yang hilang.
- Verifikasi apakah GroupDocs.Viewer memiliki lisensi yang sesuai jika Anda menemui batasan rendering.

## Aplikasi Praktis
Membagi gambar CAD menjadi petak dapat menguntungkan dalam beberapa skenario:
1. **Ulasan Arsitektur**: Fokus pada bagian tertentu dari denah lantai yang besar tanpa detail yang berlebihan.
2. **Analisis Teknik**: Mengisolasi area untuk pemeriksaan terperinci, mengoptimalkan waktu dan sumber daya.
3. **Presentasi Klien**: Klien dapat melihat bagian yang relevan dari suatu desain, meningkatkan komunikasi.

Integrasi dengan sistem .NET lain seperti aplikasi ASP.NET atau WPF sangatlah mudah, memberikan pengalaman pengguna yang lancar.

## Pertimbangan Kinerja
Saat bekerja dengan file CAD berukuran besar, pengoptimalan kinerja adalah kuncinya:
- **Optimalkan Penggunaan Memori**Mengelola memori secara efisien untuk menangani kumpulan data besar.
- **Hanya Render Ubin yang Diperlukan**: Hindari merender semua ubin sekaligus jika tidak diperlukan segera.
- **Gunakan Struktur Data yang Efisien**: Pilih struktur data yang meminimalkan overhead dan memaksimalkan kecepatan.

## Kesimpulan
Dalam tutorial ini, Anda telah mempelajari cara membagi gambar CAD menjadi petak-petak menggunakan GroupDocs.Viewer .NET. Kemampuan ini meningkatkan kemampuan Anda untuk mengelola dan menyajikan desain berskala besar secara efisien. Sebagai langkah berikutnya, pertimbangkan untuk menjelajahi fitur-fitur lain dari pustaka GroupDocs.Viewer guna lebih mengoptimalkan proyek Anda.

Siap untuk menerapkan solusi ini? Pelajari lebih lanjut dokumentasi di [Dokumentasi GroupDocs](https://docs.groupdocs.com/viewer/net/) atau jelajahi integrasi dengan framework .NET lain untuk solusi yang lebih tangguh.

## Bagian FAQ
1. **Format file apa yang didukung GroupDocs.Viewer?**
   - Mendukung lebih dari 50 format file, termasuk file CAD seperti DWG dan DXF.
2. **Bagaimana cara menangani berkas besar secara efisien?**
   - Membagi proses rendering menjadi petak-petak yang dapat dikelola seperti ditunjukkan dalam tutorial ini.
3. **Bisakah GroupDocs.Viewer digunakan untuk pemrosesan batch?**
   - Ya, dapat dikonfigurasi untuk memproses beberapa dokumen secara berurutan atau bersamaan.
4. **Apa saja pilihan lisensi untuk GroupDocs.Viewer?**
   - Mulailah dengan uji coba gratis, ajukan lisensi sementara, atau beli lisensi penuh.
5. **Apakah ada dukungan yang tersedia jika saya mengalami masalah?**
   - Dukungan terperinci tersedia melalui [Dukungan GroupDocs](https://forum.groupdocs.com/c/viewer/9).

## Sumber daya
- [Dokumentasi](https://docs.groupdocs.com/viewer/net/)
- [Referensi API](https://reference.groupdocs.com/viewer/net/)
- [Unduh GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Beli Lisensi](https://purchase.groupdocs.com/buy)
- [Versi Uji Coba Gratis](https://releases.groupdocs.com/viewer/net/)
- [Permintaan Lisensi Sementara](https://purchase.groupdocs.com/temporary-license/)

Dengan mengikuti panduan ini, Anda akan siap menangani kerumitan file CAD berukuran besar dengan mudah. Selamat membuat kode!