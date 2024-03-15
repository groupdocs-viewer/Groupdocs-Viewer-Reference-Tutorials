---
title: 画像のサイズと品質を調整する (JPG)
linktitle: 画像のサイズと品質を調整する (JPG)
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を使用して JPEG 形式の画像サイズと品質を最適化する方法を学びます。ドキュメントの表示エクスペリエンスを向上させます。
type: docs
weight: 11
url: /ja/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## 導入
Groupdocs.Viewer for .NET は、開発者がドキュメント表示機能を .NET アプリケーションにシームレスに統合できるようにする強力なライブラリです。ドキュメント表示アプリケーションにおける一般的な要件の 1 つは、特に JPEG (JPG) 画像を扱う場合に、画像のサイズと品質を調整できることです。このチュートリアルでは、Groupdocs.Viewer for .NET を使用して画像のサイズと品質を調整するプロセスを説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. C# プログラミング言語の基本的な理解。
2. Visual Studio がシステムにインストールされている。
3.  .NET ライブラリ用の Groupdocs.Viewer がインストールされています。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートする必要があります。これらの名前空間は、Groupdocs.Viewer を操作するために必要なクラスとメソッドへのアクセスを提供します。
## ステップ 1: 名前空間をインポートする
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、理解を深めるために、提供されているコード例を複数のステップに分けて見てみましょう。
## ステップ 2: 出力ディレクトリとページ ファイル パス形式を設定する
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
このステップでは、レンダリングされたイメージが保存される出力ディレクトリを指定し、各ページ イメージのファイル パスの形式を定義します。
## ステップ 3: ビューアを初期化し、JPG 表示オプションを構成する
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
ここでは、表示するドキュメントへのパスを使用して Viewer オブジェクトを初期化します。次に、JpgViewOptions のインスタンスを作成し、JPEG 画像に必要な幅と高さを設定します。
## ステップ 4: ソースドキュメントをレンダリングする
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ソース ドキュメントのレンダリングが成功したことと、出力イメージが保存される場所を示すメッセージを出力します。

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して JPEG 画像のサイズと品質を調整する方法を学習しました。上記の手順に従うことで、この機能を .NET アプリケーションに簡単に組み込むことができ、ユーザーに最適化された画像表示エクスペリエンスを提供できます。
## よくある質問
### 画質も調整できますか？
はい、JpgViewOptions の Quality プロパティを設定することで画質を調整できます。
### Groupdocs.Viewer for .NET ではどのようなドキュメント形式がサポートされていますか?
Groupdocs.Viewer for .NET は、DOCX、PDF、PPTX、XLSX などの幅広いドキュメント形式をサポートしています。
### Groupdocs.Viewer for .NET は .NET Core と互換性がありますか?
はい、Groupdocs.Viewer for .NET は、従来の .NET Framework とともに .NET Core と互換性があります。
### 出力ファイルの命名形式をカスタマイズできますか?
はい、コード内の pageFilePathFormat 変数を変更することで、出力ファイルの命名形式をカスタマイズできます。
### Groupdocs.Viewer for .NET はドキュメントの注釈をサポートしていますか?
はい。Groupdocs.Viewer for .NET は、テキストの強調表示、下線、コメントなどのドキュメント注釈の包括的なサポートを提供します。