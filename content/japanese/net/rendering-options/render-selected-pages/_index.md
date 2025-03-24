---
title: 選択したページをレンダリングする
linktitle: 選択したページをレンダリングする
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を使用してドキュメントから選択したページをレンダリングする方法を学びます。コード例を含むステップバイステップのチュートリアル。
weight: 17
url: /ja/net/rendering-options/render-selected-pages/
---

# 選択したページをレンダリングする

## 導入

このチュートリアルでは、Groupdocs.Viewer for .NET を利用してドキュメントから選択したページをレンダリングする方法を詳しく説明します。経験豊富な開発者でも、初心者でも、このステップバイステップのガイドでプロセスを簡単に説明できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

### 1. インストール

開発環境に Groupdocs.Viewer for .NET がインストールされていることを確認してください。そうでない場合は、からダウンロードできます。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).

## 名前空間のインポート

C# コード ファイルで、必要なクラスとメソッドにアクセスするために必要な名前空間をインポートします。これを行うには、`using`指令：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、提供されているコード例を複数のステップに分けてみましょう。

## ステップ 1: 出力ディレクトリを設定する

レンダリングされたページを保存するディレクトリを定義します。交換する`"Your Document Directory"`目的のディレクトリ パスに置き換えます。

```csharp
string outputDirectory = "Your Document Directory";
```

## ステップ 2: ページ ファイルのパス形式を定義する

レンダリングされるページのファイル パスの形式を指定します。これは、各ページを HTML ファイルとして出力ディレクトリに保存するために使用されます。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## ステップ 3: Viewer オブジェクトをインスタンス化する

Viewer クラスのインスタンスを作成し、レンダリングするドキュメントのパスを引数として渡します。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## ステップ 4: HTML 表示オプションを構成する

レンダリング用の HTML ビュー オプションを設定します。この例では、HTML 出力にリソースを埋め込むオプションを構成しています。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## ステップ 5: 選択したページをレンダリングする

レンダリングするページ番号を指定します。この場合、ページ 1 から 3 をレンダリングします。次に、Viewer オブジェクトの View メソッドを呼び出し、オプションとページ番号を引数として渡します。

```csharp
viewer.View(options, 1, 3);
```

## ステップ6: 結果を出力する

最後に、ドキュメントのレンダリングが成功したことと出力ファイルの保存場所を示すメッセージを表示します。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

おめでとう！ Groupdocs.Viewer for .NET を使用してドキュメントから選択したページをレンダリングする方法を学習しました。この知識があれば、ドキュメント レンダリング機能を .NET アプリケーションに簡単に統合できるようになります。

## よくある質問

### Q: PDF や画像など、さまざまな種類のドキュメントのページをレンダリングできますか?

A: はい、Groupdocs.Viewer for .NET は、PDF、Microsoft Office ドキュメント、画像ファイルなど、さまざまなドキュメント形式からのページのレンダリングをサポートしています。

### Q: 購入前にテストできる試用版はありますか?

 A: はい、Groupdocs.Viewer for .NET の無料試用版には、[Webサイト](https://releases.groupdocs.com/).

### Q: HTML 以外の出力形式をカスタマイズできますか?

A: 確かに、Groupdocs.Viewer for .NET には、HTML に加えて画像、PDF などとしてページをレンダリングするオプションが用意されています。

### Q: テスト目的で一時ライセンスを取得するにはどうすればよいですか?

A: 一時ライセンスは以下から取得できます。[一時ライセンスのページ](https://purchase.groupdocs.com/temporary-license/) Groupdocs Web サイトで。

### Q: 問題が発生した場合、どこに助けを求めればよいですか?

 A: にアクセスできます。[Groupdocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)コミュニティや開発者からのサポートと指導が必要です。