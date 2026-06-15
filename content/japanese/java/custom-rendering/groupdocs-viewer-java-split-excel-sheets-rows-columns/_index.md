---
date: '2026-06-15'
description: GroupDocs Viewer を使用して、Excel を PDF Java に変換し、Rows と Columns で Excel シートを分割する方法を学びます。セットアップ、コード、best
  practices を含みます。
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel を PDF Java に変換し、Rows と Columns でシートを分割
type: docs
url: /ja/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel を PDF に変換 (Java) と 行と列でシートを分割 (Java)

大規模な Excel ブックは、1 つの画面や印刷ページに快適に表示できる量を超えるデータを含むことがよくあります。**convert excel to pdf java** は、静的で共有可能な形式が必要なときの一般的な要件であり、**splitting Excel sheets by rows and columns** は、データをウェブや印刷レイアウトでより扱いやすくします。本ガイドでは **GroupDocs Viewer for Java** を使用して両方のタスクを実行し、ページネーションの設定方法と、パフォーマンスとトラブルシューティングのベストプラクティスを解説します。

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## クイック回答
- **使用されているライブラリは何ですか？** GroupDocs Viewer for Java.  
- **行と列の両方で分割できますか？** はい。rows‑per‑page と columns‑per‑page を同時に定義できます。  
- **ライセンスは必要ですか？** 開発にはトライアルまたは一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている出力形式は何ですか？** HTML（埋め込みリソース）が表示されます。PDF も同じオプションで生成可能です。  
- **Maven は必須ですか？** Maven は依存関係管理の推奨方法です。  
- **Excel を PDF に変換することもできますか？** もちろんです。`HtmlViewOptions` を `PdfViewOptions` に切り替え、同じページネーション設定を再利用してください。

## 「Excel の分割方法」とは？
Excel シートの分割とは、単一のワークシートを、固定された行数、列数、またはその両方に基づいて複数のページまたはファイルに分割することを意味します。この手法は、ページングされたレポートを作成したり、データをウェブページに埋め込んだり、ブック全体を一度に読み込まずに印刷用セクションを生成したりする際に便利です。

## なぜ GroupDocs Viewer for Java を使用するのか？
GroupDocs Viewer はスプレッドシートを単一パスで処理し、自動的にページネーションを行うため、手動での計算が不要です。**高速レンダリングにより、典型的な 2 コアサーバー上で 250 ページの XLSX ブックブックを 2 秒未満で処理**し、**ライブラリは 50 以上の入力および出力フォーマットをサポート**しています。対応フォーマットには XLS、XLSX、CSV、PDF、HTML などがあります。Windows、Linux、macOS、Docker コンテナ、またはクラウドベースのサーバーレスランタイムなど、JVM 互換プラットフォーム上で動作するため、Java アプリケーションが存在する場所ならどこでも統合可能です。

## 前提条件
- Java 17 以降がインストールされていること。  
- IntelliJ IDEA や Eclipse などの IDE。  
- 依存関係管理のための Maven。  
- 基本的な Java の知識と Excel ファイルの取り扱いに関する知識。

### 必要なライブラリ、バージョン、依存関係
`pom.xml` に GroupDocs リポジトリと viewer 依存関係を追加します。

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

