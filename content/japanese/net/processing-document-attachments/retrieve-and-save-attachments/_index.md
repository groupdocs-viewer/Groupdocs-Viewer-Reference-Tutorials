---
title: 添付文書の取得と保存
linktitle: 添付文書の取得と保存
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer を使用して、.NET アプリケーション内のドキュメント添付ファイルを効率的に管理します。添付ファイルを簡単に取得して保存できます。
weight: 12
url: /ja/net/processing-document-attachments/retrieve-and-save-attachments/
---
## 導入
デジタル時代において、効率的な文書処理は企業にとっても個人にとっても同様に重要です。電子メールの管理、契約書の表示、レポートへのアクセスのいずれの場合でも、文書を視覚化するための信頼できるツールが不可欠です。 GroupDocs.Viewer for .NET は堅牢なソリューションとして登場し、ユーザーが .NET アプリケーション内でさまざまなドキュメント形式を直接簡単に表示および操作できるようにします。
## 前提条件
GroupDocs.Viewer for .NET を使用してドキュメントの添付ファイルを取得および保存する方法を詳しく検討する前に、次の前提条件を満たしていることを確認してください。
1. 動作環境: .NET Framework でセットアップされた作業環境。
2. インストール: GroupDocs.Viewer for .NET ライブラリがダウンロードされ、インストールされます。からライブラリにアクセスできます。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
3. 基本的な理解: C# プログラミング言語に精通していること。
4. ドキュメント ソース: デモンストレーションを目的とした添付ファイル付きのサンプル ドキュメントへのアクセス。

## 名前空間のインポート
添付ファイルの取得と保存に GroupDocs.Viewer for .NET の利用を開始するには、必要な名前空間をインポートします。
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## ステップ 1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
ドキュメントから取得した添付ファイルを保存するディレクトリを定義します。
## ステップ 2: Viewer オブジェクトをインスタンス化する
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
添付ファイルを含むドキュメントへのパスを使用して Viewer オブジェクトをインスタンス化します。
## ステップ 3: 添付ファイルを取得する
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
ドキュメント内に存在する添付ファイルのリストを取得します。
## ステップ 4: 添付ファイルを保存する
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
各添付ファイルを繰り返し処理し、ファイル パスを定義し、指定したディレクトリに添付ファイルを保存します。
## ステップ 5: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
添付ファイルが正常に保存されたことを示す成功メッセージをディレクトリ パスとともに表示します。

## 結論
GroupDocs.Viewer for .NET をドキュメント処理ワークフローに組み込むと、添付ファイルの管理プロセスが合理化され、効率と利便性が提供されます。上記のステップバイステップ ガイドに従うことで、ユーザーは .NET アプリケーション内でドキュメントの添付ファイルをシームレスに取得および保存できます。
## よくある質問
### GroupDocs.Viewer for .NET はさまざまなドキュメント形式を処理できますか?
はい。GroupDocs.Viewer は、PDF、Microsoft Office ドキュメント、画像などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer for .NET に利用できる無料試用版はありますか?
はい、以下から無料トライアルにアクセスできます。[ここ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。[このリンク](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET のドキュメントはどこで見つけられますか?
包括的なドキュメントが利用可能です[ここ](https://tutorials.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET ではどのようなサポート オプションが利用できますか?
コミュニティ フォーラムから支援を求めることができます[ここ](https://forum.groupdocs.com/c/viewer/9).