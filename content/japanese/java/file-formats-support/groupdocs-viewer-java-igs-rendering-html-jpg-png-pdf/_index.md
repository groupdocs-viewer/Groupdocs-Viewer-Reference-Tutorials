---
date: '2026-08-08'
description: GroupDocs.Viewer for Java を使用して IGS を PDF、HTML、JPG、PNG に変換する方法を学びます。ステップバイステップのガイド、前提条件、そして
  Java 開発者向けのトラブルシューティングを提供します。
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: GroupDocs.Viewer for Java を使用して IGS を PDF、HTML、JPG、PNG に変換します。詳細なセットアップ手順、コードスニペット、そして
  Java 開発者向けのトラブルシューティングを掲載しています。
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: GroupDocs.Viewer Java を使用して IGS を PDF、HTML、JPG、PNG に変換
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: GroupDocs.Viewer Java を使用して IGS を PDF、HTML、JPG、PNG に変換
type: docs
url: /ja/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# GroupDocs.Viewer Java を使用した IGS の PDF、HTML、JPG、PNG への変換

Java アプリケーションから直接 **IGS を PDF**（または HTML、JPG、PNG）に変換する必要がある場合、ここが適切な場所です。このチュートリアルでは、ライブラリのインストールからプロジェクトに適した形式で 3D モデルをレンダリングするまで、必要なすべてを順に解説します。GroupDocs.Viewer が高速で信頼性の高い変換に最適な選択肢である理由が分かり、実際に使用できるコードスニペットをすぐに利用できるようになります。

