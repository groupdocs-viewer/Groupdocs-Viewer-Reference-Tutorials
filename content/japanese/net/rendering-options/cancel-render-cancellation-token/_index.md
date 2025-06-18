---
"description": "Groupdocs.Viewer for .NET を .NET プロジェクトにシームレスに統合して、効率的にドキュメントを表示できます。"
"linktitle": "キャンセルトークンを使用してレンダリングをキャンセルする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "キャンセルトークンを使用してレンダリングをキャンセルする"
"url": "/ja/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# キャンセルトークンを使用してレンダリングをキャンセルする

## 導入
Groupdocs.Viewer for .NETは、.NETアプリケーション内でのドキュメントの表示と処理を簡素化するために設計された強力なツールです。PDF、Microsoft Officeドキュメント、その他の一般的な形式のドキュメントを扱う場合でも、このライブラリは強力な機能を提供し、ドキュメント表示機能を.NETプロジェクトにシームレスに統合します。
## 前提条件
Groupdocs.Viewer for .NET の統合に進む前に、次の前提条件が満たされていることを確認してください。
1. インストール: 提供されているサイトからGroupdocs.Viewer for .NETライブラリをダウンロードしてインストールします。 [ダウンロードリンク](https://releases。groupdocs.com/viewer/net/).
   
2. ライセンス: ライセンスを取得する [グループドキュメント](https://purchase.groupdocs.com/buy) ライブラリの潜在能力を最大限に引き出すには、無料トライアルをご利用ください。 [一時ライセンス](https://purchase。groupdocs.com/temporary-license/).
   
3. 開発環境: Visual Studio や任意の他の .NET IDE など、互換性のある開発環境が設定されていることを確認します。

## 名前空間のインポート
Groupdocs.Viewer for .NET を効果的に活用するには、必要な名前空間をプロジェクトにインポートする必要があります。以下の手順に従ってください。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

ここで、理解と実装を深めるために、提供された例を複数のステップに分解してみましょう。
## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
この手順では、レンダリングされたドキュメント ページが保存されるディレクトリを設定します。
## ステップ2: ページファイルパスの形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ここでは、個々のドキュメント ページのファイル パスの形式を定義します。
## ステップ3: CancellationTokenSourceを初期化する
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource は、非同期操作をキャンセルするために使用できる CancellationToken インスタンスを生成するために使用されます。
## ステップ4: キャンセルトークンを取得する
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
このステップでは、レンダリング操作をキャンセルするために使用される CancellationTokenSource からトークンを取得します。
## ステップ5: ドキュメントページのレンダリング
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
ここでは、Task.Run() を使用してドキュメントページのレンダリングを非同期的に開始します。指定されたドキュメントファイル（SAMPLE_DOCX）を使用して Viewer インスタンスが作成され、レンダリングオプションが設定されます。その後、Viewer クラスの View メソッドを使用してレンダリングプロセスが開始されます。
## ステップ6: レンダリングタイムアウトを設定する
```csharp
cancellationTokenSource.CancelAfter(10);
```
このステップでは、レンダリング操作に10ミリ秒のタイムアウトを設定します。操作がこのタイムアウトを超えると、自動的にキャンセルされます。
## ステップ7: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最後に、ドキュメントが正常にレンダリングされたことを示す成功メッセージが表示されます。

## 結論
このチュートリアルでは、Groupdocs.Viewer for .NETをプロジェクトに統合するための基本事項を説明しました。上記の手順に従うことで、ドキュメント表示機能を.NETアプリケーションにシームレスに組み込み、ユーザーエクスペリエンスと生産性を向上させることができます。
## よくある質問
### Groupdocs.Viewer for .NET はすべてのドキュメント形式と互換性がありますか?
Groupdocs.Viewer for .NET は、PDF、Microsoft Office ドキュメント、画像など、幅広いドキュメント形式をサポートしています。
### レンダリングされたドキュメント ページの外観をカスタマイズできますか?
はい、ページ サイズ、品質、透かしなど、レンダリング プロセスのさまざまな側面をカスタマイズできます。
### Groupdocs.Viewer for .NET にはインターネット接続が必要ですか?
いいえ、Groupdocs.Viewer for .NET は .NET 環境内でローカルに動作し、ドキュメントの表示にインターネット接続は必要ありません。
### Groupdocs.Viewer for .NET のテクニカル サポートは受けられますか?
はい、テクニカルサポートは [Groupdocsフォーラム](https://forum.groupdocs.com/c/viewer/9)ここでは、質問したり、問題を報告したり、コミュニティと交流したりできます。
### 購入前に Groupdocs.Viewer for .NET を試すことはできますか?
はい、提供されている無料トライアルから始めることができます。 [体験版](https://releases。groupdocs.com/).