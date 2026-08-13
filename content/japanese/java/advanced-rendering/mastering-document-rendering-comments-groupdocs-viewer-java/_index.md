---
categories:
- Java Development
date: '2026-05-21'
description: GroupDocs Viewer for Java を使用して、Word を HTML に変換し、コメント付きドキュメントをレンダリングする方法を学びます。ステップバイステップのガイド、トラブルシューティング、ベストプラクティスを提供。
keywords:
- convert word to html
- increase jvm heap
- groupdocs viewer java
- how to render comments
- render document comments
lastmod: '2026-05-21'
linktitle: GroupDocs Viewer Java チュートリアル
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to convert Word to HTML and render documents with comments
    using GroupDocs Viewer for Java. Step‑by‑step guide, troubleshooting, and best
    practices.
  headline: GroupDocs Viewer Java Tutorial - Convert Word to HTML and Render Documents
    with Comments
  type: TechArticle
- description: Learn how to convert Word to HTML and render documents with comments
    using GroupDocs Viewer for Java. Step‑by‑step guide, troubleshooting, and best
    practices.
  name: GroupDocs Viewer Java Tutorial - Convert Word to HTML and Render Documents
    with Comments
  steps:
  - name: Verify Java Installation
    text: 'Open a terminal and run: You should see a version string beginning with
      `1.8` or higher. If not, download the latest JDK from the official Oracle or
      OpenJDK website.'
  - name: Check Maven Installation
    text: 'Run: Maven should report its version and the Java version it uses. Install
      Maven from the Apache website if the command is not recognised.'
  - name: Create a New Maven Project
    text: 'Generate a skeleton project with: Navigate into the newly created `viewer-demo`
      folder and you’re ready to add GroupDocs Viewer.'
  - name: Set Up Your File Paths
    text: 'Organise your input and output locations early to avoid path‑related errors:
      **Why This Approach:** - Uses modern Java NIO.2 `Path` API, which is more reliable
      than `java.io.File`. - Descriptive variable names make debugging easier. - The
      `{0}` placeholder in the output pattern is automatically repl'
  - name: Configure HTML Rendering Options
    text: 'This is where the magic happens. We tell GroupDocs exactly how we want
      the document rendered: `HtmlViewOptions` configures how the document is rendered
      to HTML, including resource handling and comment rendering. **Key Configuration
      Details:** - `forEmbeddedResources()` embeds CSS, images, and fonts '
  - name: Execute the Rendering
    text: 'Now we bring everything together: `Viewer` is the primary class used to
      load a document and perform rendering operations. The `view` call reads the
      Word file, extracts comments, generates HTML pages, and writes them to `output/html`.
      Each page is saved as `page_1.html`, `page_2.html`, etc.'
  type: HowTo
