---
title: CDR イメージのレンダリング
linktitle: CDR イメージのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して CDR イメージを HTML、JPG、PNG、PDF にレンダリングする方法を学びます。このチュートリアルを使用して CorelDRAW ファイルを簡単に変換します。
weight: 12
url: /ja/net/image-rendering/render-cdr-images/
---

# CDR イメージのレンダリング

## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して CDR (CorelDRAW) イメージをレンダリングするプロセスを説明します。 CDR は、主にベクトル グラフィック エディターである CorelDRAW に関連するファイル形式です。 GroupDocs.Viewer を使用すると、CDR ファイルを HTML、JPG、PNG、PDF などのさまざまな形式に簡単に変換できます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET がインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
2. ドキュメント ディレクトリ: レンダリングされたイメージを保存するディレクトリを準備します。
3. C# の基本知識: コード例を理解するには、C# プログラミング言語に精通している必要があります。
## 名前空間のインポート
コード例に入る前に、必要な名前空間を C# ファイルにインポートします。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ここで、各例を複数のステップに分けてみましょう。
## HTMLへのレンダリング
1. レンダリングされた HTML ファイルを保存する出力ディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML ファイルのファイル パス形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Viewer クラスを使用して、CDR ファイルを HTML にレンダリングします。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPGへのレンダリング
1. JPG ファイルのファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Viewer クラスを使用して、CDR ファイルを JPG にレンダリングします。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNG へのレンダリング
1. PNG ファイルのファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Viewer クラスを使用して、CDR ファイルを PNG にレンダリングします。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PDF へのレンダリング
1. PDF のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Viewer クラスを使用して CDR ファイルを PDF にレンダリングします。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. オプションで、追加のパラメータを`viewer.View()`方法。
## 結論
GroupDocs.Viewer for .NET を使用して CDR イメージを HTML、JPG、PNG、PDF などのさまざまな形式にレンダリングするプロセスは簡単です。このチュートリアルで概説されている手順に従うことで、要件に基づいて CDR ファイルをさまざまな形式に効率的に変換できます。
## よくある質問
### GroupDocs.Viewer for .NET は、CDR ファイルのすべてのバージョンと互換性がありますか?
GroupDocs.Viewer for .NET は、さまざまなバージョンの CorelDRAW で作成された CDR ファイルのレンダリングをサポートしています。
### レンダリングされたファイルの出力をカスタマイズできますか?
はい。GroupDocs.Viewer for .NET には、画質の調整、ウォーターマークの設定など、出力をカスタマイズするためのさまざまなオプションが用意されています。
### GroupDocs.Viewer for .NET には外部依存関係が必要ですか?
いいえ、GroupDocs.Viewer for .NET はスタンドアロン ライブラリであり、ドキュメントのレンダリングに外部依存関係を必要としません。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、GroupDocs.Viewer for .NET の無料試用版を次からダウンロードできます。[ここ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
 GroupDocs.Viewer コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.groupdocs.com/c/viewer/9).