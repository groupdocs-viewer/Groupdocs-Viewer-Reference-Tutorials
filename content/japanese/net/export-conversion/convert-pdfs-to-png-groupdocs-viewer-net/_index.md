---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET を使用して、PDF ページを元のサイズを維持しながら PNG 画像に変換する方法を学びます。このガイドでは、セットアップ、構成、ベストプラクティスについて説明します。"
"title": "GroupDocs.Viewer for .NET を使用して PDF を元のサイズのまま PNG に変換する"
"url": "/ja/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# GroupDocs.Viewer for .NET を使用して PDF を元のサイズのまま PNG に変換する

## 導入

PDFファイルを元のページサイズを維持しながらPNG画像に変換することは、高品質なドキュメントのデジタル化やWebコンテンツの作成に不可欠です。このチュートリアルでは、GroupDocs.Viewer for .NETを使用して、PDFページを元のサイズを維持しながらPNGファイルに変換する方法を説明します。

![GroupDocs.Viewer for .NET で PDF を元のサイズのまま PNG に変換する](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**学習内容:**
- プロジェクトで GroupDocs.Viewer for .NET をセットアップして構成する方法
- ページサイズを維持しながらPDFをPNG画像にレンダリングする手順
- 最適なパフォーマンスを実現するための主要な構成オプションとベストプラクティス

このチュートリアルを終える頃には、この機能をアプリケーションにシームレスに統合できるようになります。まずは、始めるために必要な前提条件を確認しましょう。

## 前提条件

プロジェクトに GroupDocs.Viewer for .NET を実装する前に、次の要件が満たされていることを確認してください。

### 必要なライブラリとバージョン
- **.NET 用 GroupDocs.Viewer**: バージョン 25.3.0 以降。

### 環境設定要件
- Visual Studio などの互換性のある開発環境。
- C# プログラミングの基本的な理解。

### 知識の前提条件
- NuGet パッケージ管理に関する知識。
- .NET アプリケーションで PDF および画像処理を扱った経験が多少あること。

これらの前提条件が満たされたら、GroupDocs.Viewer for .NET のセットアップに進むことができます。

## GroupDocs.Viewer for .NET のセットアップ

GroupDocs.Viewer for .NET の使用を開始するには、以下のインストール手順に従ってください。

### NuGet パッケージ マネージャー コンソール経由のインストール
Visual Studio でプロジェクトを開き、次のコマンドを使用します。
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### .NET CLI 経由のインストール
または、次のコマンドで .NET CLI を使用してインストールすることもできます。
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ライセンス取得手順
1. **無料トライアル**試用版をダウンロードするには [GroupDocs ダウンロード](https://releases。groupdocs.com/viewer/net/).
2. **一時ライセンス**一時ライセンスを取得して、全機能を試すには [一時ライセンスページ](https://purchase。groupdocs.com/temporary-license/).
3. **購入**延長使用の場合は、 [購入ページ](https://purchase。groupdocs.com/buy).

### 基本的な初期化とセットアップ
C# プロジェクトで GroupDocs.Viewer for .NET を初期化するには、次の手順に従います。
1. 必要な名前空間をインポートします。
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. 入力 PDF と出力ディレクトリのパスを設定します。
3. 初期化 `Viewer` 次のスニペットに示すように、ソース ドキュメントへのパスに置き換えます。
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## 実装ガイド
このセクションでは、PDF ページを元のサイズを維持しながら PNG 画像としてレンダリングする実装について説明します。

### PDFページを元のページサイズでPNGにレンダリングする
#### 概要
この機能を使用すると、PDF文書の各ページを元のサイズを維持したままPNG画像に変換できます。これは、文書の正確な視覚表現を必要とするアプリケーションに特に役立ちます。

##### ステップ1: パスの設定とビューアの初期化
入力 PDF パスと出力ディレクトリの変数を作成します。
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
初期化する `Viewer` ソースドキュメントのパスを持つクラス:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // コードブロックは次のステップに続きます
}
```
##### ステップ2: PngViewOptionsを構成する
インスタンスを作成する `PngViewOptions`出力画像のファイル名パターンを指定します。
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
各ページを元のサイズでレンダリングするようにビューア オプションを構成します。
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### ステップ3: ドキュメントページのレンダリング
電話する `View` あなたの方法 `Viewer` インスタンスに、設定されたビュー オプションを渡します。
```csharp
viewer.View(viewOptions);
```
### トラブルシューティングのヒント
- パスが正しいこととディレクトリが存在することを確認します。
- 入力ディレクトリからの読み取りと出力ディレクトリへの書き込みに必要な権限があることを確認します。

## 実用的なアプリケーション
1. **文書のデジタル化**アーカイブ PDF ドキュメントをデジタル画像に変換して、アクセスと配布を容易にします。
2. **ウェブポータル**PDF リーダーを必要とせずに、Web サイトでドキュメントのプレビューを表示します。
3. **コンテンツ管理システム（CMS）**: CMS プラットフォームと統合して、大量の PDF コンテンツを効率的に管理および表示します。

## パフォーマンスに関する考慮事項
GroupDocs.Viewer for .NET を使用してアプリケーションのパフォーマンスを最適化するには:
- 大きなファイルを扱う場合は、ドキュメントをチャンク単位で処理してメモリ使用量を制限します。
- レンダリング中にスレッドがブロックされないように、可能な場合は非同期メソッドを使用します。
- 処分する `Viewer` 使用後はすぐにインスタンスを終了してリソースを解放します。

## 結論
このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、PDF ページを元のサイズを維持しながら PNG 画像としてレンダリングする方法を学びました。環境の設定、最適な結果を得るための必要なオプションの設定、そしてこの機能の実用的な応用例について説明しました。

次のステップには、GroupDocs.Viewer で利用可能な他のレンダリング オプションを試したり、ドキュメント管理機能を強化するために GroupDocs.Viewer を大規模なプロジェクトに統合したりすることが含まれます。

## FAQセクション
1. **GroupDocs.Viewer を使用して大きな PDF ファイルを処理する最適な方法は何ですか?**
   - ドキュメントを小さなチャンクで処理し、非同期メソッドを使用してパフォーマンスを維持します。
2. **出力 PNG ファイル名をカスタマイズできますか?**
   - はい、命名パターンを指定することにより、 `PngViewOptions`。
3. **特定のページのみをレンダリングすることは可能ですか?**
   - もちろん、設定できます `PageNumbers` で `PngViewOptions` レンダリングするページを指定します。
4. **GroupDocs.Viewer のライセンスはどのように処理すればよいですか?**
   - オプションには、無料トライアル、一時ライセンス、またはフルライセンスの購入が含まれます。
5. **この設定は Web アプリケーションで使用できますか?**
   - はい、ASP.NET Core やその他の .NET ベースの Web フレームワークでの PDF のサーバー側レンダリングに適しています。

## リソース
- [ドキュメント](https://docs.groupdocs.com/viewer/net/)
- [APIリファレンス](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer をダウンロード](https://releases.groupdocs.com/viewer/net/)
- [ライセンスを購入](https://purchase.groupdocs.com/buy)
- [無料トライアル](https://releases.groupdocs.com/viewer/net/)
- [一時ライセンス](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)