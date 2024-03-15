---
title: RAR アーカイブをレンダリングする
linktitle: RAR アーカイブをレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、RAR アーカイブを HTML、JPG、PNG、または PDF 形式にレンダリングする方法を学びます。 RAR アーカイブのコンテンツを簡単に表示および共有できます。
type: docs
weight: 13
url: /ja/net/rendering-archive-files/render-rar/
---
## 導入
RAR アーカイブは、複数のファイルやフォルダーを圧縮して 1 つのコンテナーに保存するための一般的な形式です。 RAR アーカイブを HTML、JPG、PNG、PDF などのさまざまな形式にレンダリングすることは、これらのアーカイブのコンテンツを表示または共有するために不可欠な場合があります。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して RAR アーカイブをレンダリングする方法を検討します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET ライブラリを[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
2. サンプル RAR アーカイブ: レンダリングできるサンプル RAR アーカイブを用意します。

## 名前空間のインポート
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: HTML にレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ 3: JPG にレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ 4: PNG にレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ 5: PDF にレンダリングする
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 結論
GroupDocs.Viewer for .NET を使用すると、RAR アーカイブをさまざまな形式にレンダリングすることが簡単になります。このチュートリアルで概説されている手順に従うことで、RAR アーカイブを HTML、JPG、PNG、または PDF 形式に簡単に変換し、そのコンテンツを簡単に表示および共有できるようになります。
## よくある質問
### GroupDocs.Viewer for .NET は暗号化された RAR アーカイブを処理できますか?
はい。GroupDocs.Viewer for .NET は、レンダリング プロセス中に必要なパスワードが指定された場合に、暗号化された RAR アーカイブのレンダリングをサポートします。
### レンダリングされたドキュメントの出力外観をカスタマイズすることはできますか?
絶対に！ GroupDocs.Viewer for .NET は、ユーザーが好みに応じてレンダリングされたドキュメントの外観を調整できるようにする広範なカスタマイズ オプションを提供します。
### GroupDocs.Viewer for .NET は、RAR 以外の他のアーカイブ形式のレンダリングをサポートしていますか?
はい、GroupDocs.Viewer for .NET は、ZIP、TAR、7z などを含むさまざまなアーカイブ形式のレンダリングをサポートしています。
### GroupDocs.Viewer for .NET を Web アプリケーションに統合できますか?
確かに！ GroupDocs.Viewer for .NET は、デスクトップ アプリケーションと Web アプリケーションの両方への統合に適した API を提供します。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、GroupDocs.Viewer for .NET の無料トライアルを次のサイトから利用できます。[Webサイト](https://releases.groupdocs.com/).