- questions:
  - answer: Yes—simply omit the `setRenderComments(true)` call or set it to `false`.
    question: Can I render documents without comments?
  - answer: Most major formats—including DOC/DOCX, XLS/XLSX, PPT/PPTX, PDF, and many
      more. See the [official documentation](https://docs.groupdocs.com/viewer/java/)
      for the full list.
    question: What file formats support comment rendering?
  - answer: Absolutely. Use `HtmlViewOptions.setEmbedResources(false)` to generate
      external CSS files, then add your own stylesheet after rendering.
    question: Can I customize the HTML output styling?
  - answer: 'Provide a `LoadOptions` instance with the password:'
    question: How do I handle password‑protected documents?
  - answer: 'Yes—use the overloaded `view` method that accepts a `PageNumber` collection:'
    question: Is it possible to render only specific pages?
  type: FAQPage
tags:
- groupdocs-viewer
- java-tutorial
- document-rendering
- html-conversion
title: GroupDocs Viewer Java チュートリアル - Word を HTML に変換し、コメント付きドキュメントをレンダリング
type: docs
url: /ja/java/advanced-rendering/mastering-document-rendering-comments-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer Java チュートリアル: Word を HTML に変換し、コメント付きドキュメントをレンダリング

## はじめに

レビューアのメモ、コメント、注釈をすべて保持したまま **Word を HTML に変換** したい場合、ここが正しい場所です。多くの Java 開発者は、ドキュメント変換時に元ファイルに埋め込まれた貴重なフィードバックが失われる壁にぶつかります。このチュートリアルでは、GroupDocs Viewer for Java を使用して **Word を HTML に変換** し、Word、Excel、PowerPoint、PDF など幅広いドキュメントタイプをコメントデータを失わずにレンダリングする方法をステップバイステップで解説します。

GroupDocs Viewer が本番環境に適した選択肢である理由、環境設定方法、必要な正確なコード、そして大容量ファイルでもパフォーマンスを高速に保つ実証済みのコツを学べます。

![コメント付きドキュメントを GroupDocs.Viewer for Java でレンダリング](/viewer/advanced-rendering/render-documents-with-comments.png)

[コメント付きドキュメントを GroupDocs.Viewer for Java でレンダリング](/viewer/advanced-rendering/render-documents-with-comments.png)

**このチュートリアルで習得できること:**
- GroupDocs Viewer の完全なセットアップと構成
- ステップバイステップでコメントを保持した **Word を HTML に変換**
- 一般的なトラブルシューティングの解決策と回避すべき落とし穴
- 実践的な実装パターンとベストプラクティス
- 本番環境でのパフォーマンス最適化技術

## クイック回答
- **GroupDocs Viewer は Word を HTML に変換できますか？** はい—HTML レンダリングとコメントサポートを 1 行のコードで有効にできます。  
- **コメントは HTML 出力に残りますか？** 絶対に残ります—`setRenderComments(true)` がすべてのコメントと注釈を保持します。  
- **必要な Java バージョンは？** JDK 8 以上。  
- **本番環境でライセンスは必要ですか？** フルライセンスは透かしを除去し、すべての機能を利用可能にします。  
- **レンダリング速度を向上させる方法は？** 特定のページだけをレンダリングし、外部リソースを使用し、JVM ヒープサイズを増やします。

## 「コメント付きで Word を HTML に変換」とは？
*「Word を HTML に変換」* とは、Microsoft Word の *.docx* ファイルをウェブ対応の HTML ドキュメントに変換し、元のレイアウト、スタイル、埋め込まれたコメントを保持することを意味します。このプロセスにより、ブラウザは作者が意図した通りに、レビューアのフィードバックを含むドキュメントを正確に表示できます。

## なぜ GroupDocs Viewer for Java を選ぶのか？

コードに入る前に、なぜ GroupDocs Viewer が Java ベースのドキュメントレンダリングに最適なライブラリなのかを見てみましょう：

- **170 以上のサポート形式** – ライブラリは DOCX から CAD ファイルまで対応し、すべての変換ニーズを単一の依存関係で満たします。  
- **サードパーティの Office インストール不要** – Microsoft Office、LibreOffice、その他の重いランタイムが不要で、任意の OS で動作します。  
- **フォーマットと注釈を保持** – コメント、脚注、変更履歴が変換後もそのまま残ります。  
- **高速で軽量なエンジン** – 標準的な 4 コアサーバーで、通常の 100 ページ文書は 2 秒未満でレンダリングされます。  
- **充実したドキュメントと活発なコミュニティ** – 問題が発生した際に、サンプル、フォーラム、迅速なサポートが利用できます。

### このアプローチを使用すべき時
- レビューアのノートを表示する必要がある Web ベースのドキュメントビューアの構築  
- フィードバックを可視化したままにする共同レビュー プラットフォームの作成  
- 法務ポータルでオンライン表示するためのレガシー契約書の変換  
- 学習教材に講師のコメントを埋め込む e‑ラーニングソリューションの開発  

## 前提条件と環境設定

### 必要なもの
- **Java Development Kit (JDK) 8+** – アプリケーションを動かすランタイムです。  
- **Maven 3.6+** – 依存関係管理とプロジェクトビルドに使用します。  
- **お好みの IDE** – IntelliJ IDEA、Eclipse、または VS Code。  
- **コメント付きサンプルドキュメント** – レビューアのノートが含まれる DOCX、XLSX、PPTX ファイル。

### 開発環境の設定

#### 手順 1: Java インストールの確認
ターミナルを開いて次を実行してください:

```
java -version
```

`1.8` 以上で始まるバージョン文字列が表示されるはずです。表示されない場合は、公式の Oracle または OpenJDK のウェブサイトから最新の JDK をダウンロードしてください。

#### 手順 2: Maven インストールの確認
実行:

```
mvn -v
```

Maven はバージョンと使用している Java バージョンを報告するはずです。コマンドが認識されない場合は、Apache のウェブサイトから Maven をインストールしてください。

#### 手順 3: 新しい Maven プロジェクトの作成
上記でスケルトンプロジェクトを生成します。作成された `viewer-demo` フォルダーに移動すれば、GroupDocs Viewer を追加する準備が整います。

```
mvn archetype:generate -DgroupId=com.example.viewer -DartifactId=viewer-demo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

## GroupDocs.Viewer for Java の設定

### 依存関係の追加
最初のステップは、プロジェクトにライブラリを導入することです。以下の設定を `pom.xml` ファイルに追加してください:

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

**プロのコツ:** 常に [GroupDocs releases page](https://releases.groupdocs.com/viewer/java/) で最新バージョンを確認してください。ライブラリは定期的に更新・バグ修正が行われています。

### ライセンスオプションの理解
GroupDocs はプロジェクトのニーズに合わせた柔軟なライセンスを提供します：

- **無料トライアル（学習に最適）:** フル機能と評価用透かし付きの 30 日間評価。  
- **一時ライセンス（開発向け）:** 透かしなしの拡張評価。概念実証プロジェクトに最適です。申請は [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) から。  
- **フルライセンス（本番向け）:** 制限や透かしがなく、商用利用が可能です。購入は [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) から。

### 基本的な初期化パターン
このチュートリアル全体で使用する基本パターンは次の通りです:

```java
try (Viewer viewer = new Viewer("input.docx")) {
    // Rendering options will be set later
}
```

**このパターンが有効な理由:**
- **自動リソース管理** によりメモリリークを防止します。  
- **例外処理** により一般的なファイルアクセス問題を捕捉します。  
- **クリーンで読みやすいコード** は大規模プロジェクトでも保守が容易です。

## コア実装: コメント付きドキュメントのレンダリング

### プロセスの理解
ドキュメントをレンダリングするとき、ライブラリは次の 4 つの重要なステップを実行します：

1. **ドキュメント分析** – 入力ファイルを解析し、内部表現を構築します。  
2. **コメント抽出** – すべてのコメント、脚注、注釈を特定します。  
3. **HTML 生成** – 元のレイアウトを忠実に再現した、クリーンで標準準拠の HTML を作成します。  
4. **リソース処理** – 画像、CSS、フォントをインラインまたは外部ファイルとしてバンドルします。

### ステップバイステップ実装

#### 手順 1: ファイルパスの設定
入力と出力の場所を早めに整理して、パス関連のエラーを防ぎます:

```java
Path inputPath = Paths.get("documents/sample-with-comments.docx");
Path outputDir = Paths.get("output/html");
Files.createDirectories(outputDir);
```

**このアプローチの理由:**
- `java.io.File` より信頼性の高い最新の Java NIO.2 `Path` API を使用します。  
- 変数名が説明的でデバッグが容易です。  
- 出力パターンの `{0}` プレースホルダーはページ番号に自動置換されます。

#### 手順 2: HTML レンダリングオプションの設定
ここが魔法の場所です。`HtmlViewOptions` はリソース処理やコメントレンダリングを含め、ドキュメントを HTML にレンダリングする方法を設定します。

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(outputDir);
viewOptions.setRenderComments(true);   // Preserve every comment
viewOptions.setPageNumberPrefix("page_");
```

**主な設定詳細:**
- `forEmbeddedResources()` は CSS、画像、フォントを HTML に直接埋め込み、出力をポータブルにします。  
- `setRenderComments(true)` は、**Word を HTML に変換** でレビューアのノートをすべて保持する唯一の行です。  
- 代替の `forExternalResources()` は、HTML ファイルを軽量化したい場合にアセットを別途保存できます。

#### 手順 3: レンダリングの実行
すべてをまとめます:

`Viewer` はドキュメントを読み込み、レンダリング操作を実行する主要クラスです。

```java
try (Viewer viewer = new Viewer(inputPath.toFile())) {
    viewer.view(viewOptions);
}
```

`view` 呼び出しは Word ファイルを読み込み、コメントを抽出し、HTML ページを生成して `output/html` に書き込みます。各ページは `page_1.html`、`page_2.html` などとして保存されます。

### 完全な動作例
すべての部品を組み合わせると、コメントを保持したまま Word ドキュメントを HTML に変換する単一の実行可能クラスが得られます。（完全なソースコードは公式 GitHub リポジトリで入手可能です。）

## 高度な設定とオプション

### 動的出力ディレクトリの設定
大規模アプリケーションでは、ユーザー ID やタイムスタンプに基づいて出力ディレクトリを生成したい場合があります:

```java
String userId = "12345";
Path dynamicOutput = Paths.get("output", userId, LocalDate.now().toString());
Files.createDirectories(dynamicOutput);
HtmlViewOptions dynamicOptions = HtmlViewOptions.forEmbeddedResources(dynamicOutput);
```

### よくある問題とトラブルシューティング

#### 問題 1: “File Not Found” エラー
入力パスが絶対パスか作業ディレクトリからの相対パスであること、ファイル権限を確認してください。`Path` オブジェクトを使用すると文字列結合ミスを防げます。

#### 問題 2: 出力にコメントが表示されない
`viewer.view()` の **前** に `setRenderComments(true)` が呼び出されているか確認してください。また、ソースドキュメントに実際にコメントが含まれているか `viewer.getDocumentInfo().getComments()` で検査できます。

#### 問題 3: 大容量ドキュメントでのメモリ不足エラー
GroupDocs Viewer はデータをストリーミングしますが、500 ページ超の超大型ファイルは JVM ヒープを圧迫する可能性があります。`-Xmx4g` でヒープを増やすか、必要なページだけをレンダリングしてください。

#### 問題 4: レンダリング速度が遅い
`viewer.view(pageRange, viewOptions)` で特定のページ範囲だけをレンダリングします。外部リソース (`forExternalResources()`) を使用すると HTML ペイロードが小さくなり、ブラウザ側の表示が高速化します。

## 実務での実装パターン

### パターン 1: Web アプリケーション統合
Spring Boot コントローラにレンダリングロジックを統合し、オンデマンドで HTML を提供します:

```java
@RestController
@RequestMapping("/api/view")
public class DocumentController {

    @GetMapping("/{id}")
    public ResponseEntity<Resource> renderDocument(@PathVariable String id) throws IOException {
        Path docPath = Paths.get("documents", id + ".docx");
        Path outDir = Files.createTempDirectory("viewer");
        HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(outDir);
        options.setRenderComments(true);
        try (Viewer viewer = new Viewer(docPath.toFile())) {
            viewer.view(options);
        }
        // Return the first HTML page as a Resource
        Path firstPage = outDir.resolve("page_1.html");
        Resource resource = new UrlResource(firstPage.toUri());
        return ResponseEntity.ok()
                .contentType(MediaType.TEXT_HTML)
                .body(resource);
    }
}
```

### パターン 2: 複数ドキュメントのバッチ処理
フォルダー全体を変換する必要がある場合、ディレクトリをループし、`HtmlViewOptions` インスタンスを再利用してオブジェクト生成のオーバーヘッドを最小化します。

## パフォーマンス最適化とベストプラクティス

### メモリ管理のヒント
- **`Viewer` インスタンスは常に try‑with‑resources を使用** してください。  
- **大容量ドキュメントはバッチ処理** で、すべてを一度にメモリにロードしないようにします。  
- **VisualVM などのツールで JVM ヒープ使用量を監視** し、必要に応じて `-Xmx` を調整します。  
- **頻繁にアクセスされるドキュメントに適切なキャッシュを実装** し、再レンダリングを回避します。

### リソース使用ガイドライン

**小規模アプリケーション（< 100 ドキュメント/日）向け:**

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(Paths.get("output"));
options.setRenderComments(true);
```

**高負荷アプリケーション（1000+ ドキュメント/日）向け:**

```java
HtmlViewOptions options = HtmlViewOptions.forExternalResources(Paths.get("output"));
options.setRenderComments(true);
options.setCacheEnabled(true);
```

### キャッシュ戦略
レンダリングされた HTML をドキュメントハッシュをキーとした分散キャッシュ（例: Redis）に保存します。リクエストが来たらまずキャッシュを確認し、ヒットした場合はレンダリングエンジンをバイパスして即座に HTML を返します。

## GroupDocs Viewer と代替品の使い分け

### GroupDocs Viewer が最適なケース
- **ドキュメント管理システム** – 多種多様なファイルタイプと注釈を表示する必要がある場合。  
- **共同レビュー プラットフォーム** – コメントを全参加者に可視化したままにする必要がある場合。  
- **教育ツール** – 講師のノートが講義スライドと共に表示される場合。  
- **法務アプリケーション** – 弁護士のコメント付き契約書を忠実にレンダリングする必要がある場合。

### 代替品を検討すべきケース
- **シンプルな PDF 表示** – ブラウザのネイティブ PDF ビューアで十分な場合。  
- **基本的な画像変換** – `ImageIO` などの軽量ライブラリが適している場合。  
- **純粋なテキスト抽出** – Apache POI や iText の方が適切な場合。

## よくある質問

**Q: コメントなしでドキュメントをレンダリングできますか？**  
A: はい—`setRenderComments(true)` の呼び出しを省略するか、`false` に設定すれば可能です。

**Q: どのファイル形式がコメントレンダリングに対応していますか？**  
A: ほとんどの主要フォーマット—DOC/DOCX、XLS/XLSX、PPT/PPTX、PDF など—が対応しています。完全な一覧は [official documentation](https://docs.groupdocs.com/viewer/java/) をご覧ください。

**Q: HTML 出力のスタイルをカスタマイズできますか？**  
A: もちろんです。`HtmlViewOptions.setEmbedResources(false)` を使用して外部 CSS ファイルを生成し、レンダリング後に独自のスタイルシートを追加してください。

**Q: パスワード保護されたドキュメントはどう処理しますか？**  
A: パスワードを含む `LoadOptions` インスタンスを提供します:

`LoadOptions` はパスワードなどのドキュメント読み込みパラメータを指定できます。

```java
LoadOptions loadOptions = new LoadOptions("myPassword");
try (Viewer viewer = new Viewer(inputPath.toFile(), loadOptions)) {
    viewer.view(viewOptions);
}
```

**Q: 特定のページだけをレンダリングできますか？**  
A: はい—`PageNumber` コレクションを受け取るオーバーロードされた `view` メソッドを使用します:

`PageNumber` は、ページのサブセットをレンダリングする際に使用する特定のページインデックスを表します。

```java
viewer.view(new int[]{1, 3, 5}, viewOptions);
```

**Q: 大容量ドキュメントのレンダリングが遅いのはなぜですか？**  
A: 大容量ファイルは処理に時間がかかります。必要なページだけをレンダリングし、外部リソースを使用し、JVM ヒープを増やし、非同期処理を有効にすることで速度を向上させます。

**Q: レンダリングの進捗を監視するには？**  
A: GroupDocs Viewer には組み込みのコールバックはありませんが、`viewer.view()` の前後で `System.nanoTime()` を使用して処理時間を測定し、ログに記録できます。

**Q: ソースドキュメントが破損している場合はどうなりますか？**  
A: ライブラリは `ViewerException` をスローします。呼び出しを try‑catch ブロックで囲み、エラーをログに記録して穏やかに処理してください。

**Q: 商用アプリケーションで GroupDocs Viewer を使用できますか？**  
A: はい、商用ライセンスが必要です。無料トライアルは透かしが入っており、本番環境で使用するには除去が必要です。

**Q: 使用制限はありますか？**  
A: ライブラリ自体に制限はありませんが、ライセンス契約で使用上限が定められる場合があります。詳細は契約書をご確認ください。

**Q: GroupDocs Viewer を含むアプリケーションを再配布できますか？**  
A: 自分のアプリケーションは配布可能ですが、GroupDocs ライブラリのバイナリ自体を再配布することはできません。ライセンス条項をご確認ください。

## 次のステップと高度なトピック

これで **Word を HTML に変換** しながらコメントを保持するための確固たる基盤ができました。以下の方向で知識を深めてください:

- **透かし** – ブランドや機密性のためにレンダリングページにカスタム透かしを追加します。  
- **メタデータ抽出** – `viewer.getDocumentInfo()` を使用して作者、作成日、ページ数を取得します。  
- **カスタムビューア** – PDF、スプレッドシート、プレゼンテーション用に、コメントを異なる方法で非表示または強調表示する専門ビューアを構築します。  
- **クラウドストレージ統合** – AWS S3、Azure Blob、Google Drive から直接ファイルをレンダリングし、ローカルにダウンロードしません。

### 推奨学習パス
1. **さまざまなファイルタイプで実験** – Excel、PowerPoint、PDF ファイルでコメントの処理方法を確認します。  
2. **シンプルな Web ビューアの構築** – 生成された HTML を `<iframe>` または AJAX で読み込む最小限の HTML ページを作成します。  
3. **GroupDocs エコシステムの探索** – エンドツーエンドのドキュメントワークフロー向けに GroupDocs Annotation、Comparison、Signature を確認します。  
4. **コミュニティに参加** – ヒント、サンプルプロジェクト、サポートのために [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) に参加してください。

### ヘルプとサポートの取得

**公式リソース**
- [GroupDocs.Viewer ドキュメント](https://docs.groupdocs.com/viewer/java/)  
- [API リファレンス](https://apireference.groupdocs.com/viewer/java)  
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)  
- [GitHub サンプル](https://github.com/groupdocs-viewer/GroupDocs.Viewer-for-Java)

**コミュニティリソース**
- Stack Overflow (tag: `groupdocs-viewer`)  
- Reddit programming communities  
- Java developer Discord servers  

**最終更新日:** 2026-05-21  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs

```bash
java -version
javac -version
```

```bash
mvn -version
```

```bash
mvn archetype:generate -DgroupId=com.example.documentviewer -DartifactId=groupdocs-viewer-demo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

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
import com.groupdocs.viewer.Viewer;

// The try-with-resources pattern ensures proper cleanup
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // All rendering operations happen here
    // Resources are automatically closed when done
} catch (Exception e) {
    System.err.println("Error rendering document: " + e.getMessage());
    e.printStackTrace();
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Create a descriptive output directory
Path outputDirectory = Paths.get("rendered-documents");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create HTML options with embedded resources
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);

