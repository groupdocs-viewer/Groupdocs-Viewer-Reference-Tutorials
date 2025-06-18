---
"description": "Groupdocs.Viewer for .NET を使用して、CF2 などの特定の CAD 形式を HTML、JPG、PNG、PDF にレンダリングする方法を学習します。"
"linktitle": "特定のCAD形式（CF2）のレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "特定のCAD形式（CF2）のレンダリング"
"url": "/ja/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# 特定のCAD形式（CF2）のレンダリング

## 導入
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して特定のCAD形式をレンダリングする方法を説明します。Groupdocs.Viewer は、開発者が外部ソフトウェアをインストールすることなく、170種類以上のドキュメントをアプリケーションで表示できる強力なドキュメントビューアAPIです。特に、CF2などのCAD形式をHTML、JPG、PNG、PDFなどの様々な出力形式にレンダリングする方法に焦点を当てます。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- Visual Studio がシステムにインストールされています。
- Groupdocs.Viewer for .NET SDK。こちらからダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).
- C# プログラミング言語の基礎知識。
## 名前空間のインポート
まず、CAD 形式のレンダリングに必要な名前空間をインポートしましょう。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ここで、各例を複数のステップに分解してみましょう。
## CF2をHTMLにレンダリングする
### ステップ 1: レンダリングされた HTML を保存する出力ディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
### ステップ 2: HTML 出力のファイル パス形式を定義します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### ステップ 3: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // 必要に応じて追加のレンダリングオプションを設定します
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2をJPGにレンダリングする
### ステップ 1: JPG 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // 必要に応じて追加のレンダリングオプションを設定します
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2をPNGにレンダリングする

### ステップ 1: PNG 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // 必要に応じて追加のレンダリングオプションを設定します
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2をPDFにレンダリングする
### ステップ 1: PDF 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // 必要に応じて追加のレンダリングオプションを設定します
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して、CF2 などの特定の CAD 形式をレンダリングする方法を学びました。ステップバイステップのガイドに従うことで、ドキュメントレンダリング機能を .NET アプリケーションに簡単に統合できます。
## よくある質問
### Groupdocs.Viewer は CF2 以外の CAD 形式をレンダリングできますか?
はい、Groupdocs.Viewer は DWG、DXF、DGN など、幅広い CAD 形式をサポートしています。
### Groupdocs.Viewer は Web アプリケーションでドキュメントをレンダリングするのに適していますか?
はい、Groupdocs.Viewer は Web アプリケーションにシームレスに統合でき、ブラウザーで直接ドキュメントをレンダリングできます。
### Groupdocs.Viewer はレンダリングに外部依存関係を必要としますか?
いいえ、Groupdocs.Viewer はスタンドアロン API であり、外部依存関係やソフトウェアのインストールは必要ありません。
### 要件に応じてレンダリング オプションをカスタマイズできますか?
はい、Groupdocs.Viewer は、特定のニーズに合わせてカスタマイズできるさまざまなレンダリング オプションを提供します。
### Groupdocs.Viewer の試用版はありますか?
はい、Groupdocs.Viewerの無料試用版は以下から入手できます。 [ここ](https://releases。groupdocs.com/).