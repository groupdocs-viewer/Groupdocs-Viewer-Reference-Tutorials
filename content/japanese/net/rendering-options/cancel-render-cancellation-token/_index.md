---
title: キャンセルトークンを使用してレンダリングをキャンセルする
linktitle: キャンセルトークンを使用してレンダリングをキャンセルする
second_title: GroupDocs.Viewer .NET API
description: Groupdocs.Viewer for .NET を .NET プロジェクトにシームレスに統合して、ドキュメントを効率的に表示します。
weight: 11
url: /ja/net/rendering-options/cancel-render-cancellation-token/
---

# キャンセルトークンを使用してレンダリングをキャンセルする

## 導入
Groupdocs.Viewer for .NET は、.NET アプリケーション内でのドキュメントの表示と処理を簡素化するように設計された強力なツールです。 PDF、Microsoft Office ドキュメント、その他の一般的な形式を扱う場合でも、このライブラリは、ドキュメント表示機能を .NET プロジェクトにシームレスに統合するための堅牢な機能を提供します。
## 前提条件
Groupdocs.Viewer for .NET の統合に入る前に、次の前提条件が満たされていることを確認してください。
1. インストール: 提供されているから Groupdocs.Viewer for .NET ライブラリをダウンロードしてインストールします。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
   
2. ライセンス: からライセンスを取得します。[グループドキュメント](https://purchase.groupdocs.com/buy)ライブラリの可能性を最大限に引き出します。または、以下を使用して無料トライアルを開始することもできます。[仮免許](https://purchase.groupdocs.com/temporary-license/).
   
3. 開発環境: Visual Studio やその他の任意の .NET IDE など、互換性のある開発環境がセットアップされていることを確認します。

## 名前空間のインポート
Groupdocs.Viewer for .NET を効果的に利用するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順を実行します：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

ここで、理解を深めて実装するために、提供された例を複数のステップに分割してみましょう。
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
このステップでは、レンダリングされたドキュメント ページが保存されるディレクトリを設定します。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ここでは、個々のドキュメント ページのファイル パスの形式を定義します。
## ステップ 3: cancelanceTokenSource を初期化する
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
cancelTokenSource は、非同期操作をキャンセルするために使用できる cancelToken インスタンスを生成するために使用されます。
## ステップ 4: CancelToken を取得する
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
このステップでは、レンダリング操作をキャンセルするために使用されるトークンを cancelTokenSource から取得します。
## ステップ 5: ドキュメント ページをレンダリングする
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
ここでは、Task.Run() を使用してドキュメント ページのレンダリングを非同期的に開始します。指定されたドキュメント ファイル (SAMPLE_DOCX) を使用して Viewer インスタンスが作成され、レンダリング オプションが構成されます。次に、Viewer クラスの View メソッドを使用してレンダリング プロセスが開始されます。
## ステップ 6: レンダリング タイムアウトを設定する
```csharp
cancellationTokenSource.CancelAfter(10);
```
このステップでは、レンダリング操作のタイムアウトを 10 ミリ秒に設定します。操作がこのタイムアウトを超えると、操作は自動的にキャンセルされます。
## ステップ 7: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ドキュメントが正常にレンダリングされたことを示す成功メッセージが表示されます。

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NET をプロジェクトに統合する基本について説明しました。上記の手順に従うことで、ドキュメント表示機能を .NET アプリケーションにシームレスに組み込むことができ、ユーザー エクスペリエンスと生産性が向上します。
## よくある質問
### Groupdocs.Viewer for .NET はすべてのドキュメント形式と互換性がありますか?
Groupdocs.Viewer for .NET は、PDF、Microsoft Office ドキュメント、画像などを含む幅広いドキュメント形式をサポートしています。
### レンダリングされたドキュメント ページの外観をカスタマイズできますか?
はい、ページ サイズ、品質、透かしなど、レンダリング プロセスのさまざまな側面をカスタマイズできます。
### Groupdocs.Viewer for .NET にはインターネット接続が必要ですか?
いいえ、Groupdocs.Viewer for .NET は .NET 環境内でローカルに動作するため、ドキュメントの表示にインターネット接続は必要ありません。
### Groupdocs.Viewer for .NET のテクニカル サポートは利用できますか?
はい、テクニカル サポートは次の方法で利用できます。[グループドキュメントフォーラム](https://forum.groupdocs.com/c/viewer/9)、質問したり、問題を報告したり、コミュニティと交流したりできます。
### 購入する前に Groupdocs.Viewer for .NET を試すことはできますか?
はい、提供されているを使用して無料トライアルを開始できます。[体験版](https://releases.groupdocs.com/).