---
date: '2026-09-30'
description: GroupDocs Viewerを使用してJavaでページを90度回転させる方法を学びます。セットアップ、コード、パフォーマンスのヒントを含みます。
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: GroupDocs Viewerを使用してJavaでページを90度回転させます。ステップバイステップのガイド、パフォーマンスのヒント、開発者向けの実践的なユースケースを紹介します。
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: GroupDocs Viewer for Javaでページを90度回転させる
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: GroupDocs Viewer for Javaでページを90度回転させる
type: docs
url: /ja/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GroupDocs Viewer for Javaでページを90度回転する

ドキュメント（PDF、Word ファイル、スプレッドシートなど）で **ページを90度回転** する必要がある場合、Java でプログラム的に実行すれば時間を節約でき、手動エラーを排除し、操作を自動化パイプラインに組み込むことができます。この上級ガイドでは、**GroupDocs Viewer for Java** を使用して任意のサポート対象ドキュメントの最初のページを回転させる方法、この機能が実務プロジェクトで重要な理由、そしてプロセスを軽量かつメモリ効率的に保つ方法を学びます。

![GroupDocs.Viewer for Javaでドキュメントの最初のページを回転](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## クイック回答
- **「ページを90度回転する」とは何ですか？** 選択したページを時計回りに90度回転させます。  
- **どのライブラリが回転を処理しますか？** GroupDocs Viewer for Java は `rotatePage` メソッドを提供します。  
- **JavaでPDFページを回転できますか？** はい、同じ `rotatePage` 呼び出しを使用します；PDF、DOCX、XLSX などでも機能します。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用可能です；本番環境では有料ライセンスが必要です。  
- **この操作はメモリ集約的ですか？** `Viewer` インスタンスを速やかに閉じれば問題ありません；以下のパフォーマンスヒントをご参照ください。

## 「ページを90度回転する」とは何か
ページを90度回転させると、ページの向きが縦向きから横向き（またはその逆）に変わりますが、コンテンツ自体は変更されません。プレゼンテーションや横向きのみのグラフィック印刷、横向きにスキャンされたドキュメントの修正などに便利です。回転はレンダリング時に適用され、元のファイルは変更されません。

## GroupDocs Viewer for Javaでページをプログラム的に回転する理由
GroupDocs Viewer は **50 以上の入力および出力フォーマット**（PDF、DOCX、PPTX、XLSX、その他多数の画像形式を含む）をサポートしているため、外部コンバータなしで任意のドキュメントをレンダリングできます。API は流暢でスレッドセーフ、Java 8 以降のランタイム上で動作し、数十種類のファイルタイプを一貫して処理するエンタープライズ向け自動化に信頼できる選択肢です。

## 前提条件

- GroupDocs Viewer for Java（最新バージョン）
- JDK 8 以上
- Maven（または Gradle）で依存関係を管理
- IntelliJ IDEA や Eclipse などの IDE
- Java I/O の基本的な知識

## GroupDocs.Viewer for Java の設定

`pom.xml` に GroupDocs リポジトリと依存関係を追加します。このスニペットは元のチュートリアルと同じです：

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
- **無料トライアル** – GroupDocs サイトからダウンロード。  
- **一時ライセンス** – 評価期間を延長したい場合にリクエスト。  
- **フルライセンス** – 本番環境での導入に購入。

### 基本的な Viewer の初期化
`Viewer` クラスはドキュメントを読み込み、レンダリングおよび変換メソッドを提供するエントリーポイントです。コードは以下の通りそのまま使用してください：

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer を使用した Java での PDF ページ回転方法
`Viewer` で対象ファイルを読み込み、ページ番号を指定して `rotatePage` を呼び出します。このメソッドは PDF、DOCX、PPTX、XLSX などライブラリがサポートするすべてのフォーマットで機能します。回転後は、ドキュメントを新しい PDF にレンダリングするか、直接クライアントにストリーム送信でき、元のファイルは変更されません。

## ステップバイステップ実装：最初のページを90度回転

### 1. 必要なパッケージをインポート
`PdfViewOptions` は Viewer に PDF ファイルを出力させる指示を行い、`Rotation` 列挙型は回転角度を定義します。両クラスは `com.groupdocs.viewer.options` パッケージに属します。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 出力先を定義し Viewer を作成
プレースホルダーのパスを実際のディレクトリに置き換えてください。`Viewer` コンストラクタはソースドキュメントを指す `File` オブジェクトを受け取ります。

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF ビューオプションを設定し回転を適用
`rotatePage(int, Rotation)` メソッドは **1 ベース** のページインデックスと `Rotation` 列挙値を受け取ります。この例では `Rotation.ON_90_DEGREE` を使用して最初のページを時計回りに回転させます。

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. ドキュメントをレンダリング
設定したオプションで `view` を呼び出すと、回転された PDF が出力フォルダーに書き込まれます。

```java
viewer.view(viewOptions);
```

#### 動作概要
- **PdfViewOptions** は Viewer に PDF 出力ファイルを生成させます。  
- **rotatePage(int, Rotation)** は指定したページのみを回転させ、他のページは変更しません。  
- このメソッドは 3 つの回転定数をサポートします：`ON_90_DEGREE`、`ON_180_DEGREE`、`ON_270_DEGREE`。

## よくある問題と解決策

| 症状 | 考えられる原因 | 対策 |
|---------|--------------|-----|
| **FileNotFoundException** | パスが間違っているか、フォルダーが存在しません | `YOUR_OUTPUT_DIRECTORY` と `YOUR_DOCUMENT_DIRECTORY` が存在、読み取り可能であることを確認してください。 |
| **Unsupported file format** | Viewer がサポートしていない形式を回転しようとしています | [GroupDocs Viewer supported formats] ページを確認してください。 |
| **No rotation visible** | ページ番号が間違っています（0ベース） | `rotatePage` は **1 ベース** のインデックスを使用することを忘れないでください。 |
| **Out‑of‑memory errors on large docs** | 単一スレッドで多数の大きなファイルをレンダリングしている | ドキュメントを順次処理するか、同時実行数を制限したスレッドプールを使用してください。 |

## 実用的な活用例

1. **プレゼンテーション調整** – 縦向きスライドを横向きにリアルタイムで変換し、視覚的インパクトを向上させます。  
2. **大量ドキュメントの修正** – 横向きにスキャンされた PDF を自動で修正し、手作業の時間を何時間も削減します。  
3. **印刷用出力** – 縦向きの用紙に横向きグラフィックが正しく印刷されるようにし、プリンタードライバーでの手動回転を不要にします。  

## パフォーマンスのヒント

- **リソースを速やかに閉じる** – `try‑with‑resources` ブロックは `Viewer` を自動的に破棄し、メモリを解放します。  
- **バッチ処理** – スレッドごとに単一の `Viewer` インスタンスを再利用して初期化オーバーヘッドを削減します。  
- **メモリ監視** – 100 MB を超えるドキュメントは、全体をメモリに保持せずディスクへストリーム出力してください；GroupDocs Viewer は 200 MB のファイルを 250 MB 未満の RAM で処理できます。  

## よくある質問

**Q: 複数ページを一度に回転できますか？**  
A: はい、回転が必要な各ページ番号に対して `rotatePage()` を呼び出します。ループやチェーン呼び出しで実行できます。

**Q: レンダリング後に回転を元に戻す方法はありますか？**  
A: 直接的な方法はありません。回転オプションなしで再度ドキュメントをレンダリングする必要があります。

**Q: GroupDocs Viewer でページ回転をサポートするファイル形式はどれですか？**  
A: DOCX、PDF、PPTX、XLSX など、公式ドキュメントに記載されている多数の形式です。

**Q: 複数のドキュメントをバッチで自動的に回転させるには？**  
A: ファイルパスのコレクションを反復するループで回転ロジックをラップし、各ファイルに同じ `rotatePage` 設定を適用します。

**Q: 回転中のエラー処理のベストプラクティスは何ですか？**  
A: `Viewer` の使用を `try‑catch` ブロックで囲み、例外の詳細をログに記録し、必要に応じて次のファイルの処理を続行して単一の失敗でバッチ全体が止まらないようにします。

## リソース

- **ドキュメント**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API リファレンス**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **ダウンロード**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **購入**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **無料トライアル**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **一時ライセンス**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **サポート**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-09-30  
**テスト環境:** GroupDocs Viewer 25.2 for Java  
**作者:** GroupDocs

## 関連チュートリアル

- [Java で特定の PDF ページを回転する方法（GroupDocs.Viewer for Java）](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Java で URL からドキュメントをロード – GroupDocs.Viewer チュートリアル](/viewer/java/document-loading/)
- [GroupDocs Viewer Java ドキュメントビュー](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}