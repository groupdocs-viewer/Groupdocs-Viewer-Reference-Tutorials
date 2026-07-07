---
date: '2026-03-22'
description: GroupDocs Viewer for Java を使用して PDF から HTML を生成し、文字のグルーピングを無効にして正確なテキスト表現を実現する方法を学びましょう。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: PDFからHTMLを生成し、グルーピングを無効化 – GroupDocs Java
type: docs
url: /ja/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# PDF から HTML を生成し、GroupDocs Viewer for Java でグループ化を無効にする

多くのプロジェクトで **PDF から HTML を生成** し、すべてのグリフを正確な位置に保つ必要があります。これは、複雑なスクリプト、古代言語、または文字の位置が意味を左右する法的文書に特に当てはまります。このチュートリアルでは、GroupDocs Viewer for Java を使用して PDF を HTML にレンダリングする完全な手順を解説し、**文字のグループ化を無効にする方法** を示します。これにより、各文字が独立した要素として扱われます。

![GroupDocs.Viewer for Java を使用した精密なレンダリング技術](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## クイック回答
- **「グループ化を無効にする」とは何ですか？** レンダラに各文字を独立した要素として扱わせ、正確なレイアウトを保持します。  
- **どの API オプションがこれを制御しますか？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **ライセンスは必要ですか？** トライアルでテストは可能ですが、本番環境ではフルライセンスが必要です。  
- **HTML を同時に生成できますか？** はい—`HtmlViewOptions` を使用して、グループ化を無効にしたまま HTML 出力を作成できます。  
- **この機能は PDF のみですか？** 主に PDF 向けですが、ビューアは他の多くの形式もサポートしています。

## はじめに

PDF 文書を扱う際、特にヒエログリフや正確な文字表現が必要な言語を扱う場合、レンダリングの精度は極めて重要です。「文字のグループ化」機能は文字を誤ってまとめてしまい、文書内容の誤解を招くことがあります。これは、文書のテキストレイアウトを正確に再現する必要があるユーザーにとって重大な問題です。

### 前提条件

コード実装に入る前に、以下の要件を満たしていることを確認してください。
- **ライブラリ & 依存関係**: GroupDocs.Viewer for Java バージョン 25.2 以降が必要です。  
- **環境設定**: Java Development Kit (JDK) がインストールされており、IDE が Maven プロジェクトで動作するよう設定されていること。  
- **知識の前提**: Java プログラミングの基本、特にファイルパスの取り扱いと外部ライブラリの使用方法を理解していること。

## GroupDocs Viewer を使用して PDF から HTML を生成する方法

PDF から HTML を生成するプロセスは 2 段階です。ビューアを設定し、次にドキュメントをレンダリングします。重要なのは、レンダリング前に文字のグループ化をオフにすることで、HTML 出力が元の PDF のレイアウトを文字単位で忠実に再現できるようにすることです。

### GroupDocs.Viewer for Java のセットアップ

#### Maven でのインストール

まず、必要なライブラリをプロジェクトに統合します。`pom.xml` に以下の設定を追加してください。

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

#### ライセンス取得

GroupDocs.Viewer をフルに活用するには、ライセンスの取得をご検討ください。
- **無料トライアル**: 機能テスト用に無料トライアルを開始できます。  
- **一時ライセンス**: もっと時間が必要な場合は一時ライセンスを申請してください。  
- **購入**: 長期プロジェクトにはライセンス購入が推奨されます。

#### 基本的な初期化と設定

以下は、出力フォルダーの設定から文字のグループ化を無効にしたまま PDF を HTML にレンダリングするまでのフルワークフローを示す、すぐに実行可能なスニペットです。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### 実装ガイド

#### 機能: 文字のグループ化を無効にする

以下では、例の各行を分解して **なぜ** それを行うのか、そして **どのように** 文字のグループ化なしで PDF から HTML を生成できるのかを説明します。

##### 手順 1: 出力ディレクトリの定義  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**なぜ？** これにより、レンダリングされた HTML ファイルが専用フォルダーに保存され、後で簡単に見つけて管理できるようになります。

##### 手順 2: ファイルパス形式の設定  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**なぜ？** プレースホルダー (`{0}`) を使用すると、ビューアは各 PDF ページごとに別々の HTML ファイルを作成し、出力が整理された状態になります。

##### 手順 3: HTML ビューオプションの初期化  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**なぜ？** 埋め込みリソースは画像、フォント、CSS を各 HTML ページに直接バンドルするため、Web ビューアや e‑ラーニングプラットフォームに最適です。

##### 手順 4: 文字のグループ化を無効にする  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**なぜ？** これが重要な行で、レンダリングエンジンに **隣接する文字を結合しない** よう指示し、生成された HTML が元の PDF の正確なグリフ配置を反映することを保証します。

##### 手順 5: ドキュメントのレンダリング  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**なぜ？** `Viewer` を try‑with‑resources ブロックでラップすることで、すべてのネイティブリソースが自動的に解放され、長時間稼働するアプリケーションでのメモリリークを防止します。

### グループ化なしで Java の HTML を PDF から生成する

`HtmlViewOptions` クラスを使用すると、**PDF から HTML を生成** しつつ各文字を個別に保持できます。これは、正確なグリフ配置が求められる Web ポータルや e‑ラーニングプラットフォームにページを埋め込む際に特に便利です。

### よくある問題と解決策

- **FileNotFoundException** – `new Viewer(...)` に渡すパスを再確認してください。絶対パスまたは `Path.of(...)` の使用を推奨します。  
- **書き込み権限** – 出力ディレクトリが Java プロセスから書き込み可能であることを確認してください。Linux ではフォルダー権限 (`chmod 775`) を調整する必要があります。  
- **バージョン不一致** – `setDisableCharsGrouping` オプションはバージョン 25.2 以降で利用可能です。`pom.xml` が正しいバージョンを指しているか確認してください。  

### 実用例

1. **言語保存** – 中国語、日本語、アラビア語、または文字間隔が意味を持つ古代スクリプトの文書レンダリングに最適です。  
2. **法務・金融文書** – コンプライアンスが厳しい書類の正確なテキスト複製を保証します。  
3. **教育リソース** – 複雑な図表、注釈、マルチリンガルコンテンツを含む教科書に最適です。

### パフォーマンスに関する考慮点

- **リソース使用量の最適化** – 大容量 PDF はメモリを大量に消費します。ページをバッチ処理し、`Viewer` インスタンスを速やかに破棄することを検討してください。  
- **Java メモリ管理** – 複数百ページの PDF を処理する場合は、JVM ヒープ (`-Xmx2g` 以上) を調整してください。  
- **並列レンダリング** – 大量変換の場合、各スレッドに独自の `Viewer` インスタンスを持たせてマルチコア CPU を活用できます。

## よくある質問

**Q:** *なぜ文字のグループ化を無効にする必要があるのですか？*  
**A:** グループ化を無効にすると、別々のグリフに属する文字が結合されるのを防げます。これは、文字間隔や順序が意味を持つスクリプトにとって必須です。

**Q:** *`setDisableCharsGrouping` 設定は HTML 出力のみに適用されますか？*  
**A:** いいえ、PDF のレンダリングエンジン全体に影響するため、HTML、PNG、JPEG など任意の出力形式で変更が反映されます。

**Q:** *カスタムフォントとこの設定を組み合わせられますか？*  
**A:** はい。`Viewer` を初期化する前にカスタムフォントをロードすれば、グループ化ルールは引き続き適用されます。

**Q:** *グループ化を無効にするとパフォーマンスに影響しますか？*  
**A:** 各文字を個別に処理するため若干のオーバーヘッドがありますが、ほとんどの文書では影響は最小限です。

**Q:** *ページ単位でグループ化のオン/オフを切り替える方法はありますか？*  
**A:** 現在のところオプションは `PdfOptions` インスタンスごとにグローバルです。異なるページで異なる動作が必要な場合は、別々の `Viewer` インスタンスを使用してください。

## リソース

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-03-22  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作成者:** GroupDocs