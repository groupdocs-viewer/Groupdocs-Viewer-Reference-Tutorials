---
"description": "GroupDocs.Viewer for .NET を使用して、レンダリングされたHTMLからフォントを除外する方法を学びましょう。このステップバイステップガイドに従って、シームレスなドキュメント表示を実現しましょう。"
"linktitle": "レンダリングされた HTML からフォントを除外する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "レンダリングされた HTML からフォントを除外する"
"url": "/ja/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
---

# レンダリングされた HTML からフォントを除外する

## 導入
GroupDocs.Viewer for .NETは、開発者が外部依存なしに.NETアプリケーションで50種類以上のドキュメント形式を表示できる強力なドキュメントレンダリングライブラリです。このチュートリアルでは、GroupDocs.Viewerの特定の機能、つまりレンダリングされたHTML出力からフォントを除外する機能に焦点を当てます。 
## 前提条件
始める前に、次のものがあることを確認してください。
1. C# および .NET 開発に関する基本的な理解。
2. GroupDocs.Viewer for .NET がインストールされています。ダウンロードはこちらから [ここ](https://releases。groupdocs.com/viewer/net/).
3. Visual Studio または C# 開発用のその他の IDE。

## 名前空間のインポート
C# コードでは、必要な名前空間を必ず含めてください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ステップ1: 出力ディレクトリを定義する
レンダリングされた HTML ファイルを保存するディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
```
## ステップ2: ページファイルパスの形式を定義する
レンダリングされたドキュメントの個々のページのファイル パスの形式を指定します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ステップ3: ビューアオブジェクトの初期化
レンダリングするドキュメントを使用して Viewer オブジェクトをインスタンス化します。
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // ここにコードを入力してください
}
```
## ステップ4: HTML表示オプションを設定する
埋め込みリソースの形式や除外するフォントなど、HTML レンダリングのオプションを定義します。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## ステップ5: ドキュメントのレンダリング
ドキュメントをレンダリングするには、HTML 表示オプションを Viewer オブジェクトに渡します。
```csharp
viewer.View(options);
```
## ステップ6: レンダリングされたドキュメントの出力場所
レンダリングされた HTML ファイルが保存される場所をユーザーに通知します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、レンダリングされたHTML出力からフォントを除外する方法を学びました。上記の手順に従うことで、レンダリングプロセスを特定の要件に合わせてカスタマイズし、アプリケーションでドキュメントを最適に表示できるようになります。
## よくある質問
### レンダリングされた HTML から複数のフォントを除外できますか?
はい、複数のフォント名を追加できます。 `FontsToExclude` HTML 表示オプションのリスト。
### GroupDocs.Viewer はすべての .NET フレームワークと互換性がありますか?
はい、GroupDocs.Viewer は .NET Framework 4.6.1 以降をサポートしています。
### リモートの保存場所からドキュメントをレンダリングできますか?
はい、GroupDocs.Viewer は、ローカル ストレージだけでなく、リモート ストレージの場所やストリームからのドキュメントのレンダリングもサポートしています。
### GroupDocs.Viewer は HTML 出力のレスポンシブ デザインをサポートしていますか?
はい、HTML ビュー オプションを適切に調整することで、レスポンシブ レンダリングを有効にすることができます。
### GroupDocs.Viewer のテクニカル サポートは受けられますか?
はい、支援を求めたり、議論に参加したりすることができます。 [GroupDocs.Viewer フォーラム](https://forum。groupdocs.com/c/viewer/9).