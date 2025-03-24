---
title: SVG および SVGZ イメージのレンダリング
linktitle: SVG および SVGZ イメージのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して SVG および SVGZ 画像をレンダリングする方法を学びます。ベクター グラフィックを HTML、JPG、PNG、PDF に簡単に変換します。
weight: 16
url: /ja/net/image-rendering/render-svg-svgz-images/
---
## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して SVG および SVGZ 画像をレンダリングするプロセスを説明します。 GroupDocs.Viewer for .NET は、開発者が .NET アプリケーションでさまざまなドキュメント形式をレンダリングできるようにする強力なドキュメント レンダリング API です。 SVG と SVGZ はベクター グラフィックスに使用される一般的な画像形式であり、GroupDocs.Viewer for .NET を使用すると、それらを HTML、JPG、PNG、PDF などのさまざまな出力形式に簡単にレンダリングできます。
## 前提条件
始める前に、次の前提条件がインストールされ、セットアップされていることを確認してください。
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[ここ](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: Visual Studio などの .NET 開発用の有効な開発環境があることを確認します。
3. サンプル SVGZ ファイル: テスト用にサンプル SVGZ ファイルを用意します。

## 名前空間のインポート
コードに入る前に、必要な名前空間をインポートしましょう。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ 1: SVGZ を HTML にレンダリングする
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## ステップ 2: SVGZ を JPG にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## ステップ 3: SVGZ を PNG にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## ステップ 4: SVGZ を PDF にレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して SVG および SVGZ 画像をレンダリングする方法を学習しました。いくつかの簡単な手順で、SVGZ 画像を HTML、JPG、PNG、PDF などのさまざまな出力形式に変換し、さまざまな環境でアクセスして表示できるようにすることができます。
## よくある質問
### GroupDocs.Viewer は他の画像形式をレンダリングできますか?
はい。GroupDocs.Viewer は、PNG、JPEG、BMP、TIFF、GIF などを含むさまざまな画像形式のレンダリングをサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework と .NET Core の両方と互換性があります。
### レンダリング オプションをカスタマイズできますか?
はい。GroupDocs.Viewer には、要件に応じて出力をカスタマイズできる広範なレンダリング オプションが用意されています。
### GroupDocs.Viewer にはサードパーティの依存関係が必要ですか?
いいえ、GroupDocs.Viewer はスタンドアロン API であり、ドキュメントのレンダリングにサードパーティの依存関係を必要としません。
### テスト用に利用できる試用版はありますか?
はい、GroupDocs.Viewer の無料試用版を次からダウンロードできます。[ここ](https://releases.groupdocs.com/)購入する前にその機能を評価してください。