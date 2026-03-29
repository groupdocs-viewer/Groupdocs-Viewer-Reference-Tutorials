---
date: '2026-03-29'
description: GroupDocs Viewer を使用して Java でページを 90 度回転させる方法を学び、セットアップ、コード、パフォーマンスのヒントを含めましょう。
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: GroupDocs Viewer for Javaでページを90度回転させる
type: docs
url: /ja/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Javaでページを90度回転する

ドキュメント（PDF、Word ファイル、スプレッドシートなど）で **ページを90度回転** する必要がある場合、プログラムで実行すれば時間を節約でき、手動ミスを防げます。この上級ガイドでは、**GroupDocs Viewer for Java** を使用して、サポートされている任意のドキュメントの最初のページを回転させる正確な手順を解説します。最後まで読むと、プロジェクトに組み込める再利用可能なスニペットが手に入ります。  
また、Java でページを回転させる意義や、この手法が有効な一般的なシナリオ、そして処理を軽量に保つ方法についても説明します。

![GroupDocs.Viewer for Javaでドキュメントの最初のページを回転](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## クイック回答
- **「ページを90度回転する」とは何ですか？** 選択したページを時計回りに90度回転させます。  
- **どのライブラリが回転を処理しますか？** GroupDocs Viewer for Java は `rotatePage` メソッドを提供します。  
- **Java で PDF ページを回転できますか？** はい。同じ `rotatePage` 呼び出しを使用します。PDF、DOCX、XLSX などでも動作します。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用できますが、本番環境では有料ライセンスが必要です。  
- **この操作はメモリ集約的ですか？** `Viewer` インスタンスをすぐに閉じれば問題ありません。以下のパフォーマンスのヒントをご参照ください。

## 「ページを90度回転する」とは何ですか？
ページを90度回転すると、ページの向きが縦向きから横向き（またはその逆）に変更され、コンテンツ自体は変更されません。プレゼンテーションや横向きのみのグラフィックの印刷、横向きにスキャンされたドキュメントの修正などに特に便利です。

## なぜ GroupDocs Viewer for Java でプログラム的にページを回転させるのか？
GroupDocs Viewer は多数のファイル形式を扱う複雑さを抽象化します。ページ単位の変換（回転など）を適用しながら、元のファイルをそのまま保持できます。API は流暢でスレッドセーフ、Java 8 以上のランタイムで動作し、エンタープライズ向けの自動化に信頼できる選択肢です。

## 前提条件
- **GroupDocs.Viewer for Java**（最新バージョン）
- **JDK 8** 以上
- **Maven**（または Gradle）で依存関係を管理
- IntelliJ IDEA や Eclipse などの IDE
- Java I/O の基本的な知識

## GroupDocs.Viewer for Java のセットアップ
`pom.xml` に GroupDocs リポジトリと依存関係を追加します。このスニペットは元のチュートリアルと同じです：

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
- **Free trial** – GroupDocs サイトからダウンロード。  
- **Temporary license** – 評価期間を延長したい場合にリクエスト。  
- **Full license** – 本番環境での導入に購入。

### 基本的な Viewer の初期化
以下のコードは `Viewer` インスタンスを作成する最小限の方法を示しています。示されている通りに正確に記述してください：

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer を使用した Java での PDF ページ回転方法
API は多数の形式で動作しますが、ページ回転の最も一般的なユースケースは PDF です。同じ `rotatePage` メソッドを使用するので、Viewer に PDF ファイルを指定し、ページ番号を設定するだけです。

## ステップバイステップ実装：最初のページを90度回転

### 1. 必要なパッケージをインポート
これらのインポートにより、PDF レンダリングオプションと回転列挙型にアクセスできます。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 出力先を定義し、Viewer を作成
プレースホルダーのパスを実際のディレクトリに置き換えてください。

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF ビューオプションを設定し、回転を適用
`rotatePage` メソッドはページ番号（1 から始まる）と `Rotation` 列挙型の値を受け取ります。

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. ドキュメントをレンダリング
最後に `view` を呼び出して、回転した PDF を生成します。

```java
viewer.view(viewOptions);
```

#### 動作概要
- **PdfViewOptions** は Viewer に PDF ファイルを出力させることを指示します。  
- **rotatePage(int, Rotation)** は指定したページだけを回転させ、他のページはそのままにします。  
- このメソッドは `ON_90_DEGREE`、`ON_180_DEGREE`、`ON_270_DEGREE` をサポートしています。

## 一般的な問題と解決策

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| **FileNotFoundException** | パスが間違っているかフォルダーが存在しません | `YOUR_OUTPUT_DIRECTORY` と `YOUR_DOCUMENT_DIRECTORY` が存在し、読み取り可能であることを確認してください。 |
| **Unsupported file format** | Viewer がサポートしていない形式を回転しようとしています | [GroupDocs Viewer supported formats] ページを確認してください。 |
| **No rotation visible** | ページ番号を 0 ベースで指定している | `rotatePage` は **1 ベース** のインデックスを使用することを忘れないでください。 |
| **Out‑of‑memory errors on large docs** | 単一スレッドで多数の大きなファイルをレンダリングしている | ドキュメントを順次処理するか、同時実行数を制限したスレッドプールを使用してください。 |

## 実用的な応用例
- **プレゼンテーションの調整** – 縦向きスライドをリアルタイムで横向きに変換します。  
- **大量ドキュメントの修正** – 横向きにスキャンされた PDF の修正を自動化します。  
- **印刷用出力** – 縦向きの用紙でも横向きグラフィックが正しく印刷されるようにします。

## パフォーマンスのヒント
- **リソースはすぐに閉じる** – `try‑with‑resources` ブロックは `Viewer` を自動的に破棄します。  
- **バッチ処理** – 多数のファイルを扱う場合、スレッドごとに `Viewer` インスタンスを再利用してオーバーヘッドを削減します。  
- **メモリ監視** – 100 MB を超えるドキュメントでは、メモリに保持する代わりに出力をディスクにストリームすることを検討してください。

## よくある質問

**Q: 複数のページを一度に回転できますか？**  
A: はい。回転が必要な各ページ番号に対して `rotatePage()` を呼び出します。

**Q: レンダリング後に回転を元に戻す方法はありますか？**  
A: 直接的な方法はありません。回転オプションを付けずに再度ドキュメントをレンダリングする必要があります。

**Q: GroupDocs Viewer でページ回転をサポートしているファイル形式はどれですか？**  
A: DOCX、PDF、PPTX、XLSX など、公式ドキュメントに記載されている多数の形式がサポートされています。

**Q: 複数のドキュメントをバッチで自動的にページ回転させるにはどうすればよいですか？**  
A: ファイルパスのコレクションを反復するループでコードを囲み、各ファイルに同じ `rotatePage` ロジックを適用します。

**Q: 回転中のエラー処理のベストプラクティスは何ですか？**  
A: `Viewer` の使用を `try‑catch` ブロックで囲み、例外をログに記録し、必要に応じて次のファイルの処理を続行します。

## リソース
- **ドキュメント**: [GroupDocs Viewer Java ドキュメント](https://docs.groupdocs.com/viewer/java/)  
- **API リファレンス**: [GroupDocs API リファレンス](https://reference.groupdocs.com/viewer/java/)  
- **ダウンロード**: [GroupDocs Viewer for Java を取得](https://releases.groupdocs.com/viewer/java/)  
- **購入**: [ライセンスを購入](https://purchase.groupdocs.com/buy)  
- **無料トライアル**: [無料で試す](https://releases.groupdocs.com/viewer/java/)  
- **一時ライセンス**: [一時ライセンスをリクエスト](https://purchase.groupdocs.com/temporary-license/)  
- **サポート**: [GroupDocs フォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-03-29  
**テスト環境:** GroupDocs Viewer 25.2 for Java  
**作者:** GroupDocs