---
"description": "GroupDocs.Viewer for .NET を使用して、PDF を元のページサイズでレンダリングする方法を学びましょう。ステップバイステップのガイドに従って、この機能をシームレスに統合しましょう。"
"linktitle": "元のページサイズでPDFをレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "元のページサイズでPDFをレンダリングする"
"url": "/ja/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# 元のページサイズでPDFをレンダリングする

## 導入
.NET開発において、GroupDocs.ViewerはPDFを含む様々なドキュメント形式をレンダリングするための強力なツールとして際立っています。ドキュメント処理において、PDFを元のページサイズを維持しながらレンダリングすることはよくある要件の一つです。このタスクをシームレスに実現するには、GroupDocs.Viewer for .NETとその機能について包括的に理解する必要があります。

![GroupDocs.Viewer .NET で元のページ サイズで PDF をレンダリングする](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## 前提条件
GroupDocs.Viewer for .NET を使用して元のページ サイズで PDF をレンダリングする前に、次の前提条件が満たされていることを確認してください。
### 1. GroupDocs.Viewer for .NETをインストールする
まず、ウェブサイトからGroupDocs.Viewerライブラリをダウンロードしてください。ライブラリは提供されている [ダウンロードリンク](https://releases.groupdocs.com/viewer/net/)ドキュメントに記載されているインストール手順に従って、.NET プロジェクトに効果的に統合します。
### 2. 開発環境のセットアップ
.NET開発用の開発環境がセットアップされていることを確認してください。これには、Visual Studioなどの互換性のあるIDEがインストールされていることと、C#プログラミングの基礎知識が含まれます。
### 3. PDFドキュメントを入手する
GroupDocs.Viewerでレンダリングするには、サンプルPDFドキュメントが必要です。テスト目的では任意のPDFドキュメントを使用できます。お持ちでない場合は、様々なオンラインソースからサンプルPDFをダウンロードできます。

## 名前空間のインポート
PDFのレンダリングに進む前に、C#プロジェクトに必要な名前空間をインポートすることが重要です。この手順により、GroupDocs.Viewerライブラリから必要なクラスとメソッドにアクセスできるようになります。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

前提条件が整い、必要な名前空間がインポートされたので、GroupDocs.Viewer for .NET を使用して元のページ サイズで PDF をレンダリングするプロセスを簡単な手順に分解してみましょう。
## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされたページを保存するディレクトリを指定してください。 `"Your Document Directory"` 希望するディレクトリのパスを入力します。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
レンダリングされたページファイルの命名形式を設定します。この例では、ページはPNG画像として保存され、ファイル名は次の形式になります。 `"page_1.png"`、 `"page_2.png"`、 等々。
## ステップ3: 元のページサイズでPDFをレンダリングする
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
インスタンス化する `Viewer` オブジェクトをPDFファイルへのパスで置き換えます。次に、 `PngViewOptions` 指定されたページファイルパス形式で設定します。 `RenderOriginalPageSize` 財産に `true` レンダリング中に元のページ サイズを維持するためです。
## ステップ4: レンダリングされたドキュメントの場所を表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
レンダリングが成功したことを示すメッセージを出力し、レンダリングされたページが保存されるディレクトリを提供します。

## 結論
GroupDocs.Viewer for .NET を使用してPDFを元のページサイズでレンダリングするのは、このチュートリアルで概説されている手順に従えば簡単です。必要な名前空間をインポートし、ステップバイステップのガイドに従うだけで、この機能を.NETアプリケーションにシームレスに統合できます。
## よくある質問
### GroupDocs.Viewer は PDF 以外のドキュメント形式をレンダリングできますか?
はい、GroupDocs.Viewer は、Word、Excel、PowerPoint など、さまざまなドキュメント形式のレンダリングをサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework と .NET Core の両方の環境と互換性があります。
### レンダリングされたページの出力形式をカスタマイズできますか?
はい、さまざまな画像形式の設定やカスタム レンダリング オプションの指定など、GroupDocs.Viewer が提供するオプションを調整することで、出力形式をカスタマイズできます。
### GroupDocs.Viewer はクラウドベースのドキュメントレンダリングをサポートしていますか?
はい、GroupDocs.Viewer はクラウドベースのドキュメント レンダリング用の API を提供しており、クラウド ストレージ プロバイダーから直接ドキュメントをレンダリングできます。
### GroupDocs.Viewer の無料トライアルはありますか?
はい、GroupDocs.Viewerを無料トライアルで試すことができます。 [リンク](https://releases。groupdocs.com/).