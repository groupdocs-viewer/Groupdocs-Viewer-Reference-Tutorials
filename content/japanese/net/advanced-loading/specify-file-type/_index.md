---
"description": "GroupDocs.Viewer for .NET を使用してドキュメントを読み込む際にファイルの種類を指定する方法を学びます。.NET アプリケーションでさまざまな形式を正確にレンダリングします。"
"linktitle": "ドキュメントを読み込むときにファイルの種類を指定する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ドキュメントを読み込むときにファイルの種類を指定する"
"url": "/ja/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# ドキュメントを読み込むときにファイルの種類を指定する

## 導入
GroupDocs.Viewer for .NETは、DOCX、PDF、PPTXなど、幅広いファイル形式をサポートする多用途のドキュメントレンダリングAPIです。ドキュメントの読み込み時にファイルの種類を指定することで、正確なレンダリングとスムーズな閲覧エクスペリエンスをユーザーに提供できます。

![GroupDocs.Viewer for .NET でドキュメントを読み込むときにファイルの種類を指定する](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
- C# および .NET フレームワークに関する基本的な知識。
- Visual Studio がシステムにインストールされています。
- GroupDocs.Viewer for .NETがプロジェクトにインストールされています。ダウンロードはこちらから。 [ここ](https://releases。groupdocs.com/viewer/net/).
##
## 名前空間のインポート
まず、C#コードに必要な名前空間をインポートする必要があります。これらの名前空間は、ドキュメントのレンダリングに必要なクラスとメソッドへのアクセスを提供します。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: 出力ディレクトリを設定する
レンダリングされたドキュメント ページを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ページファイルパスの形式を定義する
ドキュメントの各ページの出力 HTML ファイルに名前を付ける形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ3: 読み込みオプションを指定する
インスタンスを作成する `LoadOptions` クラスを選択し、必要なファイル タイプを設定します。
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## ステップ4: ドキュメントを読み込みレンダリングする
使用 `Viewer` ドキュメントを読み込み、HTML 形式にレンダリングするクラス。
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ5: 成功メッセージを表示する
ドキュメントが正常にレンダリングされたことをユーザーに通知し、出力ファイルの場所を指定します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、ドキュメントを読み込む際にファイルの種類を指定する方法を学びました。これらの簡単な手順に従うだけで、.NETアプリケーションで様々な形式のドキュメントを正確にレンダリングできるようになります。
## よくある質問
### GroupDocs.Viewer for .NET を使用して DOCX 以外のドキュメントをレンダリングできますか?
はい、GroupDocs.Viewer は PDF、PPTX、XLSX など、幅広いファイル形式をサポートしています。
### GroupDocs.Viewer for .NET は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Framework と .NET Core の両方と互換性があります。
### GroupDocs.Viewer によって生成された出力 HTML ファイルをカスタマイズできますか?
はい、API が提供するさまざまなオプションを使用して HTML 出力をカスタマイズできます。
### GroupDocs.Viewer for .NET には外部依存関係が必要ですか?
いいえ、GroupDocs.Viewer for .NET はスタンドアロン ライブラリであり、外部依存関係は必要ありません。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、無料試用版は以下からダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).