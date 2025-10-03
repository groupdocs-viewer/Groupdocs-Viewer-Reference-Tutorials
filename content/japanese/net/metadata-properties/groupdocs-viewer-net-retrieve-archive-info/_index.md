---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET を使用してアーカイブ情報を効率的に抽出する方法を学びましょう。このガイドでは、セットアップ、コード例、そして実践的な応用例について説明します。"
"title": "GroupDocs.Viewer for .NET を使用してアーカイブ情報を取得する方法 包括的なガイド"
"url": "/ja/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
type: docs
---
# GroupDocs.Viewer for .NET を使用してアーカイブ情報を取得する方法: 包括的なガイド

## 導入

ZIPなどのアーカイブファイルから詳細情報を効率的に抽出したいとお考えですか？文書管理には、構造を理解することが不可欠です。このガイドでは、 **.NET 用 GroupDocs.Viewer** アーカイブ ファイルに関する包括的な詳細を取得して表示します。

![GroupDocs.Viewer for .NET でアーカイブ情報を取得する](/viewer/metadata-properties/retrieve-archive-information.png)

このチュートリアルでは、次の内容を取り上げます。
- .NET アプリケーションで GroupDocs.Viewer を設定する
- アーカイブファイルからビュー情報を取得する
- アーカイブ内のフォルダ構造を表示する

このガイドを読み終える頃には、これらの機能の実装についてしっかりと理解できるようになります。まずはコードを読み進める前に、必要なことを把握しましょう。

### 前提条件

以下のものを準備しておいてください。

- **ライブラリとバージョン**GroupDocs.Viewer for .NET (バージョン 25.3.0) をインストールします。
- **環境設定**Visual Studio などの適切な .NET 開発環境を使用します。
- **知識の前提条件**C# と .NET アプリケーションにおけるファイル処理に関する基本的な理解。

## GroupDocs.Viewer for .NET のセットアップ

GroupDocs.Viewer for .NET を使用するには、NuGet パッケージ マネージャーを使用してインストールします。

### インストール手順

**NuGet パッケージ マネージャー コンソール**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ライセンスの取得

GroupDocs.Viewer には、いくつかのライセンス オプションがあります。
- **無料トライアル**基本的な機能を調べます。
- **一時ライセンス**評価期間中はフル機能にアクセスできます。
- **購入**長期使用の場合は、ライセンスの購入を検討してください。

インストールとライセンスの設定が完了したら、アプリケーションでGroupDocs.Viewerを初期化してください。設定例を以下に示します。

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // ここでビューア機能を使用します。
}
```

## 実装ガイド

構造化されたアプローチのために、実装を主要な機能に分解します。

### アーカイブファイルのビュー情報を取得する

アーカイブの構造を理解することは非常に重要です。その方法は次のとおりです。

#### ビューアオブジェクトを初期化する

インスタンスを作成する `Viewer` アーカイブファイルのパスとクラスを関連付けます:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // 処理用のコードをここに入力します。
}
```

#### ビュー情報を取得する

JPG 画像形式のビュー情報を取得します。

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### ルートフォルダ情報を表示する

包括的な概要を確認するには、ルート フォルダーの詳細を印刷します。

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### サブフォルダ名を再帰的に読み取り、印刷する

アーカイブ内のサブフォルダーを探索するには、次の再帰的な方法を使用します。

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### 実用的なアプリケーション

GroupDocs.Viewer for .NET はさまざまなシナリオで使用できます。
- **文書管理システム**アーカイブ構造を自動的に抽出して表示します。
- **コンテンツ配信プラットフォーム**アーカイブされたコンテンツのプレビューをユーザーに提供します。
- **データ分析ツール**アーカイブ内のフォルダー階層を分析してビジネス分析を行います。

ASP.NET や WPF などの他のフレームワークとの統合は簡単で、既存のシステムにシームレスに組み込むことができます。

## パフォーマンスに関する考慮事項

最適なパフォーマンスを得るには:
- **リソース使用の最適化**メモリを効率的に管理し、大きなファイルを処理します。
- **メモリ管理のベストプラクティス**：処分する `Viewer` オブジェクトを適切に処理して、リソースを速やかに解放します。

## 結論

このチュートリアルでは、GroupDocs.Viewer for .NET を利用してアーカイブファイルから詳細情報を取得する方法を学習しました。これらの機能を実装することで、ドキュメント管理機能を大幅に強化できます。

### 次のステップ

GroupDocs.Viewer が提供するより高度な機能を試したり、アプリケーションの他のコンポーネントと統合したりすることを検討してください。さまざまなファイル形式や複雑なフォルダ構造を試して、理解を深めてください。

## FAQセクション

1. **の目的は何ですか？ `ViewInfoOptions`？**
   - JPG などの特定の形式でレンダリングするなど、ドキュメントの表示方法を構成します。

2. **大規模なアーカイブを効率的に処理するにはどうすればよいでしょうか?**
   - メモリ管理技術を使用して、リソースを適切に処分します。

3. **GroupDocs.Viewer はパスワードで保護されたファイルを処理できますか?**
   - はい、適切なライセンスと構成があれば、暗号化されたドキュメントを処理できます。

4. **処理できるアーカイブ ファイルのサイズに制限はありますか?**
   - 制限はシステムのメモリ容量によって異なり、ファイルが大きいほど多くのリソースが必要になります。

5. **GroupDocs.Viewer を ASP.NET アプリケーションと統合するにはどうすればよいですか?**
   - コンソール アプリケーションの場合と同様に、コントローラー アクションまたはサービス内で Viewer クラスを使用します。

## リソース

- [ドキュメント](https://docs.groupdocs.com/viewer/net/)
- [APIリファレンス](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer for .NET をダウンロード](https://releases.groupdocs.com/viewer/net/)
- [ライセンスを購入する](https://purchase.groupdocs.com/buy)
- [無料試用版](https://releases.groupdocs.com/viewer/net/)
- [臨時免許申請](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)