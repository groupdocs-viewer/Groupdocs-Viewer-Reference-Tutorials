---
"description": "GroupDocs.Viewer for .NET を使用して、CDR 画像を HTML、JPG、PNG、PDF に変換する方法を学びます。このチュートリアルで、CorelDRAW ファイルを簡単に変換できます。"
"linktitle": "CDRイメージのレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDRイメージのレンダリング"
"url": "/ja/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# CDRイメージのレンダリング

## 導入
このチュートリアルでは、GroupDocs.Viewer for .NETを使用してCDR（CorelDRAW）画像をレンダリングする手順を説明します。CDRは、主にベクターグラフィックエディタであるCorelDRAWに関連付けられたファイル形式です。GroupDocs.Viewerを使用すると、CDRファイルをHTML、JPG、PNG、PDFなどの様々な形式に簡単に変換できます。

![GroupDocs.Viewer for .NET で CDR 画像をレンダリングする](/viewer/image-rendering/render-cdr-images.png)

## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETがインストールされていることを確認してください。こちらからダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. ドキュメント ディレクトリ: レンダリングされた画像を保存するディレクトリを準備します。
3. C# の基礎知識: コード例を理解するには、C# プログラミング言語の知識が必要です。
## 名前空間のインポート
コード例に進む前に、C# ファイルに必要な名前空間をインポートします。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ここで、各例を複数のステップに分解してみましょう。
## HTMLへのレンダリング
1. レンダリングされた HTML ファイルを保存する出力ディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML ファイルのファイル パス形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Viewer クラスを使用して CDR ファイルを HTML に変換します。
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
2. Viewer クラスを使用して CDR ファイルを JPG に変換します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNGへのレンダリング
1. PNG ファイルのファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Viewer クラスを使用して CDR ファイルを PNG に変換します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PDFへのレンダリング
1. PDF のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Viewer クラスを使用して CDR ファイルを PDF に変換します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. オプションとして、レンダリングオプションを指定したり、追加のパラメータを渡して特定のページをレンダリングしたりすることもできます。 `viewer.View()` 方法。
## 結論
GroupDocs.Viewer for .NET を使って CDR 画像を HTML、JPG、PNG、PDF などの様々な形式に変換するのは簡単です。このチュートリアルで説明する手順に従うことで、CDR ファイルを要件に応じて様々な形式に効率的に変換できます。
## よくある質問
### GroupDocs.Viewer for .NET はすべてのバージョンの CDR ファイルと互換性がありますか?
GroupDocs.Viewer for .NET は、異なるバージョンの CorelDRAW で作成された CDR ファイルのレンダリングをサポートしています。
### レンダリングされたファイルの出力をカスタマイズできますか?
はい、GroupDocs.Viewer for .NET には、画像品質の調整、透かしの設定など、出力をカスタマイズするためのさまざまなオプションが用意されています。
### GroupDocs.Viewer for .NET には外部依存関係が必要ですか?
いいえ、GroupDocs.Viewer for .NET はスタンドアロン ライブラリであり、ドキュメントのレンダリングに外部依存関係は必要ありません。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、GroupDocs.Viewer for .NETの無料試用版をこちらからダウンロードできます。 [ここ](https://releases。groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
GroupDocs.Viewerコミュニティフォーラムからサポートを受けることができます [ここ](https://forum。groupdocs.com/c/viewer/9).