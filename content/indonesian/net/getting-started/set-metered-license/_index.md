---
title: Tetapkan Lisensi Terukur
linktitle: Tetapkan Lisensi Terukur
second_title: GroupDocs.Viewer .NET API
description: Tingkatkan aplikasi .NET Anda dengan GroupDocs.Viewer untuk tampilan dokumen yang lancar. Integrasikan fungsi rendering dokumen dengan mudah ke dalam proyek Anda.
type: docs
weight: 12
url: /id/net/getting-started/set-metered-license/
---
## Perkenalan
Dalam dunia pengembangan .NET, menggabungkan kemampuan melihat dokumen yang kuat ke dalam aplikasi Anda sangat penting untuk meningkatkan pengalaman dan fungsionalitas pengguna. GroupDocs.Viewer untuk .NET menawarkan solusi tangguh untuk mengintegrasikan fungsionalitas tampilan dokumen dengan lancar ke dalam proyek .NET Anda. Baik Anda bekerja dengan PDF, dokumen Microsoft Office, atau berbagai format gambar, GroupDocs.Viewer menyederhanakan proses rendering dan menampilkan dokumen-dokumen ini dalam aplikasi Anda.
## Prasyarat
Sebelum mendalami penerapan GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
 Untuk memulai, Anda harus mengunduh dan menginstal GroupDocs.Viewer untuk .NET. Anda dapat menemukan tautan unduhan[Di Sini](https://releases.groupdocs.com/viewer/net/). Ikuti petunjuk instalasi yang diberikan untuk menyiapkan perpustakaan dalam lingkungan pengembangan Anda.
### 2. Dapatkan Lisensi Terukur
Untuk menggunakan GroupDocs.Viewer untuk .NET, Anda perlu mendapatkan lisensi terukur. Lisensi ini memungkinkan Anda mengontrol dan memantau penggunaan API berdasarkan kuota yang telah ditentukan. Ikuti langkah-langkah di bawah ini untuk menyiapkan lisensi terukur Anda:

## Impor Namespace
Pertama, pastikan Anda mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET:
```csharp
using System;
```

Sekarang, mari kita uraikan kode contoh yang diberikan menjadi beberapa langkah:
## Langkah 1: Deklarasikan Kunci Publik dan Pribadi
Deklarasikan variabel untuk menyimpan kunci publik dan pribadi Anda:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Pastikan untuk mengganti`"YOUR_PUBLIC_KEY"` Dan`"YOUR_PRIVATE_KEY"` dengan kunci Anda yang sebenarnya.
## Langkah 2: Tetapkan Lisensi Terukur
Periksa apakah kunci publik disediakan. Jika tidak, minta pengguna untuk menyetel kunci:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Langkah 3: Inisialisasi Objek Terukur dan Tetapkan Lisensi
Inisialisasi objek Terukur dan atur lisensi terukur menggunakan kunci publik dan pribadi Anda:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Langkah 4: Pesan Konfirmasi
Tampilkan pesan konfirmasi yang menunjukkan bahwa lisensi telah berhasil ditetapkan:
```csharp
Console.WriteLine("License set successfully.");
```

## Kesimpulan
Kesimpulannya, GroupDocs.Viewer untuk .NET memberikan solusi komprehensif untuk menggabungkan fungsionalitas tampilan dokumen ke dalam aplikasi .NET Anda. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat dengan mudah menyiapkan lisensi terukur dan mulai memanfaatkan kemampuan GroupDocs.Viewer dalam proyek Anda.
## FAQ
### T: Di mana saya dapat menemukan dokumentasi GroupDocs.Viewer untuk .NET?
 Anda dapat menemukan dokumentasinya[Di Sini](https://reference.groupdocs.com/viewer/net/).
### T: Apakah tersedia uji coba gratis untuk GroupDocs.Viewer untuk .NET?
 Ya, Anda dapat mengakses uji coba gratis[Di Sini](https://releases.groupdocs.com/).
### T: Bagaimana cara mendapatkan lisensi sementara untuk tujuan pengujian?
 Lisensi sementara dapat diperoleh[Di Sini](https://purchase.groupdocs.com/temporary-license/).
### T: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan terkait GroupDocs.Viewer untuk .NET?
 Anda dapat mencari dukungan dan mengajukan pertanyaan di forum GroupDocs.Viewer[Di Sini](https://forum.groupdocs.com/c/viewer/9).
### T: Di mana saya dapat membeli lisensi GroupDocs.Viewer untuk .NET?
 Anda dapat membeli lisensi[Di Sini](https://purchase.groupdocs.com/buy).