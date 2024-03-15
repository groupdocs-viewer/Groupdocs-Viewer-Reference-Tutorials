---
title: CHM ファイルをレンダリングする
linktitle: CHM ファイルをレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer を使用して .NET で CHM ファイルをレンダリングする方法を学びます。 CHM を HTML、JPG、PNG、PDF 形式に簡単に変換します。
type: docs
weight: 10
url: /ja/net/rendering-web-documents/render-chm/
---
## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して CHM (コンパイルされた HTML ヘルプ) ファイルをレンダリングする方法を説明します。 GroupDocs.Viewer for .NET は、開発者が外部ソフトウェアをインストールすることなく、.NET アプリケーション内で 170 を超えるドキュメント タイプを表示できる強力なドキュメント レンダリング API です。

## 前提条件

CHM ファイルのレンダリングに入る前に、次の前提条件を満たしていることを確認してください。

### .NET 用 GroupDocs.Viewer のインストール

開始するには、GroupDocs.Viewer for .NET をインストールする必要があります。ライブラリはからダウンロードできます。[GroupDocs Web サイト](https://releases.groupdocs.com/viewer/net/)または、パッケージ マネージャー コンソールで次のコマンドを実行して、NuGet パッケージ マネージャー経由でインストールします。

```bash
Install-Package GroupDocs.Viewer
```

## 名前空間のインポート

必要な名前空間をプロジェクトにインポートしてください。

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

次に、レンダリング プロセスを複数のステップに分けてみましょう。

## ステップ 1: 出力ディレクトリを定義する

レンダリングされたファイルを保存するディレクトリを定義します。

```csharp
string outputDirectory = "Your Document Directory";
```

## ステップ 2: HTML にレンダリングする

CHM ファイルを HTML にレンダリングするには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; //すべての CHM コンテンツを 1 つのページに変換するには、true に設定します。

    viewer.View(options); //すべてのページを変換する
}
```

## ステップ 3: JPG にレンダリングする

CHM ファイルを JPG イメージにレンダリングするには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1、2、3ページのみを変換
}
```

## ステップ 4: PNG にレンダリングする

CHM ファイルを PNG イメージにレンダリングするには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1、2、3ページのみを変換
}
```

## ステップ 5: PDF にレンダリングする

CHM ファイルを PDF ドキュメントにレンダリングするには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //すべてのページを変換する
}
```

## ステップ 6: 出力を確認する

レンダリング プロセスが完了したら、レンダリングされたファイルの指定された出力ディレクトリを確認します。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

GroupDocs.Viewer for .NET を使用して CHM ファイルをレンダリングするプロセスは簡単です。このチュートリアルで概説されている手順に従うことで、.NET アプリケーション内で CHM ドキュメントを HTML、画像 (JPG、PNG)、PDF などのさまざまな形式に効率的に変換できます。

## よくある質問

### Q1: GroupDocs.Viewer は CHM 以外の他のドキュメント形式をレンダリングできますか?

A1: はい、GroupDocs.Viewer は、PDF、DOCX、XLSX、PPTX などを含む 170 を超えるドキュメント形式のレンダリングをサポートしています。

### Q2: GroupDocs.Viewer は .NET Core と互換性がありますか?

A2: はい、GroupDocs.Viewer は従来の .NET Framework に加えて .NET Core もサポートしています。

### Q3: さまざまな出力形式のレンダリング オプションをカスタマイズできますか?

A3: はい。GroupDocs.Viewer には、ページ番号の指定、画質の設定、出力パスの構成など、レンダリング プロセスをカスタマイズするためのさまざまなオプションが用意されています。

### Q4: GroupDocs.Viewer はドキュメントをレンダリングするために外部依存関係を必要としますか?

A4: いいえ、GroupDocs.Viewer はスタンドアロン ライブラリであり、外部の依存関係やサードパーティ ソフトウェアのインストールは必要ありません。

### Q5: GroupDocs.Viewer に利用できる無料トライアルはありますか?

 A5: はい、次のサイトにアクセスして、GroupDocs.Viewer の無料トライアルを利用できます。[Webサイト](https://releases.groupdocs.com/).