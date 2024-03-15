---
title: 元のページ サイズで PDF をレンダリングする
linktitle: 元のページ サイズで PDF をレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して PDF を元のページ サイズでレンダリングする方法を学びます。ステップバイステップのガイドに従って、この機能をシームレスに統合してください。
type: docs
weight: 17
url: /ja/net/pdf-rendering-options/render-pdf-original-page-size/
---
## 導入
.NET 開発の分野では、GroupDocs.Viewer は、PDF を含むさまざまなドキュメント形式をレンダリングするための強力なツールとして際立っています。ドキュメント処理における一般的な要件の 1 つは、元のページ サイズを維持しながら PDF をレンダリングすることです。このタスクをシームレスに実行するには、GroupDocs.Viewer for .NET とその機能を包括的に理解する必要があります。
## 前提条件
GroupDocs.Viewer for .NET を使用して元のページ サイズで PDF をレンダリングする前に、次の前提条件が満たされていることを確認してください。
### 1. .NET 用の GroupDocs.Viewer をインストールします。
まず、Web サイトから GroupDocs.Viewer ライブラリをダウンロードします。提供されているライブラリから入手できます。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/)。ドキュメントに記載されているインストール手順に従って、.NET プロジェクトに効果的に統合してください。
### 2. 開発環境のセットアップ
.NET 開発用に開発環境がセットアップされていることを確認してください。これには、Visual Studio などの互換性のある IDE のインストールと、C# プログラミングの基本的な理解が含まれます。
### 3. PDF ドキュメントを入手する
GroupDocs.Viewer でレンダリングするには、サンプル PDF ドキュメントが必要です。テスト目的には、任意の PDF ドキュメントを使用できます。お持ちでない場合は、さまざまなオンライン ソースからサンプル PDF をダウンロードできます。

## 名前空間のインポート
PDF のレンダリングに進む前に、必要な名前空間を C# プロジェクトにインポートすることが重要です。この手順により、GroupDocs.Viewer ライブラリから必要なクラスとメソッドにアクセスできるようになります。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

前提条件が整い、必要な名前空間がインポートされたので、GroupDocs.Viewer for .NET を使用して元のページ サイズで PDF をレンダリングするプロセスを簡単な手順に分けてみましょう。
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされたページを保存するディレクトリを必ず指定してください。交換する`"Your Document Directory"`目的のディレクトリのパスに置き換えます。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
レンダリングされたページ ファイルに名前を付ける形式を設定します。この例では、ページは次の形式のファイル名を持つ PNG 画像として保存されます。`"page_1.png"`, `"page_2.png"`、 等々。
## ステップ 3: 元のページ サイズで PDF をレンダリングする
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
インスタンス化する`Viewer`オブジェクトを PDF ファイルへのパスに置き換えます。次に、作成します`PngViewOptions`指定されたページ ファイル パス形式で。セット`RenderOriginalPageSize`財産を`true`レンダリング中に元のページ サイズを保持します。
## ステップ 4: レンダリングされたドキュメントの場所を表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
レンダリングが成功したことを示すメッセージを出力し、レンダリングされたページが保存されるディレクトリを指定します。

## 結論
このチュートリアルで概説されている手順に従えば、GroupDocs.Viewer for .NET を使用して PDF を元のページ サイズでレンダリングするのは簡単なプロセスです。必要な名前空間をインポートし、ステップバイステップのガイドに従うことで、この機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### GroupDocs.Viewer は PDF 以外のドキュメント形式をレンダリングできますか?
はい、GroupDocs.Viewer は、Word、Excel、PowerPoint などを含むさまざまなドキュメント形式のレンダリングをサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework 環境と .NET Core 環境の両方と互換性があります。
### レンダリングされたページの出力形式をカスタマイズできますか?
はい、GroupDocs.Viewer が提供するオプション (さまざまな画像形式の設定やカスタム レンダリング オプションの指定など) を調整することで、出力形式をカスタマイズできます。
### GroupDocs.Viewer はクラウドベースのドキュメント レンダリングをサポートしていますか?
はい、GroupDocs.Viewer はクラウドベースのドキュメント レンダリング用の API を提供しており、クラウド ストレージ プロバイダーからドキュメントを直接レンダリングできます。
### GroupDocs.Viewer に利用できる無料トライアルはありますか?
はい、提供されているサイトにアクセスすると、無料トライアルで GroupDocs.Viewer を探索できます。[リンク](https://releases.groupdocs.com/).