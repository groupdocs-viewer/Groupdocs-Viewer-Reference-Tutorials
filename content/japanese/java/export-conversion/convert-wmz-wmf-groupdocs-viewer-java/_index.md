---
date: '2026-02-18'
description: GroupDocs Viewer for Java を使用して WMZ および WMF ファイルを PDF、HTML、JPG、PNG に変換する方法を学びましょう。このガイドでは、GroupDocs
  Viewer Java と Java によるベクターグラフィックの変換について解説します。
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: GroupDocs Viewer for Java を使用して WMZ を PDF やその他の形式に変換する方法
type: docs
url: /ja/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 for any leftover shortcodes: none besides placeholders.

Make sure to keep code block placeholders exactly as {{CODE_BLOCK_X}}.

Now produce final answer.# GroupDocs Viewer for Java を使用して WMZ を PDF およびその他の形式に変換する方法

WMZ（Web Metafile）および WMF（Windows Metafile）ファイルを、特に **convert WMZ to PDF** のような、より扱いやすい形式に変換するのは、これらのベクターグラフィック形式がピクセルデータではなく描画指示を格納しているため、難しいことがあります。**GroupDocs Viewer for Java** を使用すれば、WMZ/WMF ドキュメントを HTML、JPG、PNG、**PDF**、その他の一般的な形式に数行のコードでレンダリングできます。

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

このチュートリアルでは、ライブラリのセットアップ方法、WMZ/WMF ファイルを目的の出力形式にレンダリングする方法、そして一般的な落とし穴の対処方法を学びます。最後まで読むと、**groupdocs viewer java** を Java アプリケーションに統合し、**java convert vector graphics** を迅速かつ確実に行えるようになります。

## クイック回答
- **What formats can WMZ/WMF be converted to?** HTML、JPG、PNG、PDF が完全にサポートされています。  
- **Do I need a license for development?** 無料トライアルでテストが可能です。商用ライセンスを取得すれば評価制限が解除されます。  
- **Which Java version is required?** Java 8 以降が推奨されます。  
- **Can I render only specific pages?** はい、view options でページ範囲を指定できます。  
- **Is memory usage a concern for large files?** try‑with‑resources を使用し、必要なページだけをレンダリングしてメモリ使用量を抑えてください。

## “convert WMZ to PDF” とは何ですか？

WMZ を PDF に変換するとは、ベクターベースの WMZ ファイルを PDF コンテナ内にラスタライズ（またはベクターデータを保持）することを意味します。PDF はどこでも閲覧可能で、検索可能、印刷可能であるため、WMZ グラフィックのアーカイブや共有に最適です。

## ベクターグラフィックの変換に GroupDocs Viewer for Java を使用する理由
- **High fidelity**: ライブラリは PDF や PNG への出力時に元の描画品質を保持します。  
- **Zero external dependencies**: ネイティブ Windows ライブラリは不要です。JDK があればどのプラットフォームでも動作します。  
- **Simple API**: `Viewer` インスタンスを 1 つ作成し、`view` 呼び出しを 1 回行うだけで変換全体を処理できます。  
- **Scalable**: 単ページのアイコンからマルチページの技術図面まで同様に扱えます。

## 前提条件

### 必要なライブラリ
- **GroupDocs.Viewer for Java** – コアレンダリングエンジンです。  
- Java Development Kit (JDK) 8 以上。

### 環境設定
- IntelliJ IDEA や Eclipse などの IDE。  
- 依存関係管理には Maven（または好みで Gradle）。

### 知識の前提条件
- Java のファイル I/O（`java.nio.file.Path`）に慣れていること。  
- ドキュメントビューアがコンテンツをレンダリングする仕組みの基本的な理解。

## GroupDocs.Viewer for Java の設定

`pom.xml` にリポジトリと依存関係を追加します：

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

> **License tip:** 評価には無料トライアルを使用し、フル機能を有効にするには一時的または購入したライセンスを適用してください。

依存関係が解決したら、各変換ステップで再利用できる `Viewer` インスタンスを作成できます。

