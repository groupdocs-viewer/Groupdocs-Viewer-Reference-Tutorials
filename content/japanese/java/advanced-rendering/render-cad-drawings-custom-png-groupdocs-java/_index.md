---
date: '2026-08-30'
description: GroupDocs.Viewer for Java を使用して、DWG を PNG に変換し、background color を設定し、画像サイズをカスタマイズする方法を学びます。
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: GroupDocs.Viewer for Java を使用して DWG を PNG に変換し、custom image width
  と background color を設定します。このガイドでは、ステップバイステップのセットアップ、code snippets、troubleshooting
  tips を提供します。
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Java で custom size と background color を使用して DWG を PNG に変換
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: GroupDocs.Viewer for Java を使用して、DWG を PNG に変換し、custom size と background color
  を設定する方法
type: docs
url: /ja/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# DWG をカスタムサイズと背景色で PNG に変換する方法（GroupDocs.Viewer for Java を使用）

このチュートリアルでは、GroupDocs.Viewer for Java を使用して、出力サイズと背景色を制御しながら **DWG を PNG に変換する方法** を学びます。レポートに CAD 図面を埋め込む必要がある場合や、Web ポータル用のサムネイルを生成する場合、バッチレンダリングを自動化する場合など、以下の手順で各 PNG ファイルの見た目を完全にコントロールできます。

## クイック回答
- **「DWG を PNG に変換する」とは何ですか？** これは、コードを通じて DWG CAD ファイルを PNG 画像に変換し、ベクターディテールをラスターピクセルとして保持するプロセスです。  
- **カスタム幅を設定できますか？** はい – `CadOptions.forRenderingByWidth(int width)` を呼び出して、必要な正確なピクセル幅を定義できます。  
- **背景色はどうやって変更しますか？** レンダリング前に `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` を使用します。  
- **必要なライブラリはどれですか？** GroupDocs.Viewer for Java（バージョン 25.2 以降）。  
- **ライセンスは必要ですか？** 一時的またはフルライセンスを取得すると評価制限が解除され、無制限のレンダリングが可能になります。

![カスタムサイズと背景色で PNG にレンダリングする CAD 図面（GroupDocs.Viewer for Java）](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer for Java とは？

GroupDocs.Viewer for Java は、サーバーサイド API で、150 以上のファイル形式（CAD ファイルを含む）を画像、PDF、または HTML にレンダリングします。AutoCAD などのサードパーティソフトウェアを必要とせずに動作するため、自動化パイプラインに最適です。

## カスタムサイズと背景色で DWG を PNG に変換する方法

DWG ファイルを `Viewer` インスタンスで読み込み、目的の幅と背景色を設定した `CadOptions` を構成し、最後に `viewer.view` を `PngViewOptions` と共に呼び出します。この 3 ステップのフローは、ファイル I/O、レンダリング、出力命名を単一のメモリ効率の高い操作で処理します。

Viewer はドキュメントを読み込みレンダリングを実行する主要クラスです。  
CadOptions は画像幅や背景色などの CAD 固有設定を構成します。  
PngViewOptions は PNG 出力形式とレンダリングページの命名パターンを定義します。

これで、任意の DWG 図面を指定した幅の PNG にレンダリングでき、ブランドや UI テーマに合わせて任意の単色（または透明）背景を選択できます。

## カスタム背景色を設定する理由

背景色を設定すると、レンダリングされた PNG が周囲の UI 要素とシームレスに調和し、不要な白い余白を防ぎ、デフォルトの白キャンバスでは失われがちな図面のディテールを強調できます。GroupDocs.Viewer は任意の `java.awt.Color`（カスタム RGB 値を含む）をサポートし、ピクセル単位での完璧なコントロールが可能です。

java.awt.Color は背景レンダリングに使用される色値を表します。

## 前提条件

- **Java Development Kit (JDK) 8+** – API は Java 8 以降を対象としています。  
- **Maven** – 依存関係管理に使用。  
- **IDE** – IntelliJ IDEA、Eclipse、またはお好みのエディタ。  
- **基本的な Java ファイル操作の知識** – DWG ソースファイルの読み取りと PNG 出力の書き込みに必要です。

## GroupDocs.Viewer for Java の設定
Maven `pom.xml` に GroupDocs リポジトリと Viewer 依存関係を追加します：

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
GroupDocs ポータルから一時的またはフルのライセンスキーを取得し、`license.lic` ファイルをプロジェクトのリソースフォルダーに配置します。これにより 20 ページの評価制限が解除され、フル解像度のレンダリングが可能になります。

### 基本的な初期化と設定
DWG ファイルが格納されているフォルダーを指す `Viewer` インスタンスを作成します：

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## 機能 1: カスタム画像サイズと背景色で CAD 図面をレンダリング

### CAD の背景色を変更する方法
CAD の背景色を変更するには、レンダリング前に CadOptions オブジェクトを構成します。`forRenderingByWidth` で幅を設定し、`setBackgroundColor` で新しい背景色を適用します。ビューアは指定された色を反映した PNG 画像を生成し、すべての出力ファイルで一貫したビジュアルスタイルを確保します。

#### 手順実装

##### 必要なパッケージをインポート
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 出力ディレクトリとファイルパス形式を設定
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### カスタムレンダリングオプションで Viewer を初期化
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**パラメータの説明**  
- `PngViewOptions` – PNG 出力形式と命名パターンを定義します。  
- `forRenderingByWidth(int width)` – 指定したピクセル幅に合わせて画像を生成し、高さは比例してスケーリングされます。  
- `setBackgroundColor(Color color)` – デフォルトの白キャンバスを選択した色で上書きし、生成資産全体の視覚的一貫性を向上させます。

#### トラブルシューティングのヒント
- 出力フォルダーが存在することを確認してください。存在しない場合は `Files.createDirectories(outputDir)` を使用します。  
- 入力ファイルパスが正しく、アプリケーションに読み取り権限があることを確認してください。

## 機能 2: レンダリングオプションで背景色を設定

### PNG の背景色を設定する方法
PNG の背景色を設定するには、Color インスタンスを作成し、レンダリング前に CadOptions に割り当てます。これにより、生成される各 PNG が指定した背景色を使用し、ブランドガイドラインや UI テーマに合わせられます。定数を使用することも、正確な RGB 値でカスタムインスタンスを作成することも可能です。

java.awt.Color は背景レンダリングに使用される色値を表します。

#### 手順実装

##### 必要なパッケージをインポート
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 背景色でレンダリングオプションを構成
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**主要な構成オプション**  
- `forRenderingByWidth(int width)` を調整して、Web サムネイル用の 800 px や高解像度印刷用の 1920 px など、さまざまな寸法に対応します。  
- 任意の定義済み `Color` 定数（例: `Color.LIGHT_GRAY`）または `new Color(r, g, b)` でカスタムインスタンスを作成し、正確なブランディングを実現できます。

## 実用的な応用例

### 1. エンジニアリング文書
カスタムレンダリングにより、すべての図面が社内スタイルガイドに準拠し、エクスポート後の手動画像編集が不要になります。

### 2. 建築ビジュアライゼーション
スライドデックやクライアント向けポータルに合わせた背景でブループリントを提示し、視覚的な統一感を向上させます。

### 3. 製造プロトタイピング
下流ツールが特定の画像サイズと背景を期待する高速プロトタイプワークフロー向けに PNG を生成します。

### 統合の可能性
このレンダリングパイプラインをドキュメント管理システム（例: SharePoint）と組み合わせ、DWG ファイルがアップロードされるたびに自動でプレビュー画像を生成できます。

## パフォーマンスに関する考慮事項

### パフォーマンス最適化
- **バッチ処理:** DWG ファイルが格納されたディレクトリをループし、各ファイルを順次レンダリングして JVM のウォームアップコストを分散させます。  
- **リソース管理:** 大規模な図面（500 ページ以上）では JVM ヒープを増やす（例: `-Xmx2g`）か、メモリ不足を防ぐために小さなバッチに分割して処理します。

### リソース使用ガイドライン
VisualVM などのツールで CPU とメモリ使用量を監視し、`Viewer` インスタンスは try‑with‑resources を使用して速やかに解放してください。

### Java メモリ管理のベストプラクティス
- 示されたように try‑with‑resources を使用して `Viewer` を自動クローズします。  
- 使用直後以外で大きな `Path` オブジェクトを保持しないようにします。

## よくある問題と解決策

| 問題 | 解決策 |
|------|--------|
| Output folder not found | ディレクトリを事前に作成するか、`Files.createDirectories(outputDirectory);` を追加してください |
| Blank image | `forRenderingByWidth` の後に `cadOptions.setBackgroundColor` が呼び出されていることを確認してください |
| Out‑of‑memory errors | JVM オプション `-Xmx` を増やすか、ファイルを小さなバッチに分割して処理してください |

## よくある質問

**Q: DWG 以外の CAD フォーマットもレンダリングできますか？**  
A: はい、GroupDocs.Viewer は DXF、DWF など複数の CAD フォーマットをサポートしています。

**Q: 定義済み定数ではなくカスタム RGB 色を使用するには？**  
A: `new Color(123, 45, 67)` で新しい `Color` をインスタンス化し、`setBackgroundColor` に渡します。

**Q: 特定のレイアウトやレイヤーだけをレンダリングすることは可能ですか？**  
A: `viewer.view` を呼び出す前に `CadOptions` でレイアウトまたはレイヤーオプションを指定できます。

**Q: 透明な背景はサポートされていますか？**  
A: 出力形式がサポートしている場合、`new Color(0,0,0,0)` を設定して完全な透明性を実現できます。

**Q: 必要な GroupDocs.Viewer のバージョンは？**  
A: 本チュートリアルはバージョン 25.2 を使用していますが、最新リリースでも同様の API が提供されています。

**最終更新日:** 2026-08-30  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs

## 関連チュートリアル

- [groupdocs viewer dwg – Java で特定の CAD 図面をレンダリングする方法（GroupDocs.Viewer 使用）](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java with GroupDocs.Viewer – 完全ガイド](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [PDF を HTML に変換し、Java で画像品質を最適化する方法（GroupDocs.Viewer 使用）](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)