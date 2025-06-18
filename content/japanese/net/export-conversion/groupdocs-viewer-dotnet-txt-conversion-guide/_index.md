---
"date": "2025-04-25"
"description": "この包括的なガイドでは、GroupDocs.Viewer for .NET を使用して TXT ファイルを HTML、JPG、PNG、PDF などの複数の形式に変換する方法を学習します。"
"title": "GroupDocs.Viewer .NET を使用して TXT を HTML、JPG、PNG、PDF に変換する完全ガイド"
"url": "/ja/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# GroupDocs.Viewer .NET で TXT を複数の形式に変換する

## 導入

テキスト ドキュメントを HTML、JPG、PNG、PDF などのさまざまな形式に簡単に変換したいとお考えですか? ドキュメント変換の管理は、特に複数のページや特定の形式要件を扱う場合には困難になることがあります。 **.NET 用 GroupDocs.Viewer** TXT ファイルをさまざまな出力形式に変換するプロセスを簡素化し、データへのアクセス性と視覚的な魅力を確保します。

![GroupDocs.Viewer for .NET で TXT を HTML、JPG、PNG、PDF に変換](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

このガイドでは、GroupDocs.Viewer for .NETを使用してTXT文書を複数ページのHTML、単一ページのHTML、JPG、PNG、PDFに変換する方法を学びます。このガイドを最後まで読むと、以下のことが理解できるようになります。
- GroupDocs.Viewer を使用して C# で TXT ファイルを変換する
- ニーズに合わせてさまざまなレンダリングオプションを実装する
- コンバージョン時のパフォーマンスの最適化

ドキュメント変換の課題を解決するために、早速取り組みましょう。

## 前提条件

始める前に、以下のものが準備されていることを確認してください。
- **開発環境**Visual Studio 2019 以降。
- **.NET フレームワーク**バージョン4.6.1以上。
- **GroupDocs.Viewer for .NET ライブラリ**：
  - NuGet パッケージ マネージャー コンソール経由: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - .NET CLI の使用: `dotnet add package GroupDocs.Viewer --version 25.3.0`

簡単に理解するには、C# プログラミングと .NET の基本的なファイル操作に精通していることをお勧めします。

## GroupDocs.Viewer for .NET のセットアップ

### インストール

まず、 **GroupDocs.Viewer** 好みのパッケージ マネージャーを使用してライブラリを実行します。

#### NuGet パッケージ マネージャー コンソール
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ライセンス

まずは **無料トライアル** または取得する **一時ライセンス** 評価制限なしで GroupDocs.Viewer for .NET の全機能を試すには:
- 無料トライアル: [ダウンロードはこちら](https://releases.groupdocs.com/viewer/net/)
- 一時ライセンス: [こちらからリクエスト](https://purchase.groupdocs.com/temporary-license/)

継続使用の場合は、直接ライセンスを購入することを検討してください。 [グループドキュメント](https://purchase。groupdocs.com/buy).

### 基本的な初期化

プロジェクトで GroupDocs.Viewer を設定するには:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Viewer オブジェクトを TXT ファイル パスで初期化します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // レンダリング コードをここに入力します。
}
```

## 実装ガイド

それでは、それぞれの機能を詳しく見て、どのように実装できるかを見てみましょう。

### TXT ドキュメントを複数ページの HTML にレンダリングする

#### 概要
この機能は、TXT文書を複数ページのHTML形式に変換する方法を示しています。テキストファイルの各ページは、埋め込まれたリソースを含む個別のHTMLファイルとしてレンダリングされます。

#### ステップ1: ビューアを設定する

作成する `Viewer` ソースTXTファイルのオブジェクト:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// サンプル テキスト ファイルを使用してビューアーを初期化します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ステップ 2 に進みます...
```

#### ステップ2: HTML表示オプションを構成する

設定 `HtmlViewOptions` 各ページを個別にレンダリングするには:

```csharp
// 複数ページのレンダリング用の HTML 表示オプションを設定します。
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// ドキュメントを複数ページの HTML としてレンダリングします。
viewer.View(options);
}
```

**説明**：その `ForEmbeddedResources()` この方法により、画像やスタイルなどのリソースが HTML ファイル内に直接埋め込まれ、簡単に共有できるようになります。

### TXT ドキュメントを単一ページの HTML にレンダリングする

#### 概要
TXT ドキュメントを単一の HTML ページに変換します。1 つの連続した Web ページとして表示する必要があるドキュメントに最適です。

#### ステップ1: ビューアを設定する

初期化する `Viewer` 物体：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// 別のテキスト ファイル用に新しい Viewer インスタンスを初期化します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // ステップ 2 に進みます...
```

#### ステップ2: シングルページHTMLオプションを構成する

設定 `HtmlViewOptions` シングルページ設定を有効にすると、次のようになります。

```csharp
// 単一の HTML ページにレンダリングするためのオプションを設定します。
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// 単一の HTML ページとしてレンダリングします。
viewer.View(options);
}
```

**説明**：その `RenderToSinglePage` プロパティにより、コンテンツ全体が 1 ページに表示されるようになります。

### TXT文書をJPGに変換する

#### 概要
この機能を使用すると、テキスト ドキュメントを JPEG 画像に変換することができ、視覚的なプレゼンテーションやアーカイブに役立ちます。

#### ステップ1: ビューアを設定する

準備する `Viewer` 物体：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// サンプル ファイルを使用してビューアを初期化します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ステップ 2 に進みます...
```

#### ステップ2: JPG表示オプションを設定する

設定 `JpgViewOptions` 画像レンダリングの場合:

```csharp
// JPG 画像としてレンダリングするためのオプションを設定します。
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// ドキュメントを JPEG ファイルとしてレンダリングします。
viewer.View(options);
}
```

**説明**：その `JpgViewOptions` クラスは、ドキュメントの各ページを JPEG 形式でレンダリングして保存する方法を指定します。

### TXT文書をPNGに変換する

#### 概要
テキスト ドキュメントを PNG 形式に変換し、透明性をサポートする高品質の画像出力を提供します。

#### ステップ1: ビューアを設定する

初期化する `Viewer` 物体：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// TXT ファイルのビューアー インスタンスを作成します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ステップ 2 に進みます...
```

#### ステップ2: PNG表示オプションを設定する

設定 `PngViewOptions`：

```csharp
// PNG 画像としてレンダリングするための表示オプションを設定します。
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// ドキュメントを PNG 形式でレンダリングします。
viewer.View(options);
}
```

**説明**：その `PngViewOptions` クラスを使用すると、各ページを透明にレンダリングできるため、レイヤー化されたグラフィックに適しています。

### TXT文書をPDFに変換する

#### 概要
この機能は、テキスト ドキュメントを誰もがアクセスできる PDF 形式に変換するのに最適です。

#### ステップ1: ビューアを設定する

準備する `Viewer` 物体：

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// サンプル テキスト ファイルのビューアー インスタンスを初期化します。
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ステップ 2 に進みます...
```

#### ステップ2: PDF表示オプションを設定する

設定 `PdfViewOptions`：

```csharp
// PDF ドキュメントとしてレンダリングするための表示オプションを設定します。
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// ドキュメントを PDF ファイルにレンダリングします。
viewer.View(options);
}
```

**説明**：その `PdfViewOptions` クラスは、TXT ファイルを PDF ドキュメントに変換して保存する方法を指定します。

## 結論

GroupDocs.Viewer for .NETを使えば、テキストドキュメントを様々な形式に変換するのが簡単です。このガイドでは、C#を使ってTXTファイルを複数ページのHTML、単一ページのHTML、JPG、PNG、PDFに変換する方法を解説しました。ドキュメントのアクセシビリティや互換性の向上をお考えの場合でも、これらの方法は堅牢なソリューションとなります。

さらに詳しいサポートや高度な機能については、 [公式GroupDocs.Viewerドキュメント](https://docs.groupdocs.com/viewer/net/)楽しいコーディングを！