![GroupDocs.Viewer for Java を使用した IGS ファイルの HTML、JPG、PNG、PDF への変換](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 簡単な回答
- **Java で IGS を PDF に変換できますか？** はい、`PdfViewOptions` と `Viewer` API を組み合わせて使用します。  
- **サポートされている出力形式は何ですか？** HTML、JPG、PNG、PDF はすべてネイティブに処理されます。  
- **本番環境でライセンスが必要ですか？** 商用ライセンスが必要です。無料トライアルでコア機能をテストできます。  
- **必要な Java バージョンは何ですか？** JDK 8 以上が必要です。ライブラリは Java 11、17 以降でも動作します。  
- **ライブラリの追加は Maven のみですか？** いいえ、Gradle を使用するか、JAR ファイルを手動でクラスパスに追加することもできます。

## IGS を PDF に変換するとは何ですか？
IGS を PDF に変換することは、中立的な 3D CAD ファイルを静的で、誰でも閲覧できるドキュメントに変換することを意味します。これにより、CAD ツールを持たないステークホルダーと設計ビジュアルを共有したり、レポートにレンダリングを埋め込んだり、コンプライアンス目的でモデルをアーカイブしたりできます。

## IGS 変換に GroupDocs.Viewer を使用する理由
GroupDocs.Viewer は外部の CAD ソフトウェアを必要とせずに IGS ファイルを処理します。**50 以上の入力および出力フォーマット**に対応し、**数百の部品**を含むアセンブリをメモリ使用量 **200 MB 未満**に抑えながらレンダリングでき、標準サーバー上の一般的なモデルでは **2 秒未満**で結果を提供します。これらの定量的なメリットにより、エンタープライズパイプラインにおいて高性能かつコスト効果の高い選択肢となります。

## 前提条件
- **GroupDocs.Viewer for Java** ≥ 25.2（最新の安定版）。  
- **JDK 8+** がインストールされ、IDE（IntelliJ IDEA、Eclipse、NetBeans など）で設定されていること。  
- 基本的な Maven の知識（任意ですが、依存関係管理のために推奨）。

## GroupDocs.Viewer for Java の設定

### Maven 依存関係
`pom.xml` に GroupDocs リポジトリと Viewer の依存関係を追加します。

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
GroupDocs.Viewer は三つのライセンスオプションを提供します：
- **Free trial** – 使用制限あり、迅速な概念実証テストに最適です。  
- **Temporary license** – 短期間の評価期間中にフル機能を利用でき、パイロットプロジェクトに最適です。  
- **Commercial license** – 本番環境での無制限使用が可能で、優先サポートとアップデートが含まれます。

### 基本的な Viewer の初期化
`Viewer` クラスはすべてのレンダリング操作のエントリーポイントです。ソースファイルを読み込み、フォーマットを解析し、目的の出力を生成するメソッドを提供します。

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## IGS を HTML にレンダリング

### IGS を HTML に変換する方法は？
`Viewer` インスタンスで IGS ファイルを読み込み、必要なすべてのアセットを埋め込む `HtmlViewOptions` オブジェクトを渡します。この呼び出しは、完全な 3D ビューを含む単一の HTML ファイルを返し、ウェブページへの埋め込みが容易になります。また、ページサイズ、背景色、インタラクティブコントロールの有無などのオプションを設定してレンダリングをカスタマイズできます。  
`HtmlViewOptions` は、リソース埋め込みやページレイアウトを含む HTML 出力の生成方法を構成します。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS を JPG にレンダリング

### IGS を JPG に変換する方法は？
`JpgViewOptions` オブジェクトを作成し、希望する解像度と圧縮品質を設定して、`Viewer` にモデルの各ページのラスタ画像を生成させます。生成された JPG ファイルは指定ディレクトリに保存でき、品質パラメータを調整してファイルサイズと視覚的忠実度のバランスを取ることができます。サムネイルや高解像度印刷に便利です。  
`JpgViewOptions` は、解像度、品質、出力ディレクトリなど JPG 画像生成の設定を指定します。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS を PNG にレンダリング

### IGS を PNG に変換する方法は？
`PngViewOptions` クラスを使用すると、オプションで透過性を持つロスレス画像を生成できます。この形式は、マーケティング資料でカラーバックグラウンドにモデルをオーバーレイするのに最適です。また、解像度と背景色をブランドガイドラインに合わせて定義でき、生成されたすべてのアセットで一貫した外観を確保します。  
`PngViewOptions` は、解像度、透過性、背景色など PNG レンダリングのパラメータを定義します。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## IGS を PDF にレンダリング

### IGS を PDF に変換する方法は？
`PdfViewOptions` を使用して、3D モデルのビジュアルレイアウトを保持したページ化された PDF を生成します。フォントを埋め込んだり、企業のブランドガイドラインに合わせてページサイズを制御したりすることも可能です。追加設定により、画像品質、圧縮レベル、マルチページアセンブリの目次を含めるかどうかを指定できます。  
`PdfViewOptions` は PDF 作成を制御し、ページサイズ、画像品質、フォント埋め込みの設定を可能にします。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 実用的な活用例
- **Web ポータル** – HTML でレンダリングされたモデルを製品コンフィギュレータに直接埋め込み、プラグインをインストールせずに顧客が回転やズームを行えるようにします。  
- **マーケティング資産** – パンフレット、スライドデック、ソーシャルメディア投稿用に高解像度の JPG/PNG 画像を生成します。  
- **技術文書** – ユーザーマニュアルに CAD モデルの PDF レンダリングを含め、エンジニアがオフラインで設計を閲覧できるようにします。  
- **品質保証** – 数千の IGS ファイルのサムネイル作成を自動化し、視覚検査ワークフローを高速化します。

## 一般的な問題と解決策

| 問題 | 解決策 |
|-------|----------|
| **出力フォルダーが見つかりません** | `Path outputDirectory` に渡されたパスを確認し、Java プロセスが対象ディレクトリに書き込み権限を持っていることを確認してください。 |
| **PDF に空白ページがある** | ソースの IGS ファイルが破損していないか確認してください。まずネイティブの CAD ビューアで開いてみます。 |
| **大規模アセンブリのレンダリングが遅い** | JVM ヒープを増やします（`-Xmx2g` 以上）。また、`viewer.getPageCount()` を使用してページ単位でレンダリングし、チャンク処理を検討してください。 |
| **PDF のフォントが欠落している** | `PdfViewOptions` を使用して必要なフォントを埋め込むか、変換サービスをホストするサーバーに欠落しているフォントをインストールしてください。 |

## よくある質問

**Q: 複数の IGS ファイルを一度に変換できますか？**  
A: はい。ファイルパスのコレクションを反復処理し、同じ `Viewer` インスタンス内で各ファイルに対して適切な `view` メソッドを呼び出します。

**Q: PDF のページサイズをカスタマイズできますか？**  
A: もちろんです。`PdfViewOptions` は `setPageSize(PageSize.A4)`, `PageSize.Letter`、および `setCustomSize(width, height)` によるカスタム寸法を提供します。

**Q: 各出力形式ごとに別々のライセンスが必要ですか？**  
A: いいえ。単一の GroupDocs.Viewer ライセンスで、HTML、JPG、PNG、PDF を含むすべてのサポート形式がカバーされます。

**Q: パフォーマンスが低下する前に IGS ファイルはどのくらいのサイズまで対応できますか？**  
A: ライブラリは **500 MB** までのファイルを確実に処理します。200 MB を超えるモデルの場合は、JVM メモリを追加で割り当て、バッチ処理でのレンダリングを検討してください。

**Q: 特定のビューや向きだけをレンダリングできますか？**  
A: GroupDocs.Viewer は IGS ファイルで定義されたデフォルトの向きをレンダリングします。カスタムビューが必要な場合は、CAD ツールでファイルを前処理するか、変換前にモデルを調整してください。

**最終更新日:** 2026-08-08  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs

## 関連チュートリアル

- [GroupDocs.Viewer Java を使用した cdr の html、jpg、png、pdf への変換](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [GroupDocs.Viewer を使用して Java で pdf を html に変換し、画像品質を最適化する方法](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)