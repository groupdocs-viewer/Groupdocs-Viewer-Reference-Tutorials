---
date: '2026-03-24'
description: GroupDocs.Viewer を使用して、Java でカスタム日時形式で EML を HTML に変換し、タイムゾーンオフセットを設定する方法を学びましょう。メールアーカイブやサポートシステムに最適です。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: GroupDocs.Viewer を使用して Java でカスタム日時を指定しながら EML を HTML に変換する
type: docs
url: /ja/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# JavaでGroupDocs.Viewerを使用したカスタム日時でEMLをHTMLに変換

今日の高速で変化するデジタル世界では、**EMLをHTMLに変換**することを迅速に、かつ適切な日時表示で行えることが、アーカイブ、サポートポータル、法的コンプライアンスにとって不可欠です。このチュートリアルでは、GroupDocs.Viewer for Java を使用してメールメッセージを HTML にレンダリングし、**カスタム日時形式**と**タイムゾーンオフセット**を適用する方法をステップバイステップで解説します。最後まで実装すれば、タイムスタンプが正確で読みやすい再利用可能なソリューションが手に入り、あらゆる**email to HTML Java**ワークフローに最適です。

![GroupDocs.Viewer for Javaでカスタム日時を使用してメールをレンダリング](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**学べること**
- JavaプロジェクトでGroupDocs.Viewerをセットアップする方法  
- 埋め込みリソース付きでメールをHTMLにレンダリングする方法  
- メールメッセージの**日付時刻形式をカスタマイズ**する方法 (custom datetime java)  
- 正しいタイムスタンプのために**タイムゾーンオフセットを設定**する方法 (timezone offset java)  

## クイック回答
- **Can GroupDocs.Viewer convert EML to HTML?** Yes, it renders EML files directly to HTML.  
- **Do I need a license?** A free trial works for testing; a paid license is required for production.  
- **Which Java version is required?** Java 8 or newer.  
- **How do I change the displayed date format?** Use `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Can I adjust the time zone?** Yes, with `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## “EMLをHTMLに変換”とは？
EML ファイルを HTML に変換すると、ヘッダー、本文、添付ファイルを含む生のメールが、ブラウザがプラグインなしで表示できるウェブフレンドリーな形式に変換されます。これにより、メールをウェブアプリケーション、アーカイブ、サポートダッシュボードに簡単に埋め込むことができます。

## このタスクにGroupDocs.Viewerを使用する理由
- **Zero‑dependency rendering** – Outlook や外部メールパーサーは不要です。  
- **Built‑in support for embedded resources** (images, attachments).  
- **Fine‑grained control** over date‑time formatting and timezone handling.  

## 前提条件

- **GroupDocs.Viewer for Java** バージョン 25.2 以上。  
- **Java Development Kit (JDK)** 8 以上 と IDE (IntelliJ IDEA、Eclipse など)。  
- 基本的なJavaの知識とMavenの使用経験。  

## GroupDocs.Viewer for Java の設定

### Maven構成
`pom.xml` に GroupDocs リポジトリと依存関係を追加します:

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
無料トライアルで開始するか、拡張テスト用に一時ライセンスをリクエストしてください。製品版の使用には正式ライセンスが必要です。

### 基本的な初期化
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Javaでカスタム日時を使用してEMLをHTMLに変換

以下のステップバイステップガイドでは、**EMLをHTMLに変換**しながらカスタム日時形式とタイムゾーンオフセットを適用する方法を示します。

### 手順 1: 出力ディレクトリとファイルパスの設定
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*説明:* `Path.of()` は HTML を保存するフォルダーへの参照を作成します。`resolve()` はファイル名を付加します。

### 手順 2: メールファイルでViewerを初期化
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*説明:* `Viewer` インスタンスは変換したい EML ファイルを指します。

### 手順 3: HtmlViewOptionsの設定
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*説明:* `forEmbeddedResources()` は画像やその他リソースを HTML 出力に直接埋め込みます。

### 手順 4: カスタム日時形式の設定 *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*説明:* このパターンは月、日、年、時、分、AM/PM マーカー、そしてタイムゾーンオフセット (`zzz`) を表示します。

### 手順 5: タイムゾーンオフセットの設定 *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*説明:* レンダリングされたタイムスタンプを目的のタイムゾーンに調整します。`"GMT+1"` を任意の有効なゾーン識別子に置き換えてください。

### Javaでメールのタイムゾーンを調整する方法
単純なオフセット以上に**メールタイムゾーンを調整**する必要がある場合（例: サマータイムの変更対応）、`java.util.TimeZone` API から `"Europe/Paris"` や `"America/New_York"` などのリージョン ID を取得し、`setTimeZoneOffset` に渡すことで常に正しいローカル時間が反映されます。

### 手順 6: ドキュメントをレンダリング
```java
viewer.view(options);
```
*説明:* カスタム日時設定が適用された HTML ファイルを生成して変換を実行します。

## トラブルシューティングのヒント
- **FileNotFoundException:** `Viewer` と `Path.of()` で使用されているパスを再確認してください。  
- **Incorrect timestamps:** `TimeZone` ID が対象の地域と一致しているか確認してください。  
- **Missing images:** `HtmlViewOptions.forEmbeddedResources()` を使用したことを確認してください。そうでない場合、外部リソースが含まれない可能性があります。  

## 実用的な応用例
1. **Email Archiving:** コンプライアンスのために検索可能なメールのHTMLスナップショットを保存する。  
2. **Customer Support Portals:** 正確なローカル時間で受信チケットを表示する。  
3. **Legal Documentation:** 標準化されたタイムスタンプ付きの裁判所提出用メール記録を作成する。  

## パフォーマンス上の考慮点
- 大量変換のために専用サーバーにデプロイする。  
- Javaヒープ使用量を監視し、`OutOfMemoryError` が発生した場合は `-Xmx` を増やす。  
- 同じメールが繰り返し要求される場合は、レンダリングされたHTMLをキャッシュする。  

## 結論
GroupDocs.Viewer for Java を使用して、カスタム日時形式とタイムゾーンオフセットを設定した **EMLをHTMLに変換**する完全な本番対応手法が手に入りました。これにより可読性が向上し、タイムスタンプの正確性が保証され、アーカイブやサポートワークフローにシームレスに組み込めます。

**次のステップ:** CSS スタイリング、ページング、PDF 変換など、Viewer の追加オプションを探索して出力をさらにカスタマイズしてください。

## よくある質問

**Q: How do I handle EML files with attachments?**  
A: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`. You can also extract them via the Viewer API if needed.

**Q: Can I change the HTML template or add custom CSS?**  
A: Yes, after rendering you can edit the generated HTML file or inject CSS programmatically before saving.

**Q: Is it possible to render multiple EML files in a batch?**  
A: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions` instance for each file.

**Q: What if I need to support other email formats like MSG?**  
A: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply change the file extension in the `Viewer` constructor.

**Q: Do I need a separate license for each server?**  
A: Licensing is per deployment; consult the GroupDocs licensing guide for multi‑server scenarios.

## リソース

- [ドキュメント](https://docs.groupdocs.com/viewer/java/)
- [APIリファレンス](https://reference.groupdocs.com/viewer/java/)
- [ダウンロード](https://releases.groupdocs.com/viewer/java/)
- [購入](https://purchase.groupdocs.com/buy)
- [無料トライアル](https://releases.groupdocs.com/viewer/java/)
- [一時ライセンス](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-03-24  
**テスト環境:** GroupDocs.Viewer 25.2 (Java)  
**作者:** GroupDocs