---
title: ノートのレンダリングと時間単位の調整 (MS Project)
linktitle: ノートのレンダリングと時間単位の調整 (MS Project)
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して MS Project ドキュメントのレンダリングをマスターします。メモをレンダリングし、時間単位を調整し、さまざまな出力形式を簡単に探索できます。
weight: 11
url: /ja/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# ノートのレンダリングと時間単位の調整 (MS Project)

## 導入
GroupDocs.Viewer for .NET は、開発者が .NET アプリケーション内でさまざまなドキュメント形式を表示および操作できるようにする強力なドキュメント レンダリング API です。このチュートリアルでは、MS Project ドキュメントに特化したノートのレンダリングと時間単位の調整に焦点を当てます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET ライブラリをダウンロードしてインストールしていることを確認してください。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: .NET サポートを備えた好みの開発環境をセットアップします。
3. MS プロジェクト ドキュメント: テスト用のサンプル MS プロジェクト ドキュメントを用意します。
## 名前空間のインポート
まず、MS Project ドキュメントのレンダリングを開始するために必要な名前空間をインポートしましょう。
## ステップ 1: 名前空間をインポートする
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
必要な名前空間をインポートしたので、包括的な理解のために各例を複数のステップに分けてみましょう。
## MS Project ドキュメントを HTML にレンダリングする
MS Project ドキュメントをメモを含めて HTML 形式でレンダリングするには、次の手順に従います。
### ステップ 2: 出力ディレクトリとファイル形式を設定する
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### ステップ 3: Viewer オブジェクトを初期化し、オプションを設定する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ 4: ドキュメントを HTML にレンダリングする
```csharp
viewer.View(options);
```
## MS Project ドキュメントを画像形式にレンダリングする
MS Project ドキュメントを JPG や PNG などの画像形式にレンダリングすることもできます。その方法は次のとおりです。
### ステップ 5: JPG の出力ディレクトリとファイル形式を設定する
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### ステップ 6: Viewer オブジェクトを初期化し、JPG オプションを設定する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ 7: ドキュメントを JPG にレンダリングする
```csharp
viewer.View(options);
```
PNG やその他の画像形式にレンダリングする場合も、同様の手順を繰り返します。
## MS プロジェクトドキュメントを PDF にレンダリングする
MS Project ドキュメントを PDF 形式にレンダリングするには、次の手順を実行します。
### ステップ 8: PDF の出力ディレクトリとファイル形式を設定する
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### ステップ 9: Viewer オブジェクトを初期化し、PDF オプションを設定する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ 10: ドキュメントを PDF にレンダリングする
```csharp
viewer.View(options);
```

## 結論
おめでとう！ GroupDocs.Viewer for .NET を使用して MS Project ドキュメントをレンダリングし、時間単位を調整する方法を学習しました。この知識をプロジェクトに組み込んで、ドキュメントの表示機能を強化します。
## よくある質問
### MS Project ドキュメントを HTML、画像、PDF 以外の形式でレンダリングできますか?
はい。GroupDocs.Viewer for .NET は、DOCX、XLSX、PPTX などのさまざまな形式へのレンダリングをサポートしています。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、次のサイトから無料トライアルを利用できます。[ここ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET の一時ライセンスを取得するにはどうすればよいですか?
訪問[このリンク](https://purchase.groupdocs.com/temporary-license/)仮免許を取得するためです。
### GroupDocs.Viewer for .NET のドキュメントはどこで見つけられますか?
ドキュメントを参照してください[ここ](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET に関連するサポートや質問はどこで受けられますか?
サポートフォーラムにアクセスできます[ここ](https://forum.groupdocs.com/c/viewer/9).