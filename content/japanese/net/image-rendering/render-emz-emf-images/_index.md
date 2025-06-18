---
"description": "GroupDocs.Viewer for .NET を使用して、EMZ および EMF 画像をさまざまな形式にレンダリングする方法を学びます。開発者向けのわかりやすいチュートリアルです。"
"linktitle": "EMZおよびEMF画像をレンダリングする"
"second_title": "GroupDocs.Viewer .NET API"
"title": "EMZおよびEMF画像をレンダリングする"
"url": "/ja/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# EMZおよびEMF画像をレンダリングする

## 導入

GroupDocs.Viewer for .NETは、開発者がEMZ（拡張Windowsメタファイル）やEMF（拡張メタファイル）画像を含む様々なドキュメント形式を.NETアプリケーションで表示できるようにする強力なドキュメントレンダリングAPIです。このチュートリアルでは、GroupDocs.Viewer for .NETを使用して、EMZおよびEMF画像をHTML、JPG、PNG、PDFなどの様々な形式にレンダリングする方法を説明します。

![GroupDocs.Viewer for .NET で EMZ および EMF 画像をレンダリングする](/viewer/image-rendering/render-emz-and-emf-images.png)

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. GroupDocs.Viewer for .NET: ライブラリは以下からダウンロードできます。 [ここ](https://releases。groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用に互換性のある開発環境が設定されていることを確認します。
3. サンプル EMZ/EMF 画像: レンダリングに使用できるサンプル EMZ および EMF 画像があります。

## 名前空間のインポート

コードに進む前に、必要な名前空間をインポートしましょう。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

それでは、各例をステップバイステップのガイド形式で複数のステップに分解してみましょう。

## EMZ/EMF 画像を HTML にレンダリングする

### ステップ1: 出力ディレクトリを設定する:
```csharp
string outputDirectory = "Your Document Directory";
```
交換する `"Your Document Directory"` レンダリングされた HTML ファイルを保存するパスに置き換えます。

### ステップ2: ページファイルパスの形式を定義する:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
これにより、レンダリングされた HTML ファイルのファイル パス形式が指定されます。

### ステップ3: HTMLにレンダリングする:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
このコードは、 `Viewer` オブジェクトをサンプル EMZ 画像に変換し、指定されたオプションを使用して HTML 形式にレンダリングします。

## EMZ/EMF 画像を JPG、PNG、PDF にレンダリングする

JPG、PNG、PDF 形式でレンダリングするには、次の手順を繰り返します。

### ステップ1: ページファイルパスの形式を定義する:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
希望する出力形式に応じてファイル名と拡張子を調整します（`jpg`、 `png`、 または `pdf`）。

### ステップ2: それぞれの形式にレンダリングする:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // 出力形式（Jpg、Png、Pdf）に応じてオプションを調整します
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
交換する `JpgViewOptions` と `PngViewOptions` または `PdfViewOptions` 希望する出力形式に基づきます。

## 結論

結論として、GroupDocs.Viewer for .NETは、EMZおよびEMF画像を.NETアプリケーションで様々な形式にレンダリングするためのシームレスなソリューションを提供します。このチュートリアルで概説されている手順に従うことで、開発者はドキュメントレンダリング機能をアプリケーションに簡単に統合できます。

## よくある質問

### Q: GroupDocs.Viewer は、EMZ および EMF 画像以外のドキュメント形式をレンダリングできますか?
A: はい、GroupDocs.Viewer は PDF、DOCX、PPTX、XLSX など、幅広いドキュメント形式をサポートしています。

### Q: GroupDocs.Viewer for .NET の無料試用版はありますか?
A: はい、無料トライアルをご利用いただけます [ここ](https://releases。groupdocs.com/).

### Q: GroupDocs.Viewer は開発者向けのサポートを提供していますか?
A: はい、GroupDocsはサポートを提供しています。 [フォーラム](https://forum.groupdocs.com/c/viewer/9) 開発者が質問したり支援を求めたりできる場所です。

### Q: GroupDocs.Viewer for .NET の一時ライセンスを購入できますか?
A: はい、一時ライセンスは購入できます [ここ](https://purchase。groupdocs.com/temporary-license/).

### Q: GroupDocs.Viewer for .NET の詳細なドキュメントはどこで入手できますか?
A: ドキュメントを参照してください [ここ](https://tutorials.groupdocs.com/viewer/net/) API の使用に関する包括的なガイダンス。