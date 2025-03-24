---
title: ストリームからドキュメントをロードする
linktitle: ストリームからドキュメントをロードする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用してストリームからドキュメントをシームレスにロードする方法を学びます。強力なドキュメント表示機能で .NET アプリケーションを強化します。
weight: 12
url: /ja/net/loading-documents/loading-document-stream/
---

# ストリームからドキュメントをロードする

## 導入
.NET 開発の領域では、ドキュメントを効率的に管理および表示することが最も重要です。高度なツールとライブラリの出現により、かつては困難に思えたタスクが簡素化されています。これらのツールの中でも、GroupDocs.Viewer for .NET は、さまざまなドキュメント形式をシームレスに処理する多用途のソリューションとして際立っています。この包括的なガイドでは、GroupDocs.Viewer for .NET を使用してストリームからドキュメントをロードする際の複雑さを詳しく説明します。経験豊富な開発者であっても、初心者であっても、このチュートリアルでは、GroupDocs.Viewer の力を効果的に活用するための知識を身につけることができます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1. C# と .NET Framework の基本的な理解: C# プログラミング言語と .NET Framework に精通していると、ここで説明する概念を理解するのに役立ちます。
   
2.  GroupDocs.Viewer for .NET のインストール: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[Webサイト](https://releases.groupdocs.com/viewer/net/).
3. IDE: コーディングとテストのために、Visual Studio などの統合開発環境 (IDE) がインストールされています。
4. ドキュメント ストリーム: ロードするドキュメント ストリームを準備します。これは、ファイル ストリームまたはその他の互換性のあるストリーム ソースである可能性があります。

## 名前空間のインポート
ストリームからドキュメントを読み込むコードを実装する前に、必ず必要な名前空間をインポートしてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
レンダリングされたドキュメントが保存されるディレクトリ パスを設定します。
## ステップ 2: ページ ファイルのパス形式を定義する
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
各ページのファイルパスの形式を定義します。ここで、「{0}」はページ番号に置き換えられます。
## ステップ 3: ドキュメント ストリームを取得する
```csharp
Stream stream = GetFileStream();
```
目的のソースからドキュメント ストリームを取得します。これは、ファイル ストリーム、メモリ ストリーム、またはその他の互換性のあるストリームである可能性があります。
## ステップ 4: ビューアを使用してドキュメントをロードする
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
ドキュメント ストリームを使用して Viewer クラスの新しいインスタンスを初期化します。次に、HTML 表示オプションを設定し、ドキュメントをレンダリングします。
## ステップ 5: 出力ディレクトリを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ドキュメントのレンダリングが成功したことをユーザーに通知し、出力が保存される場所を提供します。

## 結論
結論として、GroupDocs.Viewer for .NET は、ストリームからドキュメントを簡単にロードして表示するための堅牢なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、ドキュメント表示機能を .NET アプリケーションにシームレスに統合し、ユーザー エクスペリエンスと生産性を向上させることができます。
## よくある質問
### GroupDocs.Viewer for .NET はさまざまなドキュメント形式を処理できますか?
はい。GroupDocs.Viewer は、PDF、DOCX、XLSX、PPTX などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer for .NET は Web アプリケーションとデスクトップ アプリケーションの両方に適していますか?
絶対に！ GroupDocs.Viewer は、.NET を使用して開発された Web アプリケーションとデスクトップ アプリケーションの両方にシームレスに統合できます。
### GroupDocs.Viewer はドキュメント レンダリングのカスタマイズ オプションを提供しますか?
はい、要件に応じて、透かし、ページ回転、ズーム レベルなど、ドキュメント レンダリングのさまざまな側面をカスタマイズできます。
### GroupDocs.Viewer for .NET を商用プロジェクトで使用できますか?
はい、GroupDocs.Viewer は商用プロジェクトに適したライセンス オプションを提供します。公式からライセンスを購入できます[Webサイト](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET のテクニカル サポートは利用できますか?
はい、次のサイトが提供する専用のサポート フォーラムから技術的なサポートやガイダンスを求めることができます。[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).