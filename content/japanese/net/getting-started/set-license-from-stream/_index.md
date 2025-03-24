---
title: ストリームからライセンスを設定
linktitle: ストリームからライセンスを設定
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer を使用して .NET アプリケーションを強化し、シームレスなドキュメント表示を実現します。ステップバイステップのガイドに従って、強力なドキュメント表示機能を簡単に統合します。
weight: 11
url: /ja/net/getting-started/set-license-from-stream/
---
## 導入
.NET アプリケーションに高度なドキュメント表示機能を強化したいと考えていますか? GroupDocs.Viewer for .NET は、ドキュメント表示機能をプロジェクトにシームレスに統合するための包括的なソリューションを提供します。このチュートリアルでは、GroupDocs.Viewer for .NET を活用して強力なドキュメント表示機能でアプリケーションを強化するプロセスを詳しく説明します。 
## 前提条件
統合プロセスに入る前に、次の前提条件が満たされていることを確認してください。
1. .NET 開発の基本知識: このチュートリアルを進めるには、C# および .NET Framework に精通していることが不可欠です。
   
2.  GroupDocs.Viewer for .NET パッケージ: GroupDocs.Viewer for .NET パッケージをダウンロードしてインストールしていることを確認してください。から入手できます。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).
3.  GroupDocs ドキュメントへのアクセス:[ドキュメンテーション](https://tutorials.groupdocs.com/viewer/net/)統合プロセス中の参照に便利です。

## 名前空間のインポート
まず、必要な名前空間を .NET アプリケーションにインポートします。次の手順を実行します：
### ステップ 1: .NET プロジェクトを開きます。
.NET プロジェクトが優先開発環境で開かれていることを確認してください。
### ステップ 2: GroupDocs.Viewer 名前空間を追加します。
コード ファイルに次の名前空間を追加して、GroupDocs.Viewer 機能にアクセスします。
```csharp
using System;
using System.IO;
```
## ストリームからライセンスを設定
次のステップでは、ストリームからライセンスを設定します。次の詳細な手順に従ってください。
### ステップ 1: 出力ディレクトリを定義します。
出力ディレクトリを定義して、ドキュメントを保存するディレクトリを設定します。
```csharp
string outputDirectory = "Your Document Directory";
```
### ステップ 2: ライセンス ファイルの存在を確認します。
ライセンス ファイルがプロジェクト ディレクトリに存在するかどうかを確認します。
```csharp
if (File.Exists(Utils.LicensePath))
```
### ステップ 3: ライセンスを設定します。
ライセンス ファイルが存在する場合は、提供されたストリームを使用してライセンスを設定します。
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### ステップ 4: ライセンスの不在を処理します。
ライセンス ファイルが見つからない場合は、ライセンスを取得するための手順を指定します。
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://Purchase.groupdocs.com/faqs/licensing。 " +
                      "\nLearn how to request a temporary license at https://Purchase.groupdocs.com/temporary-license.");
}
```

## 結論
おめでとう！ GroupDocs.Viewer for .NET をアプリケーションに統合する方法を学習しました。この強力なツールを使用すると、.NET プロジェクト内のさまざまなドキュメント形式を簡単に表示できるようになり、ユーザー エクスペリエンスと生産性が向上します。
## よくある質問
### GroupDocs.Viewer for .NET を使用するにはライセンスが必要ですか?
はい、GroupDocs.Viewer for .NET を使用するにはライセンスが必要です。 GroupDocs Web サイトから一時ライセンスまたは永久ライセンスを取得できます。
### GroupDocs.Viewer を ASP.NET アプリケーションに統合できますか?
絶対に！ GroupDocs.Viewer for .NET は、デスクトップと Web アプリケーション (ASP.NET を含む) の両方にシームレスに統合します。
### GroupDocs.Viewer ではどのドキュメント形式がサポートされていますか?
GroupDocs.Viewer は、PDF、Microsoft Office (Word、Excel、PowerPoint)、画像などを含む幅広いドキュメント形式をサポートしています。
### GroupDocs.Viewer は .NET Core と互換性がありますか?
はい、GroupDocs.Viewer for .NET は .NET Framework と .NET Core の両方と互換性があります。
### アプリケーションのテーマに応じてビューア インターフェイスをカスタマイズできますか?
はい、GroupDocs.Viewer には広範なカスタマイズ オプションが用意されており、アプリケーションのテーマにシームレスに一致するようにビューア インターフェイスを調整できます。