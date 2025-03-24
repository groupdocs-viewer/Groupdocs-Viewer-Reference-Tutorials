---
title: レンダリングされた HTML からフォントを除外する
linktitle: レンダリングされた HTML からフォントを除外する
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、レンダリングされた HTML からフォントを除外する方法を学びます。シームレスなドキュメント表示については、このステップバイステップのガイドに従ってください。
weight: 10
url: /ja/net/rendering-documents-html/exclude-fonts-html/
---
## 導入
GroupDocs.Viewer for .NET は、開発者が外部の依存関係を必要とせずに .NET アプリケーションで 50 を超えるドキュメント形式を表示できる強力なドキュメント レンダリング ライブラリです。このチュートリアルでは、GroupDocs.Viewer の特定の機能、つまりレンダリングされた HTML 出力からフォントを除外する機能に焦点を当てます。 
## 前提条件
始める前に、次のものが揃っていることを確認してください。
1. C# および .NET 開発の基本的な理解。
2.  .NET 用の GroupDocs.Viewer がインストールされています。からダウンロードできます[ここ](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio または C# 開発用のその他の IDE。

## 名前空間のインポート
C# コードには、必要な名前空間を必ず含めてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ステップ 1: 出力ディレクトリを定義する
レンダリングされた HTML ファイルを保存するディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ 2: ページ ファイルのパス形式を定義する
レンダリングされるドキュメントの個々のページのファイル パスの形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ 3: ビューア オブジェクトを初期化する
レンダリングするドキュメントを使用して Viewer オブジェクトをインスタンス化します。
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    //コードはここに入力します
}
```
## ステップ 4: HTML 表示オプションを設定する
埋め込みリソースの形式や除外するフォントなど、HTML レンダリングのオプションを定義します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## ステップ 5: ドキュメントをレンダリングする
HTML ビュー オプションを Viewer オブジェクトに渡して、ドキュメントをレンダリングします。
```csharp
viewer.View(options);
```
## ステップ 6: レンダリングされたドキュメントの場所を出力する
レンダリングされた HTML ファイルが保存される場所をユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、レンダリングされた HTML 出力からフォントを除外する方法を学習しました。上記の手順に従うことで、特定の要件に合わせてレンダリング プロセスをカスタマイズし、アプリケーションでのドキュメントの最適な表示を確保できます。
## よくある質問
### レンダリングされた HTML から複数のフォントを除外できますか?
はい、複数のフォント名を追加できます。`FontsToExclude` HTML ビュー オプションのリストに表示されます。
### GroupDocs.Viewer はすべての .NET フレームワークと互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework 4.6.1 以降をサポートしています。
### リモートの保管場所からドキュメントをレンダリングできますか?
はい、GroupDocs.Viewer は、ローカル ストレージだけでなく、リモート ストレージの場所やストリームからのドキュメントのレンダリングもサポートしています。
### GroupDocs.Viewer は HTML 出力のレスポンシブ デザインをサポートしていますか?
はい、HTML 表示オプションを適宜調整することで、レスポンシブ レンダリングを有効にすることができます。
### GroupDocs.Viewer のテクニカル サポートは利用できますか?
はい、サポートを求めたり、ディスカッションに参加したりできます。[GroupDocs.Viewer フォーラム](https://forum.groupdocs.com/c/viewer/9).