---
"description": "GroupDocs.Viewer for .NET を使用してアーカイブを HTML ページにレンダリングする方法を学びましょう。ドキュメント表示機能を .NET アプリケーションに簡単に統合できます。"
"linktitle": "アーカイブを単一または複数の HTML ページにレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "アーカイブを単一または複数の HTML ページにレンダリングする"
"url": "/ja/net/rendering-archive-files/render-archives-html/"
"weight": 12
---

# アーカイブを単一または複数の HTML ページにレンダリングする

## 導入
GroupDocs.Viewer for .NETは、開発者が.NETアプリケーションにドキュメント表示機能を簡単に統合できる強力なドキュメントレンダリングライブラリです。アーカイブを単一のHTMLページにレンダリングする必要がある場合でも、複数のHTMLページにレンダリングする必要がある場合でも、このチュートリアルでは手順を段階的に説明します。
## 前提条件
このチュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
1. GroupDocs.Viewer for .NET: プロジェクトにライブラリがインストールされていることを確認してください。ダウンロードはこちらから行えます。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用の実用的な開発環境をセットアップします。
3. ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを準備します。
4. C# の基本的な理解: C# プログラミング言語の基礎を理解します。

## 名前空間のインポート
C# コードでは、必要な名前空間を必ずインポートしてください。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

GroupDocs.Viewer for .NET を使用してアーカイブを単一または複数の HTML ページにレンダリングするには、次の手順に従います。
## ステップ1: 出力ディレクトリを設定する
レンダリングされた HTML ページを保存するディレクトリを定義します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ファイルパスの形式を定義する
HTMLページのファイルパス形式を指定します。単一ページレンダリングの場合：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
複数ページのレンダリングの場合:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## ステップ3: シングルページHTMLにレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## ステップ4: 複数ページのHTMLにレンダリングする
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // ページあたりの項目数を設定する
    viewer.View(options);
}
```
## ステップ5: 出力を確認する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
GroupDocs.Viewer for .NET を使用してアーカイブを HTML ページにレンダリングするのは簡単です。このチュートリアルで説明する手順に従うことで、ドキュメント表示機能を .NET アプリケーションにシームレスに統合できます。
## よくある質問
### アーカイブ以外のドキュメント形式をレンダリングできますか?
はい、GroupDocs.Viewer は、PDF、DOCX、XLSX、PPTX など、幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer はデスクトップ アプリケーションと Web アプリケーションの両方に適していますか?
はい、GroupDocs.Viewer はデスクトップ アプリケーションと Web アプリケーションの両方でシームレスに利用できます。
### GroupDocs.Viewer では、ビューアー インターフェースのカスタマイズ オプションは提供されていますか?
はい、要件に応じてビューア インターフェイスをカスタマイズできます。
### GroupDocs.Viewer を使用してドキュメントを非同期にレンダリングできますか?
はい、GroupDocs.Viewer はパフォーマンスを向上させる非同期レンダリング機能を提供します。
### GroupDocs.Viewer はドキュメントの注釈をサポートしていますか?
はい、GroupDocs.Viewer を使用すると、ユーザーはドキュメントの注釈を効率的に表示および管理できます。