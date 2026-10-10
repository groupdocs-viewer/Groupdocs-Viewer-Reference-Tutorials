---
date: '2026-10-10'
description: GroupDocs.Viewer Java を使用して zip を html に変換し、ページあたりの項目数を設定し、リソース html
  を埋め込み、アーカイブを効率的にバッチ変換する方法を学びます。
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: GroupDocs.Viewer Java を使用して zip を html に変換し、リソースを埋め込み、ページあたりの項目数を設定し、アーカイブをバッチ処理して高速でポータブルな
  web previews を実現する方法を学びます。
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: GroupDocs.Viewer Java を使用してページネーション付き zip を HTML に変換
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ZIP を HTML に変換し、GroupDocs.Viewer Java でページあたりの項目数を設定する

多くのウェブアプリケーションでは、ZIP や RAR アーカイブの内容をブラウザに直接表示する必要があります。**ZIP を変換する方法** を使用して GroupDocs.Viewer for Java で ZIP ファイルを HTML に変換することは一般的な要件であり、ライブラリは画像、CSS、フォントを埋め込むことができるため、結果は単一のポータブルページになります。このチュートリアルでは、Maven の設定からマルチページレンダリングまで、すべてを順を追って説明し、各オプションがパフォーマンスと使いやすさにどのように影響するかを解説します。

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## クイック回答
- **「set items per page」は何を制御しますか？** アーカイブ内のファイルまたはフォルダーが各生成された HTML ページに何件表示されるかを決定します。  
- **HTML に画像や CSS を直接埋め込むことはできますか？** はい – `forEmbeddedResources` オプションを使用してリソースを HTML に埋め込みます。  
- **バッチ変換は可能ですか？** もちろんです。アーカイブのコレクションをループして、同じ設定でそれぞれをレンダリングできます。  
- **GroupDocs.Viewer の使用に Maven は必要ですか？** はい、以下のように `groupdocs-viewer` Maven 依存関係を追加してください。  
- **サポートされている出力形式は何ですか？** シングルページ HTML とマルチページ HTML の両方が利用可能で、ライブラリは 50 種類以上の入力アーカイブ形式をサポートしています。

## GroupDocs.Viewer の「set items per page」とは何ですか？
これは、マルチページドキュメントを生成する際に、各 HTML ページに表示するアーカイブエントリ（ファイルまたはフォルダー）の数をビューアに指示します。この値を調整することで、特に大規模なアーカイブの場合、ページサイズとナビゲーション速度のバランスを取ることができ、ページごとに読み込むデータ量を制限し、エンドユーザーのレンダリング時間を短縮します。

## なぜリソースを HTML に埋め込むのですか？
リソース（画像、CSS、フォント）を HTML ファイル内に直接埋め込むことで、外部ファイルなしで開くことができる単一のポータブルドキュメントが作成されます。これは、メール添付、オフライン閲覧、または出力を他のウェブページに埋め込む際に最適です。また、外部アセットパスの管理が不要になります。

## 前提条件

- **必要なライブラリ:** GroupDocs.Viewer バージョン 25.2 以降を含めます。  
- **環境:** Java Development Kit (JDK) がインストールされ、設定されていること。  
- **知識:** 基本的な Java と Maven の依存関係管理。  

## Maven GroupDocs Viewer の設定

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer は **無料トライアルリンク**、一時ライセンス、またはフル購入オプションを提供しています。プロジェクトのスケジュールに合うものを選択してください。

## 基本的な初期化
`Viewer` クラスはドキュメントやアーカイブのレンダリングのエントリーポイントです。Maven の設定後、コードにビューアを組み込みます:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## アーカイブをシングルページ HTML にレンダリングする方法
`HtmlViewOptions` クラスは、リソース埋め込みなどの HTML 出力設定を定義します。アーカイブを読み込み、HTML オプションでリソースを埋め込むよう構成し、すべてを単一の自己完結型ページにレンダリングします。これにより、すべてのファイル、画像、CSS、フォントを含む単一の HTML ファイルが生成され、オフライン使用やメール添付に適します。

**直接的な回答:** ZIP ファイル用に `Viewer` インスタンスを作成し、`HtmlViewOptions.forEmbeddedResources()` を呼び出して、`viewer.view(documentPath, options)` を実行します。これにより、すべてのファイル、画像、CSS、フォントを含む単一の HTML ファイルが生成され、オフライン使用やメール添付に適します。

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

