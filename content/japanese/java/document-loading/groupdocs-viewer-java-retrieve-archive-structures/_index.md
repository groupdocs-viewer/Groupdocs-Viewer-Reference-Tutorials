---
date: '2026-02-05'
description: GroupDocs.Viewer を使用して viewinfo を取得し、Java アーカイブ ファイル タイプの構造を取得する方法を学びます。このガイドでは、セットアップ、コード例、実際のユースケースをカバーしています。
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: JavaでViewInfoを取得し、アーカイブ構造を取得する方法
type: docs
url: /ja/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# JavaでViewInfoを取得し、アーカイブ構造を取得する方法

アーカイブファイルを効果的に管理するには、その構造を明確に理解する必要があります。このチュートリアルでは、任意のアーカイブに対して **viewinfo を取得する方法** を学び、**java アーカイブファイルタイプ** の操作にどのように役立つかを確認します。GroupDocs.Viewer の設定、ビュー情報の抽出、フォルダー階層の再帰的読み取りを順に解説し、実際のプロジェクトにソリューションを統合できるようにします。

![Java用 GroupDocs.Viewer のアーカイブ構造](/viewer/document-loading/archive-structures-java.png)

**学べること**
- Java 用 GroupDocs.Viewer の設定と構成。  
- アーカイブから **viewinfo を取得** する方法。  
- アーカイブファイルのフォルダー構造を読み取り表示するテクニック。  
- Java プロジェクトで GroupDocs.Viewer を使用する際の実用的な活用例とパフォーマンス上の考慮点。

## Quick Answers
- **viewinfo が提供するものは何ですか？** ファイルタイプ、ページ数、アーカイブのフォルダー一覧を返します。  
- **サポートされているアーカイブはどれですか？** ZIP、RAR、TAR などの一般的な形式です。  
- **ライセンスは必要ですか？** 無料トライアルは評価に利用できますが、本番環境では商用ライセンスが必要です。  
- **大きなアーカイブを処理できますか？** はい。後述のようにストリーミングと適切なメモリ管理を使用します。  
- **Maven が必要ですか？** Maven は GroupDocs.Viewer の依存関係管理に推奨される方法です。

## What is “how to get viewinfo”?
`getViewInfo` は、GroupDocs.Viewer API のメソッドで、ドキュメントまたはアーカイブのメタデータを完全にレンダリングせずに抽出します。アーカイブの場合、内部のフォルダツリーを明らかにし、どの部分をレンダリングまたはさらに処理するかを決定できます。

## Why Retrieve Java Archive File Type Structures?
**java アーカイブファイルタイプ**（例: ZIP、RAR）の内部レイアウトを理解すると、次のことが可能になります：
- すべてを展開せずに必要なファイルを迅速に特定できます。  
- 関連するサブフォルダーだけを処理する自動パイプラインを構築できます。  
- コンテンツ管理やデータ取り込みシステムにアーカイブナビゲーションを統合できます。

## Prerequisites

- **Java Development Kit (JDK):** バージョン 8 以上。  
- **Maven:** 依存関係管理とビルドに使用。  
- **基本的な Java 知識:** OOP の概念に慣れていると便利ですが必須ではありません。

また、以下のように Maven プロジェクトに GroupDocs.Viewer ライブラリを追加できるようにしてください。

## Setting Up GroupDocs.Viewer for Java

### Maven Configuration

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

### License Acquisition

- **無料トライアル:** GroupDocs のウェブサイトからトライアル版をダウンロード。  
- **一時ライセンス:** 短期評価用の一時キーをリクエスト。  
- **フルライセンス:** 本番環境で無制限に使用できる商用ライセンスを購入。

ライブラリがクラスパスに配置されたら、コーディングを開始できます。

## Implementation Guide

### How to Get ViewInfo for Archive Files

このセクションでは、`getViewInfo` を呼び出しフォルダー階層を読み取る正確な手順を示します。

#### Initialize the Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Retrieve View Information

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Display Folder Structure

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Recursive Folder Reading

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

### Feature 2: Retrieve Archive Folder Structure

この機能はアーカイブファイルのフォルダー構造を出力することに焦点を当てています。最初の機能と似ていますが、再帰的探索を強調しています。

#### Setup View Info Options

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Recursive Exploration

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Practical Applications

1. **データ管理:** アーカイブ構造を理解して大規模データセットを迅速に整理。  
2. **自動ファイル処理:** アーカイブファイルを完全に展開せずにバッチ処理。  
3. **CMS 統合:** コンテンツ管理システムにオンザフライのアーカイブナビゲーションを追加。

## Performance Considerations

- **メモリ使用量の最適化:** フォルダーを1レベルずつ処理し、`Viewer` インスタンスは速やかに閉じます。  
- **常に最新を使用:** パフォーマンス向上のため、最新の GroupDocs.Viewer バージョンと JDK を使用してください。

## Common Issues and Solutions

| 問題 | 発生理由 | 対策 |
|------|----------|------|
| `NullPointerException` がフォルダー読み取り時に発生 | `viewInfo.getFolders()` が空ディレクトリで null を返す | イテレーション前に null または空リストか確認してください。 |
| 巨大な ZIP ファイルの処理が遅い | アーカイブ全体がメモリに読み込まれる | 新しい GroupDocs バージョンで利用可能なストリーミングオプションを使用してください。 |
| ライセンスが見つからない | ライセンスファイルのパスが間違っている | ライセンスファイルをアプリケーションのルートに配置するか、`License.setLicense("path/to/license.json")` を設定してください。 |

## Frequently Asked Questions

**Q: GroupDocs.Viewer とは何ですか？**  
A: HTML、画像、PDF などの形式にドキュメント（アーカイブを含む）をレンダリングする強力な Java ライブラリです。

**Q: 他のプログラミング言語でも GroupDocs.Viewer を使用できますか？**  
A: はい、GroupDocs は複数のプラットフォーム向けに SDK を提供していますが、本チュートリアルは Java 実装に焦点を当てています。

**Q: 大きなアーカイブファイルはどう扱いますか？**  
A: 効率的なメモリ管理を実施し、必要に応じてアーカイブを分割することを検討してください。

**Q: GroupDocs.Viewer がサポートするアーカイブ形式は何ですか？**  
A: ZIP、RAR、TAR など、さまざまな形式をサポートしています。

**Q: 処理できるアーカイブのサイズに制限はありますか？**  
A: 制限はシステムリソースに依存します。対象環境でテストし、実用的な上限を確認してください。

**Q: 「viewinfo を取得する方法」はパスワード保護されたアーカイブでも機能しますか？**  
A: はい、`getViewInfo` を呼び出す前に `ArchiveOptions.setPassword("yourPassword")` でパスワードを指定できます。

## Conclusion

このガイドに従うことで、任意のサポート対象アーカイブに対して **viewinfo を取得する方法** と、GroupDocs.Viewer for Java を使用したフォルダー階層の走査方法が分かります。これらのテクニックにより、より賢いデータ処理パイプラインの構築、CMS 統合の改善、そして大量のアーカイブファイルを自信を持って扱えるようになります。次は、アーカイブ内の個別ファイルをレンダリングしたり、PDF/HTML へ変換する他の Viewer 機能を探ってみてください。

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**
- **Documentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)