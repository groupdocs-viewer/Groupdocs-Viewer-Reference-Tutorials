---
title: 非表示の列と行をレンダリングする
linktitle: 非表示の列と行をレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用すると、スプレッドシート内の非表示データのロックを簡単に解除できます。ステップバイステップのガイドに従って、隠された列と行を表示します。
weight: 13
url: /ja/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## 導入
ドキュメント視覚化の分野では、GroupDocs.Viewer for .NET は、さまざまなドキュメント形式のシームレスなレンダリングを容易にする堅牢なツールとして優れています。興味深い機能の 1 つは、スプレッドシート内の非表示の列と行を表示する機能です。このチュートリアルでは、この機能を解放し、データの可能性を解き放つ手順を詳しく説明します。
## 前提条件
この旅を開始する前に、次の前提条件が満たされていることを確認してください。
- GroupDocs.Viewer for .NET: 最新バージョンがインストールされていることを確認してください。そうでない場合は、からダウンロードできます。[公式ウェブサイト](https://releases.groupdocs.com/viewer/net/).
- ドキュメント ファイル: 非表示の列と行を実験するために、スプレッドシート形式のサンプル ドキュメント (SAMPLE.XLSX など) を準備します。
- 開発環境: できれば Visual Studio または .NET 開発に適したその他の IDE を使用して、作業環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトで、GroupDocs.Viewer の機能を効果的に活用するために必要な名前空間をインポートします。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを設定する
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
レンダリングされた HTML ページが保存される出力ディレクトリを定義します。それに応じてファイル パスの形式を調整します。
## ステップ 2: ビューアを初期化し、オプションを構成する
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
スプレッドシート ドキュメントへのパスを指定して、Viewer インスタンスを作成します。 HTML 表示オプションを構成してリソースを埋め込み、非表示の列と行のレンダリングを有効にします。
## ステップ 3: レンダリング処理を実行する
```csharp
    viewer.View(options);
}
```
ビューア オブジェクトで View メソッドを呼び出し、構成されたオプションを渡します。これにより、レンダリング プロセスが開始されます。
## ステップ 4: 出力を確認する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ソースドキュメントが正常にレンダリングされたことを確認し、指定されたディレクトリで出力を見つけます。
## 結論
GroupDocs.Viewer for .NET を使用すると、スプレッドシート内の非表示の列と行のロックを解除するのが簡単になります。このチュートリアルでは、隠蔽されたデータを明らかにするための重要な手順を説明し、ドキュメントのより包括的なビューを提供します。
## よくある質問
### スプレッドシート以外のドキュメント形式で非表示の列と行をレンダリングできますか?
はい。GroupDocs.Viewer は、スプレッドシートに加えて、Word、PDF、PowerPoint などのさまざまなドキュメント形式をサポートしています。
### レンダリングできる非表示の列と行の数に制限はありますか?
GroupDocs.Viewer は、広範囲の非表示の列と行のレンダリングを効率的に処理します。ただし、大量の非表示データがある極端な場合は、パフォーマンスに影響を与える可能性があります。
### レンダリングされたデータの出力形式をカスタマイズできますか?
絶対に！ GroupDocs.Viewer には、出力をカスタマイズするための柔軟なオプションが用意されており、レンダリングされたデータを特定のニーズに合わせて調整できます。
### GroupDocs.Viewer を使用する際にライセンスに関する考慮事項はありますか?
はい、使用法に適したライセンスを持っていることを確認してください。ライセンス オプションについては、次のサイトをご覧ください。[GroupDocs の購入](https://purchase.groupdocs.com/buy)または、[仮免許](https://purchase.groupdocs.com/temporary-license/)テスト用。
### どこでサポートを求めたり、GroupDocs コミュニティに連絡してサポートを受けたりできますか?
訪問[GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)サポート、ディスカッション、コミュニティ交流のため。