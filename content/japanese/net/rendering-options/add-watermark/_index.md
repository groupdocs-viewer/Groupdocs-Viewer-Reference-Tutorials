---
title: 文書に透かしを追加する
linktitle: 文書に透かしを追加する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用してドキュメントにウォーターマークをシームレスに追加する方法を学びます。このわかりやすいチュートリアルでドキュメントのセキュリティとブランド化を強化します。
type: docs
weight: 10
url: /ja/net/rendering-options/add-watermark/
---
## 導入
今日のデジタル時代では、さまざまなドキュメント形式をシームレスに管理および表示することが、多くの企業や個人にとって同様に必要です。幸いなことに、GroupDocs.Viewer for .NET のようなツールを使用すると、ドキュメントの処理が簡単になります。この強力な .NET ライブラリを使用すると、開発者はドキュメント表示機能をアプリケーションに簡単に統合できるため、ユーザーはドキュメントを作成した元のソフトウェアを必要とせずにドキュメントを表示できるようになります。
## 前提条件
GroupDocs.Viewer for .NET を使用してドキュメントに透かしを追加する前に、次のものが揃っていることを確認してください。
1. 環境セットアップ: .NET Framework または .NET Core がインストールされた開発環境をセットアップします。
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.groupdocs.com/viewer/net/).
3. ドキュメント ファイル: DOCX、PDF など、作業するドキュメント ファイルを準備します。
4. C# の基本知識: コード例を実装するには、C# プログラミング言語に精通している必要があります。

## 名前空間のインポート
GroupDocs.Viewer for .NET を使用してドキュメントにウォーターマークを追加する前に、必要な名前空間を C# コードにインポートしてください。この手順により、ライブラリによって提供されるクラスとメソッドにシームレスにアクセスできるようになります。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

次に、GroupDocs.Viewer for .NET を使用してドキュメントにウォーターマークを追加するプロセスを見てみましょう。透かし機能をアプリケーションにシームレスに統合するには、次の手順に従います。
## ステップ 1: 出力ディレクトリを設定する
```csharp
string outputDirectory = "Your Document Directory";
```
ウォーターマークを適用した後に出力ファイルを保存するディレクトリを指定します。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
レンダリングされたページのファイル パスの形式を設定します。この例では、ページ番号を含む HTML ファイルが生成されます。
## ステップ 3: Viewer オブジェクトをインスタンス化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    //コードは次のステップに続きます...
}
```
Viewer クラスのインスタンスを作成し、ドキュメント ファイルへのパスをパラメータとして渡します。この例では、サンプル DOCX ファイルを使用しています。
## ステップ 4: HTML 表示オプションを構成する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
ドキュメントに追加する透かしテキストなどの HTML 表示オプションを構成します。
## ステップ 5: ウォーターマーク付きのドキュメントを表示する
```csharp
viewer.View(options);
```
Viewer オブジェクトの View メソッドを呼び出し、構成されたオプションを渡します。これにより、指定された透かしを使用してドキュメントがレンダリングされます。
## ステップ 6: 出力ディレクトリのパスを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ドキュメントのレンダリングが成功したことをユーザーに通知し、出力ファイルが保存されるディレクトリを示します。

## 結論
GroupDocs.Viewer for .NET は、プログラムでドキュメントにウォーターマークを追加する便利な方法を提供します。このチュートリアルで概説されている手順に従うことで、透かし機能を .NET アプリケーションにシームレスに統合し、ドキュメントのセキュリティとブランド化を強化できます。
## よくある質問
### 透かしの外観をカスタマイズできますか?
はい、テキスト、フォント、色、サイズ、位置など、透かしのさまざまなプロパティをカスタマイズできます。
### GroupDocs.Viewer はリモート ソースからのドキュメントの表示をサポートしていますか?
はい、GroupDocs.Viewer は、ローカル ストレージおよびリモート URL からのドキュメントの表示をサポートしています。
### GroupDocs.Viewer for .NET の試用版はありますか?
はい、無料試用版を次からダウンロードできます。[ここ](https://releases.groupdocs.com/).
### 文書の複数のページに透かしを追加できますか?
確かに、GroupDocs.Viewer では、ドキュメントの個々のページまたはすべてのページに透かしを追加できます。
### 問題が発生した場合、どうすればサポートや支援を受けることができますか?
 GroupDocs コミュニティ フォーラムからヘルプやサポートを求めることができます。[ここ](https://forum.groupdocs.com/c/viewer/9).