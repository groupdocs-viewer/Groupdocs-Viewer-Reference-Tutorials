---
title: ローカルディスクからドキュメントをロードする
linktitle: ローカルディスクからドキュメントをロードする
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を使用して、ローカル ディスクからドキュメントをシームレスにレンダリングする方法を学びます。効率的なドキュメントで .NET アプリケーションを強化します。
type: docs
weight: 10
url: /ja/net/loading-documents/loading-document-local-disk/
---
## 導入
今日のデジタル時代では、さまざまなアプリケーションにとって効率的なドキュメント レンダリングが不可欠です。 Groupdocs.Viewer for .NET は、ローカル ディスクからドキュメントを直接レンダリングするための強力なソリューションを提供します。このチュートリアルでは、Groupdocs.Viewer for .NET を使用してローカル ディスクからドキュメントをロードするプロセスを説明します。経験豊富な開発者であっても、初心者であっても、このステップバイステップのガイドは、ドキュメント レンダリングを .NET アプリケーションにシームレスに統合するのに役立ちます。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1.  Groupdocs.Viewer for .NET: 最新バージョンを次からダウンロードしてインストールします。[ここ](https://releases.groupdocs.com/viewer/net/).
2. .NET 開発環境: システム上に動作する .NET 開発環境がセットアップされていることを確認してください。
3. ローカル ドキュメント: レンダリングするドキュメントをディスク上にローカルに保存します。

## 名前空間のインポート
まず、Groupdocs.Viewer for .NET の機能にアクセスするために必要な名前空間をインポートしましょう。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: ローカル ディスクからドキュメントをロードする
まず、レンダリングされた HTML ページが保存される出力ディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 2: ビューアを初期化してドキュメントをレンダリングする
Viewer オブジェクトをドキュメントのパスで初期化し、HTML 表示オプションを使用してレンダリングします。
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ 3: 出力を表示する
レンダリングが完了すると、ソース ドキュメントのレンダリングが成功したことと出力ファイルの場所を示すメッセージが表示されます。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
おめでとう！ Groupdocs.Viewer for .NET を使用してローカル ディスクからドキュメントをロードする方法を学習しました。この強力なツールは、.NET アプリケーション内でのドキュメント レンダリングの可能性の世界を開きます。
## よくある質問
### Groupdocs.Viewer for .NET を使用して、さまざまな形式のドキュメントをレンダリングできますか?
はい、Groupdocs.Viewer for .NET は、DOCX、PDF、XLSX、PPTX などを含む幅広いドキュメント形式をサポートしています。
### Groupdocs.Viewer for .NET はすべての .NET フレームワークと互換性がありますか?
Groupdocs.Viewer for .NET は、.NET Core、.NET Framework、.NET Standard を含むほとんどの .NET Framework と互換性があります。
### ドキュメントのレンダリング オプションをカスタマイズできますか?
絶対に！ Groupdocs.Viewer for .NET は、特定の要件に合わせてレンダリング プロセスを調整できる広範なカスタマイズ オプションを提供します。
### Groupdocs.Viewer for .NET の試用版はありますか?
はい、無料試用版を次からダウンロードできます。[ここ](https://releases.groupdocs.com/).
### Groupdocs.Viewer for .NET のサポートや追加リソースはどこで見つけられますか?
サポートと追加リソースについては、Groupdocs.Viewer for .NET にアクセスしてください。[フォーラム](https://forum.groupdocs.com/c/viewer/9).