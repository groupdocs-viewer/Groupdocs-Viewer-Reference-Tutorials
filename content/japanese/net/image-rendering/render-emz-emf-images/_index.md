---
title: EMZ および EMF イメージのレンダリング
linktitle: EMZ および EMF イメージのレンダリング
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET を使用して、EMZ および EMF 画像をさまざまな形式でレンダリングする方法を学びます。開発者向けのわかりやすいチュートリアル。
weight: 14
url: /ja/net/image-rendering/render-emz-emf-images/
---
## 導入

GroupDocs.Viewer for .NET は、開発者が .NET アプリケーションで EMZ (拡張 Windows メタファイル) や EMF (拡張メタファイル) 画像を含むさまざまな種類のドキュメントを表示できるようにする強力なドキュメント レンダリング API です。このチュートリアルでは、GroupDocs.Viewer for .NET を使用して、EMZ および EMF 画像を HTML、JPG、PNG、PDF などのさまざまな形式にレンダリングする方法を検討します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

1.  GroupDocs.Viewer for .NET: ライブラリは次からダウンロードできます。[ここ](https://releases.groupdocs.com/viewer/net/).
2. 開発環境: .NET 開発用に互換性のある開発環境がセットアップされていることを確認します。
3. サンプル EMZ/EMF イメージ: レンダリングに使用できるサンプル EMZ および EMF イメージを用意します。

## 名前空間のインポート

コードに入る前に、必要な名前空間をインポートしましょう。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ここで、各例をステップバイステップのガイド形式で複数のステップに分けてみましょう。

## EMZ/EMF 画像を HTML にレンダリングする

### ステップ 1: 出力ディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
```
交換する`"Your Document Directory"`レンダリングされた HTML ファイルを保存するパスを指定します。

### ステップ 2: ページ ファイルのパス形式を定義します。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
これにより、レンダリングされる HTML ファイルのファイル パス形式が指定されます。

### ステップ 3: HTML にレンダリングする:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
このコードは`Viewer`サンプル EMZ 画像を含むオブジェクトを作成し、指定されたオプションを使用して HTML 形式にレンダリングします。

## EMZ/EMF イメージを JPG、PNG、PDF にレンダリングする

JPG、PNG、PDF 形式でレンダリングするには、次の手順を繰り返します。

### ステップ 1: ページ ファイルのパス形式を定義します。
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
希望の出力形式に従ってファイル名と拡張子を調整します(`jpg`, `png` 、 または`pdf`）。

### ステップ 2: それぞれの形式でレンダリング:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    //出力形式（Jpg、Png、Pdf）に応じてオプションを調整します
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
交換する`JpgViewOptions`と`PngViewOptions`または`PdfViewOptions`希望の出力形式に基づいて。

## 結論

結論として、GroupDocs.Viewer for .NET は、EMZ および EMF イメージを .NET アプリケーションでさまざまな形式にレンダリングするためのシームレスなソリューションを提供します。このチュートリアルで概説されている手順に従うことで、開発者はドキュメント レンダリング機能をアプリケーションに簡単に統合できます。

## よくある質問

### Q: GroupDocs.Viewer は、EMZ および EMF 画像以外の他のドキュメント形式をレンダリングできますか?
A: はい、GroupDocs.Viewer は、PDF、DOCX、PPTX、XLSX などを含む幅広いドキュメント形式をサポートしています。

### Q: GroupDocs.Viewer for .NET に利用できる無料トライアルはありますか?
 A: はい、無料トライアルにアクセスできます。[ここ](https://releases.groupdocs.com/).

### Q: GroupDocs.Viewer は開発者にサポートを提供しますか?
 A: はい、GroupDocs はサポートを提供します。[フォーラム](https://forum.groupdocs.com/c/viewer/9)開発者が質問したり支援を求めたりできる場所。

### Q: GroupDocs.Viewer for .NET の一時ライセンスを購入できますか?
 A: はい、一時ライセンスを購入できます。[ここ](https://purchase.groupdocs.com/temporary-license/).

### Q: GroupDocs.Viewer for .NET の詳細なドキュメントはどこで入手できますか?
 A: ドキュメントを参照してください。[ここ](https://tutorials.groupdocs.com/viewer/net/)API の使用に関する包括的なガイダンスを参照してください。