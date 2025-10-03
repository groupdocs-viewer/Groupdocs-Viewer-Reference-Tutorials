---
"description": "シームレスなドキュメントのレンダリング、反転、回転を実現するために、Groupdocs.Viewer for .NET をアプリケーションに統合する方法を学びます。"
"linktitle": "ページをめくる、回転する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ページをめくる、回転する"
"url": "/ja/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# ページをめくる、回転する

## 導入
このチュートリアルでは、Groupdocs.Viewer for .NETの機能、特にページの反転と回転に焦点を当てて詳しく説明します。Groupdocs.Viewer for .NETは、.NETアプリケーション内で様々な形式のドキュメントをレンダリングするために設計された強力なツールです。ドキュメント管理システムを開発する場合でも、ソフトウェアにドキュメント表示機能を統合する必要がある場合でも、Groupdocs.Viewer for .NETは効率的なソリューションを提供します。
## 前提条件
始める前に、次の前提条件が設定されていることを確認してください。
### Groupdocs.Viewer for .NET のインストール
Groupdocs.Viewer for .NETを使用するには、NuGetパッケージマネージャーを使用してパッケージをインストールする必要があります。詳細なインストール手順については、 [ドキュメント](https://tutorials。groupdocs.com/viewer/net/).

## 名前空間のインポート
Groupdocs.Viewer for .NET を効果的に活用するには、プロジェクトに必要な名前空間がインポートされていることを確認してください。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Groupdocs.Viewer for .NET を使用してページをめくったり回転したりするプロセスを簡単な手順に分解してみましょう。
## ステップ1: 出力ディレクトリとファイルパスを設定する
出力ファイルを保存するディレクトリを定義し、出力ファイルのパスを指定します。
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## ステップ2: ビューアオブジェクトの初期化
表示するドキュメントへのパスを渡して、Viewer クラスのインスタンスを作成します。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## ステップ3: 表示オプションを構成する
出力ファイル形式の指定やページの回転などの追加設定など、表示オプションを設定します。
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## ステップ4: ドキュメントのレンダリング
Viewer オブジェクトの View メソッドを呼び出し、表示オプションを渡します。
```csharp
viewer.View(viewOptions);
```
## ステップ5: 成功メッセージを表示する
ドキュメントが正常にレンダリングされたことをユーザーに通知し、検証用の出力ディレクトリを指定します。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論
結論として、Groupdocs.Viewer for .NETは、ページの反転や回転など、ドキュメントのレンダリングに強力な機能を提供します。このチュートリアルで概説した手順に従うことで、これらの機能を.NETアプリケーションにシームレスに統合し、ユーザーのドキュメント閲覧エクスペリエンスを向上させることができます。
## よくある質問
### Groupdocs.Viewer for .NET はすべてのドキュメント形式と互換性がありますか?
はい、Groupdocs.Viewer for .NET は、DOCX、PDF、PPTX など、幅広いドキュメント形式をサポートしています。
### ページのめくりや回転以外に表示オプションをカスタマイズできますか?
はい、Groupdocs.Viewer for .NET では、ドキュメントを表示するためのさまざまなカスタマイズ オプションが提供されており、要件に応じてエクスペリエンスをカスタマイズできます。
### Groupdocs.Viewer for .NET の無料試用版はありますか?
はい、Groupdocs.Viewer for .NETの無料トライアルをご利用いただくには、 [Webサイト](https://releases。groupdocs.com/).
### Groupdocs.Viewer for .NET のサポートを受けるにはどうすればよいですか?
支援を求めたり、コミュニティに参加したりするために、 [Groupdocs.Viewerフォーラム](https://forum。groupdocs.com/c/viewer/9).
### Groupdocs.Viewer for .NET の一時ライセンスはどこで入手できますか?
Groupdocs.Viewer for .NETの一時ライセンスは、 [購入ページ](https://purchase。groupdocs.com/temporary-license/).