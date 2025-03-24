---
title: CAD 図面の出力画像サイズを調整する
linktitle: CAD 図面の出力画像サイズを調整する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して CAD 図面の出力画像サイズを調整する方法を学びます。視認性と使いやすさを簡単に向上させます。
weight: 15
url: /ja/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# CAD 図面の出力画像サイズを調整する

## 導入
CAD 図面は、最適な表示と表示のために特定の調整が必要になることがよくあります。 GroupDocs.Viewer for .NET は、CAD 図面出力を管理およびカスタマイズするための強力なツールセットを提供します。このチュートリアルでは、CAD 図面の出力イメージ サイズを調整するプロセスを段階的に説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[ここ](https://releases.groupdocs.com/viewer/net/).
2. ドキュメント ディレクトリ: ドキュメントが配置されるディレクトリを準備します。
3. 基本的な理解: .NET プログラミングの基本概念を理解します。

## 名前空間のインポート
まず、GroupDocs.Viewer の機能にアクセスするために必要な名前空間をインポートしてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを設定する
CAD 図面の出力イメージを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
ページ ファイル パスの形式を設定します。この形式は、個々のページに名前を付けて HTML ファイルとして保存するために使用されます。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: 画像サイズを調整する
Viewer オブジェクトの using ブロック内で、適切なオプションを設定して CAD 図面の画像サイズを調整します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## ステップ 4: 出力ディレクトリを表示する
ドキュメントをレンダリングした後、レンダリングが成功したことを示すメッセージを表示し、出力ディレクトリの場所を指定します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
CAD 図面の出力画像サイズの調整は、視認性と使いやすさを向上させるために非常に重要です。 GroupDocs.Viewer for .NET を使用すると、このプロセスが合理化および効率化され、特定の要件に応じて出力をカスタマイズできるようになります。
## よくある質問
### CAD 図面以外の他の種類のドキュメントの出力画像サイズを調整できますか?
はい、GroupDocs.Viewer for .NET はさまざまなドキュメント タイプをサポートしており、ほとんどのドキュメント形式の出力画像サイズを調整できます。
### GroupDocs.Viewer for .NET は、.NET Framework のさまざまなバージョンと互換性がありますか?
はい。GroupDocs.Viewer for .NET は、.NET Framework の複数のバージョンと互換性があり、さまざまな環境間での柔軟性と使いやすさを保証します。
### GroupDocs.Viewer for .NET で利用できるライセンス オプションはありますか?
はい、ニーズに合わせて、一時ライセンスや商用ライセンスなど、さまざまなライセンス オプションを検討できます。
### レンダリングされたドキュメントの出力形式をカスタマイズできますか?
確かに、GroupDocs.Viewer for .NET にはさまざまなカスタマイズ オプションが用意されており、好みに応じて出力形式を調整できます。
### GroupDocs.Viewer for .NET に関する追加のサポートや支援はどこで入手できますか?
 GroupDocs.Viewer フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9)サポートを受けたり、質問したり、コミュニティに参加したりするためです。