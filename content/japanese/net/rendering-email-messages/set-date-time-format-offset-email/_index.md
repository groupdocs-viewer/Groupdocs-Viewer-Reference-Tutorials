---
"description": "GroupDocs.Viewer for .NETをアプリケーションにシームレスに統合することで、強力なドキュメント表示機能を実現できます。カスタマイズ可能なオプションでユーザーエクスペリエンスを向上できます。"
"linktitle": "日時形式とタイムゾーンオフセットを設定する（メール）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "日時形式とタイムゾーンオフセットを設定する（メール）"
"url": "/ja/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# 日時形式とタイムゾーンオフセットを設定する（メール）


## 導入
GroupDocs.Viewer for .NETは、開発者が.NETアプリケーションにドキュメント表示機能をシームレスに統合できるようにする強力なツールです。GroupDocs.Viewerを使えば、PDF、Microsoft Officeドキュメント、画像など、幅広い形式のドキュメントをアプリケーション内で直接表示できます。外部プラグインやビューアは必要ありません。この包括的なチュートリアルでは、GroupDocs.Viewer for .NETの設定手順、機能の説明、そしてアプリケーションのドキュメント表示機能を強化するための効果的な活用方法をご紹介します。
## 前提条件
このチュートリアルに進む前に、次の前提条件が設定されていることを確認してください。
1. Visual Studio: システムに Visual Studio がインストールされていることを確認してください。GroupDocs.Viewer for .NET は Visual Studio と完全に互換性があり、.NET プロジェクトへのシームレスな統合を可能にします。
2. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NETを以下のサイトからダウンロードしてインストールします。 [ダウンロードリンク](https://releases.groupdocs.com/viewer/net/)提供されているインストール手順に従って、開発環境内でライブラリをセットアップします。
3. .NET Framework: 適切なバージョンの .NET Framework がインストールされていることを確認してください。GroupDocs.Viewer for .NET は、.NET Core や .NET Standard を含む、さまざまなバージョンの .NET Framework をサポートしています。

## 名前空間のインポート
GroupDocs.Viewer for .NET を効果的に活用するには、必要な名前空間をプロジェクトにインポートする必要があります。必要な名前空間をインポートするには、以下の手順に従ってください。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


提供された例を複数のステップに分解して、各コンポーネントとその機能について理解してみましょう。
## ステップ1: 出力ディレクトリとファイルパスを設定する
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
このステップでは、レンダリングされたドキュメントが保存される出力ディレクトリを定義し、出力 HTML ファイルのファイル パスを指定します。
## ステップ2: ビューアオブジェクトのインスタンス化
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
ここで、新しいインスタンスを作成します。 `Viewer` クラスに、表示するドキュメントのパス (この場合はサンプル EML ファイル) をパラメーターとして渡します。
## ステップ3: HTML表示オプションを定義する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
この手順では、ドキュメント レンダリングの HTML ビュー オプションを構成し、レンダリングされた HTML ドキュメントの出力ファイル パスを指定します。
## ステップ4: 日時形式とタイムゾーンオフセットを設定する
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
ここでは、電子メール メッセージの日付と時刻の形式をカスタマイズし、希望するタイムゾーンに応じてタイム ゾーン オフセットを設定します。
## ステップ5: ドキュメントのレンダリング
```csharp
viewer.View(options);
```
最後に、 `View` の方法 `Viewer` オブジェクトに、構成された HTML 表示オプションを渡して、ドキュメントを HTML 形式に変換します。
## ステップ6: 出力ディレクトリを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
この手順では、ドキュメントのレンダリングが成功したことを示すメッセージが表示され、レンダリングされた HTML ドキュメントが保存されている出力ディレクトリへのパスが提供されます。

## 結論
GroupDocs.Viewer for .NETは、.NETアプリケーションにドキュメント表示機能を統合するための堅牢なソリューションを提供します。このチュートリアルで説明する手順に従うことで、GroupDocs.Viewerを簡単にセットアップし、必要な名前空間をインポートし、その機能を活用してカスタマイズ可能なオプションでドキュメントをレンダリングできます。PDF、Microsoft Officeドキュメント、その他の形式を問わず、GroupDocs.Viewerはドキュメント表示プロセスを簡素化し、アプリケーションのユーザーエクスペリエンスを向上させます。
## よくある質問
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Core をサポートしており、アプリケーションのクロスプラットフォーム互換性を実現します。
### レンダリングされたドキュメントの外観をカスタマイズできますか?
もちろんです! GroupDocs.Viewer には、ズーム レベル、ページの回転など、さまざまなカスタマイズ オプションが用意されており、ユーザーの好みに応じて表示エクスペリエンスをカスタマイズできます。
### テスト用に試用版はありますか?
はい、GroupDocs.Viewer for .NETの無料試用版を以下のサイトからダウンロードできます。 [ウェブサイトリンク](https://releases.groupdocs.com/viewer/net/) 購入する前にその機能を評価します。
### GroupDocs.Viewer はパスワードで保護されたドキュメントのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer にはパスワードで保護されたドキュメントをレンダリングするためのサポートが組み込まれており、アプリケーション内での安全なドキュメント表示が保証されます。
### GroupDocs.Viewer に関する追加のサポートや支援はどこで受けられますか?
技術的な質問やサポートについては、GroupDocs.Viewerをご覧ください。 [フォーラム](https://forum.groupdocs.com/c/viewer/9) または、サポート チームに連絡して、迅速なヘルプとガイダンスを受けることもできます。