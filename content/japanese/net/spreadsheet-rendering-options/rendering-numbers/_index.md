---
"description": "Groupdocs.Viewer for .NET のパワーを体験して、Numbers ファイルをシームレスにレンダリングしましょう。HTML、JPG、PNG、PDF への変換も簡単です。"
"linktitle": "数値のレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "数値のレンダリング"
"url": "/ja/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# 数値のレンダリング

## 導入
Groupdocs.Viewer for .NET を使って Numbers ファイルをレンダリングする方法をステップバイステップで解説するチュートリアルへようこそ。経験豊富な開発者の方でも初心者の方でも、このガイドを読めば Numbers ドキュメントを様々な形式に変換する手順を理解できます。Groupdocs.Viewer for .NET は、ドキュメント表示機能を .NET アプリケーションにシームレスに統合できる強力なツールです。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- C# および .NET 開発に関する実用的な知識。
- Groupdocs.Viewer for .NETライブラリがインストールされました。ダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).
- 出力ファイルが保存されるドキュメント ディレクトリ パス。
## 名前空間のインポート
C# プロジェクトで、Groupdocs.Viewer ライブラリを使用するために必要な名前空間をインポートしていることを確認します。
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリを設定する
レンダリングを開始する前に、変換されたファイルを保存する出力ディレクトリを指定してください。「Your Document Directory」を実際のパスに置き換えてください。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: 複数ページのHTMLにレンダリングする
次のコードを使用して、Numbers ファイルを複数ページの HTML に変換します。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ3: JPGにレンダリングする
次のコードを使用して、Numbers ファイルを JPG 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ4: PNGにレンダリングする
次のコードを使用して、Numbers ファイルを PNG 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ5: PDFにレンダリングする
最後に、次のコードを使用して Numbers ファイルを PDF 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
おめでとうございます! Groupdocs.Viewer for .NET を使用して、Numbers ファイルをさまざまな形式に変換できました。
## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用した Numbers ファイルのレンダリングの基本について説明しました。この強力なライブラリは、.NET アプリケーションでドキュメントの表示と変換をシームレスに統合します。
## よくある質問
### Groupdocs.Viewer for .NET を他のドキュメント タイプでも使用できますか?
はい、Groupdocs.Viewer は、Word、Excel、PDF など、幅広いドキュメント形式をサポートしています。
### テスト目的で一時ライセンスを利用できますか?
はい、臨時免許証を取得できます [ここ](https://purchase.groupdocs.com/temporary-license/) テスト用。
### Groupdocs.Viewer for .NET のサポートはどこで受けられますか?
訪問 [Groupdocs.Viewerフォーラム](https://forum.groupdocs.com/c/viewer/9) サポートとディスカッションのため。
### Groupdocs.Viewer for .NET のフル バージョンを購入するにはどうすればよいですか?
フルバージョンを購入できます [ここ](https://purchase。groupdocs.com/buy).
### 無料試用版はありますか？
はい、無料試用版を試すことができます [ここ](https://releases。groupdocs.com/).