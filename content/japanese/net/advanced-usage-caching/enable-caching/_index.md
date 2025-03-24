---
title: キャッシュを有効にしてドキュメント処理を高速化する
linktitle: キャッシュを有効にしてドキュメント処理を高速化する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer では、キャッシュを利用して .NET アプリのドキュメント処理速度を向上させます。パフォーマンスを簡単に最適化します。
weight: 10
url: /ja/net/advanced-usage-caching/enable-caching/
---

# キャッシュを有効にしてドキュメント処理を高速化する

## 導入
.NET ドキュメント処理の領域では、パフォーマンスの最適化が最も重要です。複数のドキュメント ページを迅速にレンダリングする必要があるシナリオを想像してください。ここでキャッシングが登場します。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、キャッシュを活用してドキュメントの処理速度を向上させる方法について詳しく説明します。
## 前提条件
実装に入る前に、次の前提条件が満たされていることを確認してください。
1.  GroupDocs.Viewer for .NET SDK: SDK を次の場所からダウンロードしてインストールします。[GroupDocs.Viewer Web サイト](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: Visual Studio など、好みの .NET 開発環境をセットアップします。
3. サンプル ドキュメント: テスト目的でサンプル ドキュメントを用意します。

## 名前空間のインポート
まず、必要な名前空間をインポートします。
```csharp
using System;
using System.Diagnostics;
using System.IO;
using GroupDocs.Viewer.Caching;
using GroupDocs.Viewer.Options;
```

## ステップ 1: 出力ディレクトリとキャッシュ パスを定義する
```csharp
string outputDirectory = "Your Document Directory";
string cachePath = Path.Combine(outputDirectory, "cache");
```
ここでは、レンダリングされたページが保存される出力ディレクトリとキャッシュ パスを定義します。
## ステップ 2: ファイル キャッシュを初期化する
```csharp
FileCache cache = new FileCache(cachePath);
```
指定されたキャッシュ パスを使用してファイル キャッシュを初期化します。
## ステップ 3: ビューア設定を構成する
```csharp
ViewerSettings settings = new ViewerSettings(cache);
```
ビューア設定を構成し、初期化されたキャッシュを渡します。
## ステップ 4: ビューア インスタンスを初期化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, settings))
```
サンプル ドキュメントと構成された設定を使用してビューア インスタンスを初期化します。
## ステップ 5: HTML 表示オプションを定義する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
ページ ファイルのパス形式を指定して、埋め込みリソースの HTML 表示オプションを定義します。
## ステップ 6: ドキュメントをレンダリングしてパフォーマンスを測定する
```csharp
Stopwatch stopWatch = Stopwatch.StartNew();
viewer.View(options);
stopWatch.Stop();
```
指定されたオプションを使用してドキュメントをレンダリングし、かかった時間を測定します。
## ステップ 7: キャッシュされたデータを再利用してレンダリングを高速化する
```csharp
stopWatch.Restart();
viewer.View(options);
stopWatch.Stop();
```
キャッシュされたデータを使用してドキュメントを再レンダリングし、パフォーマンスの向上を確認します。
## ステップ 8: レンダリングされたドキュメントを出力する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
レンダリングが成功したことと出力ディレクトリの場所をユーザーに通知します。

## 結論
キャッシュは、.NET アプリケーションのドキュメント処理パフォーマンスを最適化する上で重要な役割を果たします。このチュートリアルで概説されている手順に従うことで、GroupDocs.Viewer for .NET でキャッシュを効率的に有効にし、ドキュメントのレンダリングを高速化できます。
## よくある質問
### ドキュメント処理においてキャッシュが重要なのはなぜですか?
キャッシュによりデータを再生成する必要性が減り、処理速度が向上します。
### GroupDocs.Viewer for .NET でキャッシュをカスタマイズできますか?
はい、GroupDocs.Viewer は、特定の要件に応じてキャッシュ設定を柔軟に構成できます。
### GroupDocs.Viewer は大きなドキュメントの処理に適していますか?
確かに、GroupDocs.Viewer はさまざまなサイズのドキュメントを効率的に処理し、最適なパフォーマンスを保証するように設計されています。
### GroupDocs.Viewer は複数のドキュメント形式をサポートしていますか?
はい、GroupDocs.Viewer は、DOCX、PDF、PPTX などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer の一時ライセンスを取得するにはどうすればよいですか?
 GroupDocs.Viewer の一時ライセンスは、[Webサイト](https://purchase.groupdocs.com/temporary-license/).