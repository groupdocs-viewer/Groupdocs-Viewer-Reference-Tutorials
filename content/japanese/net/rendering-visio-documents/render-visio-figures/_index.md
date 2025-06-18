---
"description": "この包括的なチュートリアルでは、GroupDocs.Viewer for .NET を使用して Visio の図をレンダリングする方法を学習します。.NET アプリケーションでのドキュメント表示機能を強化します。"
"linktitle": "Visioの図をレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Visioの図をレンダリングする"
"url": "/ja/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
---

# Visioの図をレンダリングする

## 導入
今日のデジタル時代において、ドキュメントのレンダリングは様々なアプリケーションにおいて重要な役割を果たしています。ウェブサイトへのドキュメントの表示でも、様々なフォーマットへの変換でも、効率的なレンダリングは不可欠です。GroupDocs.Viewer for .NETは、.NETアプリケーション内でドキュメントを表示および操作するための堅牢なソリューションを提供します。このチュートリアルでは、GroupDocs.Viewer for .NETを使用してVisioの図をレンダリングする方法を、簡単な手順に分解して詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. 環境設定: .NET 開発用の作業環境があることを確認します。
2. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETを以下のサイトからダウンロードしてインストールします。 [ダウンロードリンク](https://releases。groupdocs.com/viewer/net/).
3. C# の基本的な理解: C# プログラミング言語の基礎を理解します。
4. サンプル Visio ドキュメント: レンダリング用のサンプル Visio ドキュメントを準備します。

## 名前空間のインポート
C# プロジェクトでは、まず必要な名前空間をインポートします。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. HTMLへのレンダリング
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 出力ディレクトリ: レンダリングされた HTML を保存するディレクトリを定義します。
- ページ ファイル パス形式: HTML ページのパス形式を指定します。
- ビューアーの初期化: Visio ドキュメントへのパスを使用して Viewer オブジェクトを初期化します。
- HTML 表示オプション: HTML をレンダリングするためのオプションを構成します。
- Visio レンダリング オプション: 図のみのレンダリングや図の幅など、Visio レンダリングに固有のオプションを設定します。
## 2. JPGへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- HTML へのレンダリングと同様に、JPG 形式へのレンダリングのオプションを構成します。
## 3. PNGへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PNG 形式へのレンダリングの構成は、JPG レンダリングと同様のパターンに従います。
## 4. PDFへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PDF にレンダリングするには、PDF 形式に固有のオプションを構成します。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して Visio の図をレンダリングする方法を説明しました。ステップバイステップのガイドに従うことで、ドキュメントレンダリング機能を .NET アプリケーションにシームレスに統合し、ユーザーエクスペリエンスと生産性を向上させることができます。
## よくある質問
### Visio 図のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer for .NET には、図の幅、図のみのレンダリングなど、レンダリングをカスタマイズするための広範なオプションが用意されています。
### GroupDocs.Viewer for .NET は大規模なドキュメントのレンダリングに適していますか?
はい、GroupDocs.Viewer for .NET は、大規模なドキュメントのレンダリングを効率的に処理できるように最適化されています。
### GroupDocs.Viewer は Visio 以外のドキュメント形式をサポートしていますか?
はい、GroupDocs.Viewer は、PDF、Microsoft Office、AutoCAD など、幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer を Web アプリケーションに統合できますか?
はい、GroupDocs.Viewer は、ドキュメントの表示と操作のために Web アプリケーションにシームレスに統合できます。
### 購入前にテストできる試用版はありますか?
はい、無料トライアルをご利用いただけます。 [Webサイト](https://releases.groupdocs.com/) GroupDocs.Viewer for .NET の機能をテストします。