// The crucial setting – enable comment rendering!
viewOptions.setRenderComments(true);
```

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Create output directory if it doesn't exist
    if (!outputDirectory.toFile().exists()) {
        outputDirectory.toFile().mkdirs();
    }
    
    // Perform the actual rendering
    viewer.view(viewOptions);
    
    System.out.println("Document rendered successfully!");
    System.out.println("Output location: " + outputDirectory.toAbsolutePath());
    
} catch (Exception e) {
    System.err.println("Rendering failed: " + e.getMessage());
    e.printStackTrace();
}
```

```java
package com.example.documentviewer;

import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class DocumentRenderer {
    
    public static void main(String[] args) {
        renderDocumentWithComments("sample-document.docx", "output");
    }
    
    public static void renderDocumentWithComments(String inputFile, String outputDir) {
        // Set up paths
        Path outputDirectory = Paths.get(outputDir);
        Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
        
        // Configure rendering options
        HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
        viewOptions.setRenderComments(true);
        
        // Render the document
        try (Viewer viewer = new Viewer(inputFile)) {
            // Ensure output directory exists
            outputDirectory.toFile().mkdirs();
            
            // Execute rendering
            viewer.view(viewOptions);
            
            System.out.println("✓ Document rendered with comments preserved");
            System.out.println("📂 Output directory: " + outputDirectory.toAbsolutePath());
            
        } catch (Exception e) {
            System.err.println("❌ Rendering failed: " + e.getMessage());
            e.printStackTrace();
        }
    }
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class PathManager {
    
    /**
     * Creates a structured output path based on document name and timestamp
     */
    public static Path getOutputDirectoryPath(String documentName) {
        String timestamp = String.valueOf(System.currentTimeMillis());
        String cleanDocName = documentName.replaceAll("[^a-zA-Z0-9]", "_");
        
        return Paths.get("rendered-docs")
                   .resolve(cleanDocName)
                   .resolve(timestamp);
    }
    
    /**
     * Simple output directory for basic use cases
     */
    public static Path getSimpleOutputPath(String folderName) {
        return Paths.get("output").resolve(folderName);
    }
}
```

```java
// Always check if file exists before processing
Path inputPath = Paths.get("your-document.docx");
if (!inputPath.toFile().exists()) {
    throw new IllegalArgumentException("Input file not found: " + inputPath.toAbsolutePath());
}

// Check if file is readable
if (!inputPath.toFile().canRead()) {
    throw new IllegalArgumentException("Cannot read input file: " + inputPath.toAbsolutePath());
}
```

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
// This line is crucial – don't forget it!
viewOptions.setRenderComments(true);

// For debugging, you can verify the setting:
System.out.println("Comments enabled: " + viewOptions.isRenderComments());
```

```java
// Increase JVM heap size when running
// java -Xmx2g -Xms1g YourApplication

// Or process documents page by page for very large files
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setRenderComments(true);

// Render only specific pages if needed
viewer.view(viewOptions, 1, 2, 3); // Renders only pages 1, 2, and 3
```

```java
// Use external resources for faster processing of multiple pages
HtmlViewOptions viewOptions = HtmlViewOptions.forExternalResources(
    pageFilePathFormat, 
    "resources/page_{0}/", 
    "resources/page_{0}/{0}"
);

// Enable caching if processing the same document multiple times
// (Note: Implement caching at application level)
```

```java
@RestController
@RequestMapping("/api/documents")
public class DocumentController {
    
