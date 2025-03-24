---
title: GroupDocs.Viewer for .NET を使用して印刷領域をレンダリングする
linktitle: 印刷領域のレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を探索し、さまざまなドキュメント形式で印刷領域を簡単にレンダリングします。今すぐ無料トライアルを試してください! #GroupDocs.Viewer
weight: 17
url: /ja/net/spreadsheet-rendering-options/render-print-areas/
---

# GroupDocs.Viewer for .NET を使用して印刷領域をレンダリングする

## 導入
GroupDocs.Viewer for .NET を活用してドキュメント内の印刷領域をレンダリングするためのこの包括的なガイドへようこそ。ドキュメント レンダリングのための堅牢なソリューションを探している .NET 開発者にとって、ここは正しい場所です。このチュートリアルでは、GroupDocs.Viewer を使用して印刷領域をレンダリングするプロセスを説明し、アプリケーションでのシームレスなエクスペリエンスを確保します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# および .NET 開発の実践的な知識。
-  .NET 用の GroupDocs.Viewer がインストールされています。ダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- 指定したドキュメント ディレクトリ内のサンプル ドキュメント (「SAMPLE.XLSX」など)。
## 名前空間のインポート
適切に実装するには、必ず必要な名前空間を C# コードにインポートしてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: ドキュメント ディレクトリを設定する
まず、レンダリングされた HTML ページの出力ディレクトリを指定します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
出力ディレクトリとページ番号のプレースホルダーを組み合わせて、ページ ファイル パスの形式を作成します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: GroupDocs.Viewer を初期化する
サンプル ドキュメントへのパスを使用して Viewer クラスをインスタンス化します。
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## ステップ 4: HTML 表示オプションを構成する
HTML 表示オプションを構成し、ページ ファイルのパス形式を指定し、印刷領域をレンダリングするオプションを有効にします。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## ステップ 5: ドキュメントをレンダリングする
を呼び出します。`View`指定されたオプションを使用してドキュメントをレンダリングするメソッド:
```csharp
viewer.View(options);
```
## ステップ 6: 成功メッセージを表示する
ソースドキュメントが正常にレンダリングされたことを示す成功メッセージを出力します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## 結論
おめでとう！ GroupDocs.Viewer for .NET を利用してドキュメント内の印刷領域をレンダリングする方法を学習しました。この強力なツールは、.NET アプリケーションでのドキュメント レンダリングの新たな可能性を開きます。
## よくある質問
### GroupDocs.Viewer はさまざまなドキュメント形式と互換性がありますか?
はい。GroupDocs.Viewer は、PDF、DOCX、XLSX などを含む幅広いドキュメント形式をサポートしています。を参照してください。[ドキュメンテーション](https://tutorials.groupdocs.com/viewer/net/)完全なリストについては、
### 購入する前に GroupDocs.Viewer を試すことはできますか?
絶対に！無料トライアルを利用してツールを試すことができます[ここ](https://releases.groupdocs.com/).
### 問題がある場合、どこでサポートを見つけたり支援を求めたりできますか?
訪問[GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)コミュニティとつながり、支援を受けることができます。
### 利用可能な一時ライセンスのオプションはありますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET はどこで購入できますか?
ご購入いただけます[ここ](https://purchase.groupdocs.com/buy).