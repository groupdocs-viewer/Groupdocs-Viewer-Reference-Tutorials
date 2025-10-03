---
"description": "GroupDocs.Viewer for .NET を使用してPDFドキュメントの画像品質を調整する方法を学びましょう。ステップバイステップのチュートリアルに従って、シームレスに統合しましょう。"
"linktitle": "PDFの画像品質を調整する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDFの画像品質を調整する"
"url": "/ja/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
type: docs
---
# PDFの画像品質を調整する

## 導入
GroupDocs.Viewer for .NETは、開発者が.NETアプリケーションにドキュメントレンダリング機能を簡単に統合できる強力なライブラリです。このライブラリの重要な機能の一つは、PDFドキュメントのレンダリング時に画質を調整できることです。このチュートリアルでは、GroupDocs.Viewer for .NETを使用して画質を調整する手順を段階的に説明します。

![GroupDocs.Viewer .NET で PDF の画像品質を調整する](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. C# プログラミングの基礎知識。
2. Visual Studio がシステムにインストールされています。
3. GroupDocs.Viewer for .NETライブラリをダウンロードしてインストールしてください。ダウンロードはこちらから。 [ここ](https://releases。groupdocs.com/viewer/net/).

## 名前空間のインポート
まず、GroupDocs.Viewer for .NET を操作するために必要な名前空間をインポートする必要があります。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
交換する `"Your Document Directory"` レンダリングされた HTML ページを保存するパスに置き換えます。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
この行は、レンダリングされた各 HTML ページのファイル パスの形式を定義します。 `{0}` ページ番号のプレースホルダーです。
## ステップ3：画質を調整する
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
交換する `"Your PDF File Path"` PDF ドキュメントへのパスを入力します。
## ステップ4: 出力パスを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
この行には、レンダリングされた HTML ページが保存されるパスが表示されます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NETを使用してPDFドキュメントをレンダリングする際の画質を調整する方法を学びました。上記の簡単な手順に従うだけで、ニーズに合わせて画質を簡単にカスタマイズできます。
## よくある質問
### PDF 以外のドキュメント形式の画像品質を調整できますか?
はい、GroupDocs.Viewer for .NET はさまざまなドキュメント形式をサポートしており、そのほとんどで画像品質を調整できます。
### 利用可能な画質オプションは何ですか?
GroupDocs.Viewer for .NET には、低、中、高品質の画像品質のオプションが用意されています。
### 調整された画質でレンダリングする前にドキュメントをプレビューする方法はありますか?
はい、GroupDocs.Viewer for .NET を使用して、さまざまな画質設定でドキュメント プレビューを生成できます。
### GroupDocs.Viewer for .NET を商用利用する場合、ライセンスは必要ですか?
はい、商用利用にはライセンスが必要です。ライセンスは以下からご購入いただけます。 [ここ](https://purchase。groupdocs.com/buy).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
GroupDocs.Viewerフォーラムからサポートを受けることができます [ここ](https://forum。groupdocs.com/c/viewer/9).