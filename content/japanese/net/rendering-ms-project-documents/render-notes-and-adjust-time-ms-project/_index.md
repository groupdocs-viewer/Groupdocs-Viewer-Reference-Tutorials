---
"description": "GroupDocs.Viewer for .NET で MS Project ドキュメントのレンダリングをマスターしましょう。メモのレンダリング、時間単位の調整、さまざまな出力形式を簡単に確認できます。"
"linktitle": "ノートをレンダリングして時間単位を調整する (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ノートをレンダリングして時間単位を調整する (MS Project)"
"url": "/ja/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# ノートをレンダリングして時間単位を調整する (MS Project)

## 導入
GroupDocs.Viewer for .NETは、開発者が.NETアプリケーション内で様々な形式のドキュメントを表示・操作できる強力なドキュメントレンダリングAPIです。このチュートリアルでは、特にMS Projectドキュメントにおけるメモのレンダリングと時間単位の調整に焦点を当てます。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETライブラリをダウンロードしてインストールしてください。ダウンロードはこちらから行えます。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: .NET サポートを使用して、好みの開発環境を設定します。
3. MS Project ドキュメント: テスト用にサンプルの MS Project ドキュメントを用意しておきます。
## 名前空間のインポート
まず、MS Project ドキュメントのレンダリングを開始するために必要な名前空間をインポートしましょう。
## ステップ1: 名前空間をインポートする
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
必要な名前空間をインポートしたので、包括的な理解を得るために各例を複数のステップに分解してみましょう。
## MS Project ドキュメントを HTML にレンダリングする
MS Project ドキュメントをメモ付きの HTML 形式に変換するには、次の手順に従います。
### ステップ2: 出力ディレクトリとファイル形式を設定する
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### ステップ3: ビューアオブジェクトの初期化とオプションの設定
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ4: ドキュメントをHTMLにレンダリングする
```csharp
viewer.View(options);
```
## MS Project ドキュメントを画像形式に変換する
MS ProjectドキュメントをJPGやPNGなどの画像形式に変換することもできます。手順は以下のとおりです。
### ステップ5：JPGの出力ディレクトリとファイル形式を設定する
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### ステップ6: ビューアオブジェクトの初期化とJPGオプションの設定
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ7: ドキュメントをJPGにレンダリングする
```csharp
viewer.View(options);
```
PNG やその他の画像形式にレンダリングするには、同様の手順を繰り返します。
## MS Project ドキュメントを PDF に変換する
MS Project ドキュメントを PDF 形式に変換するには、次の手順に従います。
### ステップ8: PDFの出力ディレクトリとファイル形式を設定する
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### ステップ9: ビューアオブジェクトの初期化とPDFオプションの設定
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ステップ10: ドキュメントをPDFに変換する
```csharp
viewer.View(options);
```

## 結論
おめでとうございます！GroupDocs.Viewer for .NET を使用して MS Project ドキュメントをレンダリングし、時間単位を調整する方法を習得しました。この知識をプロジェクトに取り入れて、ドキュメントの表示機能を強化しましょう。
## よくある質問
### MS Project ドキュメントを HTML、画像、PDF 以外の形式でレンダリングできますか?
はい、GroupDocs.Viewer for .NET は、DOCX、XLSX、PPTX などのさまざまな形式へのレンダリングをサポートしています。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、無料トライアルをご利用いただけます [ここ](https://releases。groupdocs.com/).
### GroupDocs.Viewer for .NET の一時ライセンスを取得するにはどうすればよいですか?
訪問 [このリンク](https://purchase.groupdocs.com/temporary-license/) 臨時免許を取得する。
### GroupDocs.Viewer for .NET のドキュメントはどこで見つかりますか?
ドキュメントを参照してください [ここ](https://tutorials。groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET に関するサポートや質問はどこで受けられますか?
サポートフォーラムをご覧ください [ここ](https://forum。groupdocs.com/c/viewer/9).