---
date: '2026-01-08'
description: GroupDocs.Viewer for Java を使用して、カスタム寸法と背景色で CAD 図面を高品質な PNG 画像にレンダリングする方法を学びましょう。
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java を使用して、CAD 図面をカスタムサイズと背景色で PNG にレンダリングする方法
type: docs
url: /ja/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# GroupDocs.Viewer for Java を使用して、カスタムサイズと背景色で CAD 図面を PNG にレンダリングする方法

CAD 図面を特定のサイズと美観を保ったまま高品質な画像に変換するのに苦労していますか？このチュートリアルでは、**CAD をレンダリングする方法** を示し、カスタムサイズと背景色で PNG に変換する方法を解説します。レポート、プレゼンテーション、ウェブプレビューに必要な見た目を正確に得られます。

## クイック回答
- **“how to render CAD” とは何ですか？** コードを使用して CAD ファイル（例: DWG）を PNG などの画像形式に変換することを指します。  
- **カスタム幅を設定できますか？** はい – `CadOptions.forRenderingByWidth(int width)` を使用します。  
- **背景色はどう変更しますか？** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` を呼び出します。  
- **必要なライブラリはどれですか？** GroupDocs.Viewer for Java（バージョン 25.2 以降）。  
- **ライセンスは必要ですか？** 一時的または購入したライセンスで評価制限が解除されます。

![GroupDocs.Viewer for Java を使用した、カスタムサイズと背景色で CAD 図面を PNG にレンダリング](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## CAD 図面のレンダリング方法 – 概要
このセクションでは、主な目的である **CAD をレンダリングする方法** を拡張し、サイズと背景を制御しながら CAD 図面を PNG ファイルに変換します。完全なセットアップ、コードスニペット、実用的なヒントを順に説明します。

## 学習内容
- プロジェクトで GroupDocs.Viewer for Java を設定する  
- カスタム寸法で **DWG を PNG に変換**  
- レンダリング時に **PNG の背景色を設定** して洗練された外観にする  
- カスタムレンダリングが価値を提供する実際のシナリオ  

## 前提条件

### 必要なライブラリと依存関係
- Java Development Kit (JDK) 8 以上  
- 依存関係管理のための Maven  

### 環境セットアップ要件
- IntelliJ IDEA や Eclipse などの IDE  
- 基本的な Java の知識  

### 知識の前提条件
- Java でのファイル操作に慣れていること  

## GroupDocs.Viewer for Java の設定
Maven の `pom.xml` に GroupDocs リポジトリと依存関係を追加します:

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
評価制限を解除するために、一時的またはフルライセンスを取得します。

### 基本的な初期化と設定
CAD ファイルを指す `Viewer` インスタンスを作成します:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## 実装ガイド

### 機能 1: カスタム画像サイズと背景色で CAD 図面をレンダリング

#### 概要
この機能により、画像の幅と背景色を指定しながら **DWG を PNG に変換** できます。

#### 手順実装

##### 必要なパッケージのインポート
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 出力ディレクトリとファイルパス形式の設定
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
- `PngViewOptions` – 出力形式と命名を定義します。  
- `forRenderingByWidth(int width)` – カスタム画像幅を設定します。  
- `setBackgroundColor(Color color)` – PNG に **背景色を適用** します。

#### トラブルシューティングのヒント
- 出力フォルダーが存在するか確認し、必要なら作成します。  
- 入力ファイルのパスと権限を再確認します。  

### 機能 2: レンダリングオプションで背景色を設定

#### 概要
ここでは、視覚的一貫性を向上させるために **PNG の背景色設定** に焦点を当てます。

#### 手順実装

##### 必要なパッケージのインポート
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
- 異なる寸法のために `forRenderingByWidth(int width)` を調整します。  
- 任意の `Color` 定数またはカスタム `new Color(r,g,b)` を使用して独自の背景を設定します。  

## 実用的な応用例

### 1. エンジニアリング文書
カスタムレンダリングにより、エンジニアリング図面が企業のスタイルガイドに適合します。

### 2. 建築ビジュアライゼーション
プレゼンテーション資料に合わせたクリーンな背景でブループリントを提示します。

### 3. 製造プロトタイピング
迅速なプロトタイピングワークフローのために正確な PNG を生成します。

### 統合の可能性
このレンダリングパイプラインを文書管理システムと組み合わせて、ビジュアル資産の生成を自動化します。

## パフォーマンスに関する考慮点

### パフォーマンス最適化
- **バッチ処理:** ループで複数の CAD ファイルをレンダリングします。  
- **リソース管理:** 大きな図面のために JVM ヒープサイズを調整します。

### リソース使用ガイドライン
CPU とメモリを監視し、`Viewer` インスタンスは速やかに解放します。

### Java メモリ管理のベストプラクティス
- try‑with‑resources（上記参照）を使用して `Viewer` を自動的にクローズします。  
- 必要以上に大きな `Path` オブジェクトを保持しないようにします。

## よくある問題と解決策

| 問題 | 解決策 |
|-------|----------|
| **出力フォルダーが見つかりません** | 事前にディレクトリを作成するか、`Files.createDirectories(outputDirectory);` を追加します。 |
| **画像が空白** | `cadOptions.setBackgroundColor` が `forRenderingByWidth` の後に設定されていることを確認してください。 |
| **メモリ不足エラー** | `-Xmx` JVM オプションを増やすか、ファイルを小さなバッチで処理します。 |

## よくある質問

**Q: DWG 以外の CAD フォーマットもレンダリングできますか？**  
A: はい、GroupDocs.Viewer は DXF、DWF、その他多数の CAD ファイルタイプをサポートしています。

**Q: 定義済み定数ではなくカスタム RGB 色を使用するには？**  
A: `new Color(123, 45, 67)` のように新しい `Color` インスタンスを作成し、`setBackgroundColor` に渡します。

**Q: 特定のレイアウトやレイヤーだけをレンダリングできますか？**  
A: `viewer.view` を呼び出す前に `CadOptions` でレイアウトやレイヤーのオプションを指定できます。

**Q: ライブラリは透明な背景をサポートしていますか？**  
A: 対象フォーマットがサポートしていれば、`new Color(0,0,0,0)` に設定して完全な透明性を実現できます。

**Q: 必要な GroupDocs.Viewer のバージョンは？**  
A: 本チュートリアルはバージョン 25.2 を使用していますが、より新しいバージョンでも同じ API が保持されています。

## 結論
これで、GroupDocs.Viewer for Java を使用して、カスタム寸法と背景色で CAD 図面を PNG ファイルに **レンダリングする方法** が分かりました。これらの手法を活用して、エンジニアリング、建築、製造のワークフロー向けにプロフェッショナルなビジュアル資産を作成してください。

### 次のステップ
- 異なる画像幅や色で実験する。  
- レンダリングコードをバッチ処理サービスに統合する。  
- PDF 変換やマルチページレンダリングなど、追加の Viewer オプションを検討する。

---

**最終更新日:** 2026-01-08  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs