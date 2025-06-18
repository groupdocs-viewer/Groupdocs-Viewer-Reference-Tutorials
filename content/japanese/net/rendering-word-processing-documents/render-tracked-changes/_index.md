---
"description": "GroupDocs.Viewer for .NET を使って、ドキュメントの変更履歴を簡単に表示する方法をご紹介します。ドキュメント管理の効率性を高めましょう。"
"linktitle": "追跡された変更をレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "追跡された変更をレンダリングする"
"url": "/ja/net/rendering-word-processing-documents/render-tracked-changes/"
"weight": 10
---

# 追跡された変更をレンダリングする

## 導入
今日のデジタル時代において、文書を効率的に管理・閲覧することは、企業にとっても個人にとっても不可欠です。高度なテクノロジーの登場により、GroupDocs.Viewer for .NETのようなソリューションは、Word文書やPDFなど、様々な形式の文書を扱う方法に革命をもたらしました。この包括的なガイドでは、GroupDocs.Viewer for .NETを活用して、文書の変更履歴をシームレスに表示する方法について詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NETのインストール: GroupDocs.Viewer for .NETをダウンロードしてインストールします。 [Webサイト](https://releases。groupdocs.com/viewer/net/).
2. .NET Framework: システムに .NET Framework がインストールされていることを確認します。
3. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを準備します。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。これらの名前空間は、GroupDocs.Viewer の機能を効果的に活用するために不可欠です。
## 手順:
1. IDE を開く: Visual Studio などの好みの統合開発環境 (IDE) を起動します。
2. プロジェクトを作成または開く: GroupDocs.Viewer を使用する新しいプロジェクトを開始するか、既存のプロジェクトを開きます。
3. 名前空間のインポート: プロジェクト ファイルまたはコード ファイル内に、次の名前空間を追加します。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、提供された例を複数の手順に分解して、GroupDocs.Viewer for .NET を使用して追跡された変更をレンダリングする方法について説明します。
## ステップ1: 出力ディレクトリを設定する
まず、レンダリングされた出力を保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
交換する `"Your Document Directory"` 目的のディレクトリへのパスを入力します。
## ステップ2: ページファイルパスの形式を定義する
ページファイルパスの形式を指定します。この形式によって、レンダリングされたページの命名方法と保存方法が決定されます。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ここ、 `"page_{0}.html"` ページの名前が次のように表示されることを示します `page_1.html`、 `page_2.html`、 等々。
## ステップ3: ビューアオブジェクトの初期化
初期化する `Viewer` ドキュメントのパスを引数として渡すことでオブジェクトを作成します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // コードは次のステップに続きます...
}
```
必ず交換してください `TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` ドキュメントへのパスを入力します。
## ステップ4: HTML表示オプションを構成する
追跡された変更のレンダリングなどのレンダリング設定をカスタマイズするには、HTML ビュー オプションを構成します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
この手順により、出力 HTML で追跡された変更をレンダリングできるようになります。
## ステップ5: ドキュメントのレンダリング
設定されたオプションを使用してドキュメントをレンダリングします。
```csharp
viewer.View(options);
```
このコマンドは、指定された設定に基づいてレンダリング プロセスを開始します。
## ステップ6: 出力ディレクトリを表示する
レンダリングされた出力が保存される場所をユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
このメッセージは、レンダリングが成功したことと、出力ファイルの場所をユーザーに通知します。

## 結論
結論として、GroupDocs.Viewer for .NETは、ドキュメントの変更履歴を簡単に表示するための強力なソリューションを提供します。この記事で概説したステップバイステップガイドに従うことで、この機能を.NETアプリケーションにシームレスに統合し、ドキュメント管理の効率性を向上させることができます。
## よくある質問
### GroupDocs.Viewer for .NET を使用して、さまざまなドキュメント形式で追跡された変更をレンダリングできますか?
はい、GroupDocs.Viewer は、DOCX、PDF など、複数の形式での追跡された変更のレンダリングをサポートしています。
### GroupDocs.Viewer for .NET は、すべての .NET Framework バージョンと互換性がありますか?
はい、GroupDocs.Viewer for .NET はさまざまなバージョンの .NET Framework と互換性があり、幅広い互換性が保証されています。
### GroupDocs.Viewer はテスト目的で無料トライアルを提供していますか?
はい、購入を決定する前に、GroupDocs.Viewer の無料トライアルを利用してその機能を調べることができます。
### 特定の要件を満たすようにレンダリング設定をカスタマイズできますか?
はい、GroupDocs.Viewer は広範なカスタマイズ オプションを提供しており、ニーズに応じてレンダリング プロセスをカスタマイズできます。
### GroupDocs.Viewer に関して問題が発生した場合や質問がある場合、どこでサポートを受けられますか?
サポートとコミュニティの支援については、GroupDocs.Viewerフォーラムをご覧ください。 [このリンク](https://forum。groupdocs.com/c/viewer/9).