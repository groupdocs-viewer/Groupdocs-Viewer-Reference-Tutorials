---
title: Visio の図をレンダリングする
linktitle: Visio の図をレンダリングする
second_title: GroupDocs.Viewer .NET API
description: この包括的な内容で、GroupDocs.Viewer for .NET を使用して Visio Figure をレンダリングする方法を学習します。 .NET アプリケーションのドキュメント表示機能を強化します。
weight: 10
url: /ja/net/rendering-visio-documents/render-visio-figures/
---
## 導入
今日のデジタル時代では、ドキュメントのレンダリングはさまざまなアプリケーションで重要な役割を果たしています。 Web サイトにドキュメントを表示する場合でも、ドキュメントを別の形式に変換する場合でも、効率的なレンダリングが不可欠です。 GroupDocs.Viewer for .NET は、.NET アプリケーション内でドキュメントを表示および操作するための堅牢なソリューションを提供します。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して Visio Figure をレンダリングする方法を詳しく説明し、プロセスを簡単な手順に分けて説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. 環境セットアップ: .NET 開発のための作業環境があることを確認してください。
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
3. C# の基本的な理解: C# プログラミング言語の基礎を理解します。
4. サンプル Visio ドキュメント: レンダリングできるサンプル Visio ドキュメントを用意します。

## 名前空間のインポート
C# プロジェクトで、必要な名前空間をインポートすることから始めます。
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
- 出力ディレクトリ: レンダリングされた HTML が保存されるディレクトリを定義します。
- ページ ファイル パス形式: HTML ページのパス形式を指定します。
- Viewer の初期化: Visio ドキュメントへのパスを使用して Viewer オブジェクトを初期化します。
- HTML 表示オプション: HTML をレンダリングするためのオプションを構成します。
- Visio レンダリング オプション: Figure や Figure の幅のみのレンダリングなど、Visio レンダリングに固有のオプションを設定します。
## 2.JPGへのレンダリング
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
## 3. PNG へのレンダリング
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
- PNG 形式にレンダリングするための構成は、JPG レンダリングと同様のパターンに従います。
## 4. PDF へのレンダリング
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
- PDF にレンダリングするには、PDF 形式に固有のオプションを設定します。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して Visio Figure をレンダリングする方法を検討しました。ステップバイステップのガイドに従うことで、ドキュメント レンダリング機能を .NET アプリケーションにシームレスに統合し、ユーザー エクスペリエンスと生産性を向上させることができます。
## よくある質問
### Visio Figure のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer for .NET は、図の幅、図のみのレンダリングなど、レンダリングをカスタマイズするための広範なオプションを提供します。
### GroupDocs.Viewer for .NET は大規模なドキュメントのレンダリングに適していますか?
確かに、GroupDocs.Viewer for .NET は、大規模なドキュメントのレンダリングを効率的に処理できるように最適化されています。
### GroupDocs.Viewer は Visio 以外の他のドキュメント形式をサポートしていますか?
はい。GroupDocs.Viewer は、PDF、Microsoft Office、AutoCAD などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer を Web アプリケーションに統合できますか?
はい、GroupDocs.Viewer は、ドキュメントの表示と操作のために Web アプリケーションにシームレスに統合できます。
### 購入前にテストできる試用版はありますか?
はい、以下から無料トライアルを利用できます。[Webサイト](https://releases.groupdocs.com/) GroupDocs.Viewer for .NET の機能をテストします。