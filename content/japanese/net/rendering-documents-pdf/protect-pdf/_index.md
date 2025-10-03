---
"description": "Groupdocs.Viewer for .NETを使えば、レンダリングしたPDFにパスワードを簡単に設定して保護できます。ドキュメントを安全かつ機密に保ちましょう。"
"linktitle": "レンダリングされたPDFをパスワードで保護する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "レンダリングされたPDFをパスワードで保護する"
"url": "/ja/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
type: docs
---
# レンダリングされたPDFをパスワードで保護する

## 導入
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して、レンダリングされたPDFをパスワードで保護する方法を学びます。セキュリティ対策を追加することで、PDFドキュメントへのアクセスを制御し、機密性と整合性を確保できます。
## 前提条件
始める前に、次のものがあることを確認してください。
1. Groupdocs.Viewer for .NETライブラリ: ライブラリをダウンロードしてインストールします。 [Webサイト](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用に動作する開発環境が設定されていることを確認します。

## 名前空間のインポート
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリとファイルパスを定義する
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## ステップ2: ビューアオブジェクトの初期化とセキュリティオプションの設定
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
## ステップ3: PDFの表示オプションを設定する
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## ステップ4: セキュリティオプション付きでドキュメントをレンダリングする
```csharp
    viewer.View(options);
}
```
## ステップ5: レンダリングされたドキュメントを確認する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
以下の手順に従うことで、Groupdocs.Viewer for .NET を使用してレンダリングされたPDFをパスワードで保護できます。これにより、ドキュメントのセキュリティが確保され、承認されたユーザーのみがアクセスできるようになります。

## 結論
PDFドキュメントのセキュリティ保護は、機密性と整合性の維持に不可欠です。Groupdocs.Viewer for .NETを使用すると、レンダリングされたPDFをパスワードで簡単に保護し、機密情報へのアクセスを制御できます。

## よくある質問
### 異なるレベルの権限で PDF を保護できますか?
はい、PDF をパスワードで保護しながら、表示、印刷、コピーなどに対してさまざまな権限を指定できます。
### Groupdocs.Viewer はさまざまなファイル形式と互換性がありますか?
もちろんです！Groupdocs.Viewer は、DOCX、XLSX、PPTX、PDF など、幅広いファイル形式のレンダリングをサポートしています。
### Groupdocs.Viewer を既存の .NET アプリケーションに統合できますか?
もちろんです! Groupdocs.Viewer は、.NET アプリケーションへのシームレスな統合のための API を提供し、強力なドキュメント表示機能を実現します。
### Groupdocs.Viewer はクラウド ストレージ サービスをサポートしていますか?
はい、Groupdocs.Viewer は Dropbox、Google Drive、Amazon S3 などの一般的なクラウド ストレージ サービスとの統合をサポートしており、クラウドに保存されているドキュメントをレンダリングできます。
### Groupdocs.Viewer の試用版はありますか?
はい、Groupdocs.Viewerの無料トライアル版にアクセスして使い始めることができます。 [Webサイト](https://releases。groupdocs.com/).