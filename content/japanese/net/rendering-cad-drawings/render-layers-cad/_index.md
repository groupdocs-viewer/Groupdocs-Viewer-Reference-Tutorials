---
"description": "GroupDocs.Viewer for .NET を使用すると、.NET アプリケーションで CAD 図面をシームレスにレンダリングできます。レンダリング オプションの確認、レイヤーのカスタマイズなど、さまざまな機能をご利用いただけます。"
"linktitle": "CAD図面のレンダリングレイヤー"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD図面のレンダリングレイヤー"
"url": "/ja/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
type: docs
---
# CAD図面のレンダリングレイヤー

## 導入
GroupDocs.Viewer for .NETは、開発者が.NETアプリケーションにドキュメントレンダリング機能をシームレスに統合できるようにする強力なツールです。CAD図面、PDF、Microsoft Officeドキュメントなど、あらゆるドキュメントのレンダリングに包括的なソリューションを提供します。
## 前提条件
GroupDocs.Viewer for .NET の使用を開始する前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語の基本的な理解。
- マシンに .NET 開発環境をセットアップします。
- GroupDocs.Viewer for .NET がインストールされています。ダウンロードはこちらから [ここ](https://releases。groupdocs.com/viewer/net/).
- GroupDocs.Viewer for .NETのチュートリアルドキュメントへのアクセス。 [ここ](https://tutorials。groupdocs.com/viewer/net/).

## 名前空間のインポート
GroupDocs.Viewer for .NET の使用を開始するには、プロジェクトに必要な名前空間をインポートする必要があります。以下の手順に従ってください。

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

提供された例を複数のステップに分解してみましょう。
## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ3: ビューアオブジェクトの初期化
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // コードブロックは続きます...
}
```
## ステップ4: HTML表示オプションを設定する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ステップ5: CADレイヤーを定義する
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## ステップ6: ドキュメントのレンダリング
```csharp
viewer.View(options);
```
## ステップ7: レンダリングされたドキュメントの出力場所
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NETを使用すると、.NETアプリケーションでのCAD図面のレンダリングがシームレスになります。このガイドで説明する手順に従うだけで、ドキュメントレンダリング機能をプロジェクトに簡単に統合できます。
## よくある質問
### GroupDocs.Viewer はすべての種類の CAD 図面と互換性がありますか?
はい、GroupDocs.Viewer は、DWG や DXF を含む幅広い CAD 図面形式のレンダリングをサポートしています。
### CAD 図面のレンダリング オプションをカスタマイズできますか?
はい、GroupDocs.Viewer では、レンダリングするレイヤーの指定や出力形式の設定など、さまざまなカスタマイズ オプションが提供されています。
### GroupDocs.Viewer ではドキュメントをレンダリングするためにインターネット接続が必要ですか?
いいえ、GroupDocs.Viewer はインターネット接続を必要とせずにローカルでレンダリングを実行します。
### GroupDocs.Viewer for .NET の無料試用版はありますか?
はい、GroupDocs.Viewer for .NETの無料トライアルをご利用いただけます。 [ここ](https://releases。groupdocs.com/).
### GroupDocs.Viewer for .NET のサポートはどこで受けられますか?
技術的なサポートや質問がある場合は、GroupDocs.Viewer フォーラムをご覧ください。 [ここ](https://forum。groupdocs.com/c/viewer/9).