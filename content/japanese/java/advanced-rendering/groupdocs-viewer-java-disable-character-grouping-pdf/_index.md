---
date: '2025-12-21'
description: GroupDocs.Viewer for Java を使用して PDF のグループ化を無効にする方法を学び、PDF レンダリングオプションの
  Java HTML を活用して正確なテキスト表現を実現します。
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: GroupDocs.Viewer for JavaでPDFのグルーピングを無効にする方法
type: docs
url: /ja/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# PDFでのグルーピングを無効にする方法（GroupDocs.Viewer for Java）

PDFをレンダリングする際に **グルーピングを無効にする方法** が必要な場合、特に複雑なスクリプトや古代言語の場合、正確な文字配置が不可欠です。デフォルトの *Character Grouping* 機能は文字を誤って結合し、コンテンツの誤解を招くことがあります。このガイドでは、GroupDocs.Viewer for Java を使用してグルーピングを無効にする手順をステップバイステップで示し、すべてのグリフが正確な位置に保たれるようにします。

![GroupDocs.Viewer for Java を使用した精密レンダリング技術](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## クイック回答
- **“disable grouping” は何をしますか？** レンダラーに各文字を独立した要素として扱わせ、正確なレイアウトを保持します。  
- **どの API オプションがこれを制御しますか？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **ライセンスは必要ですか？** テストにはトライアルで動作しますが、本番環境ではフルライセンスが必要です。  
- **PDF から同時に Java HTML を生成できますか？** はい—`HtmlViewOptions` を使用して、グルーピングを無効にしながら HTML 出力を作成できます。  
- **この機能は PDF に限定されていますか？** 主に PDF 用ですが、ビューアは他の多くの形式もサポートしています。

## はじめに

PDFドキュメントを扱う際、レンダリングの精度は極めて重要です—特に、象形文字や正確な文字表現が必要な言語など、複雑なテキスト構造を扱う場合はなおさらです。「Character Grouping」機能は文字を誤ってグループ化し、ドキュメント内容の誤解を招くことがあります。これは、ドキュメントのテキストレイアウトを正確に再現する必要があるユーザーにとって特に問題となります。

### 前提条件
- **Libraries & Dependencies**: GroupDocs.Viewer for Java バージョン 25.2 以降が必要です。  
- **Environment Setup**: Java Development Kit (JDK) がインストールされており、IDE が Maven プロジェクトで動作するよう設定されていることを確認してください。  
- **Knowledge Prerequisites**: Java プログラミングの基本的な理解、特にファイルパスの取り扱いと外部ライブラリの使用に関する知識が必要です。

## PDF レンダリングでグルーピングを無効にする方法

### GroupDocs.Viewer for Java の設定

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

GroupDocs.Viewer をフル活用するには、ライセンス取得を検討してください：
- **Free Trial**: 機能をテストするために無料トライアルから始めてください。  
- **Temporary License**: もっと時間が必要な場合は、一時ライセンスを申請してください。  
- **Purchase**: 長期プロジェクトの場合は、ライセンスを購入することをお勧めします。

#### 基本的な初期化と設定

プロジェクト環境の設定から始めます。

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

#### 機能: 文字のグルーピングを無効にする

##### 手順 1: 出力ディレクトリの定義

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Why?** この手順は出力を整理し、簡単にアクセスできるようにします。

##### 手順 2: ファイルパス形式の設定

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Why?** PDF ドキュメントのページを体系的に整理するのに役立ちます。

##### 手順 3: HTML View Options の初期化

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Why?** 埋め込みリソースにより、各ページの HTML ファイルに必要なすべてのアセットが含まれます。

##### 手順 4: 文字のグルーピングを無効にする

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Why?** 文字が個別にレンダリングされ、意図したレイアウトと意味が保持されます。

##### 手順 5: ドキュメントのレンダリング

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Why?** すべてのリソースが適切にクローズされ、メモリリークを防止します。

### グルーピングなしで PDF から Java HTML を生成する

`HtmlViewOptions` クラスを使用すると、**java html from pdf** を生成しながら各文字を個別に保つことができます。これは、正確なグリフ配置が重要なウェブポータルや e‑learning プラットフォームにレンダリングされたページを埋め込む必要がある場合に特に便利です。

### トラブルシューティングのヒント
- `FileNotFoundException` を回避するために、ドキュメントパスが正しいことを確認してください。  
- 出力ディレクトリに書き込み権限があることを確認してください。  
- 使用している GroupDocs.Viewer for Java のバージョンが互換性があるか再確認してください。

## 実用的な応用例
1. **Language Preservation**: 中国語、日本語、または古代文字など、文字の精度が重要な言語のドキュメントをレンダリングするのに最適です。  
2. **Legal and Financial Documents**: コンプライアンスのために正確なテキスト表現が必要なドキュメントの正確性を保証します。  
3. **Educational Resources**: 複雑な図や注釈を含む教科書や学術論文に最適です。

## パフォーマンスに関する考慮事項
- **Optimize Resource Usage**: 大きな PDF ファイルを処理できるよう、サーバーに十分なリソースがあることを確認してください。  
- **Java Memory Management**: 効率的なデータ構造とガベージコレクションの実践を使用して、メモリを効果的に管理してください。  
- **Batch Processing**: 複数のドキュメントをレンダリングする際は、バッチ処理でスループットを向上させます。

## 結論

これで、GroupDocs.Viewer for Java を使用した PDF レンダリング時の **グルーピングを無効にする方法** を習得しました。この機能は、正確なテキスト表現が求められるアプリケーションにとって重要です。さらに探求するには、この機能を他のドキュメント管理システムと統合したり、追加のレンダリングオプションを試したりしてください。

次のステップとして、GroupDocs.Viewer のより高度な機能を探求し、大規模展開向けにパフォーマンスを微調整してください。

## よくある質問

**Q:** *なぜ文字のグルーピングを無効にする必要があるのでしょうか？*  
**A:** グルーピングを無効にすると、レンダラーが別々のグリフに属する文字を結合するのを防ぎます。これは、間隔や順序が意味を伝えるスクリプトにとって不可欠です。

**Q:** *`setDisableCharsGrouping` 設定は HTML 出力のみに適用されますか？*  
**A:** いいえ、基礎となる PDF レンダリングエンジンに影響するため、HTML、PNG などのすべての出力形式に変更が反映されます。

**Q:** *この設定をカスタムフォントと組み合わせられますか？*  
**A:** はい—`Viewer` を初期化する前にカスタムフォントをロードすれば、グルーピング規則は引き続き適用されます。

**Q:** *グルーピングを無効にするとパフォーマンスに影響しますか？*  
**A:** 若干の影響があります。エンジンが各文字を個別に処理するためですが、ほとんどのドキュメントでは影響は最小限です。

**Q:** *ページ単位でグルーピングを切り替える方法はありますか？*  
**A:** 現在、このオプションは `PdfOptions` インスタンスごとにグローバルです。異なるページごとに切り替えるには、別々の `Viewer` インスタンスを作成する必要があります。

## リソース
- [GroupDocs ドキュメント](https://docs.groupdocs.com/viewer/java/)
- [API リファレンス](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs Viewer のダウンロード](https://releases.groupdocs.com/viewer/java/)
- [ライセンス購入](https://purchase.groupdocs.com/buy)
- [無料トライアル版](https://releases.groupdocs.com/viewer/java/)
- [一時ライセンス申請](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2025-12-21  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs