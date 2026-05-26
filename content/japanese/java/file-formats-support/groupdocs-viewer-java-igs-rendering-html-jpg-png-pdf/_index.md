---
date: '2026-02-23'
description: GroupDocs.Viewer for Java を使用して IGS を PDF、HTML、JPG、PNG に変換する方法を学びましょう。実行可能なコード例が付いたステップバイステップのガイドに従ってください。
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: GroupDocs.Viewer Java を使用して IGS を PDF、HTML、JPG、PNG に変換する
type: docs
url: /ja/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

**  
A: GroupDocs.Viewer renders the default view. For custom orientations, preprocess the IGS file with a CAD tool before conversion.

Translate.

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

Translate labels.

Now produce final markdown with Japanese translations.

Be careful to keep code block placeholders unchanged. Also keep markdown formatting.

Let's construct final output.# GroupDocs.Viewer Java を使用して IGS を PDF、HTML、JPG、PNG に変換

Java アプリケーションから直接 **IGS を PDF に変換**（または HTML、JPG、PNG に変換）したい場合は、ここが最適です。このチュートリアルでは、ライブラリの設定からプロジェクトに適した形式で 3‑D モデルをレンダリングするまでの手順をすべて解説します。GroupDocs.Viewer が高速で信頼性の高い変換に最適な理由を確認し、実際に自分のソリューションに組み込めるコード例もご紹介します。

![GroupDocs.Viewer for Java を使用した IGS ファイルの HTML、JPG、PNG、PDF への変換](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Quick Answers
- **Java で IGS を PDF に変換できますか？** はい、GroupDocs.Viewer の `PdfViewOptions` を使用します。  
- **サポートされている出力形式は何ですか？** HTML、JPG、PNG、PDF。  
- **本番環境でライセンスは必要ですか？** 商用ライセンスが必要です。テスト用の無料トライアルも利用可能です。  
- **必要な Java バージョンは？** JDK 8 以上。  
- **ライブラリの追加は Maven だけですか？** いいえ、Gradle や手動で JAR を追加することもできます。

## “convert IGS to PDF” とは？
IGS（3‑D CAD データの中立フォーマット）を PDF に変換することは、複雑な 3‑D モデルを静的で広く閲覧可能なドキュメントに変換することを意味します。CAD ツールを持っていないステークホルダーと設計を共有する際に便利です。

## なぜ IGS 変換に GroupDocs.Viewer を使うのか？
- **コード不要の CAD レンダリング** – ライブラリが IGS フォーマットの解析を自動で行います。  
- **複数の出力オプション** – 1 回の API 呼び出しで HTML、JPG、PNG、PDF のいずれかを生成できます。  
- **クロスプラットフォーム** – Java が動作する OS ならどこでも使用可能です。  
- **パフォーマンス重視** – 大規模アセンブリでも高速にレンダリングします。

## 前提条件
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8 以上** がインストールされ、IDE（IntelliJ IDEA、Eclipse、NetBeans など）で設定済み  
- 基本的な Maven の知識（任意だが推奨）  

## GroupDocs.Viewer for Java のセットアップ

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
GroupDocs.Viewer には次のオプションがあります。
- **無料トライアル** – 使用制限あり、簡単なテストに最適。  
- **一時ライセンス** – 短期間の評価でフル機能を利用可能。  
- **商用ライセンス** – 本番環境での無制限利用が可能。

### 基本的な Viewer の初期化
以下のスニペットは、IGS ファイルを指す `Viewer` インスタンスの作成方法を示しています。

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
HTML 出力は、3‑D モデルをインタラクティブかつブラウザフレンドリーに表示できます。

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

**重要ポイント:** `HtmlViewOptions.forEmbeddedResources()` は、必要な CSS や画像などのリソースをすべて HTML ファイルに埋め込み、ポータブルにします。

## IGS を JPG にレンダリング

### IGS を JPG に変換する方法は？
JPG 画像はサムネイルやクイックプレビューに最適です。

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

`JpgViewOptions` を調整して解像度や圧縮品質を制御できます。

## IGS を PNG にレンダリング

### IGS を PNG に変換する方法は？
PNG は透過をサポートしているため、異なる背景にモデルを重ねる際に便利です。

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

`PngViewOptions` を試して、ファイルサイズと画質のバランスを最適化してください。

## IGS を PDF にレンダリング

### IGS を PDF に変換する方法は？
PDF は詳細な設計ドキュメントを共有する際の定番フォーマットです。このセクションは主要キーワード **convert IGS to PDF** に直接答えます。

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

`PdfViewOptions` でページレイアウト、画像品質、フォント埋め込みの有無を制御できます。

## 実用例

- **Web ポータル** – HTML でレンダリングしたモデルを製品コンフィギュレータに直接埋め込む。  
- **マーケティング素材** – 高解像度の JPG/PNG 画像を作成し、パンフレットに使用。  
- **技術文書** – ユーザーマニュアルに CAD モデルの PDF レンダリングを組み込む。  
- **品質保証** – 大量の IGS ファイルに対してサムネイル自動生成を実施。

## よくある問題と解決策

| Issue | Solution |
|-------|----------|
| **出力フォルダーが見つからない** | `Path outputDirectory` に渡したパスを確認し、Java プロセスに書き込み権限があることを確認してください。 |
| **PDF が空白ページになる** | IGS ファイルが破損していないか確認し、まず CAD ビューアで開いてみてください。 |
| **大規模アセンブリでレンダリングが遅い** | JVM ヒープを増やす（例：`-Xmx2g` 以上）と、必要に応じて `viewer.getPageCount()` を使ってページ単位でレンダリングすることを検討してください。 |
| **PDF にフォントが欠けている** | `PdfViewOptions` で必要なフォントを埋め込むか、サーバーに欠損フォントをインストールしてください。 |

## Frequently Asked Questions

**Q: 複数の IGS ファイルを一度に変換できますか？**  
A: はい。ファイルパスのリストをループし、各ファイルに対して適切な `view` メソッドを呼び出すだけです。

**Q: PDF のページサイズをカスタマイズできますか？**  
A: もちろんです。`PdfViewOptions` の `setPageSize(PageSize.A4)` などのメソッドで設定できます。

**Q: 出力形式ごとに別々のライセンスが必要ですか？**  
A: いいえ。単一の GroupDocs.Viewer ライセンスでサポートされているすべての形式をカバーします。

**Q: パフォーマンスが低下する前に IGS ファイルはどのくらいのサイズまで対応できますか？**  
A: 数百メガバイトまでのファイルを扱えますが、非常に大きなモデルの場合は JVM メモリを増やす必要があります。

**Q: 特定のビューや向きだけをレンダリングできますか？**  
A: GroupDocs.Viewer はデフォルトビューをレンダリングします。カスタム向きが必要な場合は、変換前に CAD ツールで IGS ファイルを前処理してください。

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs