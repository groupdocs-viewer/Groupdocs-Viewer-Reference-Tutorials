---
title: CMX イメージのレンダリング
linktitle: CMX イメージのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、CMX イメージをさまざまな形式に簡単にレンダリングする方法を学びます。文書管理を強化します。
type: docs
weight: 13
url: /ja/net/image-rendering/render-cmx-images/
---
## 導入
ドキュメントの管理と操作の分野では、さまざまな形式の画像をレンダリングすることが極めて重要なタスクです。 GroupDocs.Viewer for .NET は、CMX 画像を HTML、JPG、PNG、PDF などのさまざまな形式にレンダリングするための包括的な機能を提供することで、このプロセスを簡素化します。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して CMX イメージをレンダリングするプロセスを段階的に説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  GroupDocs.Viewer for .NET ライブラリ: GroupDocs.Viewer for .NET ライブラリを次からダウンロードしてインストールします。[ここ](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: .NET Framework を使用してセットアップされた実用的な開発環境を用意します。
3. CMX イメージ ファイル: レンダリングする CMX イメージ ファイルを取得します。

## 名前空間のインポート
続行する前に、.NET アプリケーションの GroupDocs.Viewer 機能にアクセスするために必要な名前空間を必ずインポートしてください。
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
- HTML レンダリング オプション: 埋め込みリソースなどの HTML レンダリング オプションを構成します。
- CMX を HTML にレンダリング: ビューア オブジェクトの View メソッドを呼び出して、CMX イメージを HTML にレンダリングします。
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
- CMX を JPG にレンダリング: ビューア オブジェクトの View メソッドを呼び出して、CMX イメージを JPG にレンダリングします。
## PNG へのレンダリング
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 出力ディレクトリの定義: レンダリングされた PNG ファイルを保存するディレクトリを設定します。
- ファイル パス形式を指定: 出力 PNG ファイルの形式を定義します。
- Viewer オブジェクトのインスタンス化: CMX イメージ ファイルを使用して Viewer クラスのインスタンスを作成します。
- PNG レンダリング オプション: PNG レンダリング オプションを構成します。
- CMX を PNG にレンダリング: ビューア オブジェクトの View メソッドを呼び出して、CMX イメージを PNG にレンダリングします。
## PDF へのレンダリング
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
- CMX を PDF にレンダリング: ビューア オブジェクトの View メソッドを呼び出して、CMX イメージを PDF にレンダリングします。

## 結論
結論として、GroupDocs.Viewer for .NET は、CMX イメージをさまざまな形式にシームレスにレンダリングするための堅牢なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、CMX イメージ レンダリング機能を .NET アプリケーションに簡単に統合でき、ドキュメント管理の効率が向上します。
## よくある質問
### CMX イメージの特定のページをレンダリングできますか?
はい、レンダリング オプションでページ番号を指定することで、特定のページをレンダリングできます。
### GroupDocs.Viewer for .NET はすべての .NET フレームワークと互換性がありますか?
はい、GroupDocs.Viewer for .NET は、.NET Core や .NET Framework などの複数の .NET フレームワークと互換性があります。
### GroupDocs.Viewer は暗号化された CMX イメージのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer は、適切な復号キーを使用した暗号化された CMX イメージのレンダリングをサポートしています。
### さまざまな出力形式のレンダリング オプションをカスタマイズできますか?
もちろん、GroupDocs.Viewer には、要件に基づいてレンダリング パラメーターをカスタマイズするための広範なオプションが用意されています。
### GroupDocs.Viewer サポートのためのコミュニティ フォーラムはありますか?
はい、サポートを求めたり、サポート フォーラムの GroupDocs.Viewer コミュニティに参加したりできます。[ここ](https://forum.groupdocs.com/c/viewer/9).