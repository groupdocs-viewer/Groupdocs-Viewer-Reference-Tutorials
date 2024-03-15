---
title: 従量制ライセンスの設定
linktitle: 従量制ライセンスの設定
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer を使用して .NET アプリケーションを強化し、シームレスなドキュメント表示を実現します。ドキュメント レンダリング機能をプロジェクトに簡単に統合します。
type: docs
weight: 12
url: /ja/net/getting-started/set-metered-license/
---
## 導入
.NET 開発の世界では、ユーザー エクスペリエンスと機能を向上させるために、強力なドキュメント表示機能をアプリケーションに組み込むことが不可欠です。 GroupDocs.Viewer for .NET は、ドキュメント表示機能を .NET プロジェクトにシームレスに統合するための堅牢なソリューションを提供します。 PDF、Microsoft Office ドキュメント、またはさまざまな画像形式を扱う場合でも、GroupDocs.Viewer を使用すると、アプリケーション内でこれらのドキュメントをレンダリングおよび表示するプロセスが簡素化されます。
## 前提条件
GroupDocs.Viewer for .NET の実装に入る前に、次の前提条件が満たされていることを確認してください。
### 1. .NET 用の GroupDocs.Viewer をインストールします。
まず、GroupDocs.Viewer for .NET をダウンロードしてインストールする必要があります。ダウンロードリンクが見つかります[ここ](https://releases.groupdocs.com/viewer/net/)。提供されるインストール手順に従って、開発環境内にライブラリをセットアップします。
### 2. 従量制ライセンスの取得
GroupDocs.Viewer for .NET を利用するには、従量制ライセンスを取得する必要があります。このライセンスを使用すると、事前定義された割り当てに基づいて API 使用量を制御および監視できます。以下の手順に従って、従量制ライセンスを設定します。

## 名前空間のインポート
まず、GroupDocs.Viewer for .NET が提供する機能にアクセスするために必要な名前空間をインポートしていることを確認します。
```csharp
using System;
```

ここで、提供されているコード例を複数のステップに分けて見てみましょう。
## ステップ 1: 公開キーと秘密キーを宣言する
公開鍵と秘密鍵を保存する変数を宣言します。
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
必ず交換してください`"YOUR_PUBLIC_KEY"`そして`"YOUR_PRIVATE_KEY"`実際のキーを使用して。
## ステップ 2: 従量制ライセンスを設定する
公開キーが提供されているかどうかを確認します。そうでない場合は、ユーザーにキーを設定するように求めます。
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://Purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## ステップ 3: 従量制オブジェクトの初期化とライセンスの設定
従量制オブジェクトを初期化し、公開キーと秘密キーを使用して従量制ライセンスを設定します。
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## ステップ 4: 確認メッセージ
ライセンスが正常に設定されたことを示す確認メッセージを表示します。
```csharp
Console.WriteLine("License set successfully.");
```

## 結論
結論として、GroupDocs.Viewer for .NET は、ドキュメント表示機能を .NET アプリケーションに組み込むための包括的なソリューションを提供します。概要を説明した手順に従うことで、従量制ライセンスを簡単に設定し、プロジェクト内で GroupDocs.Viewer の機能を活用し始めることができます。
## よくある質問
### Q: GroupDocs.Viewer for .NET のドキュメントはどこで見つけられますか?
ドキュメントを見つけることができます[ここ](https://reference.groupdocs.com/viewer/net/).
### Q: GroupDocs.Viewer for .NET に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.groupdocs.com/).
### Q: テスト目的で一時ライセンスを取得するにはどうすればよいですか?
仮免許も取得できる[ここ](https://purchase.groupdocs.com/temporary-license/).
### Q: GroupDocs.Viewer for .NET に関連するサポートや質問はどこで受けられますか?
 GroupDocs.Viewer フォーラムでサポートを求めたり、質問したりできます。[ここ](https://forum.groupdocs.com/c/viewer/9).
### Q: GroupDocs.Viewer for .NET のライセンスはどこで購入できますか?
ライセンスを購入できます[ここ](https://purchase.groupdocs.com/buy).