### 手順 4: レンダリングオプションを構成する（リソースを HTML に埋め込む）
`HtmlViewOptions` クラスは、リソース埋め込みなどの HTML 出力設定を定義します。`forEmbeddedResources()` を使用して、すべてを単一のファイルにバンドルします。

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: シングルページとしてレンダリングする
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## アーカイブをマルチページ HTML にレンダリングし、ページあたりの項目数を設定する方法
`HtmlViewOptions` クラスはページネーションもサポートしています。`options.setItemsPerPage(N)` を呼び出すことで、ビューアはアーカイブを複数の HTML ファイルに分割し、各ファイルは最大 **N** 件のエントリを表示します。このアプローチにより、大規模なアーカイブでもナビゲーション速度が向上し、各ページが軽量に保たれます。

**直接的な回答:** `HtmlViewOptions.forEmbeddedResources()` を使用し、`options.setItemsPerPage(N)` を呼び出してアーカイブをレンダリングします。ビューアはページごとに別々の HTML ファイルを生成し、各ファイルは最大 **N** 件のエントリを含むため、大規模アーカイブのナビゲーションが高速化されます。

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

### 手順 4: マルチページオプションを構成する（リソースを HTML に埋め込む）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: ページあたりの項目数を設定する（アクションの主要キーワード）
`options.setItemsPerPage(20); // how to convert zip archives with 20 entries per page`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 実用的な適用例

- **Document management systems:** 余分なビューアをインストールせずにアーカイブプレビュー機能を追加します。  
- **Web portals:** ユーザーにバンドルされたドキュメントを迅速に、ダウンロード不要で閲覧できる方法を提供します。  
- **Collaboration tools:** チームが共有アーカイブをブラウザで直接検査できるようにします。  

## パフォーマンス上の考慮点

- **Resource management:** ストリームでアーカイブを処理することでメモリ使用量を低く保ちます。ビューアはファイル全体をメモリに読み込まずに最大 500 MB のアーカイブを処理できます。  
- **Batch convert archives:** アーカイブファイルのリストをループし、同じレンダリングロジックを呼び出すことでスループットを最大化します。  
- **Caching strategy:** 同じアーカイブが頻繁にアクセスされる場合、レンダリングされた HTML をキャッシュに保存し、再処理時間を最大 70 % 短縮します。  

## よくある質問

**Q: GroupDocs.Viewer Java とは何ですか？**  
A: GroupDocs.Viewer Java は、ZIP や RAR を含む 50 以上のドキュメントおよびアーカイブ形式を、外部アプリケーションを必要とせずに HTML、PDF、または画像ファイルにレンダリングするサーバーサイドライブラリです。

**Q: GroupDocs.Viewer の無料トライアルはどうやって取得できますか？**  
A: [free trial link](https://releases.groupdocs.com/viewer/java/) にアクセスしてダウンロードおよびテストしてください。

**Q: アーカイブ以外のドキュメントタイプも変換できますか？**  
A: はい、ビューアは PDF、Word、Excel、PowerPoint、その他 35 種類以上の形式をサポートしています。

**Q: レンダリングが遅い場合はどうすればよいですか？**  
A: ページあたりの項目数を減らす、ストリーミングを有効にする、またはアーカイブを小さなバッチで処理して速度を向上させます。

**Q: サポートやヘルプはどこで得られますか？**  
A: [support forum](https://forum.groupdocs.com/c/viewer/9) でお問い合わせください。

**Q: CSS と画像を HTML に直接埋め込むことは可能ですか？**  
A: もちろんです。例に示すように `HtmlViewOptions.forEmbeddedResources` を使用してください。

**Q: アーカイブのフォルダをバッチ変換するにはどうすればよいですか？**  
A: `for` ループで各ファイルを反復処理し、同じ `Viewer` と `HtmlViewOptions` 設定を各イテレーションに適用します。

**Q: 他のユーザーと問題を議論できる場所はどこですか？**  
A: コミュニティディスカッションは [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) で行ってください。

## リソース

- **Documentation:** 機能をさらに詳しく知るには [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) をご覧ください。  
- **API reference:** 完全な API は [GroupDocs API](https://reference.groupdocs.com/viewer/java/) で確認できます。  
- **Download:** 最新のバイナリは [download page](https://releases.groupdocs.com/viewer/java/) から取得してください。  
- **Purchase and licensing:** オプションは [purchase page](https://purchase.groupdocs.com/buy) で確認してください。  
- **Support and community:** ディスカッションは [support forum](https://forum.groupdocs.com/c/viewer/9) に参加してください。  
- **GroupDocs forum:** コミュニティヘルプは [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) でアクセスできます。

**最終更新日:** 2026-10-10  
**テスト環境:** GroupDocs.Viewer 25.2  
**作者:** GroupDocs

## 関連チュートリアル

- [GroupDocs.Viewer を使用して Java で ZIP を HTML に変換し、ZIP フォルダーをレンダリングする方法](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java で ZIP を PDF に変換 - カスタムファイル名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [GroupDocs.Viewer for Java を使用して DOCX を HTML に変換する方法：ステップバイステップガイド](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}