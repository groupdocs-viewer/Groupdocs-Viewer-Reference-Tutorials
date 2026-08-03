---
date: '2026-08-03'
description: GroupDocs.Viewer Java を使用して zip を html に変換し、ページあたりの項目数を設定し、リソース html
  を埋め込み、アーカイブを効率的にバッチ変換する方法を学びます。
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: GroupDocs.Viewer Java を使用して zip を html に変換し、ページあたりの項目数を設定し、リソース html
  を埋め込み、アーカイブを効率的にバッチ変換する方法を学びます。ステップバイステップのコードとパフォーマンスのヒントに従ってください。
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: GroupDocs.Viewer Java を使用して zip を html に変換し、ページあたりの項目数を設定する
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: GroupDocs.Viewer Java を使用して zip を html に変換し、ページあたりの項目数を設定する
type: docs
url: /ja/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# GroupDocs.Viewer JavaでZIPをHTMLに変換し、ページごとの項目数を設定する

多くのウェブアプリケーションでは、ZIPやRARアーカイブの内容をブラウザに直接表示する必要があります。GroupDocs.Viewer for Java を使用すると、**convert zip to html** をワンステップで実行でき、各ページに表示されるアーカイブエントリの数を制御し、すべての画像や CSS を埋め込むことができ、さらには多数のアーカイブをバッチ処理することも可能です。このチュートリアルでは、Maven の設定からマルチページレンダリングまでの完全なワークフローを順に解説し、各設定がパフォーマンスと使いやすさにどのように影響するかを説明します。

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## クイック回答
- **「set items per page」は何を制御しますか？** アーカイブ内のファイルやフォルダーが生成された各 HTML ページに何件表示されるかを決定します。  
- **HTML に画像と CSS を直接埋め込むことはできますか？** はい – `forEmbeddedResources` オプションを使用してリソースを HTML に埋め込みます。  
- **バッチ変換は可能ですか？** もちろんです。アーカイブのコレクションをループし、同じ設定でそれぞれをレンダリングできます。  
- **GroupDocs.Viewer の使用に Maven は必要ですか？** はい、以下のように `groupdocs-viewer` Maven 依存関係を追加してください。  
- **サポートされている出力形式は何ですか？** シングルページ HTML とマルチページ HTML の両方が利用可能で、ライブラリは 50 以上の入力アーカイブタイプをサポートしています。

## GroupDocs.Viewer の「set items per page」とは何ですか？
**set items per page** 設定はアーカイブレンダリングオプションに属します。マルチページ HTML ドキュメントを生成する際に、各 HTML ページに表示するアーカイブエントリ（ファイルまたはフォルダー）の数をビューアに指示します。この値を調整することで、特に大規模なアーカイブにおいて、ページサイズとナビゲーション速度のバランスを取ることができます。

## なぜリソースを HTML に埋め込むのですか？
リソース（画像、CSS、フォント）を HTML ファイル内に直接埋め込むことで、外部ファイルなしで開くことができる単一のポータブルドキュメントが作成されます。これは、メール添付、オフライン閲覧、または出力を他のウェブページに埋め込む際に最適です。この方法は、外部アセットパスを管理する必要がなくなるため、デプロイも簡素化されます。

## 前提条件
- **必要なライブラリ:** GroupDocs.Viewer バージョン 25.2 以降を含めます。  
- **環境:** Java Development Kit (JDK) がインストールされ、設定されていること。  
- **知識:** 基本的な Java と Maven 依存関係管理。

## Maven GroupDocs Viewer 設定
`pom.xml` に GroupDocs リポジトリとビューアの依存関係を追加します:

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
GroupDocs.Viewer は **free trial link**、一時ライセンス、またはフル購入オプションを提供しています。プロジェクトのスケジュールに合うものを選択してください。

### 基本的な初期化
Maven の設定後、コードにビューアを導入します:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## アーカイブをシングルページ HTML にレンダリングする方法
Viewer はドキュメントまたはアーカイブをロードしてレンダリングするコアクラスです。

アーカイブ全体を含む単一の HTML ファイルを生成するには、ZIP ファイル用に `Viewer` インスタンスを作成し、`HtmlViewOptions.forEmbeddedResources()` を使用してすべての画像、CSS、フォントを埋め込みます。これらのオプションでアーカイブをレンダリングすると、メールやオフラインでの使用に適した自己完結型のページが生成されます。

