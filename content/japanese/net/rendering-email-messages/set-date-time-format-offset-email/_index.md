---
title: DateTime 形式とタイム ゾーン オフセットの設定 (電子メール)
linktitle: DateTime 形式とタイム ゾーン オフセットの設定 (電子メール)
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer for .NET をアプリケーションにシームレスに統合して、強力なドキュメント表示機能を実現します。カスタマイズ可能なオプションでユーザー エクスペリエンスを向上させます。
weight: 11
url: /ja/net/rendering-email-messages/set-date-time-format-offset-email/
---

# DateTime 形式とタイム ゾーン オフセットの設定 (電子メール)


## 導入
GroupDocs.Viewer for .NET は、開発者がドキュメント表示機能を .NET アプリケーションにシームレスに統合できるようにする強力なツールです。 GroupDocs.Viewer を使用すると、外部のプラグインやビューアを必要とせずに、PDF、Microsoft Office ドキュメント、画像などを含む幅広いドキュメント形式をアプリケーション内で直接表示できます。この包括的なチュートリアルでは、GroupDocs.Viewer for .NET をセットアップし、その機能を調べ、それを効果的に利用してアプリケーションのドキュメント表示機能を強化する方法を説明するプロセスを説明します。
## 前提条件
このチュートリアルに進む前に、次の前提条件が設定されていることを確認してください。
1. Visual Studio: Visual Studio がシステムにインストールされていることを確認してください。 GroupDocs.Viewer for .NET は Visual Studio と完全に互換性があり、.NET プロジェクトへのシームレスな統合を可能にします。
2.  GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET を次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/)。提供されるインストール手順に従って、開発環境内にライブラリをセットアップします。
3. .NET Framework: 適切なバージョンの .NET Framework がインストールされていることを確認してください。 GroupDocs.Viewer for .NET は、.NET Core や .NET Standard を含む、さまざまなバージョンの .NET Framework をサポートします。

## 名前空間のインポート
GroupDocs.Viewer for .NET を効果的に利用するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順に従って、必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


各コンポーネントとその機能を理解するために、提供された例を複数のステップに分割してみましょう。
## ステップ 1: 出力ディレクトリとファイル パスを設定する
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
このステップでは、レンダリングされたドキュメントが保存される出力ディレクトリを定義し、出力 HTML ファイルのファイル パスを指定します。
## ステップ 2: Viewer オブジェクトをインスタンス化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
ここでは、`Viewer`クラスを作成し、表示するドキュメント (この場合はサンプル EML ファイル) のパスをパラメーターとして渡します。
## ステップ 3: HTML 表示オプションを定義する
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
この手順では、ドキュメント レンダリングの HTML ビュー オプションを構成し、レンダリングされた HTML ドキュメントの出力ファイル パスを指定します。
## ステップ 4: DateTime 形式とタイムゾーンオフセットを設定する
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
ここでは、電子メール メッセージの日付と時刻の形式をカスタマイズし、希望のタイムゾーンに従ってタイムゾーン オフセットを設定します。
## ステップ 5: ドキュメントをレンダリングする
```csharp
viewer.View(options);
```
最後に、`View`の方法`Viewer`オブジェクトを呼び出し、ドキュメントを HTML 形式にレンダリングするために設定された HTML ビュー オプションを渡します。
## ステップ 6: 出力ディレクトリを表示する
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
このステップでは、ドキュメントのレンダリングが成功したことを示すメッセージを表示し、レンダリングされた HTML ドキュメントが配置されている出力ディレクトリへのパスを提供するだけです。

## 結論
GroupDocs.Viewer for .NET は、ドキュメント表示機能を .NET アプリケーションに統合するための堅牢なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、GroupDocs.Viewer を簡単にセットアップし、必要な名前空間をインポートし、その機能を利用してカスタマイズ可能なオプションでドキュメントをレンダリングすることができます。 PDF、Microsoft Office ドキュメント、またはその他の形式で作業している場合でも、GroupDocs.Viewer はドキュメント表示のプロセスを簡素化し、アプリケーションのユーザー エクスペリエンスを向上させます。
## よくある質問
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Core をサポートしており、アプリケーションのクロスプラットフォーム互換性を実現します。
### レンダリングされたドキュメントの外観をカスタマイズできますか?
絶対に！ GroupDocs.Viewer には、好みに応じて表示エクスペリエンスを調整するための、ズーム レベル、ページ回転などのさまざまなカスタマイズ オプションが用意されています。
### テスト目的で利用できる試用版はありますか?
はい。GroupDocs.Viewer for .NET の無料試用版を次のサイトからダウンロードできます。[ウェブサイトへのリンク](https://releases.groupdocs.com/viewer/net/)購入する前にその機能を評価してください。
### GroupDocs.Viewer はパスワードで保護されたドキュメントのレンダリングをサポートしていますか?
はい、GroupDocs.Viewer にはパスワードで保護されたドキュメントの表示サポートが組み込まれており、アプリケーション内で安全にドキュメントを表示できます。
### GroupDocs.Viewer に関する追加のサポートや支援はどこで入手できますか?
技術的な質問やサポートが必要な場合は、GroupDocs.Viewer にアクセスしてください。[フォーラム](https://forum.groupdocs.com/c/viewer/9)または、サポート チームに問い合わせて、迅速な支援と指導を受けてください。