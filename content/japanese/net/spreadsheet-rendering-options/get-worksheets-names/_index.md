---
"description": "GroupDocs.Viewer for .NET の魔法を体験してください。ドキュメント表示機能をアプリケーションにシームレスに統合できます。今すぐ無料トライアルをお試しください！"
"linktitle": "ワークシート名を取得する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ワークシート名を取得する"
"url": "/ja/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# ワークシート名を取得する

## 導入
GroupDocs.Viewer for .NETの魅力的な世界へようこそ！.NETアプリケーションで強力なドキュメント表示機能を試してみたい開発者や愛好家の方なら、きっと気に入るはずです。この包括的なガイドでは、GroupDocs.Viewerを使ったワークシート名の取得の仕組みを詳しく説明します。さあ、シートベルトを締めて、このエキサイティングな旅に出かけましょう！
## 前提条件
コーディングの魔法に進む前に、すべてがセットアップされていることを確認しましょう。
1. GroupDocs.Viewer for .NETをインストールします。 [ダウンロードリンク](https://releases.groupdocs.com/viewer/net/) GroupDocs.Viewer for .NETの最新バージョンを入手してください。インストール手順に従って、開発環境にシームレスに統合してください。
2. ドキュメントを準備する: 指定したドキュメント ディレクトリに、ターゲット ドキュメント (たとえば、「file.xlsx」という名前の Excel ファイル) があることを確認します。
## 名前空間のインポート
前提条件が整いましたので、必要な名前空間をインポートして作業を開始しましょう。これにより、アプリケーションがGroupDocs.Viewer for .NETが提供する機能を認識し、利用できるようになります。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. ドキュメントディレクトリの設定
```csharp
string outputDirectory = "Your Document Directory";
```
「Your Document Directory」を、ターゲット ドキュメントが配置されているディレクトリへのパスに置き換えます。
## 2. ビューアの初期化
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
この手順では、Excel ファイルへのパスを指定して、Viewer クラスのインスタンスを作成します。
## 3. 表示情報オプションの設定
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
ここでは、ViewInfoOptions を構成して HTML ビューを生成し、スプレッドシートのレンダリング用の追加オプションを設定します。
## 4. ビュー情報の取得
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Viewer インスタンスを利用して、構成されたオプションに基づいてビュー情報を取得します。
## 5. ワークシート名の表示
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
取得したページをループし、各ワークシートの名前をコンソールに出力します。
## 結論
おめでとうございます！GroupDocs.Viewer for .NET を使用してワークシート名を取得するプロセスを無事に完了しました。これにより、アプリケーション内のドキュメント表示機能を拡張するための可能性が無限に広がります。
## よくある質問
### GroupDocs.Viewer for .NET を他のドキュメント形式で使用できますか?
もちろんです! GroupDocs.Viewer は、PDF、Microsoft Office など、幅広いドキュメント形式をサポートしています。
### 無料トライアルはありますか？
はい、GroupDocs.Viewer for .NETを当社の [無料トライアル](https://releases。groupdocs.com/).
### 追加のサポートはどこで受けられますか?
に向かう [GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9) コミュニティのサポートとディスカッションのため。
### 一時ライセンスを取得できますか？
もちろん！ぜひお越しください [このリンク](https://purchase.groupdocs.com/temporary-license/) 一時ライセンスを取得します。
### 詳細なドキュメントリソースはありますか?
まさにその通り！ [公式文書](https://tutorials.groupdocs.com/viewer/net/) 詳しい情報とガイドについてはこちらをご覧ください。