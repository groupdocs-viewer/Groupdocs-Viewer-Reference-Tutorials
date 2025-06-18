---
"description": "Groupdocs.Viewer for .NET を使用して、ドキュメントから選択したページをレンダリングする方法を学びます。コード例を含むステップバイステップのチュートリアルです。"
"linktitle": "選択したページをレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "選択したページをレンダリング"
"url": "/ja/net/rendering-options/render-selected-pages/"
"weight": 17
---

# 選択したページをレンダリング

## 導入

このチュートリアルでは、Groupdocs.Viewer for .NET を使ってドキュメントから選択したページをレンダリングする方法を詳しく説明します。経験豊富な開発者の方でも、初心者の方でも、このステップバイステップガイドに従えば、簡単に手順を踏むことができます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

### 1. インストール

開発環境にGroupdocs.Viewer for .NETがインストールされていることを確認してください。インストールされていない場合は、以下のリンクからダウンロードできます。 [ダウンロードリンク](https://releases。groupdocs.com/viewer/net/).

## 名前空間のインポート

C#コードファイルで、必要なクラスとメソッドにアクセスするために必要な名前空間をインポートします。これは、 `using` 指令：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、提供されているサンプル コードを複数のステップに分解してみましょう。

## ステップ1: 出力ディレクトリを設定する

レンダリングされたページを保存するディレクトリを定義します。 `"Your Document Directory"` 目的のディレクトリ パスを入力します。

```csharp
string outputDirectory = "Your Document Directory";
```

## ステップ2: ページファイルパスの形式を定義する

レンダリングされたページのファイルパスの形式を指定します。これは、各ページを出力ディレクトリにHTMLファイルとして保存するために使用されます。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## ステップ3: ビューアオブジェクトのインスタンス化

レンダリングするドキュメントのパスを引数として渡して、Viewer クラスのインスタンスを作成します。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## ステップ4: HTML表示オプションを構成する

レンダリング用のHTMLビューオプションを設定します。この例では、HTML出力にリソースを埋め込むオプションを設定しています。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## ステップ5: 選択したページをレンダリングする

レンダリングするページ番号を指定します。この例では、1ページ目から3ページ目をレンダリングします。次に、ViewerオブジェクトのViewメソッドを呼び出し、オプションとページ番号を引数として渡します。

```csharp
viewer.View(options, 1, 3);
```

## ステップ6: 出力結果

最後に、ドキュメントのレンダリングが成功したことと出力ファイルが保存される場所を示すメッセージを表示します。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

おめでとうございます！Groupdocs.Viewer for .NETを使用して、ドキュメントから選択したページをレンダリングする方法を習得しました。この知識があれば、ドキュメントレンダリング機能を.NETアプリケーションに簡単に統合できます。

## よくある質問

### Q: PDF や画像など、さまざまな種類のドキュメントからページをレンダリングできますか?

A: はい、Groupdocs.Viewer for .NET は、PDF、Microsoft Office ドキュメント、画像ファイルなど、さまざまなドキュメント形式のページのレンダリングをサポートしています。

### Q: 購入前にテストできる試用版はありますか?

A: はい、Groupdocs.Viewer for .NETの無料試用版は、 [Webサイト](https://releases。groupdocs.com/).

### Q: HTML 以外の出力形式をカスタマイズできますか?

A: はい、Groupdocs.Viewer for .NET には、HTML に加えて、ページを画像や PDF などでレンダリングするオプションが用意されています。

### Q: テスト目的で一時ライセンスを取得するにはどうすればよいですか?

A: 一時ライセンスは、 [一時ライセンスページ](https://purchase.groupdocs.com/temporary-license/) Groupdocs の Web サイトをご覧ください。

### Q: 問題が発生した場合は、どこでサポートや支援を受けることができますか?

A: 訪問することができます [Groupdocs.Viewerフォーラム](https://forum.groupdocs.com/c/viewer/9) コミュニティと開発者からのサポートとガイダンスのため。