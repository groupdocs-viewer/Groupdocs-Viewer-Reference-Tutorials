---
title: CAD 図面のレイヤーをレンダリングする
linktitle: CAD 図面のレイヤーをレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、.NET アプリケーションで CAD 図面をシームレスにレンダリングします。レンダリング オプションを調べたり、レイヤーをカスタマイズしたりできます。
type: docs
weight: 13
url: /ja/net/rendering-cad-drawings/render-layers-cad/
---
## 導入
GroupDocs.Viewer for .NET は、開発者がドキュメント レンダリング機能を .NET アプリケーションにシームレスに統合できるようにする強力なツールです。 CAD 図面、PDF、Microsoft Office ドキュメントなどをレンダリングする必要がある場合でも、GroupDocs.Viewer は包括的なソリューションを提供します。
## 前提条件
GroupDocs.Viewer for .NET の使用に入る前に、次の前提条件を満たしていることを確認してください。
- C# プログラミング言語の基本的な理解。
- マシン上にセットアップされた .NET 開発環境。
-  .NET 用の GroupDocs.Viewer がインストールされています。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- 参照用の GroupDocs.Viewer for .NET ドキュメントへのアクセス (次の場所にあります)[ここ](https://reference.groupdocs.com/viewer/net/).

## 名前空間のインポート
GroupDocs.Viewer for .NET の使用を開始するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順を実行します：

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

提供された例を複数のステップに分けてみましょう。
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: ビューア オブジェクトを初期化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    //コードブロックは継続します...
}
```
## ステップ 4: HTML 表示オプションを設定する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ステップ 5: CAD レイヤーを定義する
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## ステップ 6: ドキュメントをレンダリングする
```csharp
viewer.View(options);
```
## ステップ 7: レンダリングされたドキュメントの場所を出力する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NET を使用すると、.NET アプリケーションでの CAD 図面のレンダリングがシームレスなプロセスになります。このガイドで概説されている手順に従うことで、ドキュメント レンダリング機能をプロジェクトに簡単に統合できます。
## よくある質問
### GroupDocs.Viewer はあらゆる種類の CAD 図面と互換性がありますか?
はい、GroupDocs.Viewer は、DWG や DXF を含む幅広い CAD 図面形式のレンダリングをサポートしています。
### CAD 図面のレンダリング オプションをカスタマイズできますか?
確かに、GroupDocs.Viewer は、レンダリングするレイヤーの指定や出力形式の設定など、さまざまなカスタマイズ オプションを提供します。
### GroupDocs.Viewer ではドキュメントを表示するためにインターネット接続が必要ですか?
いいえ、GroupDocs.Viewer はインターネット接続を必要とせずにローカルでレンダリングを実行します。
### GroupDocs.Viewer for .NET に利用できる無料試用版はありますか?
はい、GroupDocs.Viewer for .NET の無料トライアルにアクセスできます。[ここ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
技術的なサポートや質問がある場合は、GroupDocs.Viewer フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9).