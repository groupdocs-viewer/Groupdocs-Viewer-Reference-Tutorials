---
"description": "GroupDocs.Viewer for .NET を使って、様々な形式の XML SpreadSheetML ファイルをシームレスにレンダリングできます。アプリケーションに簡単に統合できます。"
"linktitle": "XML SpreadSheetML のレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "XML SpreadSheetML のレンダリング"
"url": "/ja/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# XML SpreadSheetML のレンダリング

## 導入
GroupDocs.Viewer for .NETの世界へようこそ！このチュートリアルでは、強力な.NETライブラリであるGroupDocs.Viewerを使用して、XML SpreadSheetMLファイルを簡単にレンダリングする方法を説明します。経験豊富な開発者の方でも、初心者の方でも、このステップバイステップガイドに従えば、XML SpreadSheetMLレンダリングをアプリケーションに簡単に統合できます。
## 前提条件
チュートリアルに進む前に、次の前提条件が設定されていることを確認してください。
- .NET をサポートする開発環境。
- GroupDocs.Viewer for .NETライブラリがインストールされています。ダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).
- C# プログラミングの基本的な理解。
## 名前空間のインポート
まず、必要な名前空間をC#プロジェクトにインポートします。これにより、GroupDocs.Viewerが提供する機能にアクセスできるようになります。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ステップ1: ドキュメントディレクトリを設定する
出力が保存されるドキュメント ディレクトリへのパスを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: 出力ファイルのパスを指定する
HTML、JPG、PNG、PDF 出力ファイルの完全なパスを設定します。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## ステップ3: 読み込みオプションを指定する
正確にレンダリングするには、ファイルの種類を Excel 2003 XML SpreadSheetML として明示的に指定します。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## ステップ4: マルチページHTMLにレンダリングする
HTML ビュー オプションを使用して、XML SpreadSheetML ファイルを複数ページの HTML ドキュメントに変換します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ5：JPGにレンダリングする
指定されたオプションを使用して、XML SpreadSheetML ファイルを JPG 画像に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ6: PNGにレンダリングする
同様に、指定されたオプションを使用してファイルを PNG 画像に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ7: PDFにレンダリングする
最後に、指定されたオプションを使用して、XML SpreadSheetML ファイルを PDF ドキュメントに変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 結論
おめでとうございます！GroupDocs.Viewer for .NETを使用してXML SpreadSheetMLファイルをレンダリングする方法を習得しました。この多機能ライブラリが提供するその他の機能とオプションを活用して、ドキュメントの表示機能を強化しましょう。
## よくある質問
### GroupDocs.Viewer は他のファイル形式と互換性がありますか?
はい、GroupDocs.Viewer は PDF、Word、Excel など、幅広いドキュメント形式をサポートしています。
### レンダリングされたドキュメントの外観をカスタマイズできますか?
もちろんです！GroupDocs.Viewer にはさまざまなカスタマイズ オプションが用意されており、特定のニーズに合わせて出力をカスタマイズできます。
### 追加のサポートやリソースはどこで見つかりますか?
訪問 [GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9) コミュニティのサポートと探索 [ドキュメント](https://tutorials.groupdocs.com/viewer/net/) 詳細情報については。
### 無料トライアルはありますか？
はい、無料トライアルにアクセスできます [ここ](https://releases。groupdocs.com/).
### 一時ライセンスを取得するにはどうすればよいですか?
臨時免許証を取得できます [ここ](https://purchase。groupdocs.com/temporary-license/).