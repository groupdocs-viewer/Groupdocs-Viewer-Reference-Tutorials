---
title: 不足しているフォントを置換する
linktitle: 不足しているフォントを置換する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer を使用して、.NET ドキュメント内の不足しているフォントを簡単に置き換える方法を学びます。簡単な手順で正確なレンダリングを実現します。
type: docs
weight: 20
url: /ja/net/rendering-options/replace-missing-font/
---
## 導入
.NET 開発の世界では、効率的なドキュメント処理が非常に重要です。 GroupDocs.Viewer for .NET は、.NET アプリケーション内でさまざまなドキュメント形式を表示するための強力なソリューションを提供します。このチュートリアルでは、GroupDocs.Viewer for .NET を使用してドキュメント内の欠落しているフォントを置き換える方法を説明します。 PDF、PowerPoint プレゼンテーション、Word ドキュメントのいずれを扱う場合でも、GroupDocs.Viewer はプロセスを簡素化し、フォントが欠落している場合でもドキュメントが正確に表示されるようにします。
## 前提条件
このチュートリアルに入る前に、次のものが揃っていることを確認してください。
1. GroupDocs.Viewer for .NET: Web サイトから GroupDocs.Viewer ライブラリをダウンロードしてインストールします](https://releases.groupdocs.com/viewer/net/）。
2. 開発環境: Visual Studio などの .NET 開発環境をセットアップします。
3. C# の基本的な知識: C# プログラミング言語と .NET フレームワークに関する知識。

## 名前空間のインポート
C# コードで、GroupDocs.Viewer 機能にアクセスするために必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ここで、GroupDocs.Viewer for .NET を使用してドキュメント内で欠落しているフォントを置換するプロセスを見てみましょう。
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされたドキュメント ページが保存されるディレクトリを設定します。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
出力HTMLファイルに名前を付ける形式を指定します。この例では、各ページは「page」という命名規則に従って HTML ファイルとして保存されます。_{page_number}.html」。
## ステップ 3: ビューア オブジェクトを初期化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Viewer クラスの新しいインスタンスを初期化し、ドキュメント ファイル (この場合は、フォントが欠落している PowerPoint プレゼンテーション) へのパスをパラメーターとして渡します。
## ステップ 4: HTML 表示オプションを設定する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
HtmlViewOptions のインスタンスを作成し、HTML 出力内にリソースを埋め込むように構成します。不足しているフォントの代わりに使用するデフォルトのフォント名を指定します。
## ステップ 5: ドキュメントをレンダリングする
```csharp
viewer.View(options);
```
Viewer オブジェクトの View メソッドを呼び出し、HTML ビュー オプションを渡します。これにより、指定されたオプションを使用してドキュメント ページがレンダリングされます。
## ステップ 6: 出力パスを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ドキュメントのレンダリングが成功したことを示すメッセージを出力し、出力 HTML ファイルが保存されるパスを指定します。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用してドキュメント内の欠落しているフォントを置き換える方法を学習しました。これらの手順に従うことで、特定のフォントが使用できない場合でも、ドキュメントが正確にレンダリングされることを保証できます。 GroupDocs.Viewer はプロセスを簡素化し、フォントの互換性の問題を気にせずに堅牢な .NET アプリケーションの構築に集中できるようにします。
## よくある質問
### GroupDocs.Viewer は他のタイプのフォント関連の問題を処理できますか?
はい。GroupDocs.Viewer は、フォントの置換やフォントの検出など、フォント関連のさまざまな機能を提供します。
### GroupDocs.Viewer はすべての .NET フレームワークと互換性がありますか?
GroupDocs.Viewer は、.NET Core や .NET Standard を含む幅広い .NET フレームワークをサポートします。
### GroupDocs.Viewer のデフォルトのフォント置換をカスタマイズできますか?
もちろん、選択したフォントを、不足しているフォントのデフォルトの代替フォントとして指定することもできます。
### GroupDocs.Viewer はドキュメントのバッチ処理をサポートしていますか?
はい。GroupDocs.Viewer を使用すると、複数のドキュメントを同時に処理できるため、バッチ処理シナリオに最適です。
### GroupDocs.Viewer に関するさらなる支援やサポートはどこで入手できますか?
 GroupDocs.Viewer フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9)サポートやご質問がございましたら。