---
title: FODG および ODG イメージのレンダリング
linktitle: FODG および ODG イメージのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、FODG および ODG 画像を HTML、JPG、PNG、PDF にレンダリングする方法を学びます。文書処理を強化します。
weight: 15
url: /ja/net/image-rendering/render-fodg-odg-images/
---
## 導入
ソフトウェア開発の世界では、ドキュメント形式を効率的に処理することが最も重要です。 GroupDocs.Viewer for .NET は、.NET アプリケーション内で FODG および ODG イメージをレンダリングするプロセスを簡素化するように設計された強力なツールです。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、これらの画像を HTML、JPG、PNG、PDF などのさまざまな形式にレンダリングするために必要な手順を説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[ここ](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: システムに .NET Framework がインストールされていることを確認してください。
3. C# の基本的な知識: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
実装を始める前に、必要な名前空間をインポートします。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ 1: 出力ディレクトリを設定する
```csharp
string outputDirectory = "Your Document Directory";
```
交換する`"Your Document Directory"`レンダリングされたイメージを保存するディレクトリ パスを指定します。
## ステップ 2: HTML にレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
このステップでは、FODG 画像を HTML 形式にレンダリングします。
## ステップ 3: JPG にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ここでは、FODG 画像が JPG 形式にレンダリングされます。
## ステップ 4: PNG にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
この手順では、FODG 画像を PNG 形式に変換します。
## ステップ 5: PDF にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
最後に、FODG 画像が PDF 形式にレンダリングされます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して FODG および ODG イメージをさまざまな形式にレンダリングする方法を検討しました。これらの手順に従うことで、ドキュメント レンダリング機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### GroupDocs.Viewer for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?
GroupDocs.Viewer for .NET は、最新バージョンを含む幅広い .NET Framework バージョンと互換性があります。
### GroupDocs.Viewer for .NET を使用してドキュメントを非同期的にレンダリングできますか?
はい。GroupDocs.Viewer for .NET は、パフォーマンスを向上させるための非同期レンダリング機能を提供します。
### GroupDocs.Viewer for .NET は、暗号化されたドキュメントのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer for .NET は、適切な復号キーを使用した暗号化されたドキュメントのレンダリングをサポートしています。
### GroupDocs.Viewer for .NET を使用してレンダリング出力をカスタマイズすることはできますか?
確かに、GroupDocs.Viewer for .NET は、要件に応じてレンダリング出力を調整するためのさまざまなカスタマイズ オプションを提供します。
### GroupDocs.Viewer for .NET を使用して、リモート ストレージの場所からドキュメントをレンダリングできますか?
はい、GroupDocs.Viewer for .NET は、ローカルとリモートの両方のストレージ場所からのドキュメントのレンダリングをサポートしています。