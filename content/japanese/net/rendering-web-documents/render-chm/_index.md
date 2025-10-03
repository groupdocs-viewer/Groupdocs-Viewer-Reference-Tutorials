---
"description": "GroupDocs.Viewerを使用して.NETでCHMファイルをレンダリングする方法を学びましょう。CHMをHTML、JPG、PNG、PDF形式に簡単に変換できます。"
"linktitle": "CHMファイルのレンダリング"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CHMファイルのレンダリング"
"url": "/ja/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# CHMファイルのレンダリング

## 導入
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して CHM（コンパイル済み HTML ヘルプ）ファイルをレンダリングする方法を説明します。GroupDocs.Viewer for .NET は、強力なドキュメント レンダリング API であり、開発者は外部ソフトウェアをインストールすることなく、.NET アプリケーション内で 170 種類以上のドキュメントを表示できます。

## 前提条件

CHM ファイルのレンダリングに進む前に、次の前提条件が満たされていることを確認してください。

### GroupDocs.Viewer for .NET のインストール

始めるには、GroupDocs.Viewer for .NETをインストールする必要があります。ライブラリは以下からダウンロードできます。 [GroupDocsウェブサイト](https://releases.groupdocs.com/viewer/net/) または、パッケージ マネージャー コンソールで次のコマンドを実行して、NuGet パッケージ マネージャー経由でインストールします。

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

ここで、レンダリング プロセスを複数のステップに分解してみましょう。

## ステップ1: 出力ディレクトリを定義する

レンダリングされたファイルを保存するディレクトリを定義します。

```csharp
string outputDirectory = "Your Document Directory";
```

## ステップ2: HTMLにレンダリングする

CHM ファイルを HTML に変換するには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // すべてのCHMコンテンツを1ページに変換するにはtrueに設定します

    viewer.View(options); // すべてのページを変換する
}
```

## ステップ3: JPGにレンダリングする

CHM ファイルを JPG 画像に変換するには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1、2、3ページのみ変換する
}
```

## ステップ4: PNGにレンダリングする

CHM ファイルを PNG 画像に変換するには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 1、2、3ページのみ変換する
}
```

## ステップ5: PDFにレンダリングする

CHM ファイルを PDF ドキュメントに変換するには、次のコード スニペットを使用します。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // すべてのページを変換する
}
```

## ステップ6: 出力を確認する

レンダリング プロセスが完了したら、指定した出力ディレクトリでレンダリングされたファイルを確認します。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

GroupDocs.Viewer for .NET を使った CHM ファイルのレンダリングは簡単です。このチュートリアルで説明する手順に従うことで、.NET アプリケーション内で CHM ドキュメントを HTML、画像（JPG、PNG）、PDF などの様々な形式に効率的に変換できます。

## よくある質問

### Q1: GroupDocs.Viewer は CHM 以外のドキュメント形式をレンダリングできますか?

A1: はい、GroupDocs.Viewer は、PDF、DOCX、XLSX、PPTX など、170 を超えるドキュメント形式のレンダリングをサポートしています。

### Q2: GroupDocs.Viewer は .NET Core と互換性がありますか?

A2: はい、GroupDocs.Viewer は従来の .NET Framework に加えて .NET Core もサポートしています。

### Q3: さまざまな出力形式のレンダリング オプションをカスタマイズできますか?

A3: はい、GroupDocs.Viewer には、ページ番号の指定、画像品質の設定、出力パスの構成など、レンダリング プロセスをカスタマイズするためのさまざまなオプションが用意されています。

### Q4: GroupDocs.Viewer では、ドキュメントをレンダリングするために外部依存関係が必要ですか?

A4: いいえ、GroupDocs.Viewer はスタンドアロン ライブラリであり、外部依存関係やサードパーティ ソフトウェアのインストールは必要ありません。

### Q5: GroupDocs.Viewer の無料トライアルはありますか?

A5: はい、GroupDocs.Viewerの無料トライアルをご利用いただくには、 [Webサイト](https://releases。groupdocs.com/).