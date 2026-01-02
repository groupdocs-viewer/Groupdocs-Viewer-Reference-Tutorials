---
date: '2026-01-02'
description: GroupDocs.Viewer を使用して JPG 品質を調整し、Java で PDF のサイズを削減する方法をご紹介します。PDF 画像を圧縮し、ファイルサイズと視覚的忠実度のバランスを取るシンプルな手法です。
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: PDFサイズ削減（Java） – GroupDocsでJPG品質を最適化
type: docs
url: /ja/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# PDFサイズ削減 Java – GroupDocsでJPG品質を最適化

PDF を扱う際、ファイルサイズと視覚的忠実度のバランスを取ることは一般的な課題です。このチュートリアルでは、GroupDocs.Viewer for Java を使用して PDF ドキュメント内の JPG 画像品質を調整することで **reduce PDF size Java** を実現する方法を紹介します。セットアップ、コード実装、実用的なヒントを順に解説し、可読性を損なうことなく PDF 画像を自信を持って圧縮できるようになります。

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## クイック回答
- **「reduce PDF size Java」とは何ですか？** 画像品質、圧縮、リソース処理を調整して Java アプリケーションで PDF ファイルを小さくすることを指します。  
- **JPG 品質を制御する設定はどれですか？** `PdfViewOptions.setJpgQuality(byte quality)` で、0（最低）から 100（最高）までの値を指定します。  
- **同じフローで PPTX を PDF に変換できますか？** はい—`Viewer` に `.pptx` ソースを指定すれば同じオプションが適用されます。  
- **Web 公開向けの一般的な品質レベルは？** ほとんどの Web シナリオで **50‑70** の値がバランスの取れた設定です。  
- **この機能にライセンスは必要ですか？** 評価用の無料トライアルは利用可能ですが、実稼働環境では正式ライセンスが必要です。

## “reduce PDF size Java” とは？
Java で PDF サイズを削減することは、特に画像などのリソースを最適化し、最終ファイルの保存容量を減らし、読み込み速度を向上させることを意味します。JPG 品質を下げることで、実質的に **PDF 画像を圧縮** でき、文書サイズの大部分を占める画像を削減できます。

## なぜ GroupDocs ViewerでJPG品質を調整するのか？
- **大幅なサイズ削減**: 画像品質を下げるだけで、元の解像度にもよりますが PDF を 30‑70 % 縮小できます。  
- **単一パス変換**: 別途画像処理ステップは不要です。GroupDocs が PDF 生成時に自動で処理します。  
- **柔軟性**: プロジェクト要件に合わせて `byte` の品質値を細かく調整可能です（例: 高品質印刷 vs 軽量 Web プレビュー）。  

## 前提条件
- **GroupDocs.Viewer for Java** バージョン 25.2 以降。  
- Maven ベースの Java プロジェクトで JDK 8 以上。  
- Java と PDF 操作の基本的な知識。  

## GroupDocs.Viewer for Java の設定
`pom.xml` に GroupDocs リポジトリと依存関係を追加します。

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

> **プロのコツ:** バージョンは常に最新に保ち、パフォーマンス向上や新しい圧縮オプションの恩恵を受けましょう。

## 実装ガイド

### Step 1: Resolve the Output Directory Path
PDF を保存する出力フォルダーを作成するヘルパークラスを作成します。

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### Step 2: Configure `PdfViewOptions` with Desired JPG Quality
レンダリング前に JPG 品質レベル（0‑100）を設定します。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**Explanation:**  
- `setJpgQuality(byte quality)` は、GroupDocs が JPG 画像に対してどれだけ圧縮を行うかを指示します。値が低いほどファイルは小さくなりますが、視覚的な鮮明さが低下する可能性があります。  
- この例では `source.pptx` を使用して **convert pptx to pdf** を実演しつつ、同時に画像を圧縮しています。

### Step 3: Run the Code and Verify the Result
`FeatureAdjustQualityOfJpgImages.run()` を実行します。生成された `output.pdf` には指定した品質レベルの JPG 画像が含まれ、実質的に **PDF 画像を圧縮** して全体のファイルサイズが削減されます。

## Common Issues & Troubleshooting
- **ファイルパスが正しくない:** `source.pptx` が作業ディレクトリからの相対パスで存在することを確認してください。  
- **権限不足:** 出力フォルダーは書き込み可能である必要があります。そうでない場合は `RuntimeException` がスローされます。  
- **予想外に大きな PDF:** サイズ目標に対して `quality` の値が十分に低く設定されているか確認してください。  

## Practical Applications
1. **文書アーカイブ:** 小さな PDF は保存コストを削減し、検索速度を向上させます。  
2. **Web 公開:** PDF が埋め込まれたりリンクされたりする際のページ読み込みが高速化します。  
3. **メール添付:** 送信前に画像品質を下げることでサイズ制限をクリアできます。  

## Performance Considerations
- **バッチ処理:** 大量の文書を扱う場合は、メモリ使用量を監視しながら並列スレッドで処理すると効果的です。  
- **最適品質設定:** 印刷用 PDF には高品質（80‑100）を、Web プレビューには 30‑50 が目安となります。  

## Conclusion
これで **reduce PDF size Java** を実現し、GroupDocs.Viewer を使って JPG 画像品質を調整する方法が分かりました。さまざまな品質レベルで実験し、既存のパイプラインにコードを統合して、より高速で軽量な PDF を手に入れましょう。

### Next Steps
- ユースケースに最適な品質設定を見つけるために、さまざまな値をテストしてください。  
- ウォーターマーキングやパスワード保護など、他の GroupDocs 機能も探索してみましょう。  

## FAQ Section

1. **JPG 品質を調整するとファイルサイズはどのように変わりますか？**  
   品質を下げることでファイルサイズが減少し、文書の共有や保存が容易になります。

2. **JPG 以外のフォーマットの画像品質も調整できますか？**  
   この機能は PDF 内の JPG 画像に特化していますが、GroupDocs.Viewer には他フォーマット向けのオプションも用意されています。

3. **Web 用の理想的な JPG 品質設定は？**  
   50‑70 前後が、クリアさとサイズ削減のバランスが取れた一般的な設定です。

4. **バッチワークフローで自動化できますか？**  
   はい、この機能を組み込めば複数文書を効率的に処理できます。

5. **期待通りに PDF が生成されない場合は？**  
   入力ドキュメントのパスと、すべての依存関係が正しく設定されているか確認してください。

## Frequently Asked Questions

**Q:** *このアプローチで DOCX など他の形式を PDF に変換しながらサイズを削減できますか？*  
**A:** もちろんです。同じ `PdfViewOptions.setJpgQuality` 設定は、JPG 画像を生成するすべてのソース形式で機能します。

**Q:** *JPG 品質を下げてもテキストの描画に影響はありますか？*  
**A:** ありません。テキストはベクターベースで保持され、鮮明さはそのままです。影響を受けるのはラスタ画像のみです。

**Q:** *ページごとに異なる品質レベルを設定できますか？*  
**A:** 現在の GroupDocs の実装では、変換ごとに統一された品質設定が適用されます。ページ単位の制御が必要な場合は、専用の画像処理ライブラリで PDF を後処理する必要があります。

**Q:** *本番環境での使用にはライセンスが必要ですか？*  
**A:** はい、商用利用には有効な GroupDocs.Viewer ライセンスが必要です。評価用に無料トライアルをご利用いただけます。

**Q:** *実際の品質削減をどのように確認できますか？*  
**A:** 変換前後のファイルサイズを比較し、PDF を開いて画像の鮮明さを目視で確認してください。

---

**Last Updated:** 2026-01-02  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)