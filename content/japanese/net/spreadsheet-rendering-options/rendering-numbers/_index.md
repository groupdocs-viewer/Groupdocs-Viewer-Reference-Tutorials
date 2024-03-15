---
title: レンダリング数
linktitle: レンダリング数
second_title: GroupDocs.Viewer .NET API
description: Numbers ファイルをシームレスにレンダリングする場合の Groupdocs.Viewer for .NET の機能を試してください。 HTML、JPG、PNG、PDF に簡単に変換できます。
type: docs
weight: 15
url: /ja/net/spreadsheet-rendering-options/rendering-numbers/
---
## 導入
Groupdocs.Viewer for .NET を使用して Numbers ファイルをレンダリングするためのこのステップバイステップのチュートリアルへようこそ。経験豊富な開発者でも初心者でも、このガイドでは Numbers ドキュメントをさまざまな形式に変換するプロセスを説明します。 Groupdocs.Viewer for .NET は、ドキュメント表示機能を .NET アプリケーションにシームレスに統合できる強力なツールです。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# および .NET 開発の実践的な知識。
-  .NET ライブラリ用の Groupdocs.Viewer がインストールされています。ダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
- 出力ファイルが保存されるドキュメント ディレクトリのパス。
## 名前空間のインポート
C# プロジェクトで、Groupdocs.Viewer ライブラリを使用するために必要な名前空間をインポートしていることを確認します。
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを設定する
レンダリングを開始する前に、変換されたファイルが保存される出力ディレクトリを定義します。 「Your Document Directory」を実際のパスに置き換えます。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: 複数ページの HTML をレンダリングする
次のコードを使用して、Numbers ファイルを複数ページの HTML に変換します。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 3: JPG にレンダリングする
次のコードを使用して、Numbers ファイルを JPG 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 4: PNG にレンダリングする
次のコードを使用して、Numbers ファイルを PNG 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ステップ 5: PDF にレンダリングする
最後に、次のコードを使用して Numbers ファイルを PDF 形式に変換します。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
おめでとう！ Groupdocs.Viewer for .NET を使用して、Numbers ファイルをさまざまな形式にレンダリングすることに成功しました。
## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET を使用して Numbers ファイルをレンダリングする基本について説明しました。この強力なライブラリは、.NET アプリケーションでドキュメントを表示および変換するためのシームレスな統合を提供します。
## よくある質問
### Groupdocs.Viewer for .NET を他のドキュメント タイプで使用できますか?
はい。Groupdocs.Viewer は、Word、Excel、PDF などを含む幅広いドキュメント形式をサポートしています。
### 一時ライセンスはテスト目的で利用できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.groupdocs.com/temporary-license/)テスト用。
### Groupdocs.Viewer for .NET のサポートはどこで見つけられますか?
訪問[Groupdocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)支援とディスカッションのために。
### Groupdocs.Viewer for .NET のフルバージョンを購入するにはどうすればよいですか?
フルバージョンを購入できます[ここ](https://purchase.groupdocs.com/buy).
### 無料の試用版はありますか?
はい、無料試用版を試すことができます[ここ](https://releases.groupdocs.com/).