---
additionalTitle: GroupDocs API References
date: 2025-12-15
description: GroupDocs.Viewer を使用してドキュメントに透かしを追加し、PDF .NET ファイルをレンダリングする方法を学びましょう。.NET
  と Java で 170 以上のフォーマットの閲覧をマスターしてください。
is_root: true
linktitle: GroupDocs.Viewer Tutorials
title: GroupDocs.Viewer チュートリアルで文書にウォーターマークを追加
type: docs
url: /ja/
weight: 11
---

# GroupDocs.Viewer チュートリアル

GroupDocs.Viewer チュートリアルハブへようこそ。ここでは、**add watermark document** を支援し、.NET と Java 用の強力なドキュメントビューア API をマスターするための包括的なチュートリアルとガイドを見つけることができます。Web アプリケーション、デスクトップアプリ、モバイルソリューションのいずれを構築していても、GroupDocs.Viewer は PDF、Microsoft Office（Word、Excel、PowerPoint）、CAD、画像など、さまざまなドキュメント形式をシームレスにレンダリングおよび表示できます。

## クイック回答
- **What does “add watermark document” mean?** それは、レンダリングされたドキュメントの各ページに半透明のテキストまたは画像のオーバーレイを埋め込むことを指します。  
- **Which formats support watermarks?** GroupDocs.Viewer がレンダリングするすべての形式、PDF、DOCX、XLSX、CAD、メールメッセージなどがサポートします。  
- **Do I need a license?** 本番環境で使用するには有効な GroupDocs.Viewer ライセンスが必要です。無料トライアルも利用可能です。  
- **Can I combine watermarks with other features?** はい。ウォーターマークはキャッシュ、カスタムレンダリング、セキュリティ設定と組み合わせて適用できます。  
- **Is it compatible with .NET Core?** もちろんです。GroupDocs.Viewer は .NET Framework、.NET Core、.NET 5/6 以降でも動作します。

## GroupDocs.Viewer for .NET チュートリアル

{{% alert color="primary" %}}
高精細なドキュメント閲覧機能で .NET アプリケーションを強化しましょう。GroupDocs.Viewer for .NET のチュートリアルでは、強力なドキュメントビューアを統合するために必要なすべてを提供します。170 以上のドキュメント形式を HTML、JPEG、PNG、PDF にレンダリングする方法を学びます。CAD 図面の特定レイアウトのレンダリング、ドキュメント添付ファイルの処理、パフォーマンス最適化などの高度なトピックも探求できます。C#、ASP.NET、その他の .NET フレームワークで、堅牢でプロフェッショナルなドキュメント閲覧体験を構築し始めましょう。
{{% /alert %}}

These are links to some useful .NET resources:
 
- [ドキュメントの読み込み](./net/loading-documents/)
- [高度な読み込みオプション](./net/advanced-loading/)
- [高度な使用（キャッシュ）](./net/advanced-usage-caching/)
- [レンダリングオプション](./net/rendering-options/)
- [アーカイブファイルのレンダリング](./net/rendering-archive-files/)
- [CAD 図面のレンダリング](./net/rendering-cad-drawings/)
- [はじめに](./net/getting-started/)
- [メールメッセージのレンダリング](./net/rendering-email-messages/)
- [画像レンダリング](./net/image-rendering/)
- [ドキュメントを PDF にレンダリング](./net/rendering-documents-pdf/)
- [ドキュメントを画像にレンダリング](./net/rendering-documents-images/)
- [ドキュメントを HTML にレンダリング](./net/rendering-documents-html/)
- [ドキュメント添付ファイルの処理](./net/processing-document-attachments/)
- [テキストファイルのレンダリング](./net/rendering-text-files/)
- [Visio ドキュメントのレンダリング](./net/rendering-visio-documents/)
- [Web ドキュメントのレンダリング](./net/rendering-web-documents/)
- [ワードプロセッシングドキュメントのレンダリング](./net/rendering-word-processing-documents/)
- [スプレッドシートレンダリングオプション](./net/spreadsheet-rendering-options/)
- [PDF レンダリングオプション](./net/pdf-rendering-options/)
- [Outlook データファイル（PST、OST）のレンダリング](./net/rendering-outlook-data-files/)
- [Microsoft Project ドキュメントのレンダリング](./net/rendering-ms-project-documents/)
- [ドキュメントの読み込み](./net/document-loading/)
- [レンダリングの基本](./net/rendering-basics/)
- [高度なレンダリング](./net/advanced-rendering/)
- [パフォーマンス最適化](./net/performance-optimization/)
- [セキュリティと権限](./net/security-permissions/)
- [ウォーターマークと注釈](./net/watermarks-annotations/)
- [ファイル形式のサポート](./net/file-formats-support/)
- [クラウドおよびリモートドキュメントレンダリング](./net/cloud-remote-document-rendering/)
- [キャッシュとリソース管理](./net/caching-resource-management/)
- [メタデータとプロパティ](./net/metadata-properties/)
- [エクスポートと変換](./net/export-conversion/)
- [カスタムレンダリング](./net/custom-rendering/)

