---
"description": "Groupdocs.Viewer for .NET を使用して、JPEG形式の画像のサイズと品質を最適化する方法を学びましょう。ドキュメントの表示エクスペリエンスを向上させます。"
"linktitle": "画像のサイズと品質を調整する（JPG）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "画像のサイズと品質を調整する（JPG）"
"url": "/ja/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# 画像のサイズと品質を調整する（JPG）

## 導入
Groupdocs.Viewer for .NETは、開発者が.NETアプリケーションにドキュメント表示機能をシームレスに統合できるようにする強力なライブラリです。ドキュメント表示アプリケーションでは、特にJPEG（JPG）画像を扱う際に、画像のサイズと品質を調整する機能が求められることがよくあります。このチュートリアルでは、Groupdocs.Viewer for .NETを使用して画像のサイズと品質を調整する手順を詳しく説明します。
## 前提条件
始める前に、以下のものを用意してください。
1. C# プログラミング言語の基本的な理解。
2. Visual Studio がシステムにインストールされています。
3. Groupdocs.Viewer for .NETライブラリがインストールされています。ダウンロードはこちらから。 [ここ](https://releases。groupdocs.com/viewer/net/).

## 名前空間のインポート
まず、C#コードに必要な名前空間をインポートする必要があります。これらの名前空間は、Groupdocs.Viewerの操作に必要なクラスとメソッドへのアクセスを提供します。
## ステップ1: 名前空間をインポートする
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、理解を深めるために、提供されているサンプル コードを複数のステップに分解してみましょう。
## ステップ2: 出力ディレクトリとページファイルパスの形式を設定する
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
このステップでは、レンダリングされた画像が保存される出力ディレクトリを指定し、各ページ画像のファイル パスの形式を定義します。
## ステップ3: ビューアを初期化し、JPG表示オプションを構成する
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
ここでは、Viewerオブジェクトを、表示するドキュメントへのパスで初期化します。次に、JpgViewOptionsのインスタンスを作成し、JPEG画像の幅と高さを設定します。
## ステップ4: ソースドキュメントのレンダリング
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ソース ドキュメントのレンダリングが成功したことと、出力画像が保存される場所を示すメッセージを出力します。

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して JPEG 画像のサイズと品質を調整する方法を学習しました。上記の手順に従うことで、この機能を .NET アプリケーションに簡単に組み込み、ユーザーに最適な画像表示エクスペリエンスを提供できます。
## よくある質問
### 画質も調整できますか？
はい、JpgViewOptions の Quality プロパティを設定することで画像の品質を調整できます。
### Groupdocs.Viewer for .NET ではどのようなドキュメント形式がサポートされていますか?
Groupdocs.Viewer for .NET は、DOCX、PDF、PPTX、XLSX など、幅広いドキュメント形式をサポートしています。
### Groupdocs.Viewer for .NET は .NET Core と互換性がありますか?
はい、Groupdocs.Viewer for .NET は、従来の .NET Framework に加えて .NET Core とも互換性があります。
### 出力ファイルの命名形式をカスタマイズできますか?
はい、コード内の pageFilePathFormat 変数を変更することで、出力ファイルの命名形式をカスタマイズできます。
### Groupdocs.Viewer for .NET はドキュメントの注釈をサポートしていますか?
はい、Groupdocs.Viewer for .NET は、テキストの強調表示、下線、コメントなどのドキュメント注釈を包括的にサポートします。