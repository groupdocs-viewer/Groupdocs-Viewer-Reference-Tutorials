---
title: ドキュメントをJPGPNGにレンダリング
linktitle: ドキュメントをJPGPNGにレンダリング
second_title: GroupDocs.Viewer .NET API
description: ユーザー エクスペリエンスと生産性を向上させるために、GroupDocs.Viewer を使用して .NET でドキュメントを JPG/PNG にシームレスにレンダリングする方法を説明します。
weight: 10
url: /ja/net/rendering-documents-images/render-jpg-png/
---
## 導入

.NET 開発の世界では、ドキュメントを効率的に処理することがさまざまなアプリケーションにとって不可欠です。ドキュメント管理システム、電子商取引プラットフォーム、コンテンツ豊富なアプリケーションのいずれを構築している場合でも、ドキュメントをシームレスに表示できる機能は非常に重要です。ここで GroupDocs.Viewer for .NET が活躍し、JPG や PNG などのさまざまな形式でドキュメントをレンダリングするための包括的なソリューションを提供します。

## 前提条件

GroupDocs.Viewer for .NET の使用に入る前に、確認する必要がある前提条件がいくつかあります。

1. .NET 開発環境: マシン上に動作する .NET 開発環境がセットアップされていることを確認します。これには、.NET SDK のインストールが含まれます。

2. GroupDocs.Viewer ライセンス: GroupDocs.Viewer の有効なライセンスを取得します。ライセンスを購入することも、評価目的で一時的なライセンスを使用することもできます。

3. インストール: 提供されているから GroupDocs.Viewer for .NET をダウンロードしてインストールします。[ダウンロードリンク](https://releases.groupdocs.com/viewer/net/).

4. ドキュメント ファイル: レンダリングするドキュメント ファイルを準備します。 GroupDocs.Viewer は、DOCX、PDF、PPT などのさまざまな形式をサポートしています。

## 名前空間のインポート

GroupDocs.Viewer for .NET を使用してドキュメントのレンダリングを開始するには、必要な名前空間をプロジェクトにインポートする必要があります。これにより、ライブラリが提供する機能にアクセスできるようになります。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

GroupDocs.Viewer for .NET を使用すると、ドキュメントを JPG または PNG 形式でレンダリングする簡単なプロセスになります。以下は、これを達成するためのステップバイステップのガイドです。

## ステップ 1: 出力ディレクトリを定義する

まず、レンダリングされたページを保存するディレクトリを定義します。このディレクトリは存在し、アプリケーションからアクセスできる必要があります。

```csharp
string outputDirectory = "Your Document Directory";
```

## ステップ 2: ページ ファイルのパス形式を定義する

レンダリングされた各ページのファイル パスの形式を指定します。 GroupDocs.Viewer が置き換えられます`{0}`ファイルを保存するときにページ番号を付けます。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## ステップ 3: Viewer オブジェクトをインスタンス化する

のインスタンスを作成します。`Viewer`レンダリングするドキュメント ファイルへのパスを指定してクラスを作成します。

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    //レンダリング用のコードはここにあります
}
```

## ステップ 4: レンダリング オプションを定義する

要件に応じてレンダリング オプションを指定します。 JPG/PNG レンダリングの場合は、次を使用します。`JpgViewOptions`または`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## ステップ 5: ドキュメントをレンダリングする

を呼び出します。`View`の方法`Viewer`オブジェクトを作成し、前に作成したレンダリング オプションを渡します。

```csharp
viewer.View(options);
```

## ステップ 6: 結果を出力する

レンダリング プロセスが完了したら、レンダリングが成功したことをユーザーに通知し、レンダリングされたページが保存されるディレクトリを提供できます。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 結論

結論として、GroupDocs.Viewer for .NET は、JPG や PNG などのさまざまな形式でドキュメントをレンダリングするための強力なソリューションを提供します。このチュートリアルで概説されている手順に従うことで、ドキュメント レンダリング機能を .NET アプリケーションにシームレスに統合し、ユーザー エクスペリエンスと生産性を向上させることができます。

## よくある質問

### Q: GroupDocs.Viewer for .NET を使用して DOCX 以外のドキュメントをレンダリングできますか?

A: はい、GroupDocs.Viewer は、PDF、PPT、XLS などを含む幅広いドキュメント形式をサポートしています。

### Q: GroupDocs.Viewer for .NET に利用できる無料トライアルはありますか?

 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.groupdocs.com/).

### Q: 評価目的で一時ライセンスを取得するにはどうすればよいですか?

A: 一時ライセンスは次のサイトからリクエストできます。[ここ](https://purchase.groupdocs.com/temporary-license/).

### Q: GroupDocs.Viewer for .NET のドキュメントはどこで見つけられますか?

 A: 詳細なドキュメントが入手可能です[ここ](https://tutorials.groupdocs.com/viewer/net/).

### Q: GroupDocs.Viewer for .NET に関連するサポートや質問はどこで受けられますか?

 A: サポート フォーラムにアクセスしてください。[ここ](https://forum.groupdocs.com/c/viewer/9)援助のために。