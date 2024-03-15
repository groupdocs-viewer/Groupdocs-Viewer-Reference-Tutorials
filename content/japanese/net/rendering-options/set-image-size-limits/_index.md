---
title: 画像サイズ制限を設定する
linktitle: 画像サイズ制限を設定する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、.NET アプリケーションで画像サイズの制限を簡単に設定し、ドキュメントの表示エクスペリエンスを向上させる方法を学びます。
type: docs
weight: 21
url: /ja/net/rendering-options/set-image-size-limits/
---
## 導入
GroupDocs.Viewer for .NET は、.NET アプリケーション内でのシームレスなドキュメント表示を容易にするように設計された強力なツールです。その堅牢な機能と直感的なインターフェイスにより、開発者はドキュメント表示機能をプロジェクトに簡単に統合し、ユーザー エクスペリエンスと生産性を向上させることができます。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して画像サイズ制限を設定し、パフォーマンスと効率を維持しながらドキュメントを最適に表示する方法を検討します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  GroupDocs.Viewer for .NET: 必要な GroupDocs.Viewer for .NET ライブラリが開発環境にインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: Visual Studio などの好みの .NET 開発環境を必要な構成でセットアップします。
3. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを指定し、そのディレクトリ パスがアプリケーション内でアクセスできることを確認します。

## 名前空間のインポート
実装に進む前に、GroupDocs.Viewer for .NET の機能に効果的にアクセスするために必要な名前空間をインポートすることが重要です。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリとファイル パスを定義する
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
必ず交換してください`"Your Document Directory"`ドキュメントディレクトリへの実際のパスを置き換えます。
## ステップ 2: Viewer オブジェクトを初期化し、ドキュメント パスを指定する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    //TestFiles.SAMPLE_DOCX は、サンプル ドキュメントへのパスを表します。
    //これを目的のドキュメントへのパスに置き換えます。
```
交換する`TestFiles.SAMPLE_DOCX`ドキュメントへのパスを含めます。これは、DOCX、PDF、またはその他のサポートされているファイル形式です。
## ステップ 3: JPEG 表示オプションを構成する
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
を調整します。`MaxWidth`プロパティを使用して、要件に応じてレンダリングされたイメージの最大幅を設定します。これにより、画像が指定された幅を超えず、最適な表示が維持されます。
## ステップ 4: 指定されたオプションを使用してドキュメントをレンダリングする
```csharp
viewer.View(options);
```
このコード行はレンダリング プロセスをトリガーし、定義されたサイズ制限で出力イメージを生成します。
## ステップ 5: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
レンダリングが成功すると、正常に完了したことを示すメッセージが出力ディレクトリのパスとともに表示されます。

## 結論
結論として、GroupDocs.Viewer for .NET を使用して画像サイズ制限を設定する技術を習得すると、.NET アプリケーション内でのドキュメントの表示エクスペリエンスを大幅に向上させることができます。このチュートリアルで概説されているステップバイステップのガイドに従うことで、パフォーマンスと効率を確保しながら画像表示を簡単に最適化できます。
## よくある質問
### レンダリングされたイメージの最大幅と最大高さの両方を設定できますか?
はい、表示オプションの適切なプロパティを使用して、最大幅と最大高さの両方を設定できます。
### GroupDocs.Viewer for .NET ではどのようなドキュメント形式がサポートされていますか?
GroupDocs.Viewer for .NET は、DOCX、PDF、PPT、XLS などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer for .NET は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Core との互換性を提供し、最新の .NET アプリケーションへのシームレスな統合を可能にします。
### JPEG以外の出力画像形式をカスタマイズできますか?
はい。GroupDocs.Viewer for .NET は、PNG、TIFF、PDF などのさまざまな出力形式をサポートしています。
### 購入前にテストできる試用版はありますか?
はい、次のサイトから無料試用版を利用できます。[Webサイト](https://releases.groupdocs.com/viewer/net/)。購入する前に、GroupDocs.Viewer for .NET の機能を確認してください。