---
date: '2026-04-01'
description: GroupDocs Viewer for Java を使用して CAD 図面をタイルに分割し、レンダリング性能を向上させ、大容量ファイルの取り扱いを簡素化する方法を学びましょう。
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: GroupDocs Viewer を使用して CAD 図面をタイルに分割する方法
type: docs
url: /ja/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# CAD図面をタイルに分割する方法（GroupDocs Viewer）

もし **CADの分割方法** について小さくて扱いやすい部分に分けることを考えているなら、ここが適切な場所です。このチュートリアルでは、**GroupDocs Viewer for Java** を使用して大きな CAD 図面をタイルに分割するために必要な正確な手順を順に説明します。最後まで読むと、レンダリング速度を向上させ、メモリ使用量を削減し、Web やモバイルアプリケーションで図面を表示しやすくする、すぐに使えるソリューションが手に入ります。

![GroupDocs.Viewer for Java を使用した CAD 図面の分割](/viewer/advanced-rendering/split-cad-drawings-java.png)

## クイック回答
- **「CADの分割」は何を実現しますか？** 巨大な図面を小さな画像（タイル）に分割し、読み込みが速くなり、メモリ消費が少なくなります。  
- **タイルの形式は何ですか？** デフォルトでは PNG ファイルが生成されますが、Viewer のオプションで他の形式もサポートされています。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用できますが、本番環境では有料ライセンスが必要です。  
- **タイルサイズを変更できますか？** はい。`tileWidth` と `tileHeight` の計算式を調整して目的に合わせてください。  
- **このアプローチはスレッドセーフですか？** `Viewer` インスタンスを try‑with‑resources で個別に使用して各タイルをレンダリングすれば、同時実行でも安全です。

## 「CADの分割」とは何ですか？
CAD の分割とは、単一の（しばしば非常に大きな）CAD 図面を複数の矩形セクション（タイル）に分割することを指します。各タイルは独立してレンダリングされ、ユーザーが実際に必要とする部分だけを読み込むことができるため、ウェブマップ、ドキュメントポータル、モバイルビューアに最適です。

## なぜ GroupDocs Viewer for Java を使用するのか？
GroupDocs Viewer は、DWG、DXF、DWF を含む 100 以上のファイル形式を即座にサポートします。そのタイル API を使用すると正確な座標を指定でき、ファイル全体を処理せずに必要な領域だけをレンダリングできます。これにより CPU サイクルが節約され、帯域幅が削減され、よりスムーズなユーザー体験が提供されます。

## 前提条件
- **ライブラリ**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: 任意の最新 Java Development Kit（Java 8 以上）。  
- **IDE**: IntelliJ IDEA、Eclipse、または他の Java 対応 IDE。  
- **ビルドツール**: Maven（依存関係を追加すれば他のビルドツールでも可）。  

## GroupDocs.Viewer for Java の設定
`pom.xml` に GroupDocs リポジトリと依存関係を追加します:

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
GroupDocs Viewer は評価用の無料トライアルライセンスを提供しています:

- **無料トライアル**: ライブラリをダウンロードするには [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) をご覧ください。  
- **一時ライセンス**: [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) で申請してください。  
- **フルライセンス**: [Purchase Page](https://purchase.groupdocs.com/buy) で本番用ライセンスを購入してください。

### 基本的な初期化
ライブラリが正しくロードされることを確認するために、シンプルな `Viewer` インスタンスを作成します:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## CAD 図面をタイルに分割するステップバイステップガイド

### 手順 1: 出力ディレクトリの定義
各タイルを個別の PNG ファイルとして保存します。ユーティリティメソッドを使用すると、パスロジックがシンプルで再利用可能になります。

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### 手順 2: ビューオプションの設定
レンダリング形式を PNG に設定し、ビューアにすべてのページを事前読み込みしないよう指示します（メモリ節約）。

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### 手順 3: タイル寸法の計算
まず図面の元の幅と高さを取得し、次にそれを 4 つの等しい象限に分割します。

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### 手順 4: タイルのレンダリングと保存
計算したタイルをレンダリングオプションに追加し、`Viewer` に PNG ファイルを生成させます。

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### トラブルシューティングのヒント
- **ビルドパス** – GroupDocs の JAR ファイルがクラスパスに含まれていることを確認してください。  
- **権限** – 出力フォルダが Java プロセスから書き込み可能であることを確認してください。  
- **例外** – `ViewerException` が出た場合、DWG ファイルが破損していないか、正しいライセンスが適用されているかを再確認してください。

## CAD タイル分割の一般的なユースケース
1. **Web Mapping** – ユーザーがパン/ズームする際に、フロアプランの表示領域だけを読み込みます。  
2. **Document Management** – 各タイルを個別に保存し、プレビュー生成を高速化します。  
3. **Mobile Viewing** – 現在の画面に必要なタイルだけをダウンロードすることで帯域幅を削減します。

## パフォーマンス上の考慮点
- **タイルサイズ** – 大きなタイルはファイル数が減りますがレンダリングが遅くなります。UI の要件に合わせてバランスを取ってください。  
- **メモリ監視** – 非常に大きな図面を処理する際は、Java のプロファイリングツール（例: VisualVM）でヒープ使用量を監視してください。  
- **リソースクリーンアップ** – 上記の try‑with‑resources パターンはネイティブリソースを自動的に解放します。

## よくある質問

**Q: 同じアプローチで他のファイルタイプ（PDF、画像）をタイルに分割できますか？**  
A: はい。GroupDocs Viewer は多くの形式をサポートしており、対応するオプションクラス（例: `PdfViewOptions`）を使用すれば可能です。

**Q: 出力画像の品質を変更するには？**  
A: `viewOptions.setResolution(int dpi)` を調整するか、`PngOptions` オブジェクトで圧縮設定を行ってください。

**Q: 非常に大きな DWG ファイルでメモリ不足になる場合、どうすればよいですか？**  
A: タイルの寸法を小さくする、JVM ヒープ（`-Xmx`）を増やす、または `Viewer` インスタンスを分けてタイルを順次レンダリングしてください。

**Q: タイルを非同期にレンダリングすることは可能ですか？**  
A: もちろん可能です。各タイルのレンダリング呼び出しを `CompletableFuture` でラップするか、エグゼキュータサービスを使用して並列化してください。

**Q: タイルごとに別々のライセンスが必要ですか？**  
A: いいえ。単一の有効な GroupDocs Viewer ライセンスで、アプリケーション内のすべてのレンダリング操作がカバーされます。

## リソース
- [ドキュメント](https://docs.groupdocs.com/viewer/java/)
- [API リファレンス](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer のダウンロード](https://releases.groupdocs.com/viewer/java/)
- [ライセンス購入](https://purchase.groupdocs.com/buy)
- [無料トライアル](https://releases.groupdocs.com/viewer/java/)
- [一時ライセンス](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)

---

**最終更新日:** 2026-04-01  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs  

---