---
title: レンダリングされた PDF をパスワードで保護する
linktitle: レンダリングされた PDF をパスワードで保護する
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を使用して、レンダリングされた PDF をパスワードで簡単に保護します。文書を安全かつ機密に保ちます。
type: docs
weight: 12
url: /ja/net/rendering-documents-pdf/protect-pdf/
---
## 導入
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して、レンダリングされた PDF をパスワードで保護する方法を学習します。セキュリティ対策を追加することで、PDF ドキュメントへのアクセスを制御し、機密性と整合性を確保できます。
## 前提条件
始める前に、次のものが揃っていることを確認してください。
1.  Groupdocs.Viewer for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Webサイト](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用に動作する開発環境がセットアップされていることを確認してください。

## 名前空間のインポート
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリとファイル パスを定義する
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## ステップ 2: Viewer オブジェクトを初期化し、セキュリティ オプションを設定する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## ステップ 3: PDF 表示オプションを設定する
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## ステップ 4: セキュリティ オプションを使用してドキュメントをレンダリングする
```csharp
    viewer.View(options);
}
```
## ステップ 5: レンダリングされたドキュメントを確認する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
次の手順に従って、Groupdocs.Viewer for .NET を使用して、レンダリングされた PDF をパスワードで保護できます。これにより、ドキュメントの安全性が確保され、許可されたユーザーのみがアクセスできるようになります。

## 結論
PDF ドキュメントを保護することは、機密性と完全性を維持するために不可欠です。 Groupdocs.Viewer for .NET を使用すると、レンダリングされた PDF をパスワードで簡単に保護し、機密情報へのアクセスを制御できます。

## よくある質問
### さまざまなレベルの権限で PDF を保護できますか?
はい、PDF をパスワードで保護しながら、表示、印刷、コピーなどに対してさまざまな権限を指定できます。
### Groupdocs.Viewer はさまざまなファイル形式と互換性がありますか?
絶対に！ Groupdocs.Viewer は、DOCX、XLSX、PPTX、PDF などを含む幅広いファイル形式のレンダリングをサポートします。
### Groupdocs.Viewer を既存の .NET アプリケーションに統合できますか?
確かに！ Groupdocs.Viewer は、.NET アプリケーションにシームレスに統合するための API を提供し、堅牢なドキュメント表示機能を提供します。
### Groupdocs.Viewer はクラウド ストレージ サービスをサポートしていますか?
はい。Groupdocs.Viewer は、Dropbox、Google Drive、Amazon S3 などの一般的なクラウド ストレージ サービスとの統合をサポートしており、クラウドに保存されているドキュメントをレンダリングできます。
### Groupdocs.Viewer の試用版はありますか?
はい、Groupdocs.Viewer の使用を開始するには、[Webサイト](https://releases.groupdocs.com/).