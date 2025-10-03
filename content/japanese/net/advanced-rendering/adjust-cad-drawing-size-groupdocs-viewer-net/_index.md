---
"date": "2025-04-25"
"description": "GroupDocs.Viewer .NET を使用して CAD 図面のサイズを調整し、画像の品質と Web パフォーマンスを効率的に最適化する方法を学びます。"
"title": "GroupDocs.Viewer .NET を使用して CAD 図面のサイズを最適化し、Web パフォーマンスを向上"
"url": "/ja/net/advanced-rendering/adjust-cad-drawing-size-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# GroupDocs.Viewer .NET を使用して CAD 図面のサイズを最適化し、Web パフォーマンスを向上

## 導入

大規模なCAD図面を最適なサイズでレンダリングするのは、特にWebアプリケーションの読み込み時間を短縮し、パフォーマンスを向上させる上で困難な場合があります。GroupDocs.Viewer for .NETは、スケール係数を使用して出力画像のサイズを調整することで、このプロセスを簡素化します。このチュートリアルでは、GroupDocs.Viewerを使用してCAD図面のサイズを設定し、最適化する方法について説明します。

![GroupDocs.Viewer for .NET で CAD 図面のサイズを最適化](/viewer/advanced-rendering/optimize-cad-drawing-size-img.png)

**学習内容:**
- GroupDocs.Viewer for .NET のセットアップ
- スケール係数を使用してCAD図面のサイズを調整する
- オプションの設定と一般的な問題のトラブルシューティング

環境の構成を始める前に、前提条件を確認してください。

## 前提条件

### 必要なライブラリ、バージョン、依存関係
このチュートリアルを実行するには、次のものが必要です。
- GroupDocs.Viewer for .NET (バージョン 25.3.0 以降)
- Visual Studioのような.NET互換IDE

### 環境設定要件
システムに以下がインストールされていることを確認してください。
- .NET Framework バージョン 4.6.1 以降
- C# および .NET プロジェクトのセットアップに関する基本的な理解

### 知識の前提条件
CAD ファイル、HTML レンダリングの概念、C# プログラミングに関する基本的な知識があると役立ちます。

## GroupDocs.Viewer for .NET のセットアップ

GroupDocs.Viewer を使用するための環境設定は簡単です。各種パッケージマネージャーを使用してインストールする方法は次のとおりです。

