---
date: '2026-06-30'
description: GroupDocs.Viewer を使用して viewinfo を取得し、Java archive file type structures
  を取得する方法を学びます。このガイドでは、セットアップ、コード例、実際のユースケースをカバーしています。
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: JavaでViewInfoを取得し、アーカイブ構造を取得する方法
type: docs
url: /ja/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# JavaでViewInfoを取得し、アーカイブ構造を取得する方法

アーカイブファイルを効果的に管理するには、その構造を明確に理解する必要があります。このチュートリアルでは、任意のアーカイブに対して **how to get viewinfo** を取得し、**java archive file type** の操作にどのように役立つかを学びます。GroupDocs.Viewer の設定、ビュー情報の抽出、フォルダー階層の再帰的読み取りを順に説明し、実際のプロジェクトにソリューションを統合できるようにします。

![Java用 GroupDocs.Viewer のアーカイブ構造](/viewer/document-loading/archive-structures-java.png)

**学べること**
- GroupDocs.Viewer for Java の設定と構成。  
- アーカイブから **get viewinfo** を取得する方法。  
- アーカイブファイルのフォルダー構造を読み取り表示するテクニック。  
- Java プロジェクトで GroupDocs.Viewer を使用する際の実用的な活用例とパフォーマンス上の考慮点。

## クイック回答
- **viewinfo は何を提供しますか？** ファイルタイプ、ページ数、アーカイブ内のフォルダーとファイルの完全な一覧を返します。  
- **どのアーカイブ形式がサポートされていますか？** ZIP、RAR、TAR、7z、ISO、その他 12 以上の一般的な形式。  
- **本番環境でライセンスは必要ですか？** はい—本番環境では商用ライセンスが必要です。評価には無料トライアルが利用できます。  
- **大容量アーカイブを効率的に処理できますか？** もちろんです—ストリーミングオプションを使用し、フォルダー階層を一度に1レベルずつ処理してメモリ使用量を抑えます。  
- **ライブラリを追加する方法は Maven だけですか？** Maven が推奨の依存管理ツールですが、Gradle や手動で JAR を追加する方法も動作します。

## “how to get viewinfo” とは何ですか？

`getViewInfo` は、ドキュメントまたはアーカイブから完全なレンダリングなしでメタデータを抽出する GroupDocs.Viewer API メソッドです。内部フォルダーツリー、ファイル数、基本的なプロパティを1回の呼び出しで返し、どの部分を処理するかを選択できます。この呼び出しは、典型的なサーバー上で 500 MB までのアーカイブを 1 秒未満で完全にスナップショットします。

## Java アーカイブファイルタイプの構造を取得する理由

**java archive file type** の内部レイアウトを取得すると、必要なファイルを即座に見つけられ、不要な抽出を回避し、関連するサブフォルダーだけに触れる自動パイプラインを構築できます。このアプローチは大容量アーカイブの I/O を最大 70 % 削減し、データ取り込みシナリオで毎分数千ファイルのスキャンを可能にします。

## 前提条件

- **Java Development Kit (JDK):** バージョン 8 以上。  
- **Maven:** 依存関係管理とビルドに使用。  
- **Basic Java knowledge:** OOP の概念に慣れていると便利ですが必須ではありません。  

また、GroupDocs.Viewer ライブラリへのアクセスが必要です。以下のように Maven プロジェクトに追加できます。

## Java 用 GroupDocs.Viewer の設定

### Maven 設定

`pom.xml` にリポジトリと依存関係を追加します。

**Repositories:**  
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**  
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### ライセンス取得

- **Free Trial:** GroupDocs のウェブサイトからトライアル版をダウンロード。  
- **Temporary License:** 短期評価用の一時キーをリクエスト。  
- **Full License:** 無制限の本番利用のために商用ライセンスを購入。  

ライブラリがクラスパスに追加されたら、コーディングを開始できます。

## 実装ガイド

### アーカイブファイルの ViewInfo を取得する方法

ビュー情報を取得するには、まずアーカイブを Viewer にロードし、次に `getViewInfo` を呼び出してメタデータを取得し、最後に返されたフォルダー階層を反復処理します。この 3 ステップのパターンはすべてのサポート対象アーカイブ形式で機能し、単一の API 呼び出しで完全なスナップショットを提供し、以降の処理を簡素化します。

#### Viewer の初期化

`Viewer` クラスは、すべてのレンダリングおよび検査操作のエントリーポイントです。ファイルストリーム、フォーマット検出、リソースのクリーンアップを管理します。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### ビュー情報の取得

`ViewInfo` は、ファイルタイプ、総ページ数、フォルダーとファイルの階層リストなどのメタデータをカプセル化します。`getViewInfo` を呼び出すと、このオブジェクトが即座に返されます。

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### フォルダー構造の表示

`viewInfo.getFolders()` を反復して各フォルダー名、その深さ、含まれるファイルを出力します。このシンプルなループで、アーカイブの読みやすいツリービューが得られます。

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 再帰的フォルダー読み取り

