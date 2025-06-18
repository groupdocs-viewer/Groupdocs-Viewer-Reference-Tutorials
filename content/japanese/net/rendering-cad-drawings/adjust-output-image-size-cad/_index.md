---
"description": "GroupDocs.Viewer for .NET を使用してCAD図面の出力画像サイズを調整する方法を学びましょう。視認性と使いやすさを簡単に向上できます。"
"linktitle": "CAD図面の出力画像サイズを調整する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CAD図面の出力画像サイズを調整する"
"url": "/ja/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# CAD図面の出力画像サイズを調整する

## 導入
CAD図面は、最適な表示とプレゼンテーションを実現するために、多くの場合、特別な調整が必要です。GroupDocs.Viewer for .NETは、CAD図面の出力を管理およびカスタマイズするための強力なツールセットを提供します。このチュートリアルでは、CAD図面の出力画像サイズを調整する手順を段階的に説明します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETをダウンロードしてインストールします。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. ドキュメント ディレクトリ: ドキュメントが保存されるディレクトリを準備します。
3. 基本的な理解: .NET プログラミングの基本的な概念を理解します。

## 名前空間のインポート
まず、GroupDocs.Viewer 機能にアクセスするために必要な名前空間をインポートしてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリを設定する
CAD 図面の出力画像を保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ページファイルパスの形式を定義する
ページファイルパスの形式を設定します。この形式は、個々のページに名前を付けてHTMLファイルとして保存する際に使用されます。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ3：画像サイズを調整する
Viewer オブジェクトの using ブロック内で、適切なオプションを設定して CAD 図面の画像サイズを調整します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## ステップ4: 出力ディレクトリを表示する
ドキュメントをレンダリングした後、レンダリングが成功したことを示すメッセージを表示し、出力ディレクトリの場所を示します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
CAD図面の出力画像サイズを調整することは、その視認性と使いやすさを向上させる上で非常に重要です。GroupDocs.Viewer for .NETを使用すると、このプロセスが合理化され、効率化され、特定の要件に合わせて出力をカスタマイズできるようになります。
## よくある質問
### CAD 図面以外の種類のドキュメントの出力画像サイズを調整できますか?
はい、GroupDocs.Viewer for .NET はさまざまなドキュメント タイプをサポートしており、ほとんどのドキュメント形式で出力画像のサイズを調整できます。
### GroupDocs.Viewer for .NET は、.NET フレームワークの異なるバージョンと互換性がありますか?
はい、GroupDocs.Viewer for .NET は複数のバージョンの .NET フレームワークと互換性があり、さまざまな環境にわたって柔軟性と使いやすさを保証します。
### GroupDocs.Viewer for .NET には利用できるライセンス オプションはありますか?
はい、ニーズに合わせて、一時ライセンスや商用ライセンスなど、さまざまなライセンス オプションを検討できます。
### レンダリングされたドキュメントの出力形式をカスタマイズできますか?
はい、GroupDocs.Viewer for .NET にはさまざまなカスタマイズ オプションが用意されており、ユーザーの状況に応じて出力形式をカスタマイズできます。
### GroupDocs.Viewer for .NET に関する追加のサポートや支援はどこで受けられますか?
GroupDocs.Viewerフォーラムにアクセスしてください [ここ](https://forum.groupdocs.com/c/viewer/9) サポートを受けたり、質問したり、コミュニティに参加したりできます。