---
"description": "GroupDocs.Viewer を使用すると、.NET アプリケーション内でドキュメントの添付ファイルを効率的に管理できます。添付ファイルの取得と保存も簡単です。"
"linktitle": "ドキュメントの添付ファイルを取得して保存する"
"second_title": "GroupDocs.Viewer .NET API"
"title": "ドキュメントの添付ファイルを取得して保存する"
"url": "/ja/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
---

# ドキュメントの添付ファイルを取得して保存する

## 導入
デジタル時代において、効率的なドキュメント処理は企業にとっても個人にとっても不可欠です。メールの管理、契約書の閲覧、レポートへのアクセスなど、ドキュメントを視覚化するための信頼性の高いツールは不可欠です。GroupDocs.Viewer for .NETは、ユーザーが.NETアプリケーション内で様々な形式のドキュメントを簡単に表示・操作できるようにする堅牢なソリューションです。

![GroupDocs.Viewer .NET でドキュメントの添付ファイルを取得して保存する](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## 前提条件
ドキュメント添付ファイルの取得と保存に GroupDocs.Viewer for .NET を活用する前に、次の前提条件を満たしていることを確認してください。
1. 動作環境: .NET Framework でセットアップされた作業環境。
2. インストール：GroupDocs.Viewer for .NETライブラリをダウンロードしてインストールします。ライブラリには、 [ダウンロードリンク](https://releases。groupdocs.com/viewer/net/).
3. 基本的な理解: C# プログラミング言語に精通していること。
4. ドキュメント ソース: デモンストレーション用の添付ファイルを含むサンプル ドキュメントへのアクセス。

## 名前空間のインポート
ドキュメント添付ファイルの取得と保存に GroupDocs.Viewer for .NET を利用するには、必要な名前空間をインポートします。
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## ステップ1: 出力ディレクトリを定義する
```csharp
string outputDirectory = "Your Document Directory";
```
ドキュメントから取得した添付ファイルを保存するディレクトリを定義します。
## ステップ2: ビューアオブジェクトのインスタンス化
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
添付ファイルを含むドキュメントへのパスを使用して Viewer オブジェクトをインスタンス化します。
## ステップ3: 添付ファイルを取得する
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
ドキュメント内に存在する添付ファイルのリストを取得します。
## ステップ4: 添付ファイルを保存する
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
各添付ファイルを反復処理し、ファイル パスを定義して、添付ファイルを指定されたディレクトリに保存します。
## ステップ5: 成功メッセージを表示する
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
添付ファイルの保存が成功したことを示す成功メッセージをディレクトリ パスとともに表示します。

## 結論
GroupDocs.Viewer for .NETをドキュメント処理ワークフローに組み込むことで、添付ファイルの管理プロセスが合理化され、効率性と利便性が向上します。上記のステップバイステップガイドに従うことで、ユーザーは.NETアプリケーション内でドキュメントの添付ファイルをシームレスに取得・保存できます。
## よくある質問
### GroupDocs.Viewer for .NET はさまざまなドキュメント形式を処理できますか?
はい、GroupDocs.Viewer は、PDF、Microsoft Office ドキュメント、画像など、幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer for .NET の無料試用版はありますか?
はい、無料トライアルは以下からアクセスできます。 [ここ](https://releases。groupdocs.com/).
### GroupDocs.Viewer for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。 [このリンク](https://purchase。groupdocs.com/temporary-license/).
### GroupDocs.Viewer for .NET のドキュメントはどこで見つかりますか?
包括的なドキュメントが利用可能 [ここ](https://tutorials。groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET ではどのようなサポート オプションが利用できますか?
コミュニティフォーラムから支援を求めることができます [ここ](https://forum。groupdocs.com/c/viewer/9).