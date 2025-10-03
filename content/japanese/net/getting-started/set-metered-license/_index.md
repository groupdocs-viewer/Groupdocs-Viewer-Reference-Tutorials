---
"description": "GroupDocs.Viewer で .NET アプリケーションを強化し、シームレスなドキュメント表示を実現します。ドキュメントレンダリング機能をプロジェクトに簡単に統合できます。"
"linktitle": "従量制ライセンスの設定"
"second_title": "GroupDocs.Viewer .NET API"
"title": "従量制ライセンスの設定"
"url": "/ja/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# 従量制ライセンスの設定

## 導入
.NET開発の世界では、強力なドキュメント表示機能をアプリケーションに組み込むことが、ユーザーエクスペリエンスと機能性の向上に不可欠です。GroupDocs.Viewer for .NETは、ドキュメント表示機能を.NETプロジェクトにシームレスに統合するための堅牢なソリューションを提供します。PDF、Microsoft Officeドキュメント、さまざまな画像形式を扱う場合でも、GroupDocs.Viewerはアプリケーション内でこれらのドキュメントをレンダリングおよび表示するプロセスを簡素化します。

![GroupDocs.Viewer for .NET で従量制ライセンスを設定する](/viewer/getting-started/set-metered-license.png)

## 前提条件
GroupDocs.Viewer for .NET の実装に進む前に、次の前提条件が満たされていることを確認してください。
### 1. GroupDocs.Viewer for .NETをインストールする
まず、GroupDocs.Viewer for .NETをダウンロードしてインストールする必要があります。ダウンロードリンクは以下にあります。 [ここ](https://releases.groupdocs.com/viewer/net/)提供されているインストール手順に従って、開発環境内でライブラリをセットアップします。
### 2. 従量制ライセンスを取得する
GroupDocs.Viewer for .NET を利用するには、従量制ライセンスを取得する必要があります。このライセンスでは、事前定義されたクォータに基づいて API の使用量を制御および監視できます。従量制ライセンスを設定するには、以下の手順に従ってください。

## 名前空間のインポート
まず、GroupDocs.Viewer for .NET によって提供される機能にアクセスするために必要な名前空間をインポートしていることを確認します。
```csharp
using System;
```

ここで、提供されているサンプル コードを複数のステップに分解してみましょう。
## ステップ1: 公開鍵と秘密鍵を宣言する
公開鍵と秘密鍵を保存する変数を宣言します。
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
必ず交換してください `"YOUR_PUBLIC_KEY"` そして `"YOUR_PRIVATE_KEY"` 実際のキーを使用します。
## ステップ2: 従量制ライセンスを設定する
公開鍵が提供されているかどうかを確認します。提供されていない場合は、ユーザーに鍵の設定を促します。
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## ステップ3: 計測対象オブジェクトを初期化し、ライセンスを設定する
Metered オブジェクトを初期化し、公開キーと秘密キーを使用して従量制ライセンスを設定します。
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## ステップ4: 確認メッセージ
ライセンスが正常に設定されたことを示す確認メッセージを表示します。
```csharp
Console.WriteLine("License set successfully.");
```

## 結論
結論として、GroupDocs.Viewer for .NETは、.NETアプリケーションにドキュメント表示機能を組み込むための包括的なソリューションを提供します。概要に示された手順に従うだけで、従量制ライセンスを簡単に設定し、プロジェクト内でGroupDocs.Viewerの機能を活用し始めることができます。
## よくある質問
### Q: GroupDocs.Viewer for .NET のドキュメントはどこで入手できますか?
ドキュメントは以下にあります [ここ](https://tutorials。groupdocs.com/viewer/net/).
### Q: GroupDocs.Viewer for .NET の無料試用版はありますか?
はい、無料トライアルにアクセスできます [ここ](https://releases。groupdocs.com/).
### Q: テスト目的で一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスを取得できる [ここ](https://purchase。groupdocs.com/temporary-license/).
### Q: GroupDocs.Viewer for .NET に関するサポートや質問はどこで受けられますか?
GroupDocs.Viewerフォーラムでサポートを求めたり質問したりできます [ここ](https://forum。groupdocs.com/c/viewer/9).
### Q: GroupDocs.Viewer for .NET のライセンスはどこで購入できますか?
ライセンスを購入することができます [ここ](https://purchase。groupdocs.com/buy).