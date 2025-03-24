---
title: PDF でのレイヤー化レンダリングを有効にする
linktitle: PDF でのレイヤー化レンダリングを有効にする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して PDF ドキュメントでレイヤー化レンダリングを有効にする方法を学びます。ドキュメントの表示エクスペリエンスを簡単に強化します。
weight: 15
url: /ja/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して PDF ドキュメントのレイヤー化レンダリングを有効にするプロセスを詳しく説明します。レイヤー化されたレンダリングにより、ドキュメントの表示と操作が強化され、よりインタラクティブな表示エクスペリエンスがユーザーに提供されます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. GroupDocs.Viewer for .NET: プロジェクトで GroupDocs.Viewer for .NET を使用するために必要なパッケージまたはライブラリがインストールされていることを確認してください。
2. Visual Studio: 提供されたサンプルをコーディングして実行するには、システムに Visual Studio がインストールされている必要があります。
3. C# の基本的な理解: このチュートリアルは、C# プログラミング言語の構文と概念に精通していることを前提としています。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされた出力を保存するディレクトリ パスを必ず指定してください。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
この手順では、レンダリングされた出力内の個々のページのファイル パスの形式を設定します。`{0}`はページ番号のプレースホルダーです。
## ステップ 3: レイヤード レンダリングを有効にする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
ここでは、`Viewer`オブジェクトを指定し、処理する PDF ドキュメントを指定します。次に設定します`HtmlViewOptions`定義されたページ ファイル パス形式を使用します。設定することにより`EnableLayeredRendering`財産を`true`で`PdfOptions`では、PDF ドキュメントのレイヤー化レンダリングを有効にします。
## ステップ 4: 出力ディレクトリを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ソース ドキュメントのレンダリングが成功したことを示すメッセージを出力し、指定されたディレクトリ内の出力を確認するようにユーザーに促します。

## 結論
GroupDocs.Viewer for .NET を使用して PDF ドキュメントのレイヤー化レンダリングを有効にすると、ドキュメントの表示機能が強化され、より豊かでインタラクティブなエクスペリエンスがユーザーに提供されます。このチュートリアルで概説されている手順に従うことで、この機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### PDF ドキュメントのレイヤー化レンダリングとは何ですか?
レイヤー化されたレンダリングにより、PDF ドキュメント内のさまざまなコンポーネントの分離と操作が可能になり、インタラクティブな表示と強化されたユーザー エクスペリエンスが可能になります。
### レンダリングされたドキュメントの出力ディレクトリをカスタマイズできますか?
はい、要件に応じて出力用の任意のディレクトリ パスを指定できます。
### GroupDocs.Viewer は PDF 以外のファイル形式をサポートしていますか?
はい。GroupDocs.Viewer は、Word、Excel、PowerPoint などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework 環境と .NET Core 環境の両方と互換性があります。
### 追加のサポートや支援はどこで入手できますか?
ビューア ライブラリに関する質問やサポートについては、GroupDocs.Viewer フォーラムにアクセスしてください。