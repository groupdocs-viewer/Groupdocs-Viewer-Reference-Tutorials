---
title: 特定の CAD フォーマットのレンダリング (CF2)
linktitle: 特定の CAD フォーマットのレンダリング (CF2)
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を使用して、CF2 などの特定の CAD 形式を HTML、JPG、PNG、PDF にレンダリングする方法を学びます。
weight: 12
url: /ja/net/rendering-cad-drawings/render-specific-cad-formats/
---
## 導入
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して特定の CAD 形式をレンダリングする方法を検討します。 Groupdocs.Viewer は強力なドキュメント ビューア API であり、開発者は外部ソフトウェアをインストールすることなく、アプリケーションで 170 を超えるドキュメント タイプを表示できます。具体的には、CF2 などの CAD 形式を HTML、JPG、PNG、PDF などのさまざまな出力形式にレンダリングすることに焦点を当てます。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
- Visual Studio がシステムにインストールされている。
-  .NET SDK 用の Groupdocs.Viewer。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- C# プログラミング言語の基本的な知識。
## 名前空間のインポート
まず、CAD 形式のレンダリングに必要な名前空間をインポートしましょう。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ここで、各例を複数のステップに分けてみましょう。
## CF2 を HTML にレンダリングする
### ステップ 1: レンダリングされた HTML が保存される出力ディレクトリを定義します。
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
    //必要に応じて追加のレンダリング オプションを設定します
    //options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2をJPGにレンダリング
### ステップ 1: JPG 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    //必要に応じて追加のレンダリング オプションを設定します
    //options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 を PNG にレンダリング

### ステップ 1: PNG 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    //必要に応じて追加のレンダリング オプションを設定します
    //options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 を PDF にレンダリング
### ステップ 1: PDF 出力のファイル パス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### ステップ 2: Viewer オブジェクトを初期化し、入力 CF2 ファイルを指定します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    //必要に応じて追加のレンダリング オプションを設定します
    //options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して CF2 などの特定の CAD 形式をレンダリングする方法を学習しました。ステップバイステップのガイドに従うことで、ドキュメント レンダリング機能を .NET アプリケーションに簡単に統合できます。
## よくある質問
### Groupdocs.Viewer は CF2 以外の他の CAD 形式をレンダリングできますか?
はい、Groupdocs.Viewer は、DWG、DXF、DGN などを含む幅広い CAD 形式をサポートしています。
### Groupdocs.Viewer は Web アプリケーションでドキュメントをレンダリングするのに適していますか?
確かに、Groupdocs.Viewer は Web アプリケーションにシームレスに統合して、ブラウザーで直接ドキュメントをレンダリングできます。
### Groupdocs.Viewer のレンダリングには外部依存関係が必要ですか?
いいえ、Groupdocs.Viewer はスタンドアロン API であり、外部の依存関係やソフトウェアのインストールは必要ありません。
### 要件に応じてレンダリング オプションをカスタマイズできますか?
はい。Groupdocs.Viewer には、特定のニーズに合わせてカスタマイズできるさまざまなレンダリング オプションが用意されています。
### Groupdocs.Viewer の試用版はありますか?
はい、Groupdocs.Viewer の無料試用版を次のサイトから入手できます。[ここ](https://releases.groupdocs.com/).