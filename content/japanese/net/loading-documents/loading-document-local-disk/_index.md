---
"description": "Groupdocs.Viewer for .NET を使用して、ローカルディスクからドキュメントをシームレスにレンダリングする方法を学びましょう。効率的なドキュメントで .NET アプリケーションを強化しましょう。"
"linktitle": "ローカルディスクからドキュメントを読み込む"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ローカルディスクからドキュメントを読み込む"
"url": "/ja/net/loading-documents/loading-document-local-disk/"
"weight": 10
type: docs
---
# ローカルディスクからドキュメントを読み込む

## 導入
今日のデジタル時代において、効率的なドキュメントレンダリングは様々なアプリケーションにとって不可欠です。Groupdocs.Viewer for .NETは、ローカルディスクから直接ドキュメントをレンダリングするための強力なソリューションを提供します。このチュートリアルでは、Groupdocs.Viewer for .NETを使用してローカルディスクからドキュメントを読み込む手順を説明します。経験豊富な開発者の方でも、初心者の方でも、このステップバイステップガイドは、ドキュメントレンダリングを.NETアプリケーションにシームレスに統合するのに役立ちます。

![GroupDocs.Viewer .NET を使用してローカル ディスクからドキュメントを読み込む](/viewer/loading-documents/load-documents-from-local-disk.png)

## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. Groupdocs.Viewer for .NET: 最新バージョンをダウンロードしてインストールしてください。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. .NET 開発環境: システムに動作する .NET 開発環境が設定されていることを確認します。
3. ローカル ドキュメント: レンダリングするドキュメントをディスク上にローカルに保存します。

## 名前空間のインポート
まず、Groupdocs.Viewer for .NET の機能にアクセスするために必要な名前空間をインポートしましょう。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ1: ローカルディスクからドキュメントを読み込む
まず、レンダリングされた HTML ページを保存する出力ディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ2: ビューアを初期化してドキュメントをレンダリングする
ドキュメントのパスを使用して Viewer オブジェクトを初期化し、HTML ビュー オプションを使用してレンダリングします。
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ステップ3: 出力を表示する
レンダリングが完了したら、ソース ドキュメントのレンダリングが成功したことと出力ファイルの場所を示すメッセージを表示します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
おめでとうございます！Groupdocs.Viewer for .NETを使ってローカルディスクからドキュメントを読み込む方法を習得しました。この強力なツールは、.NETアプリケーション内でのドキュメントレンダリングの可能性を無限に広げます。
## よくある質問
### Groupdocs.Viewer for .NET を使用して、異なる形式のドキュメントをレンダリングできますか?
はい、Groupdocs.Viewer for .NET は、DOCX、PDF、XLSX、PPTX など、幅広いドキュメント形式をサポートしています。
### Groupdocs.Viewer for .NET はすべての .NET フレームワークと互換性がありますか?
Groupdocs.Viewer for .NET は、.NET Core、.NET Framework、.NET Standard を含むほとんどの .NET フレームワークと互換性があります。
### ドキュメントのレンダリング オプションをカスタマイズできますか?
もちろんです! Groupdocs.Viewer for .NET には、レンダリング プロセスを特定の要件に合わせて調整できる広範なカスタマイズ オプションが用意されています。
### Groupdocs.Viewer for .NET の試用版はありますか?
はい、無料試用版は以下からダウンロードできます。 [ここ](https://releases。groupdocs.com/).
### Groupdocs.Viewer for .NET のサポートや追加リソースはどこで見つかりますか?
サポートと追加リソースについては、Groupdocs.Viewer for .NET をご覧ください。 [フォーラム](https://forum。groupdocs.com/c/viewer/9).