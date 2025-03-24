---
title: XML SpreadSheetML のレンダリング
linktitle: XML SpreadSheetML のレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、さまざまな形式の XML SpreadSheetML ファイルのシームレスなレンダリングを探索します。アプリケーションに簡単に統合できます。
weight: 16
url: /ja/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## 導入
GroupDocs.Viewer for .NET の世界へようこそ!このチュートリアルでは、強力な .NET ライブラリである GroupDocs.Viewer を使用して XML SpreadSheetML ファイルを簡単にレンダリングする方法を説明します。経験豊富な開発者であっても、初心者であっても、このステップバイステップのガイドは、XML SpreadSheetML レンダリングをアプリケーションに簡単に統合するのに役立ちます。
## 前提条件
チュートリアルに入る前に、次の前提条件が設定されていることを確認してください。
- .NET をサポートする開発環境。
-  .NET ライブラリ用の GroupDocs.Viewer がインストールされています。ダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- C# プログラミングの基本的な理解。
## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。これにより、GroupDocs.Viewer が提供する機能に確実にアクセスできるようになります。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ 1: ドキュメント ディレクトリを設定する
出力が保存されるドキュメント ディレクトリへのパスを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: 出力ファイルのパスを指定する
HTML、JPG、PNG、PDF 出力ファイルのフルパスを設定します。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## ステップ 3: ロード オプションを指定する
正確にレンダリングするには、ファイルの種類を Excel 2003 XML SpreadSheetML として明示的に指定します。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## ステップ 4: マルチページ HTML にレンダリングする
HTML 表示オプションを利用して、XML SpreadSheetML ファイルを複数ページの HTML ドキュメントにレンダリングします。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 5: JPG にレンダリングする
指定されたオプションを使用して、XML SpreadSheetML ファイルを JPG 画像にレンダリングします。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 6: PNG にレンダリングする
同様に、指定されたオプションを使用してファイルを PNG イメージにレンダリングします。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 7: PDF にレンダリングする
最後に、指定されたオプションを使用して、XML SpreadSheetML ファイルを PDF ドキュメントにレンダリングします。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 結論
おめでとう！ GroupDocs.Viewer for .NET を使用して XML SpreadSheetML ファイルをレンダリングする方法を学習しました。この多用途ライブラリが提供する機能やオプションをさらに探索して、ドキュメントの表示機能を強化します。
## よくある質問
### GroupDocs.Viewer は他のファイル形式と互換性がありますか?
はい。GroupDocs.Viewer は、PDF、Word、Excel などを含む幅広いドキュメント形式をサポートしています。
### レンダリングされたドキュメントの外観をカスタマイズできますか?
絶対に！ GroupDocs.Viewer にはさまざまなカスタマイズ オプションが用意されており、特定のニーズに合わせて出力を調整できます。
### 追加のサポートやリソースはどこで入手できますか?
訪問[GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)コミュニティのサポートを求めて、[ドキュメンテーション](https://tutorials.groupdocs.com/viewer/net/)詳細については。
### 無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.groupdocs.com/).
### 一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.groupdocs.com/temporary-license/).