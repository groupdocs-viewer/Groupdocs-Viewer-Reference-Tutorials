---
date: '2026-02-23'
description: GroupDocs.Viewer Java を使用して、ページあたりの項目数の設定、リソースの HTML 埋め込み、アーカイブを単一ページまたは複数ページの
  HTML に一括変換する方法を学びましょう。
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'ページあたりの項目数を設定: GroupDocs.Viewer JavaでアーカイブをHTMLに変換'
type: docs
url: /ja/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

 are correct.

Now produce final answer.# ページあたりの項目数を設定: GroupDocs.Viewer JavaでアーカイブをHTMLに変換

ZIPやRARなどのアーカイブファイルをウェブフレンドリーなHTMLに変換することは、ブラウザ上で直接文書を共有またはレビューしたいときに頻繁に必要となります。このガイドでは、アーカイブをレンダリングする際の**ページあたりの項目数の設定方法**、自己完結型出力のためのリソースHTMLの埋め込み方法、そしてGroupDocs.Viewer Javaを使用したアーカイブのバッチ変換の効率的な方法を学びます。

![GroupDocs.Viewer for Java を使用したアーカイブのHTML変換](/viewer/export-conversion/convert-archives-to-html-java.png)

## クイック回答
- **“ページあたりの項目数”は何を制御しますか？** アーカイブ内のファイルまたはフォルダーが各生成されたHTMLページに何件表示されるかを決定します。  
- **画像やCSSをHTMLに直接埋め込むことはできますか？** はい – `forEmbeddedResources` オプションを使用してリソースHTMLを埋め込みます。  
- **バッチ変換は可能ですか？** もちろんです。アーカイブのコレクションをループし、同じ設定でそれぞれをレンダリングできます。  
- **GroupDocs.Viewerの使用にMavenは必要ですか？** はい、以下のように `maven groupdocs viewer` 依存関係を追加してください。  
- **サポートされている出力形式は何ですか？** シングルページHTML Java とマルチページHTML Java の両方が利用可能です。

## GroupDocs.Viewerの“ページあたりの項目数”とは？
**ページあたりの項目数** 設定はアーカイブレンダリングオプションに属します。マルチページHTMLドキュメントを生成する際に、各HTMLページに表示するアーカイブエントリ（ファイルまたはフォルダー）の数をビューアに指示します。この値を調整することで、特に大規模なアーカイブにおいてページサイズとナビゲーション速度のバランスを取ることができます。

## なぜリソースHTMLを埋め込むのか？
リソース（画像、CSS、フォント）をHTMLファイル内に直接埋め込むことで、外部ファイルなしで開くことができる単一のポータブルドキュメントが作成されます。これは、メール添付、オフライン閲覧、または出力を他のウェブページに埋め込む際に最適です。

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
GroupDocs.Viewer は **無料トライアルリンク**、一時ライセンス、またはフル購入オプションを提供しています。プロジェクトのスケジュールに合ったものを選択してください。

### 基本的な初期化
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## アーカイブをシングルページHTMLにレンダリングする方法

### 手順 1: 出力ディレクトリの定義
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 手順 2: シングルページ出力のファイル名を設定
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 手順 3: ビューアの初期化
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 手順 4: レンダリングオプションの設定（リソースHTMLを埋め込む）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: シングルページとしてレンダリング
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## アーカイブをマルチページHTMLにレンダリングし、ページあたりの項目数を設定する方法

### 手順 1: 出力ディレクトリを再利用
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 手順 2: 複数ページ用のファイル名フォーマットを定義
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 手順 3: ビューアを再度初期化
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 手順 4: マルチページオプションの設定（リソースHTMLを埋め込む）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 手順 5: ページあたりの項目数を設定（アクションの主要キーワード）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 実用的な活用例
- **ドキュメント管理システム:** 追加のビューアをインストールせずにアーカイブプレビュー機能を追加します。  
- **ウェブポータル:** ユーザーにバンドルされた文書を迅速に、ダウンロード不要で閲覧できる方法を提供します。  
- **コラボレーションツール:** チームが共有アーカイブをブラウザ上で直接検査できるようにします。  

## パフォーマンス上の考慮点
- **リソース管理:** メモリ使用量に注意し、大量バッチの場合はJVMのガベージコレクタのチューニングを検討してください。  
- **アーカイブのバッチ変換:** アーカイブファイルのリストをループし、同じレンダリングロジックを呼び出してスループットを最大化します。  
- **キャッシュ戦略:** 同じアーカイブが頻繁にアクセスされる場合、レンダリングされたHTMLをキャッシュに保存します。  

## よくある質問
**Q: GroupDocs.Viewer Java とは何ですか？**  
A: HTML、PDF、画像などの形式に文書（アーカイブを含む）をレンダリングする多目的ライブラリです。

**Q: GroupDocs.Viewer の無料トライアルを入手するには？**  
A: [無料トライアルリンク](https://releases.groupdocs.com/viewer/java/) にアクセスしてダウンロードおよびテストしてください。

**Q: アーカイブ以外の文書タイプも変換できますか？**  
A: はい、ビューアは PDF、Word、Excel など多数の形式をサポートしています。

**Q: レンダリングが遅い場合はどうすればよいですか？**  
A: ページあたりの項目数を減らす、ストリーミングを有効にする、またはアーカイブを小さなバッチで処理してください。

**Q: サポートやヘルプはどこで得られますか？**  
A: [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9) へお問い合わせください。

**Q: CSS と画像を HTML に直接埋め込むことは可能ですか？**  
A: もちろんです。例に示すように `HtmlViewOptions.forEmbeddedResources` を使用してください。

**Q: アーカイブのフォルダーをバッチ変換するには？**  
A: `for` ループで各ファイルを反復処理し、各イテレーションで同じ `Viewer` と `HtmlViewOptions` 設定を適用します。

## リソース
- **ドキュメンテーション:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) で機能を詳しく確認してください。  
- **API リファレンス:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/) で完全な API を確認してください。  
- **ダウンロード:** [download page](https://releases.groupdocs.com/viewer/java/) から最新のバイナリを取得してください。  
- **購入とライセンス:** [purchase page](https://purchase.groupdocs.com/buy) でオプションを確認してください。  
- **サポートとコミュニティ:** [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) でディスカッションに参加してください。

---

**最終更新日:** 2026-02-23  
**テスト環境:** GroupDocs.Viewer 25.2  
**作成者:** GroupDocs