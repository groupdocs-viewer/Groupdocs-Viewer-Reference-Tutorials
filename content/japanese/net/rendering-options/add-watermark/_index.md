---
"description": "GroupDocs.Viewer for .NET を使用して、ドキュメントにシームレスに透かしを追加する方法を学びましょう。このわかりやすいチュートリアルで、ドキュメントのセキュリティとブランディングを強化しましょう。"
"linktitle": "文書に透かしを追加する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "文書に透かしを追加する"
"url": "/ja/net/rendering-options/add-watermark/"
"weight": 10
---

# 文書に透かしを追加する

## 導入
今日のデジタル時代において、様々な形式のドキュメントをシームレスに管理・閲覧することは、多くの企業や個人にとって必要不可欠です。GroupDocs.Viewer for .NETのようなツールがあれば、ドキュメントの取り扱いは容易になります。この強力な.NETライブラリにより、開発者はドキュメント閲覧機能をアプリケーションに簡単に統合することができ、ユーザーはドキュメントを作成した元のソフトウェアを必要とせずにドキュメントを閲覧できるようになります。
## 前提条件
GroupDocs.Viewer for .NET を使用してドキュメントに透かしを追加する前に、次のものを用意してください。
1. 環境のセットアップ: .NET Framework または .NET Core がインストールされた開発環境をセットアップします。
2. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETライブラリを以下のサイトからダウンロードしてインストールします。 [ダウンロードページ](https://releases。groupdocs.com/viewer/net/).
3. ドキュメント ファイル: DOCX、PDF など、作業するドキュメント ファイルを準備します。
4. C# の基礎知識: コード例を実装するには、C# プログラミング言語の知識が必要です。

## 名前空間のインポート
GroupDocs.Viewer for .NET を使用してドキュメントに透かしを追加する前に、C# コードに必要な名前空間をインポートしてください。この手順により、ライブラリが提供するクラスとメソッドにシームレスにアクセスできるようになります。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

それでは、GroupDocs.Viewer for .NET を使用してドキュメントに透かしを追加する手順を順に見ていきましょう。以下の手順に従って、透かし機能をアプリケーションにシームレスに統合してください。
## ステップ1: 出力ディレクトリを設定する
```csharp
string outputDirectory = "Your Document Directory";
```
透かしを適用した後、出力ファイルを保存するディレクトリを指定します。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
レンダリングされるページのファイルパスの形式を設定します。この例では、ページ番号付きのHTMLファイルが生成されます。
## ステップ3: ビューアオブジェクトのインスタンス化
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // コードは次のステップに続きます...
}
```
Viewerクラスのインスタンスを作成し、ドキュメントファイルへのパスをパラメータとして渡します。この例では、サンプルのDOCXファイルを使用しています。
## ステップ4: HTML表示オプションを構成する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
ドキュメントに追加する透かしテキストを含む、HTML 表示オプションを構成します。
## ステップ5: 透かし入りの文書を表示する
```csharp
viewer.View(options);
```
ViewerオブジェクトのViewメソッドを呼び出し、設定されたオプションを渡します。これにより、指定された透かしが入ったドキュメントがレンダリングされます。
## ステップ6: 出力ディレクトリのパスを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ドキュメントのレンダリングが成功したことをユーザーに通知し、出力ファイルが保存されるディレクトリを示します。

## 結論
GroupDocs.Viewer for .NETは、プログラムでドキュメントに透かしを追加する便利な方法を提供します。このチュートリアルで説明する手順に従うことで、透かし機能を.NETアプリケーションにシームレスに統合し、ドキュメントのセキュリティとブランディングを強化できます。
## よくある質問
### 透かしの外観をカスタマイズできますか?
はい、テキスト、フォント、色、サイズ、位置など、透かしのさまざまなプロパティをカスタマイズできます。
### GroupDocs.Viewer はリモート ソースからのドキュメントの表示をサポートしていますか?
はい、GroupDocs.Viewer は、ローカル ストレージとリモート URL からのドキュメントの表示をサポートしています。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、無料試用版は以下からダウンロードできます。 [ここ](https://releases。groupdocs.com/).
### 文書の複数のページに透かしを追加できますか?
はい、GroupDocs.Viewer では、ドキュメントの個々のページまたはすべてのページに透かしを追加できます。
### 問題が発生した場合、どうすればサポートや支援を受けることができますか?
GroupDocsコミュニティフォーラムからヘルプとサポートを求めることができます [ここ](https://forum。groupdocs.com/c/viewer/9).