    @PostMapping("/render")
    public ResponseEntity<String> renderDocument(
            @RequestParam("file") MultipartFile file) {
        
        try {
            // Save uploaded file temporarily
            Path tempFile = Files.createTempFile("upload", ".tmp");
            file.transferTo(tempFile.toFile());
            
            // Render with comments
            String outputDir = renderDocumentWithComments(
                tempFile.toString(), 
                "web-output"
            );
            
            return ResponseEntity.ok("Document rendered: " + outputDir);
            
        } catch (Exception e) {
            return ResponseEntity.badRequest()
                .body("Rendering failed: " + e.getMessage());
        }
    }
}
```

```java
public class BatchDocumentProcessor {
    
    public void processFolderWithComments(String inputFolder) {
        File folder = new File(inputFolder);
        File[] files = folder.listFiles((dir, name) -> 
            name.toLowerCase().endsWith(".docx") || 
            name.toLowerCase().endsWith(".xlsx") ||
            name.toLowerCase().endsWith(".pptx")
        );
        
        if (files == null) return;
        
        for (File file : files) {
            try {
                String outputDir = file.getName().replace(".", "_") + "_output";
                renderDocumentWithComments(file.getAbsolutePath(), outputDir);
                System.out.println("✓ Processed: " + file.getName());
                
            } catch (Exception e) {
                System.err.println("❌ Failed to process " + file.getName() + ": " + e.getMessage());
            }
        }
    }
}
```

```java
// Simple approach works fine
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
}
```

```java
public class DocumentRenderingService {
    private final ExecutorService executorService = 
        Executors.newFixedThreadPool(4); // Limit concurrent renderings
    
