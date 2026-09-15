---
date: '2026-09-15'
description: GroupDocs.Viewer for Java を使用して、カスタム datetime フォーマットと timezone offset
  で eml を html に変換する方法を学びましょう。メールアーカイブやサポートポータルに最適です。
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: GroupDocs.Viewer for Java を使用して、カスタム datetime フォーマットと timezone offset
  で eml を html に変換します。正確なメール表示のための step‑by‑step ガイドをご覧ください。
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: GroupDocs.Viewer を使用し、Java でカスタム datetime を指定して eml を html に変換する
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: GroupDocs.Viewer を使用し、Java でカスタム datetime を指定して eml を html に変換する
type: docs
url: /ja/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer を使用した Java でのカスタム日時付き eml から html への変換

最新のサポートおよびアーカイブシステムでは、**eml を html に変換**し、正確なタイムスタンプを保持しながら迅速に処理できることが必須です。このチュートリアルでは、EML メールを HTML にレンダリングし、**カスタム日時形式**を適用し、GroupDocs.Viewer for Java を使用して**タイムゾーンオフセット**を設定する方法を示します。最後まで読むと、任意の **email to html conversion** ワークフローで正確でウェブ対応のメールビューを生成できる再利用可能なスニペットが手に入ります。

![GroupDocs.Viewer for Java を使用したカスタム日時付きメールのレンダリング](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## クイック回答
- **GroupDocs.Viewer は EML を HTML に変換できますか？** はい – API は外部メールクライアントなしで EML ファイルを直接 HTML にレンダリングします。  
- **本番環境でライセンスは必要ですか？** テストには無料トライアルで問題ありませんが、本番展開には有料ライセンスが必要です。  
- **サポートされている Java バージョンは？** Java 8 以降が完全にサポートされています。  
- **表示される日付形式を変更するには？** `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")` を呼び出します。  
- **タイムゾーンを調整できますか？** はい、`options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))` を使用します。

## “convert eml to html” とは？
`Convert eml to html` は、EML メールファイルをブラウザで表示できる HTML ドキュメントに変換するプロセスです。EML ファイルを HTML に変換すると、ヘッダー、本文、添付ファイルを含む生のメールが、プラグイン不要でブラウザが表示できるウェブフレンドリーな形式に変換されます。これにより、メールをウェブアプリケーション、アーカイブ、サポートダッシュボードに簡単に埋め込むことができます。

## このタスクに GroupDocs.Viewer を使用する理由
GroupDocs.Viewer は **50 以上の入力および出力形式** をサポートし、EML、MSG、PST、PDF などを含み、数百ページに及ぶメールでもファイル全体をメモリにロードせずにレンダリングできます。Outlook やサードパーティのパーサーが不要なゼロ依存エンジンにより、**カスタム日時形式**と**タイムゾーンオフセット**を完全に制御しながらリソース使用量を抑えられます。

## 前提条件
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ と Java IDE（IntelliJ IDEA、Eclipse、VS Code）  
- Maven（依存関係管理）

## GroupDocs.Viewer for Java の設定

### Maven 設定
`pom.xml` に GroupDocs リポジトリと Viewer 依存関係を追加します。

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
無料トライアルで開始するか、拡張テスト用に一時ライセンスをリクエストしてください。本番利用にはフルライセンスを購入します。

### 基本的な初期化
変換したい EML ファイルを指す `Viewer` インスタンスを作成します。

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## カスタム日時付きで eml を html に変換する (java)

以下の手順で、EML ファイルを HTML にレンダリングしながらカスタム日時形式とタイムゾーンオフセットを適用します。

### 手順 1: 出力ディレクトリとファイルパスの設定
生成された HTML を保存する場所を定義します。

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*説明:* `Path.of()` は HTML を保存するフォルダーへの参照を作成します。`resolve()` はファイル名を付加します。

### 手順 2: メールファイルでビューアを初期化
対象の EML ファイル用に `Viewer` クラスのインスタンスを作成します。

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*説明:* `Viewer` インスタンスは変換したい EML ファイルを指します。

### 手順 3: HtmlViewOptions の構成
画像やその他のリソースを HTML 出力に直接埋め込む `HtmlViewOptions` オブジェクトを作成します。

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*説明:* `forEmbeddedResources()` は画像やその他のリソースを HTML 出力に直接埋め込みます。

### 手順 4: カスタム日時形式の設定 *(custom datetime java)*
`setDateTimeFormat` はメールのタイムスタンプをレンダリングする際に使用する日付時刻パターンを設定します。  
すべてのタイムスタンプに使用するパターンを定義します。

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*説明:* このパターンは月、日、年、時間、分、AM/PM マーカー、タイムゾーンオフセット（`zzz`）を表示します。

### 手順 5: タイムゾーンオフセットの設定 *(timezone offset java)*
`setTimeZoneOffset` はすべてのメールタイムスタンプに適用するタイムゾーンを指定します。  
希望するタイムゾーンにタイムスタンプを調整します。

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*説明:* レンダリングされたタイムスタンプを希望のタイムゾーンに調整します。`"GMT+1"` を任意の有効なゾーン識別子に置き換えてください。

### Java でメールのタイムゾーンを調整する方法
単純なオフセット以上に **メールタイムゾーンを調整** する必要がある場合（例: サマータイムの変更）には、`java.util.TimeZone` API から `"Europe/Paris"` や `"America/New_York"` などの地域 ID を使用して適切な `TimeZone` オブジェクトを取得し、`setTimeZoneOffset` に渡します。これにより、メールのタイムスタンプは常に正しいローカル時間を反映します。

### 手順 6: ドキュメントのレンダリング
変換を実行し、最終的な HTML ファイルを生成します。

```java
viewer.view(options);
```
*説明:* カスタム日付時刻設定を反映した HTML ファイルを生成して変換を実行します。

## カスタム日時形式はレンダリングされた HTML にどのように影響しますか？
カスタム日時形式は生成された HTML 内の各メールタイムスタンプの表示方法を決定し、可読性とロケール準拠に影響します。`"MMM dd, yyyy hh:mm a zzz"` のようなパターンを指定することで、月の省略形、日、年、時間、分、AM/PM マーカー、明示的なタイムゾーンオフセットが一貫して表示され、グローバルサポートチームにとって重要です。

## GroupDocs.Viewer がメールレンダリングでサポートするファイル形式は？
GroupDocs.Viewer は **EML、MSG、PST、MBOX、EMLX** ファイルを HTML、PDF、PNG、JPEG にレンダリングできます。合計で 50 以上の文書・画像形式をサポートしており、追加のコンバータなしでメールを最も一般的なウェブフレンドリーな出力形式に変換できます。

## 複数の eml ファイルをバッチ変換するには？
すべての EML ファイルを単一ディレクトリに配置し、`for` または `foreach` ループで各ファイルを処理します。同じ `HtmlViewOptions` インスタンスを再利用し、各ファイルに対して `viewer.view` を呼び出すことで、オブジェクト生成のオーバーヘッドを最小化し、バルク変換の速度を向上させます。

## トラブルシューティングのヒント
- **FileNotFoundException:** `Viewer` と `Path.of()` で使用しているパスを確認してください。  
- **Incorrect timestamps:** `TimeZone` ID が対象地域と一致していることを確認してください。  
- **Missing images:** `HtmlViewOptions.forEmbeddedResources()` を使用したか確認してください。使用しない場合、外部リソースが省かれることがあります。  

## 実用的な活用例
1. **メールアーカイブ:** コンプライアンス監査用に検索可能な HTML スナップショットを保存。  
2. **カスタマーサポートポータル:** 世界中のエージェント向けに正確なローカル時間でチケットを表示。  
3. **法的文書化:** 標準化されたタイムスタンプ付きの裁判所提出用メール記録を作成。  

## パフォーマンス上の考慮点
- バルク変換には専用サーバーをデプロイ。  
- Java ヒープ使用量を監視し、`OutOfMemoryError` が発生した場合は `-Xmx` を増やす。  
- 同一メールが頻繁にリクエストされる場合は、生成された HTML をキャッシュして CPU 負荷を削減。  

## 結論
これで、GroupDocs.Viewer for Java を使用して **eml を html に変換**し、カスタム日時形式とタイムゾーンオフセットを設定する完全な本番対応手法が手に入りました。このソリューションは可読性を向上させ、タイムスタンプの正確性を保証し、アーカイブ、サポート、法務ワークフローにシームレスに組み込めます。

**次のステップ:** カスタム CSS の注入、ページネーション、PDF 変換など、Viewer の追加オプションを探索して、アプリケーションの要件に合わせて出力をさらにカスタマイズしてください。

## よくある質問

**Q: 添付ファイル付きの eml ファイルはどう扱いますか？**  
A: `HtmlViewOptions.forEmbeddedResources()` を使用すると添付ファイルは自動的に埋め込まれます。別ファイルとして取得したい場合は Viewer API で抽出可能です。

**Q: HTML テンプレートやカスタム CSS を変更できますか？**  
A: はい、レンダリング後に生成された HTML ファイルを編集するか、保存前にプログラムで CSS を注入できます。

**Q: 複数の eml ファイルをバッチでレンダリングできますか？**  
A: はい、レンダリングロジックをループで囲み、各ファイルに同じ `HtmlViewOptions` インスタンスを再利用してください。

**Q: msg など他のメール形式もサポートしていますか？**  
A: GroupDocs.Viewer は MSG、PST などのメールコンテナもサポートしています。`Viewer` コンストラクタの拡張子を変更するだけで対応できます。

**Q: サーバーごとに別々のライセンスが必要ですか？**  
A: ライセンスはデプロイ単位です。マルチサーバー環境については GroupDocs のライセンスガイドをご参照ください。

## リソース

- [ドキュメント](https://docs.groupdocs.com/viewer/java/)
- [API リファレンス](https://reference.groupdocs.com/viewer/java/)
- [ダウンロード](https://releases.groupdocs.com/viewer/java/)
- [購入](https://purchase.groupdocs.com/buy)
- [無料トライアル](https://releases.groupdocs.com/viewer/java/)
- [一時ライセンス](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-09-15  
**テスト環境:** GroupDocs.Viewer 25.2 (Java)  
**作者:** GroupDocs

## 関連チュートリアル

- [メールを HTML に変換しフィールド名を変更 – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – GroupDocs.Viewer を使用したメールから PDF へのレンダリング最適化](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java のレスポンシブ HTML レンダリング](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