**NuGet パッケージ マネージャー コンソール**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ライセンス取得手順
GroupDocs.Viewer をご利用いただくには、無料トライアルから始めるか、より広範なテストのために一時ライセンスを取得してください。本番環境でご利用いただくには、ライセンスのご購入が必要です。
1. **無料トライアル:** 最新バージョンをダウンロードするには [GroupDocsリリース](https://releases。groupdocs.com/viewer/net/).
2. **一時ライセンス:** 臨時免許を申請する [Webサイト](https://purchase。groupdocs.com/temporary-license/).
3. **購入：** フルアクセスするには、次のリンクからライセンスを購入してください: [GroupDocs購入](https://purchase。groupdocs.com/buy).

### C# による基本的な初期化とセットアップ
パッケージをインストールしたら、.NET プロジェクトで GroupDocs.Viewer を初期化して設定する方法は次のとおりです。
```csharp
using System;
using GroupDocs.Viewer;

namespace CadImageAdjustment
{
    class Program
    {
        static void Main(string[] args)
        {
            string documentPath = "path/to/your/sample.dwg"; // CADファイルへのパス

            using (Viewer viewer = new Viewer(documentPath))
            {
                // 構成とレンダリングロジックはここに記述します
            }
        }
    }
}
```

## 実装ガイド

### CAD図面の出力画像サイズの調整
この機能は、品質を損なうことなくCAD図面をさまざまなサイズでレンダリングする必要がある場合に特に便利です。手順を詳しく説明します。

#### ステップ1: ビューアオブジェクトの初期化
まず、 `Viewer` オブジェクトをドキュメント パスに関連付けます。
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // 追加の設定は後ほど行います
}
```

#### ステップ2: 表示オプションを構成する
HTML表示オプションを設定して、CAD図面の表示方法を指定します。簡潔にするために埋め込みリソースを使用します。
```csharp
string outputDirectory = "your/output/directory/";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

#### ステップ3: CADレンダリングオプションを設定する
出力画像のサイズを調整するには、スケール係数を使用します。ここでは、スケール係数として `0.5f`これにより、画像サイズが半分に縮小されます。
```csharp
options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
```

#### ステップ4: ドキュメントのレンダリング
最後に、 `View` 指定されたオプションを使用してドキュメントをレンダリングするメソッド。
```csharp
viewer.View(options);
```

### トラブルシューティングのヒント
- ファイル パスが正しく、アクセス可能であることを確認してください。
- エラーが発生した場合は、すべての依存関係が適切にインストールされていることを確認してください。
- レンダリング中に発生した問題をログに記録します。

## 実用的なアプリケーション
CAD イメージのサイズを調整することは、実世界ではさまざまな用途に使用できます。
1. **Webポータル:** 大規模な図面を最適化して、建築プランを紹介する Web ポータルでの読み込み時間を短縮します。
2. **モバイルアプリケーション:** 画面スペースが限られているモバイル デバイス向けに、CAD ファイルの縮小版をレンダリングします。
3. **クロスプラットフォーム統合:** GroupDocs.Viewer を .NET アプリケーションと統合して、さまざまなプラットフォーム間でシームレスなドキュメント表示エクスペリエンスを提供します。

## パフォーマンスに関する考慮事項

### パフォーマンスを最適化するためのヒント
- スケール係数を賢く使用して品質とパフォーマンスのバランスを取ります。
- 処分する `Viewer` 使用後はすぐにオブジェクトを破棄してリソースを解放します。

### リソース使用ガイドライン
特に大きなファイルを扱う場合には、レンダリング中のメモリ使用量を監視して、効率的なリソース割り当てを確保します。

### .NET メモリ管理のベストプラクティス
適切な廃棄パターンを実装し、アプリケーションの応答性を維持するために、該当する場合は非同期操作の使用を検討してください。

## 結論

このチュートリアルでは、GroupDocs.Viewer for .NET を使用してCAD図面の出力画像サイズを調整する方法について説明しました。環境設定、表示オプションの設定、スケール係数を使用したドキュメントのレンダリングを行うことで、様々なアプリケーションで大規模なCADファイルを効率的に管理できます。

**次のステップ:**
- GroupDocs.Viewer の追加機能をご覧ください
- 特定のニーズに合わせてさまざまな構成を試してみてください

試してみませんか？今すぐこのソリューションをプロジェクトに実装しましょう。

## FAQセクション

1. **GroupDocs.Viewer は無料で使用できますか?**
   - はい、無料トライアルで機能をテストすることができます。
2. **GroupDocs.Viewer はどのようなファイル形式をサポートしていますか?**
   - CAD ファイルを含む 80 種類以上のドキュメントおよび画像形式をサポートしています。
3. **大規模な CAD ファイルを効率的に処理するにはどうすればよいですか?**
   - スケール係数を使用してレンダリングされたイメージのサイズを縮小し、パフォーマンスを向上させます。
4. **出力形式をカスタマイズする方法はありますか?**
   - はい、HTML 表示オプションを構成したり、PDF や画像ファイルなどのサポートされている他の形式を使用したりできます。
5. **レンダリングに失敗した場合はどうすればいいですか?**
   - ファイル パスを確認し、依存関係がインストールされていることを確認し、トラブルシューティングのためにエラー ログを確認します。

## リソース
- [ドキュメント](https://docs.groupdocs.com/viewer/net/)
- [APIリファレンス](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer をダウンロード](https://releases.groupdocs.com/viewer/net/)
- [ライセンスを購入](https://purchase.groupdocs.com/buy)
- [無料トライアル](https://releases.groupdocs.com/viewer/net/)
- [一時ライセンス](https://purchase.groupdocs.com/temporary-license/)
- [サポートフォーラム](https://forum.groupdocs.com/c/viewer/9)