    public CompletableFuture<String> renderAsync(String documentPath) {
        return CompletableFuture.supplyAsync(() -> {
            try (Viewer viewer = new Viewer(documentPath)) {
                // Rendering logic here
                return "success";
            } catch (Exception e) {
                throw new RuntimeException(e);
            }
        }, executorService);
    }
}
```

```java
public class CachedDocumentRenderer {
    private final Map<String, String> renderCache = new ConcurrentHashMap<>();
    
    public String renderWithCaching(String documentPath) {
        String cacheKey = generateCacheKey(documentPath);
        
        return renderCache.computeIfAbsent(cacheKey, key -> {
            // Only render if not already cached
            return performActualRendering(documentPath);
        });
    }
    
    private String generateCacheKey(String documentPath) {
        // Include file modification time in cache key
        File file = new File(documentPath);
        return documentPath + "_" + file.lastModified();
    }
}
```

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your-password");
try (Viewer viewer = new Viewer("protected-doc.docx", loadOptions)) {
    // Render as usual
}
```

```java
viewer.view(viewOptions, 1, 3, 5); // Renders only pages 1, 3, and 5
```

```java
System.out.println("Starting render for: " + documentName);
long startTime = System.currentTimeMillis();
viewer.view(viewOptions);
long endTime = System.currentTimeMillis();
System.out.println("Rendering completed in: " + (endTime - startTime) + "ms");
```

```java
try (Viewer viewer = new Viewer(documentPath)) {
    viewer.view(viewOptions);
} catch (CorruptOrDamagedFileException e) {
    System.err.println("Document is corrupted: " + e.getMessage());
} catch (Exception e) {
    System.err.println("General error: " + e.getMessage());
}
```

## 関連チュートリアル

- [GroupDocs.Viewer for Java で Word 文書のトラッキング変更をレンダリング](/viewer/java/advanced-rendering/render-tracked-changes-word-docs-groupdocs-viewer-java/)
- [GroupDocs.Viewer for Java のレスポンシブ HTML レンダリング: 包括的ガイド](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [GroupDocs.Viewer for Java を使用してドキュメントを HTML としてロードおよびレンダリングする方法](/viewer/java/rendering-basics/groupdocs-viewer-java-html-rendering/)