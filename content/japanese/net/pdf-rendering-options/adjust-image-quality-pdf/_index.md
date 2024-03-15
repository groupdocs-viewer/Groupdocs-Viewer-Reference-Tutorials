---
title: PDFの画質を調整する
linktitle: PDFの画質を調整する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して PDF ドキュメントの画質を調整する方法を学びます。シームレスな統合については、段階的なチュートリアルに従ってください。
type: docs
weight: 10
url: /ja/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## 導入
GroupDocs.Viewer for .NET は、開発者がドキュメント レンダリング機能を .NET アプリケーションに簡単に統合できるようにする強力なライブラリです。このライブラリの重要な機能の 1 つは、PDF ドキュメントをレンダリングするときに画質を調整できることです。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して画質を調整するプロセスを段階的に説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. C# プログラミングの基本的な知識。
2. Visual Studio がシステムにインストールされている。
3. GroupDocs.Viewer for .NET ライブラリがダウンロードされ、インストールされました。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).

## 名前空間のインポート
まず、GroupDocs.Viewer for .NET を操作するために必要な名前空間をインポートする必要があります。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
交換する`"Your Document Directory"`レンダリングされた HTML ページを保存するパスを指定します。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
この行は、レンダリングされる各 HTML ページのファイル パスの形式を定義します。`{0}`はページ番号のプレースホルダーです。
## ステップ 3: 画質を調整する
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
交換する`"Your PDF File Path"`PDF ドキュメントへのパスを含めます。
## ステップ 4: 出力パスを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
この行には、レンダリングされた HTML ページが保存されるパスが表示されます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して PDF ドキュメントをレンダリングするときに画質を調整する方法を学習しました。上記の簡単な手順に従うことで、要件に応じて画質を簡単にカスタマイズできます。
## よくある質問
### PDF 以外のドキュメント形式の画質を調整できますか?
はい、GroupDocs.Viewer for .NET はさまざまなドキュメント形式をサポートしており、ほとんどの形式で画質を調整できます。
### 利用可能な画質オプションは何ですか?
GroupDocs.Viewer for .NET には、低、中、高の画質のオプションが用意されています。
### 調整された画質でドキュメントをレンダリングする前にドキュメントをプレビューする方法はありますか?
はい、GroupDocs.Viewer for .NET を使用して、さまざまな画質設定でドキュメント プレビューを生成できます。
### GroupDocs.Viewer for .NET を商用利用するにはライセンスが必要ですか?
はい、商用利用するにはライセンスを取得する必要があります。ライセンスは以下から購入できます[ここ](https://purchase.groupdocs.com/buy).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
GroupDocs.Viewer フォーラムからサポートを受けることができます[ここ](https://forum.groupdocs.com/c/viewer/9).