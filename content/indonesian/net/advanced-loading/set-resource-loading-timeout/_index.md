---
"description": "Pelajari cara mengonfigurasi batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET secara efisien. Kuasai pemrosesan dokumen dengan presisi dan stabilitas."
"linktitle": "Mengatur Batas Waktu Pemuatan Sumber Daya (Lanjutan)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Mengatur Batas Waktu Pemuatan Sumber Daya (Lanjutan)"
"url": "/id/net/advanced-loading/set-resource-loading-timeout/"
"weight": 13
---

# Mengatur Batas Waktu Pemuatan Sumber Daya (Lanjutan)

## Perkenalan
Dalam bidang pengembangan .NET, GroupDocs.Viewer menyediakan perangkat yang canggih untuk merender dokumen dan gambar dengan presisi dan efisiensi. Untuk memanfaatkan kemampuannya, diperlukan pemahaman tentang seluk-beluknya, termasuk pengaturan batas waktu pemuatan sumber daya. Dalam tutorial ini, kita akan mempelajari proses konfigurasi batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET.

![Mengatur Batas Waktu Pemuatan Sumber Daya (Lanjutan) di GroupDocs.Viewer untuk .NET](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## Prasyarat
Sebelum memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar Pengembangan .NET: Keakraban dengan pemrograman C# dan dasar-dasar kerangka .NET sangatlah penting.
2. Instalasi GroupDocs.Viewer untuk .NET: Unduh dan instal pustaka GroupDocs.Viewer untuk .NET dari [halaman unduhan](https://releases.groupdocs.com/viewer/net/).
3. Lingkungan Pengembangan Terpadu (IDE): Pasang IDE seperti Visual Studio di sistem Anda.

## Mengimpor Ruang Nama
Sebelum menyelami proses pengkodean, impor namespace yang diperlukan:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Langkah 1: Tentukan Direktori Output
Pertama, tentukan direktori tempat dokumen yang dirender akan disimpan:
```csharp
string outputDirectory = "Your Document Directory";
```
Mengganti `"Your Document Directory"` dengan jalur di mana Anda ingin menyimpan dokumen yang telah dirender.
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format untuk jalur file setiap halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Format ini akan menghasilkan nama file seperti `page_1.html`Bahasa Indonesia: `page_2.html`, dll., dalam direktori keluaran yang ditentukan.
## Langkah 3: Konfigurasikan Opsi Muat
Konfigurasikan opsi pemuatan, termasuk batas waktu pemuatan sumber daya:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Dalam contoh ini, batas waktu 5 detik ditetapkan untuk pemuatan sumber daya.
## Langkah 4: Inisialisasi Objek Penampil
Inisialisasi `Viewer` objek dengan dokumen yang akan dirender dan opsi muat yang ditentukan:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
Mengganti `TestFiles.WITH_EXTERNAL_IMAGE_DOC` dengan jalur ke dokumen yang ingin Anda render.
## Langkah 5: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML untuk sumber daya yang tertanam:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Konfigurasi ini memastikan bahwa sumber daya yang tertanam seperti gambar disertakan dalam HTML yang ditampilkan.
## Langkah 6: Render Dokumen
Render dokumen menggunakan opsi yang dikonfigurasi:
```csharp
viewer.View(options);
```
Langkah ini memulai proses rendering.
## Langkah 7: Menampilkan Direktori Output
Menampilkan pesan yang menunjukkan keberhasilan rendering dan lokasi direktori output:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Menguasai batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET sangat penting untuk memastikan proses rendering dokumen yang lancar. Dengan mengikuti tutorial ini, Anda telah memperoleh wawasan tentang cara mengonfigurasi batas waktu secara efektif, yang akan meningkatkan kemahiran Anda dalam pengembangan .NET.
## Pertanyaan yang Sering Diajukan
### Apa pentingnya pengaturan batas waktu pemuatan sumber daya?
Menetapkan batas waktu pemuatan sumber daya memastikan bahwa proses rendering tidak terhenti tanpa batas waktu, sehingga meningkatkan stabilitas aplikasi.
### Bisakah batas waktu pemuatan sumber daya disesuaikan berdasarkan jenis dokumen?
Ya, batas waktu pemuatan sumber daya dapat disesuaikan berdasarkan kompleksitas dan ukuran dokumen yang sedang dirender.
### Apakah ada implikasi kinerja dari pengaturan batas waktu yang lebih pendek?
Batas waktu yang lebih pendek dapat menyebabkan pemrosesan dokumen yang kompleks tidak tuntas jika sumber daya tidak dapat dimuat dalam durasi yang ditentukan.
### Apakah GroupDocs.Viewer cocok untuk merender berbagai format dokumen?
Ya, GroupDocs.Viewer mendukung rendering berbagai format dokumen termasuk PDF, DOCX, XLSX, dan banyak lagi.
### Bisakah batas waktu pemuatan sumber daya dinonaktifkan?
Meskipun tidak disarankan, batas waktu pemuatan sumber daya dapat ditetapkan ke nilai tinggi atau dinonaktifkan sama sekali, bergantung pada persyaratan spesifik.