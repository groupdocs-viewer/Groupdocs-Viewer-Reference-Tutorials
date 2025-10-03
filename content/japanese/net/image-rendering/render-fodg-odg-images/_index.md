---
"description": "GroupDocs.Viewer for .NET を使用して、FODG および ODG 画像を HTML、JPG、PNG、PDF に変換する方法を学びます。ドキュメント処理を強化します。"
"linktitle": "FODGおよびODGイメージのレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "FODGおよびODGイメージのレンダリング"
"url": "/ja/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# FODGおよびODGイメージのレンダリング

## 導入
ソフトウェア開発の世界では、ドキュメント形式の効率的な処理が最も重要です。GroupDocs.Viewer for .NETは、.NETアプリケーション内でFODGおよびODG画像をレンダリングするプロセスを簡素化するために設計された強力なツールです。このチュートリアルでは、GroupDocs.Viewer for .NETを使用してこれらの画像をHTML、JPG、PNG、PDFなどの様々な形式にレンダリングするために必要な手順を詳しく説明します。

![GroupDocs.Viewer for .NET で FODG および ODG 画像をレンダリングする](/viewer/image-rendering/render-fodg-and--odg-images.png)

## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETをダウンロードしてインストールします。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. .NET Framework: システムに .NET Framework がインストールされていることを確認してください。
3. C# の基礎知識: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
実装を開始する前に、必要な名前空間をインポートします。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ1: 出力ディレクトリを設定する
```csharp
string outputDirectory = "Your Document Directory";
```
交換する `"Your Document Directory"` レンダリングされた画像を保存するディレクトリ パスに置き換えます。
## ステップ2: HTMLにレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
この手順では、FODG イメージを HTML 形式にレンダリングします。
## ステップ3: JPGにレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ここで、FODG イメージは JPG 形式でレンダリングされます。
## ステップ4: PNGにレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
この手順では、FODG イメージを PNG 形式に変換します。
## ステップ5: PDFにレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
最後に、FODG イメージは PDF 形式にレンダリングされます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、FODG および ODG 画像を様々な形式にレンダリングする方法を説明しました。これらの手順に従うことで、ドキュメントレンダリング機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### GroupDocs.Viewer for .NET は、すべてのバージョンの .NET Framework と互換性がありますか?
GroupDocs.Viewer for .NET は、最新バージョンを含む幅広い .NET Framework バージョンと互換性があります。
### GroupDocs.Viewer for .NET を使用してドキュメントを非同期にレンダリングできますか?
はい、GroupDocs.Viewer for .NET は、パフォーマンスを向上させる非同期レンダリング機能を提供します。
### GroupDocs.Viewer for .NET は暗号化されたドキュメントのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer for .NET は、適切な復号化キーを使用して暗号化されたドキュメントのレンダリングをサポートしています。
### GroupDocs.Viewer for .NET でレンダリング出力をカスタマイズすることは可能ですか?
はい、GroupDocs.Viewer for .NET には、要件に応じてレンダリング出力をカスタマイズするためのさまざまなカスタマイズ オプションが用意されています。
### GroupDocs.Viewer for .NET を使用してリモート ストレージの場所からドキュメントをレンダリングできますか?
はい、GroupDocs.Viewer for .NET は、ローカルとリモートの両方のストレージ場所からのドキュメントのレンダリングをサポートしています。