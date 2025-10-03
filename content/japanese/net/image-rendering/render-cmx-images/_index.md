---
"description": "GroupDocs.Viewer for .NET を使用して、CMX 画像をさまざまな形式に簡単にレンダリングする方法を学びましょう。ドキュメント管理を強化します。"
"linktitle": "CMXイメージのレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CMXイメージのレンダリング"
"url": "/ja/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# CMXイメージのレンダリング

## 導入
ドキュメントの管理と操作において、様々な形式から画像をレンダリングすることは極めて重要なタスクです。GroupDocs.Viewer for .NETは、CMX画像をHTML、JPG、PNG、PDFなどの様々な形式にレンダリングするための包括的な機能を提供することで、このプロセスを簡素化します。このチュートリアルでは、GroupDocs.Viewer for .NETを使用してCMX画像をレンダリングする手順を段階的に説明します。

![GroupDocs.Viewer for .NET で CMX 画像をレンダリングする](/viewer/image-rendering/render-cmx-images.png)

## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NETライブラリ: GroupDocs.Viewer for .NETライブラリを以下のサイトからダウンロードしてインストールします。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: .NET フレームワークを使用して動作する開発環境をセットアップします。
3. CMX イメージ ファイル: レンダリングする CMX イメージ ファイルを取得します。

## 名前空間のインポート
続行する前に、.NET アプリケーションで GroupDocs.Viewer 機能にアクセスするために必要な名前空間をインポートしてください。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## HTMLへのレンダリング
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- 出力ディレクトリの定義: レンダリングされた HTML ファイルを保存するディレクトリを設定します。
- ファイル パス形式の指定: 出力 HTML ファイルの形式を定義します。
- Viewer オブジェクトのインスタンス化: CMX イメージ ファイルを使用して Viewer クラスのインスタンスを作成します。
- HTML レンダリング オプション: リソースの埋め込みなどの HTML レンダリング オプションを構成します。
- CMX を HTML にレンダリングする: ビューア オブジェクトの View メソッドを呼び出して、CMX イメージを HTML にレンダリングします。
## JPGへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- 出力ディレクトリの定義: レンダリングされた JPG ファイルを保存するディレクトリを設定します。
- ファイル パス形式の指定: 出力 JPG ファイルの形式を定義します。
- Viewer オブジェクトのインスタンス化: CMX イメージ ファイルを使用して Viewer クラスのインスタンスを作成します。
- JPG レンダリング オプション: JPG レンダリング オプションを構成します。
- CMX を JPG にレンダリングする: ビューアー オブジェクトの View メソッドを呼び出して、CMX イメージを JPG にレンダリングします。
## PNGへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 出力ディレクトリの定義: レンダリングされた PNG ファイルを保存するディレクトリを設定します。
- ファイル パス形式の指定: 出力 PNG ファイルの形式を定義します。
- Viewer オブジェクトのインスタンス化: CMX イメージ ファイルを使用して Viewer クラスのインスタンスを作成します。
- PNG レンダリング オプション: PNG レンダリング オプションを構成します。
- CMX を PNG にレンダリングする: ビューアー オブジェクトの View メソッドを呼び出して、CMX イメージを PNG にレンダリングします。
## PDFへのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 出力ディレクトリの定義: レンダリングされた PDF ファイルを保存するディレクトリを設定します。
- ファイル パス形式の指定: 出力 PDF ファイルの形式を定義します。
- Viewer オブジェクトのインスタンス化: CMX イメージ ファイルを使用して Viewer クラスのインスタンスを作成します。
- PDF レンダリング オプション: PDF レンダリング オプションを構成します。
- CMX を PDF にレンダリングする: ビューアー オブジェクトの View メソッドを呼び出して、CMX イメージを PDF にレンダリングします。

## 結論
結論として、GroupDocs.Viewer for .NETは、CMX画像を様々な形式にシームレスにレンダリングするための堅牢なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、CMX画像レンダリング機能を.NETアプリケーションに簡単に統合し、ドキュメント管理の効率を向上させることができます。
## よくある質問
### CMX イメージの特定のページをレンダリングできますか?
はい、レンダリング オプションでページ番号を指定することで、特定のページをレンダリングできます。
### GroupDocs.Viewer for .NET はすべての .NET フレームワークと互換性がありますか?
はい、GroupDocs.Viewer for .NET は、.NET Core や .NET Framework を含む複数の .NET フレームワークと互換性があります。
### GroupDocs.Viewer は暗号化された CMX イメージのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer は適切な復号化キーを使用して暗号化された CMX イメージのレンダリングをサポートしています。
### さまざまな出力形式のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer は、要件に応じてレンダリング パラメータをカスタマイズするための幅広いオプションを提供します。
### GroupDocs.Viewer サポート用のコミュニティ フォーラムはありますか?
はい、サポートフォーラムでサポートを求めたり、GroupDocs.Viewerコミュニティに参加したりできます。 [ここ](https://forum。groupdocs.com/c/viewer/9).