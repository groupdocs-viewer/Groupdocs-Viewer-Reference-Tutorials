---
date: '2026-01-10'
description: GroupDocs.Viewer を使用して、Java でカスタム日時形式で EML を HTML に変換し、タイムゾーンオフセットを設定する方法を学びましょう。メールのアーカイブやサポートシステムに最適です。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: GroupDocs.Viewer を使用した Java でのカスタム日時による EML から HTML への変換
type: docs
url: /ja/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# JavaでGroupDocs.Viewerを使用したカスタム日時でEMLをHTMLに変換

## はじめに

今日の高速なデジタル社会では、**EML を HTML に変換**し、正しい日時表示を行うことが、アーカイブ、サポートポータル、法的コンプライアンスにおいて重要です。このチュートリアルでは、GroupDocs.Viewer for Java を使用してメールメッセージを HTML にレンダリングし、**カスタム日時フォーマット**と**タイムゾーンオフセット**を適用する方法を説明します。最後まで実装すれば、タイムスタンプが正確で読みやすい再利用可能なソリューションが手に入ります。

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**学べること**
- Java プロジェクトへの GroupDocs.Viewer の設定方法  
- 埋め込みリソース付きでメールを HTML にレンダリングする方法  
- メールメッセージの**日時フォーマットをカスタマイズ**する方法（custom datetime format java）  
- 正しいタイムスタンプを得るために**タイムゾーンオフセットを設定**する方法（set timezone offset java）  

## クイック回答
- **GroupDocs.Viewer は EML を HTML に変換できますか？** はい、EML ファイルを直接 HTML にレンダリングします。  
- **ライセンスは必要ですか？** 無料トライアルでテスト可能です。製品版では有料ライセンスが必要です。  
- **必要な Java バージョンは？** Java 8 以上。  
- **表示される日付形式を変更するには？** `options.getEmailOptions().setDateTimeFormat(...)` を使用します。  
- **タイムゾーンを調整できますか？** はい、`options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))` で設定できます。

## 「EML を HTML に変換する」とは？
EML ファイルを HTML に変換すると、ヘッダー・本文・添付ファイルを含む生のメールが、ブラウザが追加プラグインなしで表示できるウェブフレンドリーな形式に変わります。これにより、ウェブアプリケーション、アーカイブ、サポートダッシュボードにメールを簡単に埋め込めます。

## このタスクに GroupDocs.Viewer を使う理由
- **依存関係ゼロのレンダリング** – Outlook や外部メールパーサーは不要です。  
- **埋め込みリソースの組み込みサポート**（画像、添付ファイル）。  
- **日時フォーマットとタイムゾーン処理の細かい制御**が可能です。  

## 前提条件

- **GroupDocs.Viewer for Java** バージョン 25.2 以降。  
- **Java Development Kit (JDK)** 8 以上と IDE（IntelliJ IDEA、Eclipse など）。  
- 基本的な Java の知識と Maven の利用経験。

## GroupDocs.Viewer for Java のセットアップ

### Maven 設定
`pom.xml` に GroupDocs リポジトリと依存関係を追加します。

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
無料トライアルで開始するか、拡張テスト用に一時ライセンスをリクエストしてください。製品環境ではフルライセンスが必要です。

### 基本的な初期化
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java でカスタム日時付き EML を HTML に変換

以下のステップバイステップガイドでは、**EML を HTML に変換**しながらカスタム日時フォーマットとタイムゾーンオフセットを適用する方法を示します。

### 手順 1: 出力ディレクトリとファイルパスの設定
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*説明:* `Path.of()` は HTML を保存するフォルダーへの参照を作成します。`resolve()` でファイル名を付加します。

### 手順 2: メールファイルで Viewer を初期化
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*説明:* `Viewer` インスタンスは変換したい EML ファイルを指します。

### 手順 3: HtmlViewOptions の構成
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*説明:* `forEmbeddedResources()` は画像やその他リソースを HTML 出力に直接埋め込みます。

### 手順 4: カスタム日時フォーマットの設定 *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*説明:* このパターンは月・日・年・時・分・AM/PM マーカー、そしてタイムゾーンオフセット（`zzz`）を表示します。

### 手順 5: タイムゾーンオフセットの設定 *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*説明:* レンダリングされたタイムスタンプを目的のタイムゾーンに調整します。`"GMT+1"` を任意の有効なゾーン識別子に置き換えてください。

### 手順 6: ドキュメントのレンダリング
```java
viewer.view(options);
```
*説明:* 変換を実行し、カスタム日時設定が適用された HTML ファイルを生成します。

## トラブルシューティングのヒント
- **FileNotFoundException:** `Viewer` と `Path.of()` で使用しているパスを再確認してください。  
- **タイムスタンプが正しくない:** `TimeZone` ID が対象地域と一致しているか確認してください。  
- **画像が欠落している:** `HtmlViewOptions.forEmbeddedResources()` を使用したか確認してください。外部リソースは含まれません。

## 実用例
1. **メールアーカイブ:** コンプライアンス用に検索可能な HTML スナップショットを保存。  
2. **カスタマーサポートポータル:** 正確なローカル時間で受信チケットを表示。  
3. **法的文書化:** 標準化されたタイムスタンプ付きの裁判所提出用メール記録を作成。  

## パフォーマンス考慮事項
- 大量変換は専用サーバーで実行してください。  
- Java ヒープ使用量を監視し、`OutOfMemoryError` が出たら `-Xmx` を増やします。  
- 同一メールが頻繁に要求される場合は、レンダリング済み HTML をキャッシュしてください。  

## 結論
これで、GroupDocs.Viewer for Java を使用してカスタム日時フォーマットとタイムゾーンオフセットを適用しながら **EML を HTML に変換**する完全な本番対応手法が手に入りました。可読性が向上し、タイムスタンプの正確性が保証され、アーカイブやサポートワークフローにシームレスに組み込めます。

**次のステップ:** CSS スタイリング、ページネーション、PDF 変換など、Viewer の追加オプションを探索して出力をさらにカスタマイズしてください。

## よくある質問

**Q: 添付ファイル付きの EML をどう扱いますか？**  
A: `HtmlViewOptions.forEmbeddedResources()` を使用すると添付ファイルは自動的に埋め込まれます。必要に応じて Viewer API で抽出することも可能です。

**Q: HTML テンプレートやカスタム CSS を変更できますか？**  
A: はい、レンダリング後に生成された HTML ファイルを編集するか、保存前にプログラムで CSS を注入できます。

**Q: 複数の EML ファイルをバッチ処理できますか？**  
A: ループでレンダリングロジックを回し、各ファイルごとに同じ `HtmlViewOptions` インスタンスを再利用してください。

**Q: MSG など他のメール形式にも対応できますか？**  
A: GroupDocs.Viewer は MSG、PST などのメールコンテナもサポートしています。`Viewer` コンストラクタの拡張子を変更するだけです。

**Q: サーバーごとに別々のライセンスが必要ですか？**  
A: ライセンスはデプロイ単位です。マルチサーバーシナリオについては GroupDocs のライセンスガイドをご参照ください。

## リソース

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-01-10  
**テスト環境:** GroupDocs.Viewer 25.2 (Java)  
**作者:** GroupDocs  

---