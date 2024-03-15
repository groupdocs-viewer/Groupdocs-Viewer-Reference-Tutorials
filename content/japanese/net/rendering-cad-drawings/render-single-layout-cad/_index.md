---
title: CAD 図面での単一レイアウトのレンダリング
linktitle: CAD 図面での単一レイアウトのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して CAD 図面で単一のレイアウトをレンダリングする方法を学びます。簡単な手順で .NET アプリケーションにシームレスに統合できます。
type: docs
weight: 14
url: /ja/net/rendering-cad-drawings/render-single-layout-cad/
---
## 導入
.NET 開発の領域では、CAD 図面の処理と表示が一般的な要件です。 GroupDocs.Viewer for .NET は、.NET アプリケーション内で CAD 図面をレンダリングするための包括的なソリューションを提供することで、このタスクを簡素化します。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して CAD 図面内の単一レイアウトをレンダリングする方法について詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
- C# プログラミング言語と .NET Framework の基本的な理解。
- Visual Studio がシステムにインストールされている。
-  GroupDocs.Viewer for .NET ライブラリがダウンロードされ、プロジェクトで参照されます。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- CAD ファイル形式とその構造についての知識。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートして、GroupDocs.Viewer 機能にアクセスします。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ステップ 1: 出力ディレクトリを定義する
レンダリングされた出力を保存するディレクトリを指定します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
レンダリングされた各ページのファイル パスの形式を定義します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: Viewer オブジェクトをインスタンス化する
GroupDocs.Viewer によって提供される Viewer クラスのインスタンスを作成します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## ステップ 4: HTML 表示オプションを構成する
埋め込みリソースを使用して HTML 出力をレンダリングするためのオプションを構成します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ステップ 5: CAD レイアウト名の指定
レンダリングする CAD レイアウトの名前を指定します。
```csharp
options.CadOptions.LayoutName = "Model";
```
## ステップ 6: CAD 図面をレンダリングする
指定されたオプションを使用して Viewer オブジェクトの View メソッドを呼び出します。
```csharp
viewer.View(options);
```
## ステップ 7: 成功メッセージを表示する
ソースドキュメントのレンダリングが成功したことをユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
CAD 図面のレンダリングは、特にレイアウトを扱う場合、大変な作業になることがあります。ただし、GroupDocs.Viewer for .NET を使用すると、プロセスがシームレスかつ効率的になります。このチュートリアルで概説されている手順に従うことで、.NET アプリケーション内の CAD 図面で単一のレイアウトを簡単にレンダリングできます。
## よくある質問
### GroupDocs.Viewer for .NET を使用して複数のレイアウトを同時にレンダリングできますか?
はい。GroupDocs.Viewer for .NET は、CAD 図面からの複数のレイアウトのレンダリングをサポートしています。
### GroupDocs.Viewer はさまざまな CAD ファイル形式と互換性がありますか?
確かに、GroupDocs.Viewer は、DWG、DXF、DGN などを含む幅広い CAD ファイル形式をサポートしています。
### CAD 図面のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer は、要件に応じてレンダリング設定をカスタマイズするための広範なオプションを提供します。
### GroupDocs.Viewer for .NET に利用できる無料試用版はありますか?
はい、無料トライアルを利用して、GroupDocs.Viewer の機能を探索できます。[ここ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
質問やサポートが必要な場合は、GroupDocs.Viewer フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9).