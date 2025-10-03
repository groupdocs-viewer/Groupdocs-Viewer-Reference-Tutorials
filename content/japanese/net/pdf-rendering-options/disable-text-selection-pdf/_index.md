---
"description": "GroupDocs.Viewer for .NET を使用してPDF内のテキスト選択を無効にする方法を学びましょう。シームレスな統合のために、ステップバイステップガイドに従ってください。"
"linktitle": "PDF でテキスト選択を無効にする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF でテキスト選択を無効にする"
"url": "/ja/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# PDF でテキスト選択を無効にする

## 導入
GroupDocs.Viewer for .NETは、強力なドキュメントレンダリングAPIです。開発者は、このAPIを使用することで、.NETアプリケーションにドキュメント表示機能を容易に統合できます。GroupDocs.Viewerが提供する主要な機能の一つは、PDFドキュメント内のテキスト選択を無効にする機能です。この機能は、機密文書からのテキストコピーを防止し、ドキュメントのセキュリティと整合性を確保する必要があるシナリオで特に役立ちます。

![GroupDocs.Viewer .NET で PDF 内のテキスト選択を無効にする](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## 前提条件
GroupDocs.Viewer for .NET を使用して PDF でのテキスト選択を無効にする方法のステップバイステップ ガイドに進む前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NETのインストール: GroupDocs.Viewer for .NETを以下のサイトからダウンロードしてインストールしてください。 [ダウンロードリンク](https://releases。groupdocs.com/viewer/net/).
2. ドキュメントディレクトリ: ドキュメントを保存するディレクトリを用意してください。PDFドキュメントをレンダリングするには、コードスニペットでこのディレクトリを指定する必要があります。

## 名前空間のインポート
まず、GroupDocs.Viewer for .NETが提供する機能にアクセスするために必要な名前空間をインポートする必要があります。手順は以下のとおりです。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、GroupDocs.Viewer for .NET を使用して PDF ドキュメント内のテキスト選択を無効にするプロセスを複数のステップに分解してみましょう。
## ステップ1: 出力ディレクトリを指定する
```csharp
string outputDirectory = "Your Document Directory";
```
このステップでは、 `"Your Document Directory"` PDF ドキュメントが保存されているディレクトリ パスに置き換えます。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
このステップでは、レンダリングされるHTMLページのファイルパスの形式を定義します。PDFドキュメントの各ページは、連番のページを持つHTMLファイルに変換されます。
## ステップ3: テキスト選択を無効にしてPDFドキュメントをレンダリングする
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
交換する `"Path to Your PDF Document"` PDFファイルへの実際のパスを指定します。このコードスニペットは、 `Viewer` オブジェクトは、リソースを埋め込むためのHTML表示オプションを設定し、設定によってテキスト選択を無効にします。 `RenderTextAsImage` 財産に `true`。
## ステップ4: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF ドキュメントをレンダリングした後、このステップでは、レンダリングされた HTML ページが保存されるディレクトリとともに成功メッセージが表示されます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用してPDFドキュメント内のテキスト選択を無効にする方法を学習しました。ステップバイステップガイドに従うことで、この機能を.NETアプリケーションにシームレスに統合し、ドキュメントのセキュリティを確保し、ユーザーエクスペリエンスを向上させることができます。
## よくある質問
### レンダリングされた HTML ページの出力ディレクトリをカスタマイズできますか?
はい、レンダリングされた HTML ページを保存する任意のディレクトリ パスを指定できます。
### GroupDocs.Viewer for .NET は、異なるバージョンの .NET Framework と互換性がありますか?
はい、GroupDocs.Viewer for .NET は、.NET Core や .NET Framework を含むさまざまなバージョンの .NET Framework と互換性があります。
### テキスト選択を無効にすると、PDF ドキュメントの他の機能に影響しますか?
いいえ、テキスト選択を無効にしても、ユーザーがドキュメントからテキストを選択してコピーできなくなるだけです。その他の機能はそのまま残ります。
### ドキュメントをレンダリングした後で、テキスト選択を再度有効にできますか?
はい、テキスト選択を有効にするには、 `RenderTextAsImage` 財産に `false` HTML 表示オプションで。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、GroupDocs.Viewer for .NETの無料トライアルは、 [Webサイト](https://releases。groupdocs.com/).