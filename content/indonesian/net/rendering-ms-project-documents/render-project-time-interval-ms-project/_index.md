---
"description": "Integrasikan GroupDocs.Viewer for .NET dengan lancar ke dalam aplikasi Anda untuk tampilan dokumen yang efisien. Tingkatkan produktivitas dengan kemampuan rendering yang serbaguna."
"linktitle": "Render Interval Waktu Proyek Tertentu (MS Project)"
"second_title": "API Penampil GroupDocs.NET"
"title": "Render Interval Waktu Proyek Tertentu (MS Project)"
"url": "/id/net/rendering-ms-project-documents/render-project-time-interval-ms-project/"
"weight": 12
---

# Render Interval Waktu Proyek Tertentu (MS Project)

## Perkenalan
Dalam bidang pengembangan perangkat lunak, penanganan dan penyajian berbagai format dokumen yang efisien merupakan hal yang terpenting. Baik untuk melihat atau memanipulasi dokumen, memiliki alat yang tepat dapat meningkatkan produktivitas dan menyederhanakan proses secara signifikan. GroupDocs.Viewer untuk .NET menonjol sebagai solusi serbaguna, yang menawarkan kepada pengembang kemampuan untuk mengintegrasikan kemampuan melihat dokumen ke dalam aplikasi .NET mereka dengan lancar.
## Prasyarat
Sebelum menyelami integrasi GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Keakraban dengan .NET Framework
Pastikan Anda memiliki pemahaman dasar tentang kerangka kerja .NET, termasuk bahasa pemrograman C# dan Visual Studio IDE.
### 2. Instalasi GroupDocs.Viewer untuk .NET
Unduh dan instal GroupDocs.Viewer untuk .NET dari [tautan unduhan](https://releases.groupdocs.com/viewer/net/)Ikuti petunjuk instalasi yang diberikan untuk menyiapkan pustaka dalam lingkungan pengembangan Anda.
### 3. Lisensi yang Sah atau Lisensi Sementara
Dapatkan lisensi yang valid dari [GrupDocs](https://purchase.groupdocs.com/buy) atau mendapatkan lisensi sementara dari [Di Sini](https://purchase.groupdocs.com/temporary-license/) untuk memanfaatkan fungsionalitas penuh GroupDocs.Viewer untuk .NET.
### 4. Contoh Dokumen
Siapkan dokumen contoh, seperti berkas MS Project, untuk menguji fungsi rendering.

## Mengimpor Ruang Nama
Gabungkan namespace yang diperlukan ke dalam proyek Anda untuk mengakses fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Mari kita uraikan contoh rendering interval waktu proyek tertentu dari file MS Project menjadi beberapa langkah:
## Langkah 1: Tentukan Direktori Output
```csharp
string outputDirectory = "Your Document Directory";
```
Tentukan direktori tempat halaman HTML yang dirender akan disimpan.
## Langkah 2: Tentukan Format Jalur File Halaman
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Mengatur format untuk jalur berkas setiap halaman HTML yang dirender.
## Langkah 3: Buat Instansiasi Objek Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
Buat contoh kelas Viewer dan teruskan jalur ke contoh berkas MS Project.
## Langkah 4: Konfigurasikan Opsi Tampilan HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Konfigurasikan opsi tampilan HTML untuk rendering, tentukan format untuk sumber daya yang tertanam.
## Langkah 5: Ambil Informasi Tampilan Manajemen Proyek
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
Ambil informasi tampilan manajemen proyek untuk menentukan tanggal mulai dan berakhirnya proyek.
## Langkah 6: Tetapkan Tanggal Mulai dan Berakhir
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
Tetapkan tanggal mulai dan berakhir untuk interval proyek yang akan diberikan.
## Langkah 7: Render Dokumen
```csharp
viewer.View(options);
```
Mulailah proses rendering dengan opsi yang ditentukan.
## Langkah 8: Menampilkan Direktori Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Beritahukan pengguna tentang keberhasilan rendering dan tampilkan direktori tempat output disimpan.

## Kesimpulan
Mengintegrasikan GroupDocs.Viewer for .NET ke dalam proyek Anda memungkinkan Anda menangani tugas tampilan dokumen secara efisien, meningkatkan pengalaman pengguna dan produktivitas. Dengan mengikuti panduan langkah demi langkah yang diberikan, Anda dapat menggabungkan fungsi rendering dokumen ke dalam aplikasi .NET Anda dengan lancar.
## Pertanyaan yang Sering Diajukan
### Apakah GroupDocs.Viewer untuk .NET kompatibel dengan semua format dokumen?
GroupDocs.Viewer untuk .NET mendukung berbagai format dokumen, termasuk Microsoft Office, PDF, CAD, dan banyak lagi.
### Bisakah saya menyesuaikan tampilan dokumen yang ditampilkan?
Ya, Anda dapat menyesuaikan berbagai aspek proses rendering, seperti tata letak halaman, pemberian tanda air, dan rotasi halaman.
### Apakah GroupDocs.Viewer untuk .NET cocok untuk aplikasi web?
Tentu saja, GroupDocs.Viewer untuk .NET dapat diintegrasikan secara mulus ke dalam aplikasi web untuk menyediakan kemampuan melihat dokumen.
### Apakah GroupDocs.Viewer untuk .NET menawarkan dukungan untuk platform seluler?
Ya, GroupDocs.Viewer untuk .NET mendukung platform seluler, memungkinkan Anda membuat aplikasi dengan fitur tampilan dokumen responsif.
### Apakah ada forum komunitas tempat saya dapat mencari bantuan dengan GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengunjungi [Forum Penampil GroupDocs](https://forum.groupdocs.com/c/viewer/9) untuk mengajukan pertanyaan, berbagi ide, dan berinteraksi dengan pengguna dan pengembang lain.