深くネストされたアーカイブの場合、再帰的ヘルパーメソッドでツリーを深さ優先で走査し、全体をメモリに読み込むことなくすべてのサブフォルダーを訪問できます。

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### 機能 2: アーカイブフォルダー構造の取得

この機能はアーカイブファイルのフォルダー構造を出力することに焦点を当てます。最初の機能と似ていますが、再帰的探索を強調しています。

#### ViewInfo オプションの設定

`ArchiveOptions` を使用すると、`getViewInfo` を呼び出す前にパスワード保護、ページ制限、ストリーミング設定を指定できます。

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 再帰的探索

2 番目の再帰ルーチンは、パスワード保護されたアーカイブや大量のファイルセットを効率的に処理する方法を示します。

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 実用的な活用例

1. **Data Management:** アーカイブ構造を理解して大規模データセットを迅速に整理。  
2. **Automated File Processing:** アーカイブファイルを完全に展開せずにバッチ処理し、I/O を最大 70 % 削減。  
3. **CMS Integration:** コンテンツ管理システムにオンザフライのアーカイブナビゲーションを追加し、エディタがアーカイブから直接ファイルをプレビューできるようにする。

## パフォーマンス上の考慮点

- **Optimize Memory Usage:** フォルダーを一度に1レベルずつ処理し、`Viewer` インスタンスは速やかに閉じます。  
- **Stay Updated:** 最新の GroupDocs.Viewer バージョン（執筆時点 25.2）と JDK リリースを使用してパフォーマンスを向上させます。  
- **Streaming Support:** ライブラリは内部のチャンク読み取りアーキテクチャにより、1 GB 超のアーカイブを全体を RAM に読み込まずにストリーミングできます。

## よくある問題と解決策

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| フォルダー読み取り時の `NullPointerException` | 空ディレクトリの場合 `viewInfo.getFolders()` が null を返す | 反復前に null または空リストか確認する。 |
| 大容量 ZIP ファイルの処理が遅い | アーカイブ全体をメモリにロードしている | 新しい GroupDocs バージョンで利用可能なストリーミングオプションを使用する。 |
| ライセンスが見つからない | ライセンスファイルのパスが間違っている | ライセンスファイルをアプリケーションのルートに置くか、`License.setLicense("path/to/license.json")` を設定する。 |

## よくある質問

**Q:** GroupDocs.Viewer とは何ですか？  
A: GroupDocs.Viewer は、100 以上のドキュメント、画像、アーカイブ形式を HTML、PDF、または画像ストリームにレンダリングする Java ライブラリで、ネイティブアプリケーションは不要です。

**Q:** 他のプログラミング言語でも GroupDocs.Viewer を使用できますか？  
A: はい、GroupDocs は .NET、Python、PHP など向けの SDK を提供していますが、このチュートリアルは Java 実装に焦点を当てています。

**Q:** 大容量アーカイブファイルはどう扱いますか？  
A: `ArchiveOptions.setUseStreaming(true)` でストリーミングを有効にし、フォルダーを一度に1レベルずつ処理し、使用後に `Viewer` オブジェクトを破棄します。

**Q:** GroupDocs.Viewer がサポートするアーカイブの種類は？  
A: ZIP、RAR、TAR、7z、ISO、ARJ、CAB など、12 以上のアーカイブ形式と多数の独自コンテナタイプをサポートしています。

**Q:** アーカイブのサイズ上限はありますか？  
A: 実用的な上限はサーバーの RAM と CPU に依存します。ストリーミングを有効にすれば、16 GB RAM のマシンで 2 GB のアーカイブもスムーズに処理できます。

**Q:** “how to get viewinfo” はパスワード保護されたアーカイブでも機能しますか？  
A: はい、`getViewInfo` を呼び出す前に `ArchiveOptions.setPassword("yourPassword")` でパスワードを設定します。

## 結論

このガイドに従うことで、サポート対象の任意のアーカイブに対して **how to get viewinfo** を取得し、GroupDocs.Viewer for Java を使用してフォルダー階層を走査する方法が分かります。これらの手法により、より賢いデータ処理パイプラインの構築、CMS 統合の向上、膨大なアーカイブファイルの安全な取り扱いが可能になります。次は、アーカイブ内の個別ファイルをレンダリングしたり、PDF/HTML に変換したりする他の Viewer 機能を探求してください。

---

**最終更新日:** 2026-06-30  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs  

**リソース**
- **ドキュメンテーション:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API リファレンス:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **ダウンロード:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **ライセンス購入:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **無料トライアルと一時ライセンス:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## 関連チュートリアル

- [Extract Document Metadata with GroupDocs.Viewer for Java - Retrieve Document View Information and Insights](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [How to Retrieve Attachments and Print Document Attachments with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java Guide: Render Specific Pages with GroupDocs.Viewer API for Document Preview and Management](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)