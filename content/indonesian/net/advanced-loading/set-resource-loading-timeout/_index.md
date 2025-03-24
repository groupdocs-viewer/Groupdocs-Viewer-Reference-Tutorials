---
title: Tetapkan Batas Waktu Pemuatan Sumber Daya (Lanjutan)
linktitle: Tetapkan Batas Waktu Pemuatan Sumber Daya (Lanjutan)
second_title: GroupDocs.Viewer .NET API
description: Pelajari cara mengonfigurasi batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET secara efisien. Render dokumen master dengan presisi dan stabilitas.
weight: 13
url: /id/net/advanced-loading/set-resource-loading-timeout/
---
## Perkenalan
Dalam bidang pengembangan .NET, GroupDocs.Viewer menyediakan perangkat canggih untuk merender dokumen dan gambar dengan presisi dan efisiensi. Memanfaatkan kemampuannya memerlukan pemahaman seluk-beluknya, termasuk menetapkan batas waktu pemuatan sumber daya. Dalam tutorial ini, kita akan mempelajari proses mengonfigurasi batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET.
## Prasyarat
Sebelum memulai tutorial ini, pastikan Anda memiliki prasyarat berikut:
1. Pengetahuan Dasar tentang Pengembangan .NET: Keakraban dengan pemrograman C# dan dasar-dasar kerangka .NET sangat penting.
2.  Instalasi GroupDocs.Viewer untuk .NET: Unduh dan instal perpustakaan GroupDocs.Viewer untuk .NET dari[Unduh Halaman](https://releases.groupdocs.com/viewer/net/).
3. Lingkungan Pengembangan Terpadu (IDE): Miliki IDE seperti Visual Studio yang terinstal di sistem Anda.

## Impor Namespace
Sebelum mendalami proses pengkodean, impor namespace yang diperlukan:
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
 Mengganti`"Your Document Directory"`dengan jalur tempat Anda ingin menyimpan dokumen yang dirender.
## Langkah 2: Tentukan Format Jalur File Halaman
Tentukan format jalur file masing-masing halaman:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Format ini akan menghasilkan nama file seperti`page_1.html`, `page_2.html`, dll., dalam direktori keluaran yang ditentukan.
## Langkah 3: Konfigurasikan Opsi Pemuatan
Konfigurasikan opsi pemuatan, termasuk batas waktu pemuatan sumber daya:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
Dalam contoh ini, batas waktu 5 detik ditetapkan untuk pemuatan sumber daya.
## Langkah 4: Inisialisasi Objek Penampil
 Inisialisasi`Viewer` objek dengan dokumen yang akan dirender dan opsi pemuatan yang ditentukan:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Mengganti`TestFiles.WITH_EXTERNAL_IMAGE_DOC` dengan jalur ke dokumen yang ingin Anda render.
## Langkah 5: Konfigurasikan Opsi Tampilan HTML
Konfigurasikan opsi tampilan HTML untuk sumber daya yang disematkan:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Konfigurasi ini memastikan bahwa sumber daya yang disematkan seperti gambar disertakan dalam HTML yang dirender.
## Langkah 6: Render Dokumen
Render dokumen menggunakan opsi yang dikonfigurasi:
```csharp
viewer.View(options);
```
Langkah ini memulai proses rendering.
## Langkah 7: Tampilkan Direktori Output
Tampilkan pesan yang menunjukkan keberhasilan rendering dan lokasi direktori keluaran:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Kesimpulan
Menguasai batas waktu pemuatan sumber daya di GroupDocs.Viewer untuk .NET sangat penting untuk memastikan kelancaran proses rendering dokumen. Dengan mengikuti tutorial ini, Anda mendapatkan wawasan tentang cara mengonfigurasi batas waktu secara efektif, sehingga meningkatkan kemahiran Anda dalam pengembangan .NET.
## FAQ
### Apa pentingnya menetapkan batas waktu pemuatan sumber daya?
Menetapkan batas waktu pemuatan sumber daya memastikan bahwa proses rendering tidak terhenti tanpa batas waktu, sehingga meningkatkan stabilitas aplikasi.
### Bisakah batas waktu pemuatan sumber daya disesuaikan berdasarkan jenis dokumen?
Ya, batas waktu pemuatan sumber daya dapat disesuaikan berdasarkan kompleksitas dan ukuran dokumen yang dirender.
### Apakah ada implikasi kinerja jika menetapkan batas waktu yang lebih singkat?
Batas waktu yang lebih singkat dapat menyebabkan rendering dokumen kompleks menjadi tidak lengkap jika sumber daya tidak dapat dimuat dalam durasi yang ditentukan.
### Apakah GroupDocs.Viewer cocok untuk merender berbagai format dokumen?
Ya, GroupDocs.Viewer mendukung rendering berbagai format dokumen termasuk PDF, DOCX, XLSX, dan banyak lagi.
### Bisakah batas waktu pemuatan sumber daya dinonaktifkan?
Meskipun tidak disarankan, waktu tunggu pemuatan sumber daya dapat disetel ke nilai tinggi atau dinonaktifkan sama sekali bergantung pada persyaratan tertentu.