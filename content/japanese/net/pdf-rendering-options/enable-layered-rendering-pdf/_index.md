---
"description": "GroupDocs.Viewer for .NET を使用して、PDF ドキュメントで階層化レンダリングを有効にする方法を学びます。ドキュメントの表示エクスペリエンスを簡単に向上できます。"
"linktitle": "PDFでレイヤーレンダリングを有効にする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDFでレイヤーレンダリングを有効にする"
"url": "/ja/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# PDFでレイヤーレンダリングを有効にする

## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して PDF ドキュメントで階層化レンダリングを有効にするプロセスを詳しく説明します。階層化レンダリングにより、ドキュメントの表示と操作が強化され、よりインタラクティブな表示エクスペリエンスをユーザーに提供できます。

![GroupDocs.Viewer .NET で PDF の階層化レンダリングを有効にする](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: プロジェクトで GroupDocs.Viewer for .NET を使用するために必要なパッケージまたはライブラリがインストールされていることを確認してください。
2. Visual Studio: 提供されている例をコーディングおよび実行するには、システムに Visual Studio がインストールされている必要があります。
3. C# の基本的な理解: このチュートリアルでは、C# プログラミング言語の構文と概念に精通していることを前提としています。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされた出力を保存するディレクトリ パスを必ず指定してください。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
この手順では、レンダリングされた出力内の個々のページのファイル パスの形式を設定します。 `{0}` ページ番号のプレースホルダーです。
## ステップ3: レイヤーレンダリングを有効にする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
ここでは、 `Viewer` オブジェクトを作成し、処理するPDF文書を指定します。次に、 `HtmlViewOptions` 定義されたページファイルパス形式を使用します。設定により `EnableLayeredRendering` 財産に `true` で `PdfOptions`、PDF ドキュメントの階層化レンダリングを有効にします。
## ステップ4: 出力ディレクトリを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ソース ドキュメントのレンダリングが成功したことを示すメッセージを出力し、指定されたディレクトリ内の出力を確認するようユーザーに促します。

## 結論
GroupDocs.Viewer for .NET を使用してPDFドキュメントの階層化レンダリングを有効にすると、ドキュメントの表示機能が強化され、よりリッチでインタラクティブなユーザーエクスペリエンスを提供できます。このチュートリアルで説明する手順に従うことで、この機能を.NETアプリケーションにシームレスに統合できます。
## よくある質問
### PDF ドキュメントのレイヤー化レンダリングとは何ですか?
レイヤー化されたレンダリングにより、PDF ドキュメント内のさまざまなコンポーネントを分離して操作できるようになり、インタラクティブな表示と強化されたユーザー エクスペリエンスが実現します。
### レンダリングされたドキュメントの出力ディレクトリをカスタマイズできますか?
はい、要件に応じて出力のディレクトリ パスを任意に指定できます。
### GroupDocs.Viewer は PDF 以外のファイル形式もサポートしていますか?
はい、GroupDocs.Viewer は、Word、Excel、PowerPoint など、幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework と .NET Core の両方の環境と互換性があります。
### 追加のサポートや援助はどこで受けられますか?
ビューアー ライブラリに関する質問やサポートについては、GroupDocs.Viewer フォーラムをご覧ください。