## 実装ガイド

HTML、JPG、PNG、PDF の 4 つの変換シナリオを順に解説します。各例は同じパターンに従います—出力パスを定義し、ソース WMZ ファイルで `Viewer` をインスタンス化し、適切な view options を設定し、`view` を呼び出します。

### WMZ/WMF を HTML にレンダリング

#### 概要
HTML 出力により、グラフィックをウェブページに直接埋め込めます。すべてのリソース（画像、CSS）は単一ファイルに含まれます。

**ステップ 1: 出力ディレクトリパスを定義**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**ステップ 2: Viewer を初期化し HTML にレンダリング**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF を JPG にレンダリング

#### 概要
JPG は広くサポートされているラスタ形式で、プレビューやメール添付に最適です。

**ステップ 1: 出力ディレクトリパスを定義**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**ステップ 2: Viewer を初期化し JPG にレンダリング**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF を PNG にレンダリング

#### 概要
PNG は透過をサポートし、異なる背景とブレンドする必要があるグラフィックに最適です。

**ステップ 1: 出力ディレクトリパスを定義**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**ステップ 2: Viewer を初期化し PNG にレンダリング**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF を PDF にレンダリング

#### 概要
PDF はプラットフォームに依存せず、検索可能で、元のレイアウトを保持したドキュメントを提供します。

**ステップ 1: 出力ディレクトリパスを定義**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**ステップ 2: Viewer を初期化し PDF にレンダリング**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## よくある問題と解決策

| 問題 | 原因 | 解決策 |
|-------|-------|----------|
| **OutOfMemoryError** が大きな WMZ ファイルで発生 | Viewer がドキュメント全体をメモリに読み込むため | `PageStreamViewOptions` を使用してページごとにレンダリングするか、JVM ヒープ（`-Xmx`）を増やしてください。 |
| **Missing fonts** が PDF で発生 | ソース WMZ にフォントが埋め込まれていない | 必要なフォントをホストマシンにインストールするか、`FontSettings` でカスタムフォントを指定してください。 |
| **Blank PNG output** が発生 | 出力パスが正しくない、または書き込み権限が不足している | `outputDirectory` が存在し、アプリケーションに書き込み権限があることを確認してください。 |
| **HTML resources not loading** が発生 | `forExternalResources` を使用し、ファイルをコピーしていない | 自己完結型 HTML ファイルにするには `forEmbeddedResources` を使用してください。 |

## よくある質問

**Q: 同じコードで WMF を PNG に変換できますか？**  
A: はい。PNG の例は WMZ と WMF の両方で機能します。`TestFiles.SAMPLE_WMZ` を WMF のソースに置き換えるだけです。

**Q: ページの一部だけを変換することは可能ですか？**  
A: もちろんです。`PdfViewOptions`（または他の形式に対応するオプション）を使用し、レンダリング前に `setPageNumbers(List<Integer>)` を呼び出してください。

**Q: 各出力形式ごとに別々のライセンスが必要ですか？**  
A: いいえ。1 つの GroupDocs Viewer ライセンスで HTML、JPG、PNG、PDF などすべてのサポート形式がカバーされます。

**Q: “java convert vector graphics” がパフォーマンスに与える影響は？**  
A: ベクターからラスタへの変換は CPU に負荷がかかります。大量のバッチ処理では、マルチスレッド化やファイル間で単一の `Viewer` インスタンスを再利用することを検討してください。

**Q: PDF はベクター品質を保持しますか、それともラスタライズされますか？**  
A: WMZ/WMF を PDF に変換する際、GroupDocs Viewer は可能な限りベクター指示を保持し、スケーラブルな PDF を生成します。

## 結論

これで、**GroupDocs Viewer for Java** を使用して **convert WMZ to PDF** やその他の一般的な形式に変換するための、完全な本番対応ガイドが手に入りました。オンデマンドでグラフィックを配信するウェブサービスや、ドキュメントを PDF として保存するアーカイブツールの構築に関わらず、上記の手順で迅速に実装できます。

---

**最終更新日:** 2026-02-18  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs