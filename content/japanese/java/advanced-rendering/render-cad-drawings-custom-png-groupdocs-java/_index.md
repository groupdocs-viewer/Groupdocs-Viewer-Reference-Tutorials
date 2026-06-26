---
date: '2026-03-16'
description: GroupDocs.Viewer for Java を使用して、カスタムサイズと背景色で DWG を PNG に変換する方法を学びましょう。
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java を使用して、DWG をカスタムサイズと背景色で PNG に変換する方法
type: docs
url: /ja/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# DWG を PNG に変換する方法（カスタムサイズと背景色） - GroupDocs.Viewer for Java を使用

DWG を **PNG に変換** しながら画像サイズと背景のスタイリングを完全にコントロールしたい場合は、ここが最適です。このチュートリアルでは CAD ファイルを PNG としてレンダリングし、幅をカスタマイズし、背景色を変更して、レポート、プレゼンテーション、または Web プレビューの要件に合った出力を得る方法をステップバイステップで解説します。

## クイック回答
- **「DWG を PNG に変換」とは何ですか？**  
  DWG CAD ファイルをコードを使って PNG 画像に変換するプロセスです。  
- **カスタム幅を設定できますか？**  
  はい – `CadOptions.forRenderingByWidth(int width)` を使用します。  
- **背景色はどう変更しますか？**  
  `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` を呼び出します。  
- **必要なライブラリはどれですか？**  
  GroupDocs.Viewer for Java（バージョン 25.2 以降）。  
- **ライセンスは必要ですか？**  
  評価制限を解除するには、一時的または購入したライセンスが必要です。

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## DWG を PNG に変換する方法 – 概要
このセクションでは、**DWG を PNG に変換** しつつサイズと背景を制御するという主目的を詳しく説明します。完全なセットアップ、必要なコード、そして一般的な落とし穴を回避する実用的なヒントをご紹介します。

## 学べること
- Maven プロジェクトで GroupDocs.Viewer for Java を設定する方法  
- カスタム寸法で **DWG を PNG に変換** する方法  
- レンダリング時に **CAD の背景色を変更** して洗練された外観にする方法  
- カスタムレンダリングが価値を生む実際のシナリオ  

## 前提条件

### 必要なライブラリと依存関係
- Java Development Kit (JDK) 8 以上  
- 依存関係管理のための Maven  

### 環境設定要件
- IntelliJ IDEA または Eclipse などの IDE  
- 基本的な Java の知識  

### 知識の前提条件
- Java でファイルを扱う経験  

## GroupDocs.Viewer for Java の設定
Maven の `pom.xml` に GroupDocs リポジトリと依存関係を追加します：

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
評価制限を解除するために、一時的またはフルライセンスを取得してください。

### 基本的な初期化と設定
CAD ファイルを指す `Viewer` インスタンスを作成します：

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
この機能を使うと、**DWG を PNG に変換** しながらカスタム幅を指定し、新しい背景色を適用できます。

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
- `PngViewOptions` – 出力形式と命名規則を定義します。  
- `forRenderingByWidth(int width)` – カスタム画像幅を設定します。  
- `setBackgroundColor(Color color)` – **PNG の背景色を設定** して視覚的一貫性を向上させます。

#### トラブルシューティングのヒント
- 出力フォルダーが存在するか確認し、必要なら作成してください。  
- 入力ファイルパスと権限を再確認してください。  

## 機能 2: レンダリングオプションで背景色を設定

### PNG の背景色を設定する方法
ここでは **背景色設定 PNG** オプションに焦点を当て、すべてのレンダリング画像がブランドパレットに合致するようにします。

#### 手順実装

##### 必要なパッケージのインポート
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### 背景色付きレンダリングオプションの構成
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
- 任意の `Color` 定数またはカスタム `new Color(r,g,b)` を使用して独自の背景を作成できます。  

## 実用的な応用例

### 1. エンジニアリング文書
カスタムレンダリングにより、エンジニアリング図面が企業のスタイルガイドに準拠します。

### 2. 建築ビジュアライゼーション
プレゼンテーション資料に合わせたクリーンな背景でブループリントを提示できます。

### 3. 製造プロトタイピング
高速プロトタイピングワークフロー向けに正確な PNG を生成します。

### 統合の可能性
このレンダリングパイプラインをドキュメント管理システムと組み合わせて、ビジュアル資産の自動生成を実現できます。

## パフォーマンスに関する考慮事項

### パフォーマンス最適化
- **バッチ処理:** ループで複数の CAD ファイルをレンダリングします。  
- **リソース管理:** 大きな図面用に JVM ヒープサイズを調整します。

### リソース使用ガイドライン
CPU とメモリを監視し、`Viewer` インスタンスは速やかに解放してください。

### Java メモリ管理のベストプラクティス
- 示したように try‑with‑resources を使用して `Viewer` を自動クローズします。  
- 必要以上に大きな `Path` オブジェクトを保持しないようにします。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **出力フォルダーが見つからない** | 事前にディレクトリを作成するか、`Files.createDirectories(outputDirectory);` を追加してください |
| **画像が空白になる** | `cadOptions.setBackgroundColor` を `forRenderingByWidth` の後に設定してください |
| **メモリ不足エラー** | `-Xmx` JVM オプションを増やすか、ファイルを小さなバッチで処理してください |

## FAQ（よくある質問）

**Q: DWG 以外の CAD フォーマットもレンダリングできますか？**  
A: はい、GroupDocs.Viewer は DXF、DWF など複数の CAD ファイルタイプをサポートしています。

**Q: 定義済み定数ではなくカスタム RGB 色を使用するには？**  
A: 新しい `Color` インスタンスを作成します。例: `new Color(123, 45, 67)` を `setBackgroundColor` に渡します。

**Q: 特定のレイアウトやレイヤーだけをレンダリングすることは可能ですか？**  
A: `viewer.view` を呼び出す前に `CadOptions` でレイアウトまたはレイヤーオプションを指定できます。

**Q: ライブラリは透明背景をサポートしていますか？**  
A: 対象フォーマットが透明をサポートしている場合、`new Color(0,0,0,0)` に設定すると完全な透明背景になります。

**Q: 必要な GroupDocs.Viewer のバージョンは？**  
A: 本チュートリアルはバージョン 25.2 を使用していますが、最新バージョンでも同じ API が利用可能です。

---

**最終更新日:** 2026-03-16  
**テスト環境:** GroupDocs.Viewer 25.2 for Java  
**作者:** GroupDocs