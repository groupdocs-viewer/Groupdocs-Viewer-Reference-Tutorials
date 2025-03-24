---
title: アーカイブを単一または複数の HTML ページにレンダリングする
linktitle: アーカイブを単一または複数の HTML ページにレンダリングする
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用してアーカイブを HTML ページにレンダリングする方法を学びます。ドキュメント表示機能を .NET アプリケーションに簡単に統合します。
weight: 12
url: /ja/net/rendering-archive-files/render-archives-html/
---

# アーカイブを単一または複数の HTML ページにレンダリングする

## 導入
GroupDocs.Viewer for .NET は、開発者がドキュメント表示機能を .NET アプリケーションに簡単に統合できるようにする強力なドキュメント レンダリング ライブラリです。アーカイブを単一の HTML ページにレンダリングする必要がある場合でも、複数の HTML ページにレンダリングする必要がある場合でも、このチュートリアルでは、そのプロセスを段階的に説明します。
## 前提条件
このチュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
1.  GroupDocs.Viewer for .NET: プロジェクトにライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用に作業用の開発環境をセットアップします。
3. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを準備します。
4. C# の基本的な理解: C# プログラミング言語の基本を理解します。

## 名前空間のインポート
C# コードで、必要な名前空間を必ずインポートしてください。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

GroupDocs.Viewer for .NET を使用してアーカイブを単一または複数の HTML ページにレンダリングするには、次の手順に従います。
## ステップ 1: 出力ディレクトリを設定する
レンダリングされた HTML ページを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ファイル パス形式を定義する
HTML ページのファイル パス形式を指定します。単一ページのレンダリングの場合:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
複数ページのレンダリングの場合:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## ステップ 3: 単一ページの HTML にレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## ステップ 4: 複数ページの HTML をレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; //ページごとに項目を設定する
    viewer.View(options);
}
```
## ステップ 5: 出力を確認する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NET を使用してアーカイブを HTML ページにレンダリングするプロセスは簡単です。このチュートリアルで概説されている手順に従うことで、ドキュメント表示機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### アーカイブ以外のドキュメント形式をレンダリングできますか?
はい。GroupDocs.Viewer は、PDF、DOCX、XLSX、PPTX などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer はデスクトップ アプリケーションと Web アプリケーションの両方に適していますか?
確かに、GroupDocs.Viewer はデスクトップ アプリケーションと Web アプリケーションの両方でシームレスに利用できます。
### GroupDocs.Viewer はビューア インターフェイスのカスタマイズ オプションを提供しますか?
はい、要件に応じてビューア インターフェイスをカスタマイズできます。
### GroupDocs.Viewer を使用してドキュメントを非同期にレンダリングできますか?
はい。GroupDocs.Viewer は、パフォーマンスを向上させるための非同期レンダリング機能を提供します。
### GroupDocs.Viewer はドキュメントの注釈をサポートしていますか?
はい、GroupDocs.Viewer を使用すると、ユーザーはドキュメントの注釈を効率的に表示および管理できます。