### ライセンス取得
[GroupDocs](https://purchase.groupdocs.com/buy) から無料トライアル、一時ライセンス、またはフルライセンスを取得してください。

## Excel を PDF に変換する方法 (Java)

`Viewer` クラスは、ドキュメントをロードし、さまざまな出力形式向けのレンダリングメソッドを提供する GroupDocs Viewer のコアコンポーネントです。`SpreadsheetOptions` を使用すると、スプレッドシートのレンダリングにおいて rows‑per‑page や columns‑per‑page などのページネーション設定を制御できます。

`new Viewer("source.xlsx")` で Excel ファイルをロードし、ページネーション用に `SpreadsheetOptions` を設定し、`viewer.view(pdfOptions, stream)` を呼び出します。この 1 回の呼び出しで、設定した行/列の制限を考慮しながらブックブックを PDF に変換します。変換は数式、画像、セルスタイルを保持し、配布に適した忠実な PDF コピーを生成します。

## 行で Excel シートを分割する方法

行で分割すると、固定された行数（例：15 行）を含む一連の HTML ページが作成されます。このアプローチは、ビューごとに表示するレコード数を制限したいダッシュボードに最適です。ビューアは `page_0.html`、`page_1.html` などの個別の HTML ファイルを生成し、各ファイルに指定された行数が含まれます。これにより、ウェブインターフェイスで必要な部分だけをロードでき、帯域幅とレンダリング時間を削減できます。

### 定義アンカー
`Viewer` は、ドキュメントをロードし、選択した出力形式へのレンダリングを調整する GroupDocs Viewer のコアクラスです。

### 手順実装

#### 手順 1: パスを設定し Viewer を初期化する
まず、分割ページの保存先を定義し、ソースブックブック用に `Viewer` インスタンスを作成します。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### 手順 2: 1 ページあたりの行数を設定する
各ページに含める行数をビューアに指示します。

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### 手順 3: ドキュメントをレンダリングする
最後に、定義したオプションを使用してブックブックをレンダリングします。

```java
viewer.view(viewOptions);
```

## 行と列で Excel シートを分割する方法

場合によっては、1 ページに行 **と** 列のマトリックス（例：15 行 × 7 列）を表示する必要があります。これにより、各 HTML ページのレイアウトを完全に制御できます。生成されたページは、例えば最初のページで行 1‑15 と列 A‑G、次のページで行 16‑30 と列 H‑N といった矩形のセルブロックを表示します。このグリッド形式のページネーションは、標準用紙サイズに合わせた印刷レポート作成に便利です。

### 定義アンカー
`SpreadsheetOptions` は、生成される各ページに表示する行数と列数を設定します。

### 手順実装

#### 手順 1: パスを設定し Viewer を初期化する
設定は行のみの例と同様で、ファイル名だけが変わります。

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### 手順 2: 1 ページあたりの行数と列数を設定する
グリッド形式の分割を作成するために、両方の次元を指定します。

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### 手順 3: ドキュメントをレンダリングする
同じ `view` 呼び出しでレンダリングします。

```java
viewer.view(options);
```

## 実用的な活用例
- **Generate Excel report Java**: 大規模な財務モデルをページングされた HTML レポートのシリーズに変換します。  
- **GroupDocs Viewer Excel**: 分割ページをウェブポータルに直接埋め込み、インタラクティブなデータ探索を実現します。  
- **Render Excel HTML Java**: 生成された HTML ページをサーブレットまたは Spring コントローラ経由で提供し、クライアント側の高速レンダリングを実現します。  

## パフォーマンス上の考慮点
- **メモリ使用量** – 大規模ブックブックはヒープを大量に消費する可能性があるため、JVM の `-Xmx` 設定を増やすことを検討してください。  
- **チャンクサイズ** – ページサイズとレンダリング速度のバランスを取るように行/列数を選択します。  
- **バージョン更新** – パフォーマンス向上のために GroupDocs Viewer を常に最新に保ちます。最新の 25.2 リリースは、24.x と比較してレンダリング速度を最大 30 % 向上させます。

## よくある問題とトラブルシューティング
| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| `OutOfMemoryError` | ページあたりの行数が多すぎる非常に大きなシートをレンダリングしている | `countRowsPerPage` を減らすか、JVM ヒープを増やしてください |
| 空の出力ファイル | ファイルパスが間違っている、または書き込み権限がない | `outputDirectory` が存在し、書き込み可能であることを確認してください |
| HTML リソースが読み込めない | `forEmbeddedResources` を使用しているが、異なるベース URL からファイルを提供している | 出力フォルダー全体を提供するか、`forExternalResources` に切り替えてください |

## よくある質問

**Q: HTML の代わりに PDF を生成できますか？**  
A: はい。`HtmlViewOptions` を `PdfViewOptions` に置き換え、同じ `SpreadsheetOptions` 設定を保持してください。

**Q: 固定行/列ではなくセルの内容に基づいて分割することは可能ですか？**  
A: コンテンツベースの直接分割は GroupDocs Viewer には組み込まれていませんが、Apache POI でブックブックを前処理し、別々のシートを作成してからレンダリングできます。

**Q: GroupDocs Viewer は古い Excel フォーマット（XLS）をサポートしていますか？**  
A: はい。ビューアは XLS、XLSX、CSV などのスプレッドシート形式を処理します。

**Q: 生成された HTML を Spring MVC のビューに埋め込むにはどうすればよいですか？**  
A: 出力フォルダーを静的リソースとして提供し、Thymeleaf または JSP テンプレートから生成された `page_0.html`、`page_1.html` などを参照してください。

**Q: 商用展開にはどのライセンスが必要ですか？**  
A: GroupDocs のフルプロダクションライセンスが必要です。トライアルライセンスは評価目的のみです。

## リソース
- **ドキュメント**: [GroupDocs Viewer Java ドキュメント](https://docs.groupdocs.com/viewer/java/)
- **API リファレンス**: [GroupDocs API リファレンス](https://reference.groupdocs.com/viewer/java/)
- **ダウンロード**: [GroupDocs Viewer Java リリース](https://releases.groupdocs.com/viewer/java/)
- **購入**: [GroupDocs ライセンス購入](https://purchase.groupdocs.com/buy)
- **無料トライアル**: [GroupDocs 無料トライアル](https://releases.groupdocs.com/viewer/java/)
- **一時ライセンス**: [一時ライセンス取得](https://purchase.groupdocs.com/temporary-license/)
- **サポート**: [GroupDocs サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-06-15  
**テスト環境:** GroupDocs Viewer 25.2 for Java  
**作者:** GroupDocs  

## 関連チュートリアル

- [GroupDocs.Viewer を使用した Java スプレッドシートで非表示行と列をレンダリングする](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [GroupDocs.Viewer を使用した Java で空行のレンダリングをスキップする: パフォーマンスガイド](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [包括的ガイド: GroupDocs.Viewer Java で Excel 2003 XML を HTML/JPG/PNG/PDF に変換](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)