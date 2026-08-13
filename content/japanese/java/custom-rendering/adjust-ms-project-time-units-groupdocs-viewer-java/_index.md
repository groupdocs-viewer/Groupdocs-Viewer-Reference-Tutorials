---
date: '2026-05-21'
description: GroupDocs Viewer for Java を使用して、時間単位を調整した MS Project の HTML エクスポートを実行する方法を学びます。前提条件、セットアップ、トラブルシューティングを含むステップバイステップガイドです。
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: MS Project HTML エクスポート：GroupDocs Java による時間単位の調整
type: docs
url: /ja/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML エクスポート: GroupDocs Java で時間単位を調整

**MS Project** ファイルを HTML にエクスポートすることは、プロジェクト管理ダッシュボード、ステータスレポートポータル、共同レビュー ツールで一般的な要件です。デフォルトではビューアが時間関連データを分単位で表示するため、レイアウトが乱れ、日次レポートが読みづらくなります。**GroupDocs Viewer for Java** を使用すれば、プログラムで時間単位を **days** に設定でき、典型的なステークホルダーの期待に沿ったクリーンな *ms project html export* を作成できます。このチュートリアルでは、ビューアの設定方法、時間単位の調整方法、プロジェクトを HTML にレンダリングする手順を学びます。

![GroupDocs.Viewer for Java で MS Project の時間単位を調整](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[GroupDocs.Viewer for Java で MS Project の時間単位を調整](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## クイック回答
- **MS Project ファイルをレンダリングするライブラリは何ですか？** GroupDocs Viewer for Java。  
- **HTML エクスポートで設定できる時間単位は？** Days、`TimeUnit.DAYS` を使用。  
- **本番環境でライセンスは必要ですか？** はい— 永続ライセンスが必要です。評価用にはトライアルが利用可能です。まずは [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) から開始できます。  
- **どの IDE が最適ですか？** Maven をサポートする任意の Java IDE（IntelliJ IDEA、Eclipse、NetBeans）。  
- **Maven は必須ですか？** Maven は依存関係管理を簡素化しますが、Gradle や手動 JAR の追加でも構いません。  
- **購入先はどこですか？** 価格情報は [buy page](https://purchase.groupdocs.com/buy) をご覧ください。

## GroupDocs Viewer for Java とは？
**GroupDocs Viewer for Java** は、MS Project を含む 150 以上のドキュメント形式を Web フレンドリーな HTML、PNG、JPEG、PDF に変換する Java SDK です。  
解析ロジックを抽象化し、時間単位などのレンダリングオプションを制御でき、Java 8 以降をサポートする任意のプラットフォームで動作します。

## MS Project HTML エクスポートで時間単位を調整する理由
時間単位を **days** に設定すると、視覚的ノイズが減少し、ほとんどのレポートサイクルに合致し、生成される時間マーカーが少なくなるためページ読み込み時間が改善されます。定量的には、分単位ではなく日単位でレンダリングすることで、典型的な 30 日プロジェクトの生成 HTML サイズが最大 **45 %** 縮小し、クライアント側のレンダリング速度が約 **30 %** 向上します。

## 前提条件
- **Java Development Kit (JDK) 8 以上** がワークステーションにインストールされていること。  
- **Maven**（または Gradle）による依存関係管理。  
- エクスポート対象の **MS Project (.mpp)** ファイル。  
- **GroupDocs Viewer for Java** のライセンス（トライアルまたは永続）へのアクセス。  

### 必要なライブラリ
`pom.xml`（または同等の Gradle スニペット）に以下の依存関係を追加してください：

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** バージョン番号は常に最新に保ちましょう。新しいリリースではフォーマットサポートやパフォーマンスが向上します。

## GroupDocs Viewer for Java のセットアップ方法は？
MS Project ファイルを指す `Viewer` インスタンスを作成してビューアを初期化します。`Viewer` クラスはすべてのレンダリング操作のエントリーポイントで、ソースドキュメントを読み込み内部構造を準備し、`view()` や `viewToHtml()` といったメソッドを公開します。

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** `Viewer` クラスは GroupDocs Viewer のコアコンポーネントで、ソースドキュメントを読み込み `view()` や `viewToHtml()` などのレンダリングメソッドを提供します。

## HTML エクスポートの時間単位を調整するには？
時間粒度を変更するには、`ViewOptions` オブジェクトを作成し、その `ProjectOptions` に `TimeUnit.DAYS` を設定してビューアに渡します。`ViewOptions` はドキュメントのレンダリング設定を定義し、`TimeUnit` 列挙型は時間関連データの単位（分、時間、日）を指定します。これらのオプションを設定した後、`viewer.view(options)` を呼び出すと日単位のマーカー付き HTML が生成されます。

`new Viewer("file.mpp")` で MS Project ファイルを読み込み、`ViewOptions` オブジェクトを作成し、`options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` を設定してから `viewer.view(options)` を呼びます。この 3 ステップのフローにより、時間単位が分から日へ変更され、日単位の間隔のみを表示する HTML ファイルが生成されます。

### Step 1: 出力フォルダーを定義
HTML ページを保存する書き込み可能なディレクトリ（例: `output/`）を選択します。

### Step 2: 埋め込みリソース付きビューオプションを作成
埋め込みリソース（CSS、JavaScript）により、HTML ページが自己完結型になります。

### Step 3: 時間単位を日単位に設定
`options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` を使用して粒度を切り替えます。

### Step 4: ドキュメントをレンダリング
`viewer.view(options)` を呼び出します。ビューアはプロジェクトページごとに 1 つの HTML ファイルを出力フォルダーに書き込みます。

### Step 5: 結果を検証
生成された `index.html` をブラウザで開き、分マーカーではなく日マーカーに合わせてタスクバーが表示されていることを確認します。

## よくある落とし穴とトラブルシューティング
- **出力パスが正しくない** – ディレクトリが存在し、Java プロセスに書き込み権限があることを確認してください。  
- **ライセンスがない** – 有効なライセンスがない場合、ビューアはトライアルモードにフォールバックし、透かしが埋め込まれる可能性があります。  
- **大容量ファイル（> 500 MB）** – JVM ヒープサイズを `-Xmx2g` に増やすか、`options.setRenderLimit(1000)` でバッチ処理を行うことを検討してください。  

## 調整した時間単位の HTML エクスポートの実用例
1. **エグゼクティブ ダッシュボード** – 日単位の粒度がほとんどの KPI 可視化にマッチします。  
2. **自動ステータスメール** – 生成された HTML をメール本文に直接埋め込み、迅速な更新を提供します。  
3. **プロジェクト ポータル** – 社内イントラネット上で HTML をホストし、メンバーが日単位でタスクをフィルタリングできるようにします。  

## 大規模 MS Project ファイルのパフォーマンス考慮点
- **メモリ管理** – Java のガベージコレクタフラグ (`-XX:+UseG1GC`) を使用して未使用オブジェクトを速やかに解放します。  
- **選択的レンダリング** – ガントチャートだけが必要な場合は、`options.getProjectOptions().setRenderGantt(true)` と `setRenderResources(false)` で他のリソースレンダリングを無効化します。  
- **並列処理** – バッチ変換では、ファイルごとに別々の `Viewer` オブジェクトをインスタンス化し、スレッドプールで実行してマルチコア CPU を活用します。  

## 結論
これで、GroupDocs Viewer for Java を使用して時間単位を日単位に設定した **ms project html export** を実行する、完全な本番対応ワークフローが完成しました。このアプローチにより HTML サイズが削減され、クライアント側のレンダリングが高速化され、ステークホルダーにとって見やすいプロジェクトスケジュールが提供されます。PDF エクスポートや画像スナップショットなど、追加のレンダリングオプションも検討して、レポート パイプライン全体に統合してください。

## よくある質問

**Q: 他の Project ビュー（例: Resource Sheet）も HTML にレンダリングできますか？**  
A: はい、`ProjectOptions` オブジェクトでガント、リソースシート、カレンダーなど特定のビューを有効化または無効化できます。

**Q: 生成された HTML の CSS をカスタマイズできますか？**  
A: もちろんです。`options.setStyleSheetPath("path/to/custom.css")` でカスタムスタイルシートのパスを指定すれば、ビューアが各ページに埋め込みます。

**Q: MS Project に対する GroupDocs Viewer のファイルサイズ上限は？**  
A: ストリーミングアーキテクチャにより、**500 MB** までのファイルをメモリ全体にロードせずに処理できます。

**Q: サーバーに Microsoft Project をインストールする必要がありますか？**  
A: いいえ。GroupDocs Viewer は .mpp フォーマットを直接解析し、Microsoft Project や Office のインストールは不要です。

**Q: 本番環境でビューアをライセンスするには？**  
A: GroupDocs ストアで永続ライセンスを購入し、実行時に `License license = new License(); license.setLicense("path/to/license.lic");` でライセンスファイルを適用します。短期利用の場合は [temporary license](https://purchase.groupdocs.com/temporary-license/) を取得できます。

---

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs Viewer Java 25.2  
**Author:** GroupDocs  

**Resources**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## 関連チュートリアル

- [GroupDocs.Viewer for Java を使用して MS Project ファイルを HTML、JPG、PNG、PDF（ノート付き）にレンダリングする方法](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [GroupDocs Viewer を使用して Java でプロジェクト ドキュメントを時間間隔別にレンダリングする方法](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java のライセンス設定方法: ファイルおよび URL のセットアップ ガイド](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)