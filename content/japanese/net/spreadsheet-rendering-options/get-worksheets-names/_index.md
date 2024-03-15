---
title: ワークシート名の取得
linktitle: ワークシート名の取得
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET の魅力を体験してください – ドキュメントの表示をアプリケーションにシームレスに統合します。今すぐ無料トライアルを試してください!
type: docs
weight: 11
url: /ja/net/spreadsheet-rendering-options/get-worksheets-names/
---
## 導入
GroupDocs.Viewer for .NET の魅力的な世界へようこそ! .NET アプリケーション内の強力なドキュメント表示機能を探索することに熱心な開発者や愛好家なら、きっと満足できるでしょう。この包括的なガイドでは、GroupDocs.Viewer を使用したワークシート名の取得の複雑さを詳しく説明します。さあ、シートベルトを締めて、このエキサイティングな旅に出かけましょう!
## 前提条件
コーディングの魔法に入る前に、すべての設定が完了していることを確認しましょう。
1.  GroupDocs.Viewer for .NET をインストールします。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/)GroupDocs.Viewer for .NET の最新バージョンを取得します。インストール手順に従って、開発環境にシームレスに統合します。
2. ドキュメントを準備する: 指定したドキュメント ディレクトリにターゲット ドキュメント (たとえば「file.xlsx」という名前の Excel ファイル) があることを確認します。
## 名前空間のインポート
前提条件が整ったので、必要な名前空間をインポートして作業を開始しましょう。これにより、アプリケーションは GroupDocs.Viewer for .NET によって提供される機能を認識し、利用できるようになります。
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
「Your Document Directory」を、ターゲット ドキュメントが存在するディレクトリへのパスに置き換えます。
## 2. ビューアの初期化
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
このステップでは、Viewer クラスのインスタンスを作成し、Excel ファイルへのパスを提供します。
## 3. 表示情報オプションの構成
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
ここでは、HTML ビューを生成し、スプレッドシート レンダリングの追加オプションを設定するように ViewInfoOptions を構成します。
## 4. ビュー情報の取得
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Viewer インスタンスを使用して、構成されたオプションに基づいてビュー情報を取得します。
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
おめでとう！ GroupDocs.Viewer for .NET を使用してワークシート名を取得するプロセスを正常に完了しました。これにより、アプリケーション内のドキュメント表示機能を強化するための無数の可能性が開かれます。
## よくある質問
### GroupDocs.Viewer for .NET を他のドキュメント形式で使用できますか?
絶対に！ GroupDocs.Viewer は、PDF、Microsoft Office などを含む幅広いドキュメント形式をサポートしています。
### 無料トライアルはありますか?
はい、GroupDocs.Viewer for .NET を使用して探索できます。[無料トライアル](https://releases.groupdocs.com/).
### 追加のサポートはどこで見つけられますか?
に向かう[GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9)コミュニティのサポートとディスカッションのために。
### 仮免許は取得できますか？
確かに！訪問[このリンク](https://purchase.groupdocs.com/temporary-license/)仮免許を取得するためです。
### 利用可能な詳細なドキュメント リソースはありますか?
絶対に！をチェックしてください[公式ドキュメント](https://reference.groupdocs.com/viewer/net/)詳細な情報とガイドについては、こちらをご覧ください。