---
"description": "GroupDocs.Viewer for .NET を使用して SVG および SVGZ 画像をレンダリングする方法を学びます。ベクターグラフィックを HTML、JPG、PNG、PDF に簡単に変換できます。"
"linktitle": "SVGおよびSVGZ画像のレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "SVGおよびSVGZ画像のレンダリング"
"url": "/ja/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# SVGおよびSVGZ画像のレンダリング

## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して SVG および SVGZ 画像をレンダリングする手順を説明します。GroupDocs.Viewer for .NET は、開発者が .NET アプリケーションでさまざまなドキュメント形式をレンダリングできるようにする強力なドキュメントレンダリング API です。SVG と SVGZ はベクターグラフィックで使用される一般的な画像形式で、GroupDocs.Viewer for .NET を使用すると、HTML、JPG、PNG、PDF などのさまざまな出力形式に簡単にレンダリングできます。

![GroupDocs.Viewer for .NET で SVG および SVGZ 画像をレンダリングする](/viewer/image-rendering/render-svg-and-svgz-images.png)

## 前提条件
始める前に、次の前提条件がインストールされ、設定されていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETをダウンロードしてインストールします。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: Visual Studio など、.NET 開発用の実用的な開発環境があることを確認します。
3. サンプル SVGZ ファイル: テスト用にサンプル SVGZ ファイルを用意しておきます。

## 名前空間のインポート
コードに進む前に、必要な名前空間をインポートしましょう。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ1: SVGZをHTMLにレンダリングする
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## ステップ2: SVGZをJPGにレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## ステップ3: SVGZをPNGにレンダリングする
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## ステップ4：SVGZをPDFに変換する
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用してSVGおよびSVGZ画像をレンダリングする方法を学びました。わずか数ステップで、SVGZ画像をHTML、JPG、PNG、PDFなどの様々な出力形式に変換し、さまざまな環境でアクセスおよび表示できるようになります。
## よくある質問
### GroupDocs.Viewer は他の画像形式をレンダリングできますか?
はい、GroupDocs.Viewer は、PNG、JPEG、BMP、TIFF、GIF など、さまざまな画像形式のレンダリングをサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework と .NET Core の両方と互換性があります。
### レンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer は広範なレンダリング オプションを提供しており、要件に応じて出力をカスタマイズできます。
### GroupDocs.Viewer にはサードパーティの依存関係が必要ですか?
いいえ、GroupDocs.Viewer はスタンドアロン API であり、ドキュメントのレンダリングにサードパーティの依存関係は必要ありません。
### テスト用に試用版はありますか?
はい、GroupDocs.Viewerの無料試用版をこちらからダウンロードできます。 [ここ](https://releases.groupdocs.com/) 購入する前にその機能を評価します。