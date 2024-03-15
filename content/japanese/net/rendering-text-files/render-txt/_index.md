---
title: テキスト ファイル (.txt) のレンダリング
linktitle: テキスト ファイル (.txt) のレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、テキスト ファイルを複数の形式にシームレスに変換する方法を確認します。ドキュメント管理機能を簡単に強化します。
type: docs
weight: 10
url: /ja/net/rendering-text-files/render-txt/
---
## 導入
ドキュメントの管理と操作の分野では、GroupDocs.Viewer for .NET が強力なツールとして登場し、さまざまなドキュメント形式を効率的にレンダリングするための豊富な機能を提供します。この記事では、GroupDocs.Viewer for .NET を利用してテキスト ファイル (.txt) を複数の形式にレンダリングする際の複雑な仕組みについて詳しく説明します。テキスト ファイルを HTML、JPG、PNG、PDF に変換する場合でも、GroupDocs.Viewer には、これらのタスクをシームレスに実行するために必要なツールが備わっています。
## 前提条件
変換プロセスを詳しく調べる前に、次の前提条件が満たされていることを確認してください。
### 1. GroupDocs.Viewer for .NET のインストール
開発環境に GroupDocs.Viewer for .NET がインストールされていることを確認してください。から必要なファイルをダウンロードできます。[Webサイト](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework に関する基本的な知識
プロジェクトのセットアップ方法やコードベース内でライブラリを利用する方法など、.NET Framework の基本を理解します。
### 3. サンプルテキストファイル
変換するサンプル テキスト ファイル (.txt) を準備します。これらのファイルは、変換プロセスの入力として機能します。

## 名前空間のインポート
変換プロセスに入る前に、必ず必要な名前空間をプロジェクトにインポートしてください。これにより、GroupDocs.Viewer for .NET が提供する機能にシームレスにアクセスできるようになります。
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
変換プロセスを効果的に進めるために、各例を複数のステップに分けて説明します。

## ステップ 1: HTML 出力パスを定義する
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML出力ファイルのフルパスを指定します。
## ステップ 2: テキスト ファイルを複数ページの HTML にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
インスタンス化する`Viewer`オブジェクトとテキスト ファイルへのパス。構成、設定`HtmlViewOptions`埋め込みリソースの場合は、テキスト ファイルを複数ページの HTML にレンダリングします。
## ステップ 3: シングルページ HTML 出力パスを定義する
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
単一ページの HTML 出力ファイルのフルパスを指定します。
## ステップ 4: テキスト ファイルを単一ページの HTML にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
インスタンス化する`Viewer`オブジェクトとテキスト ファイルへのパス。構成、設定`HtmlViewOptions`埋め込みリソースとセットの場合`RenderToSinglePage`本当のこと。テキスト ファイルを単一ページの HTML にレンダリングします。
## ステップ 5: JPG 出力パスを定義する
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG出力ファイルのフルパスを指定します。
## ステップ 6: テキスト ファイルを JPG にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
インスタンス化する`Viewer`オブジェクトとテキスト ファイルへのパス。構成、設定`JpgViewOptions`出力パスを指定し、テキスト ファイルを JPG 形式にレンダリングします。
## ステップ 7: PNG 出力パスを定義する
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
PNG出力ファイルのフルパスを指定します。
## ステップ 8: テキスト ファイルを PNG にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
インスタンス化する`Viewer`オブジェクトとテキスト ファイルへのパス。構成、設定`PngViewOptions`出力パスを指定し、テキスト ファイルを PNG 形式にレンダリングします。
## ステップ 9: PDF 出力パスを定義する
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
PDF出力ファイルのフルパスを指定します。
## ステップ 10: テキスト ファイルを PDF にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
インスタンス化する`Viewer`オブジェクトとテキスト ファイルへのパス。構成、設定`PdfViewOptions`出力パスを指定し、テキスト ファイルを PDF 形式にレンダリングします。

## 結論
結論として、GroupDocs.Viewer for .NET を使用すると、開発者はテキスト ファイルを HTML、JPG、PNG、PDF などのさまざまな形式に簡単にレンダリングできるようになります。この記事で説明するステップバイステップ ガイドに従うことで、GroupDocs.Viewer を .NET アプリケーションにシームレスに統合し、ドキュメント管理機能を強化できます。
## よくある質問
### Q: GroupDocs.Viewer for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?
はい。GroupDocs.Viewer for .NET は、さまざまな .NET Framework バージョンと互換性があるように設計されており、開発における多用途性と柔軟性を確保しています。
### Q: レンダリングされたドキュメントの出力外観をカスタマイズできますか?
絶対に！ GroupDocs.Viewer は広範なカスタマイズ オプションを提供し、開発者が好みや要件に応じてレンダリングされたドキュメントの外観を調整できるようにします。
### Q: GroupDocs.Viewer for .NET の試用版はありますか?
はい、次のサイトで利用可能な無料トライアルにアクセスして、GroupDocs.Viewer for .NET の機能を調べることができます。[Webサイト]( https://releases.groupdocs.com/).
### Q: GroupDocs.Viewer for .NET に関するサポートやサポートを受けるにはどうすればよいですか?
 GroupDocs.Viewer for .NET に関する問い合わせ、サポート、支援については、専用のサポート フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9).
### Q: GroupDocs.Viewer for .NET の一時ライセンスを購入できますか?
はい、一時ライセンスを購入できます。これにより、ユーザーは特定の期間、GroupDocs.Viewer for .NET を柔軟かつ便利に利用できるようになります。