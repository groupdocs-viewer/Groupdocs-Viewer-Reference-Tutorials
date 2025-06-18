---
"description": "GroupDocs.Viewer for .NET を使用して、CAD 図面で単一レイアウトをレンダリングする方法を学びます。簡単な手順で、.NET アプリケーションにシームレスに統合できます。"
"linktitle": "CAD図面で単一レイアウトをレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD図面で単一レイアウトをレンダリングする"
"url": "/ja/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# CAD図面で単一レイアウトをレンダリングする

## 導入
.NET開発において、CAD図面の取り扱いと表示は一般的な要件です。GroupDocs.Viewer for .NETは、.NETアプリケーション内でCAD図面をレンダリングするための包括的なソリューションを提供することで、この作業を簡素化します。このチュートリアルでは、GroupDocs.Viewer for .NETを使用してCAD図面内の単一レイアウトをレンダリングする方法について詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語と .NET フレームワークの基本的な理解。
- Visual Studio がシステムにインストールされています。
- GroupDocs.Viewer for .NETライブラリをダウンロードし、チュートリアルをプロジェクトに追加します。ダウンロードはこちらから。 [ここ](https://releases。groupdocs.com/viewer/net/).
- CAD ファイル形式とその構造に関する知識。

## 名前空間のインポート
まず、GroupDocs.Viewer 機能にアクセスするために必要な名前空間を C# コードにインポートします。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ステップ1: 出力ディレクトリを定義する
レンダリングされた出力を保存するディレクトリを指定します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ページファイルパスの形式を定義する
レンダリングされる各ページのファイル パスの形式を定義します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ3: ビューアオブジェクトのインスタンス化
GroupDocs.Viewer によって提供される Viewer クラスのインスタンスを作成します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## ステップ4: HTML表示オプションを構成する
埋め込みリソースを含む HTML 出力をレンダリングするためのオプションを構成します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ステップ5: CADレイアウト名を指定する
レンダリングする CAD レイアウトの名前を指定します。
```csharp
options.CadOptions.LayoutName = "Model";
```
## ステップ6：CAD図面のレンダリング
指定されたオプションを使用して、Viewer オブジェクトの View メソッドを呼び出します。
```csharp
viewer.View(options);
```
## ステップ7: 成功メッセージを表示する
ソース ドキュメントのレンダリングが成功したことをユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
CAD図面のレンダリング、特にレイアウトを扱う際には、非常に困難な作業になりがちです。しかし、GroupDocs.Viewer for .NETを使えば、このプロセスはシームレスかつ効率的になります。このチュートリアルで説明する手順に従えば、.NETアプリケーション内でCAD図面内の単一のレイアウトを簡単にレンダリングできます。
## よくある質問
### GroupDocs.Viewer for .NET を使用して複数のレイアウトを同時にレンダリングできますか?
はい、GroupDocs.Viewer for .NET は、CAD 図面から複数のレイアウトをレンダリングすることをサポートしています。
### GroupDocs.Viewer はさまざまな CAD ファイル形式と互換性がありますか?
はい、GroupDocs.Viewer は、DWG、DXF、DGN など、幅広い CAD ファイル形式をサポートしています。
### CAD 図面のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer には、要件に応じてレンダリング設定をカスタマイズするための幅広いオプションが用意されています。
### GroupDocs.Viewer for .NET の無料試用版はありますか?
はい、GroupDocs.Viewer の機能を無料でお試しいただけます。 [ここ](https://releases。groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
ご質問やサポートについては、GroupDocs.Viewer フォーラムをご覧ください。 [ここ](https://forum。groupdocs.com/c/viewer/9).