### 手順 1: 出力ディレクトリを定義する
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 手順 2: シングルページ出力のファイル名を設定する
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 手順 3: ビューアを初期化する
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 手順 4: レンダリングオプションを設定する（リソースを HTML に埋め込む）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: シングルページとしてレンダリングする
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## アーカイブをマルチページ HTML にレンダリングし、ページごとの項目数を設定する方法
`HtmlViewOptions` は、ページネーションやリソース埋め込みを含む、ビューアが HTML 出力をレンダリングする方法を設定します。

アーカイブを複数ページに分割するには、`HtmlViewOptions.forEmbeddedResources()` を作成し、`options.setItemsPerPage(20)` で希望のページサイズを設定します。ビューアは別々の HTML ファイルを生成し、各ファイルは指定されたエントリ数まで表示するため、大規模なアーカイブのナビゲーションが向上し、読み込みが速くなります。

### 手順 1: 出力ディレクトリを再利用する
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 手順 2: 複数ページ用のファイル名フォーマットを定義する
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 手順 3: ビューアを再度初期化する
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 手順 4: マルチページオプションを設定する（リソースを HTML に埋め込む）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: ページごとの項目数を設定する（アクションの主要キーワード）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 実用的な活用例
- **Document management systems:** 余分なビューアをインストールせずにアーカイブプレビュー機能を追加します。  
- **Web portals:** ユーザーにバンドルされたドキュメントを迅速に、ダウンロード不要で閲覧できる方法を提供します。  
- **Collaboration tools:** チームが共有アーカイブをブラウザ上で直接検査できるようにします。

## パフォーマンス上の考慮点
- **Resource management:** アーカイブをストリームで処理することでメモリ使用量を抑えます。ビューアはファイル全体をメモリに読み込まずに、最大 500 MB のアーカイブを処理できます。  
- **Batch convert archives:** アーカイブファイルのリストをループし、同じレンダリングロジックを呼び出すことでスループットを最大化します。  
- **Caching strategy:** 同じアーカイブが頻繁にアクセスされる場合、レンダリングされた HTML をキャッシュに保存し、再処理時間を最大 70 % 短縮します。

## よくある質問
**Q: GroupDocs.Viewer Java とは何ですか？**  
A: GroupDocs.Viewer Java は、ZIP や RAR を含む 50 以上のドキュメントおよびアーカイブ形式を、外部アプリケーションを必要とせずに HTML、PDF、または画像ファイルにレンダリングするサーバーサイドライブラリです。

**Q: GroupDocs.Viewer の無料トライアルはどうやって取得できますか？**  
A: ダウンロードとテストのために [free trial link](https://releases.groupdocs.com/viewer/java/) にアクセスしてください。

**Q: アーカイブ以外のドキュメントタイプも変換できますか？**  
A: はい、ビューアは PDF、Word、Excel、PowerPoint、その他 35 以上のフォーマットをサポートしています。

**Q: レンダリングが遅い場合はどうすればよいですか？**  
A: ページごとの項目数を減らす、ストリーミングを有効にする、またはアーカイブを小さなバッチで処理して速度を向上させてください。

**Q: サポートやヘルプはどこで得られますか？**  
A: [support forum](https://forum.groupdocs.com/c/viewer/9) でお問い合わせください。

**Q: CSS と画像を HTML に直接埋め込むことは可能ですか？**  
A: もちろんです。例に示すように `HtmlViewOptions.forEmbeddedResources` を使用してください。

**Q: アーカイブのフォルダをバッチ変換するにはどうすればよいですか？**  
A: `for` ループで各ファイルを反復処理し、各イテレーションで同じ `Viewer` と `HtmlViewOptions` 設定を適用します。

## リソース
- **Documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) で機能を詳しく確認してください。  
- **API reference:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/) でフル API を確認してください。  
- **Download:** 最新のバイナリは [download page](https://releases.groupdocs.com/viewer/java/) から取得してください。  
- **Purchase and licensing:** オプションは [purchase page](https://purchase.groupdocs.com/buy) をご覧ください。  
- **Support and community:** ディスカッションは [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) に参加してください。

---

**Last Updated:** 2026-08-03  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## 関連チュートリアル
- [Java で GroupDocs.Viewer を使用して ZIP を HTML に変換し、ZIP フォルダーをレンダリングする方法](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java で ZIP を PDF に変換 - カスタムファイル名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java を使用して DOCX を HTML に変換する方法：ステップバイステップガイド](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)