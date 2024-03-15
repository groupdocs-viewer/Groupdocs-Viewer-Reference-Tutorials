---
title: 追跡された変更をレンダリングする
linktitle: 追跡された変更をレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、ドキュメント内の追跡された変更を簡単にレンダリングする方法を説明します。文書管理の効率を高めます。
type: docs
weight: 10
url: /ja/net/rendering-word-processing-documents/render-tracked-changes/
---
## 導入
今日のデジタル時代では、ドキュメントを効率的に管理および表示することは、企業にとっても個人にとっても同様に重要です。高度なテクノロジの出現により、GroupDocs.Viewer for .NET などのソリューションは、Word 文書や PDF などのさまざまな文書形式の操作方法に革命をもたらしました。この包括的なガイドでは、GroupDocs.Viewer for .NET を活用して、ドキュメント内の追跡された変更をシームレスに表示する方法を詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. GroupDocs.Viewer for .NET のインストール: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[Webサイト](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: システムに .NET Framework がインストールされていることを確認します。
3. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを準備します。

## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。これらの名前空間は、GroupDocs.Viewer の機能を効果的に利用するために不可欠です。
## 手順:
1. IDE を開く: Visual Studio など、好みの統合開発環境 (IDE) を起動します。
2. プロジェクトを作成または開く: 新しいプロジェクトを開始するか、GroupDocs.Viewer を使用する既存のプロジェクトを開きます。
3. 名前空間のインポート: プロジェクト ファイルまたはコード ファイル内に、次の名前空間を追加します。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、提供された例を複数のステップに分けて、GroupDocs.Viewer for .NET を使用して追跡された変更をレンダリングする手順を説明します。
## ステップ 1: 出力ディレクトリを設定する
まず、レンダリングされた出力を保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
交換する`"Your Document Directory"`目的のディレクトリへのパスを置き換えます。
## ステップ 2: ページ ファイルのパス形式を定義する
ページ ファイル パスの形式を指定します。この形式は、レンダリングされたページの名前と保存方法を決定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ここ、`"page_{0}.html"`ページに次の名前が付けられることを示します`page_1.html`, `page_2.html`、 等々。
## ステップ 3: ビューア オブジェクトを初期化する
を初期化します`Viewer`ドキュメントのパスを引数として渡すことでオブジェクトを取得します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    //コードは次のステップに続きます...
}
```
必ず交換してください`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES`ドキュメントへのパスを含めます。
## ステップ 4: HTML 表示オプションを構成する
HTML 表示オプションを構成して、追跡された変更のレンダリングなどのレンダリング設定をカスタマイズします。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
このステップにより、出力 HTML で追跡された変更をレンダリングできるようになります。
## ステップ 5: ドキュメントをレンダリングする
構成されたオプションを使用してドキュメントをレンダリングします。
```csharp
viewer.View(options);
```
このコマンドは、指定された設定に基づいてレンダリング プロセスを開始します。
## ステップ 6: 出力ディレクトリを表示する
レンダリングされた出力が保存される場所をユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
このメッセージは、レンダリングが成功したことと、出力ファイルの場所をユーザーに通知します。

## 結論
結論として、GroupDocs.Viewer for .NET は、ドキュメント内の追跡された変更を簡単にレンダリングするための強力なソリューションを提供します。この記事で説明するステップバイステップのガイドに従うことで、この機能を .NET アプリケーションにシームレスに統合し、ドキュメント管理の効率を高めることができます。
## よくある質問
### GroupDocs.Viewer for .NET を使用して、追跡された変更をさまざまなドキュメント形式でレンダリングできますか?
はい、GroupDocs.Viewer は、DOCX、PDF などの複数の形式で追跡された変更のレンダリングをサポートしています。
### GroupDocs.Viewer for .NET は、すべての .NET Framework バージョンと互換性がありますか?
はい。GroupDocs.Viewer for .NET は、.NET Framework のさまざまなバージョンと互換性があり、幅広い互換性が保証されています。
### GroupDocs.Viewer はテスト目的で無料トライアルを提供していますか?
はい、購入を決定する前に、GroupDocs.Viewer の無料トライアルを利用してその機能を調べることができます。
### 特定の要件を満たすようにレンダリング設定をカスタマイズできますか?
確かに、GroupDocs.Viewer には広範なカスタマイズ オプションが用意されており、ニーズに応じてレンダリング プロセスを調整できます。
### GroupDocs.Viewer に関して問題が発生したり質問がある場合は、どこに問い合わせればよいですか?
サポートとコミュニティ支援が必要な場合は、次の GroupDocs.Viewer フォーラムにアクセスしてください。[このリンク](https://forum.groupdocs.com/c/viewer/9).