---
title: PDF でのテキスト選択を無効にする
linktitle: PDF でのテキスト選択を無効にする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して PDF 内のテキスト選択を無効にする方法を学びます。シームレスな統合については、ステップバイステップのガイドに従ってください。
weight: 13
url: /ja/net/pdf-rendering-options/disable-text-selection-pdf/
---
## 導入
GroupDocs.Viewer for .NET は、開発者がドキュメント表示機能を .NET アプリケーションに簡単に統合できるようにする強力なドキュメント レンダリング API です。 GroupDocs.Viewer が提供する重要な機能の 1 つは、PDF ドキュメント内のテキスト選択を無効にする機能です。この機能は、ユーザーが機密文書からテキストをコピーできないようにして、文書のセキュリティと整合性を確保する必要があるシナリオで特に役立ちます。
## 前提条件
GroupDocs.Viewer for .NET を使用して PDF 内のテキスト選択を無効にする方法に関するステップバイステップ ガイドに入る前に、次の前提条件が満たされていることを確認してください。
1.  GroupDocs.Viewer for .NET のインストール: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールしていることを確認します。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
2. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを準備します。 PDF ドキュメントをレンダリングするには、コード スニペットでこのディレクトリを指定する必要があります。

## 名前空間のインポート
まず、GroupDocs.Viewer for .NET が提供する機能にアクセスするために必要な名前空間をインポートする必要があります。その方法は次のとおりです。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、GroupDocs.Viewer for .NET を使用して PDF ドキュメント内のテキスト選択を無効にするプロセスを複数のステップに分けてみましょう。
## ステップ 1: 出力ディレクトリを指定する
```csharp
string outputDirectory = "Your Document Directory";
```
このステップでは、`"Your Document Directory"` PDF ドキュメントが置かれているディレクトリ パスに置き換えます。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
このステップでは、レンダリングされる HTML ページのファイル パスの形式を定義します。 PDF ドキュメントの各ページは、連続したページ番号が付いた HTML ファイルに変換されます。
## ステップ 3: テキスト選択を無効にして PDF ドキュメントをレンダリングする
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
交換する`"Path to Your PDF Document"`PDF ファイルへの実際のパスを含めます。このコード スニペットは、`Viewer`オブジェクトを設定し、リソースを埋め込むための HTML ビュー オプションを構成し、設定によってテキスト選択を無効にします。`RenderTextAsImage`財産を`true`.
## ステップ 4: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
PDF ドキュメントをレンダリングした後、このステップでは、レンダリングされた HTML ページが保存されているディレクトリとともに成功メッセージが表示されます。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して PDF ドキュメント内のテキスト選択を無効にする方法を学習しました。ステップバイステップのガイドに従うことで、この機能を .NET アプリケーションにシームレスに統合して、ドキュメントのセキュリティを確保し、ユーザー エクスペリエンスを向上させることができます。
## よくある質問
### レンダリングされた HTML ページの出力ディレクトリをカスタマイズできますか?
はい、レンダリングされた HTML ページを保存する任意のディレクトリ パスを指定できます。
### GroupDocs.Viewer for .NET は、.NET Framework のさまざまなバージョンと互換性がありますか?
はい、GroupDocs.Viewer for .NET は、.NET Core や .NET Framework などの .NET Framework のさまざまなバージョンと互換性があります。
### テキスト選択を無効にすると、PDF ドキュメントの他の機能に影響しますか?
いいえ、テキスト選択を無効にしても、ユーザーが文書からテキストを選択してコピーできなくなるだけです。他の機能はそのまま残ります。
### ドキュメントのレンダリング後にテキスト選択を再度有効にすることはできますか?
はい、設定するだけでテキスト選択を有効にできます。`RenderTextAsImage`財産を`false` HTML ビューのオプションで。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、GroupDocs.Viewer for .NET の無料トライアルにアクセスできます。[Webサイト](https://releases.groupdocs.com/).