---
"description": "Tingkatkan aplikasi .NET Anda dengan GroupDocs.Viewer untuk tampilan dokumen yang lancar. Integrasikan fungsionalitas rendering dokumen ke dalam proyek Anda dengan mudah."
"linktitle": "Tetapkan Lisensi Terukur"
"second_title": "API Penampil GroupDocs.NET"
"title": "Tetapkan Lisensi Terukur"
"url": "/id/net/getting-started/set-metered-license/"
"weight": 12
---

# Tetapkan Lisensi Terukur

## Perkenalan
Dalam dunia pengembangan .NET, menggabungkan kemampuan tampilan dokumen yang canggih ke dalam aplikasi Anda sangat penting untuk meningkatkan pengalaman dan fungsionalitas pengguna. GroupDocs.Viewer untuk .NET menawarkan solusi yang tangguh untuk mengintegrasikan fungsionalitas tampilan dokumen ke dalam proyek .NET Anda dengan lancar. Baik Anda bekerja dengan PDF, dokumen Microsoft Office, atau berbagai format gambar, GroupDocs.Viewer menyederhanakan proses rendering dan tampilan dokumen-dokumen ini dalam aplikasi Anda.

![Tetapkan Lisensi Terukur dengan GroupDocs.Viewer untuk .NET](/viewer/getting-started/set-metered-license.png)

## Prasyarat
Sebelum terjun ke implementasi GroupDocs.Viewer untuk .NET, pastikan Anda memiliki prasyarat berikut:
### 1. Instal GroupDocs.Viewer untuk .NET
Untuk memulai, Anda perlu mengunduh dan menginstal GroupDocs.Viewer untuk .NET. Anda dapat menemukan tautan unduhannya [Di Sini](https://releases.groupdocs.com/viewer/net/)Ikuti petunjuk instalasi yang diberikan untuk menyiapkan pustaka dalam lingkungan pengembangan Anda.
### 2. Dapatkan Lisensi Terukur
Untuk menggunakan GroupDocs.Viewer for .NET, Anda perlu memperoleh lisensi terukur. Lisensi ini memungkinkan Anda untuk mengontrol dan memantau penggunaan API berdasarkan kuota yang telah ditetapkan. Ikuti langkah-langkah di bawah ini untuk menyiapkan lisensi terukur Anda:

## Mengimpor Ruang Nama
Pertama, pastikan Anda mengimpor namespace yang diperlukan untuk mengakses fungsionalitas yang disediakan oleh GroupDocs.Viewer untuk .NET:
```csharp
using System;
```

Sekarang, mari kita uraikan contoh kode yang diberikan menjadi beberapa langkah:
## Langkah 1: Nyatakan Kunci Publik dan Pribadi
Nyatakan variabel untuk menyimpan kunci publik dan privat Anda:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Pastikan untuk mengganti `"YOUR_PUBLIC_KEY"` Dan `"YOUR_PRIVATE_KEY"` dengan kunci Anda yang sebenarnya.
## Langkah 2: Tetapkan Lisensi Terukur
Periksa apakah kunci publik tersedia. Jika tidak, minta pengguna untuk menyetel kunci:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Langkah 3: Inisialisasi Objek Terukur dan Tetapkan Lisensi
Inisialisasi objek Metered dan tetapkan lisensi terukur menggunakan kunci publik dan pribadi Anda:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Langkah 4: Pesan Konfirmasi
Menampilkan pesan konfirmasi yang menunjukkan bahwa lisensi telah berhasil ditetapkan:
```csharp
Console.WriteLine("License set successfully.");
```

## Kesimpulan
Sebagai kesimpulan, GroupDocs.Viewer untuk .NET menyediakan solusi komprehensif untuk menggabungkan fungsi tampilan dokumen ke dalam aplikasi .NET Anda. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat dengan mudah menyiapkan lisensi terukur dan mulai memanfaatkan kemampuan GroupDocs.Viewer dalam proyek Anda.
## Pertanyaan yang Sering Diajukan
### T: Di mana saya dapat menemukan dokumentasi untuk GroupDocs.Viewer untuk .NET?
Anda dapat menemukan dokumentasinya [Di Sini](https://tutorials.groupdocs.com/viewer/net/).
### T: Apakah ada uji coba gratis yang tersedia untuk GroupDocs.Viewer untuk .NET?
Ya, Anda dapat mengakses uji coba gratis [Di Sini](https://releases.groupdocs.com/).
### T: Bagaimana saya bisa mendapatkan lisensi sementara untuk tujuan pengujian?
Lisensi sementara dapat diperoleh [Di Sini](https://purchase.groupdocs.com/temporary-license/).
### T: Di mana saya dapat mencari dukungan atau mengajukan pertanyaan terkait GroupDocs.Viewer untuk .NET?
Anda dapat mencari dukungan dan mengajukan pertanyaan di forum GroupDocs.Viewer [Di Sini](https://forum.groupdocs.com/c/viewer/9).
### T: Di mana saya dapat membeli lisensi untuk GroupDocs.Viewer untuk .NET?
Anda dapat membeli lisensi [Di Sini](https://purchase.groupdocs.com/buy).