## GroupDocs.Viewer でウォーターマークドキュメントを追加する方法

ウォーターマークの追加は、ブランド化、機密保持、または規制遵守のためにしばしば必要です。GroupDocs.Viewer を使用すると、ドキュメントを HTML、PDF、画像形式にレンダリングする際にウォーターマークを適用できます。手順は簡単です：

1. **Create a `WatermarkOptions` object** とテキスト、色、不透明度、回転を設定します。  
2. **Pass the options** を適切なレンダリングメソッド（例: `RenderToPdf`、`RenderToHtml`、`RenderToImage`）に渡します。  
3. **Render the document** — 出力にはすべてのページにウォーターマークが含まれます。

このアプローチは、**render pdf .net** シナリオ、CAD 図面、メールメッセージなど、すべてのサポート対象ファイルタイプで機能します。

## GroupDocs.Viewer for Java チュートリアル

{{% alert color="primary" %}}
GroupDocs.Viewer for Java を使用して、Java アプリケーションに多用途で効率的なドキュメントビューアを統合しましょう。チュートリアルでは、環境設定から高度なレンダリング機能の実装まで、すべてのステップを案内します。マルチレイアウト CAD ファイルやパスワード保護されたアーカイブなど、複雑なドキュメントを含む多数のファイル形式の表示方法を学びます。例に従ってドキュメントを HTML5、画像、PDF にレンダリングし、クロスプラットフォームのドキュメント閲覧を簡単に実現できます。
{{% /alert %}}

These are links to some useful Java resources:

- [はじめに](./java/getting-started/)
- [ドキュメントの読み込み](./java/document-loading/)
- [レンダリングの基本](./java/rendering-basics/)
- [高度なレンダリング](./java/advanced-rendering/)
- [パフォーマンス最適化](./java/performance-optimization/)
- [セキュリティと権限](./java/security-permissions/)
- [ウォーターマークと注釈](./java/watermarks-annotations/)
- [ファイル形式のサポート](./java/file-formats-support/)
- [クラウドおよびリモートドキュメントレンダリング](./java/cloud-remote-document-rendering/)
- [キャッシュとリソース管理](./java/caching-resource-management/)
- [メタデータとプロパティ](./java/metadata-properties/)
- [エクスポートと変換](./java/export-conversion/)
- [カスタムレンダリング](./java/custom-rendering/)

## よくある質問

**Q: 画像としてレンダリングされたドキュメントにウォーターマークを追加できますか？**  
A: はい。`WatermarkOptions` を `RenderToImage` と組み合わせて使用し、生成された各画像ページにウォーターマークを埋め込むことができます。

**Q: ウォーターマークの追加はレンダリング性能に影響しますか？**  
A: 影響は最小限です。GroupDocs.Viewer はオーバーレイ処理を最適化しており、特にキャッシュと組み合わせた場合に効果的です。

**Q: メールメッセージのレンダリング時にウォーターマークはサポートされていますか？**  
A: もちろんです。レンダリングされたメールメッセージの HTML または PDF 出力にウォーターマークを適用できます。

**Q: ウォーターマークの外観をカスタマイズするには？**  
A: フォントファミリー、サイズ、色、不透明度、回転角度を設定でき、画像をウォーターマークとして使用することも可能です。

**Q: ページごとに異なるウォーターマークを適用できますか？**  
A: 標準 API は均一なウォーターマークを適用しますが、カスタムレンダリングロジックを実装すればページごとに異なるウォーターマークを設定できます。

**最終更新日:** 2025-12-15  
**テスト環境:** GroupDocs.Viewer 23.11 for .NET & Java  
**作者:** GroupDocs