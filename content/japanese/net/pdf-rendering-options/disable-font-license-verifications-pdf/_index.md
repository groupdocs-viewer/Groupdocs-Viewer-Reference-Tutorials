---
title: PDF でのフォント ライセンス検証を無効にする
linktitle: PDF でのフォント ライセンス検証を無効にする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用すると、.NET でのシームレスなドキュメント表示機能を利用できるようになります。最小限の依存関係でドキュメントのレンダリングを簡単に統合およびカスタマイズできます。
weight: 12
url: /ja/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---

# PDF でのフォント ライセンス検証を無効にする

## 導入
.NET 開発の領域では、多くのアプリケーションにとってドキュメントの管理と操作が重要な側面となります。 PDF、Word ドキュメント、その他の種類のファイルを表示する場合でも、これらのタスクを効率的に処理する強力なツールが不可欠です。ここで、GroupDocs.Viewer for .NET が活躍します。この強力なライブラリは、開発者にドキュメント表示機能を .NET アプリケーションにシームレスに統合する機能を提供します。
## 前提条件
GroupDocs.Viewer for .NET の使用に入る前に、いくつかの前提条件を満たしている必要があります。
### 1. Visual Studioをインストールする
何よりもまず、システムに Visual Studio がインストールされていることを確認してください。まだダウンロードしていない場合は、Microsoft Web サイトからダウンロードできます。
### 2. .NET 用の GroupDocs.Viewer をダウンロードします。
に向かってください。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/) GroupDocs.Viewer for .NET の最新バージョンを入手します。提供されるインストール手順に従って、開発環境内でセットアップします。
### 3. 一時ライセンスを取得する
開発およびテスト中に GroupDocs.Viewer for .NET の可能性を最大限に引き出すには、一時ライセンスを取得することをお勧めします。以下からリクエストできます[ここ](https://purchase.groupdocs.com/temporary-license/).

## 名前空間のインポート
前提条件を満たしたら、プロジェクトで GroupDocs.Viewer for .NET の利用を開始する準備が整います。まず、必要な名前空間をコードベースにインポートします。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

より明確に理解できるように、提供された例を複数のステップに分けてみましょう。
## ステップ 1: 出力ディレクトリを定義する
まず、レンダリングされたドキュメント ページを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
ドキュメントの個々のページのファイル パスの形式を設定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## ステップ 3: ビューア オブジェクトを初期化する
Viewer クラスのインスタンスを作成し、表示するドキュメントへのパスを渡します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## ステップ 4: HTML 表示オプションを構成する
ドキュメントを HTML として表示するためのオプションを定義し、埋め込みリソース (画像など) の形式を指定します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ステップ 5: フォントのライセンス検証を無効にする
スムーズなレンダリングを確保するには、フォント ライセンスの検証を無効にするオプションを有効にします。
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## ステップ 6: ドキュメントを表示する
Viewer オブジェクトの View メソッドを呼び出し、構成されたオプションを渡します。
```csharp
viewer.View(options);
```
## ステップ 7: 出力ディレクトリを表示する
レンダリングされたドキュメント ページが保存される場所をユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NET は、ドキュメント表示機能を .NET アプリケーションに簡単に統合するための包括的なソリューションを開発者に提供します。このチュートリアルで概説されている手順に従うことで、この強力なライブラリを効果的に利用してドキュメント管理ワークフローを強化できます。
## よくある質問
### GroupDocs.Viewer for .NET は複数のドキュメント形式を処理できますか?
はい。GroupDocs.Viewer は、PDF、Microsoft Word、Excel、PowerPoint などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer for .NET は Web アプリケーションに適していますか?
確かに、GroupDocs.Viewer は、.NET テクノロジを使用して開発されたデスクトップ アプリケーションと Web アプリケーションの両方にシームレスに統合できます。
### GroupDocs.Viewer には追加の依存関係が必要ですか?
いいえ、GroupDocs.Viewer for .NET には最小限の依存関係があり、既存のプロジェクトに簡単に統合できます。
### レンダリングされたドキュメントの外観をカスタマイズできますか?
はい。GroupDocs.Viewer には、特定の要件に合わせてレンダリングされたドキュメントの外観と動作をカスタマイズするためのさまざまなオプションが用意されています。
### GroupDocs.Viewer for .NET のテクニカル サポートは利用できますか?
はい。[フォーラム](https://forum.groupdocs.com/c/viewer/9).