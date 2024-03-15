---
title: ドキュメントをロードするときにファイルの種類を指定する
linktitle: ドキュメントをロードするときにファイルの種類を指定する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用してドキュメントをロードするときにファイルの種類を指定する方法を学習します。 .NET アプリケーションでさまざまな形式を正確にレンダリングします。
type: docs
weight: 10
url: /ja/net/advanced-loading/specify-file-type/
---
## 導入
GroupDocs.Viewer for .NET は、DOCX、PDF、PPTX などの幅広いファイル形式をサポートする多用途のドキュメント レンダリング API です。ドキュメントをロードするときにファイルの種類を指定すると、ユーザーが正確にレンダリングされ、スムーズな表示エクスペリエンスを確保できます。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- C# と .NET Framework の基本的な知識。
- Visual Studio がシステムにインストールされている。
- GroupDocs.Viewer for .NET がプロジェクトにインストールされています。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
##
## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートする必要があります。これらの名前空間は、ドキュメントのレンダリングに必要なクラスとメソッドへのアクセスを提供します。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを設定する
レンダリングされたドキュメント ページを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
ドキュメントの各ページの出力 HTML ファイルに名前を付ける形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: ロード オプションを指定する
のインスタンスを作成します。`LoadOptions`クラスを選択し、目的のファイルタイプを設定します。
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## ステップ 4: ドキュメントをロードしてレンダリングする
使用`Viewer`クラスを使用してドキュメントをロードし、HTML 形式にレンダリングします。
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ 5: 成功メッセージを表示する
ドキュメントが正常にレンダリングされたことをユーザーに通知し、出力ファイルの場所を指定します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、ドキュメントを読み込むときにファイルの種類を指定する方法を学習しました。これらの簡単な手順に従うことで、.NET アプリケーションでさまざまなドキュメント形式を正確にレンダリングできます。
## よくある質問
### GroupDocs.Viewer for .NET を使用して DOCX 以外のドキュメントをレンダリングできますか?
はい。GroupDocs.Viewer は、PDF、PPTX、XLSX などを含む幅広いファイル形式をサポートしています。
### GroupDocs.Viewer for .NET は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Framework と .NET Core の両方と互換性があります。
### GroupDocs.Viewer によって生成された出力 HTML ファイルをカスタマイズできますか?
はい、API が提供するさまざまなオプションを使用して HTML 出力をカスタマイズできます。
### GroupDocs.Viewer for .NET には外部依存関係が必要ですか?
いいえ、GroupDocs.Viewer for .NET はスタンドアロン ライブラリであり、外部の依存関係は必要ありません。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、無料試用版を次からダウンロードできます。[ここ](https://releases.groupdocs.com/viewer/net/).