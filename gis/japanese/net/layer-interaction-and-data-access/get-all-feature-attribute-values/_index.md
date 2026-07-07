---
date: 2026-06-15
description: Aspose.GIS for .NET を使用して C# で shapefile の属性値を読み取る方法を学び、すべてのフィーチャ属性を取得し、属性を効率的にダンプする方法をご紹介します。
keywords:
- read shapefile attribute values
- Aspose.GIS attribute extraction
- C# GIS tutorial
linktitle: すべてのフィーチャ属性値を取得
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to read shapefile attribute values in C# using Aspose.GIS
    for .NET, retrieve every feature attribute, and dump attributes efficiently.
  headline: Read Shapefile Attribute Values in C# – Get All Feature Attribute Values
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS fully supports .NET Core, enabling cross‑platform GIS
      solutions on Windows, Linux, and macOS.
    question: Is Aspose.GIS compatible with .NET Core?
  - answer: Absolutely. The library handles Shapefile, GeoJSON, KML, GML, CSV, and
      over 30 other formats without additional plugins.
    question: Can I work with different GIS file formats using Aspose.GIS?
  - answer: You can acquire a temporary license for evaluation [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for testing?
  - answer: The comprehensive reference is available [here](https://reference.aspose.com/gis/net/).
    question: Where is the official documentation for Aspose.GIS?
  - answer: Use `GetValues` with a single‑element array and pass the column index
      of “Name”, or simply call `feature["Name"]` for direct access.
    question: How do I retrieve only the “Name” attribute from each feature?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: C# で Shapefile の属性値を読み取る – すべてのフィーチャ属性値を取得
url: /ja/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# すべてのフィーチャ属性値を取得

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用した C# で **シェープファイルの属性値の読み取り方法** を学びます。ライブマッピングアプリケーションの構築、バルク空間分析の実行、または属性テーブルのエクスポートが必要な場合でも、シェープファイルからすべてのフィールドを抽出することは基本的なスキルです。データディレクトリの設定から属性コレクションのダンプまで、完全なワークフローを順に解説し、コードをクリーンで高性能に保つベストプラクティスのヒントも紹介します。

## クイック回答
- **このコードは何をしますか？** シェープファイルを開き、各フィーチャを反復処理し、すべての属性値または選択されたサブセットを取得します。  
- **必要なライブラリはどれですか？** Aspose.GIS for .NET（.NET Framework、.NET Core、.NET 5/6 で動作）。  
- **ライセンスは必要ですか？** テストには一時ライセンスで十分ですが、本番環境ではフルライセンスが必須です。  
- **他のフォーマットも読み取れますか？** はい。同じ API で GeoJSON、KML、GML、CSV、その他 30 以上の GIS フォーマットを読み取れます。  
- **属性をダンプするには？** `feature.GetValuesDump()` を呼び出すと、シリアライズや直接検査が可能な object 配列が取得できます。

## 「read shapefile C#」とは何ですか？
C# でシェープファイルを読み取るとは、GIS ライブラリで `.shp` ファイルを開き、ベクターフィーチャを反復処理し、付随する `.dbf` ファイルに格納された属性データにアクセスすることを意味します。Aspose.GIS は低レベルのファイル処理を抽象化し、数行のコードだけで属性値を抽出できるようにします。

## 属性を読み取るために Aspose.GIS を使用する理由は？
Aspose.GIS は高性能でクロスプラットフォームな API を提供し、シェープファイルからの属性抽出を簡素化します。**30 以上の GIS フォーマット**に対応し、標準的な 4 コアサーバー上で **1 秒あたり最大 500 000 フィーチャ** を処理できます。また、`GetValues` や `GetValuesDump` といった直感的なメソッドにより、手動での DBF パースが不要になります。Windows、Linux、macOS で追加プラグインなしに動作し、テスト用のライセンスフリー（テスト時）コードが必要な場合に最適です。

## 前提条件
- **Aspose.GIS for .NET** – [Aspose.GIS for .NET ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
- **開発環境** – Visual Studio 2022、Rider、または .NET 6+ をサポートする任意の IDE。  
- **サンプルシェープファイル** – `InputShapeFile.shp` などのファイルを、マシン上の既知のフォルダーに配置してください。  

## 名前空間のインポート
`Aspose.Gis` 名前空間には、`VectorLayer` や `Feature` などのコア GIS 型が含まれます。  
`VectorLayer` はシェープファイルなどのベクターデータセットを表し、`Feature` は個々の空間レコードを表します。  
```csharp
using System;
using Aspose.Gis;
```

## ステップ 1: ドキュメント ディレクトリの設定
シェープファイルが格納されているフォルダーを定義し、API が `.shp`、`.shx`、`.dbf` ファイルを見つけられるようにします。  
```csharp
string dataDir = "Your Document Directory";
```
“Your Document Directory” をシェープファイルが存在する実際のパスに置き換えてください。

## ステップ 2: VectorLayer を開く
`VectorLayer` はベクターデータセット（シェープファイル、GeoJSON など）を表します。これを開くと、すべてのジオメトリデータを読み込まずにスキーマがロードされ、メモリ使用量が抑えられます。  
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
このステップでは、ファイルパスとフォーマット（シェープファイル）を指定します。

## ステップ 3: すべてのフィーチャ属性値を取得する
`GetValues` は、事前に確保した配列にフィーチャの生の属性値を埋め込みます。このアプローチは、決定的で固定サイズの結果セットが必要な場合に最適です。  
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
このスニペットは、**すべての**フィーチャの属性を固定サイズの配列に読み込む方法を示しています。

## ステップ 4: 複数のフィーチャ属性値を取得する
フィールドのサブセットだけが必要な場合、より小さな配列を渡すか、列インデックスを使用して転送データを制限できます。これによりメモリオーバーヘッドが削減され、処理速度が向上します。  
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
ここでは、特定の属性値（例: “Name” と “Population”）を読み取る方法を示しています。

## ステップ 5: 属性値をオブジェクト ダンプとして取得する
`GetValuesDump` は、フィーチャのスキーマに一致するすべての属性値を含む `object[]` を返します。これにより、順序や型を事前に把握していなくてもフィールドを列挙できます。  
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
この最終ステップでは、デバッグやシリアライズのために属性をダンプする柔軟でスキーマ非依存の方法を示しています。

## よくある問題と解決策
- **配列サイズの不一致** – `GetValues` に渡す配列が期待する属性数と一致していることを確認してください。そうでないと `null` エントリが返ります。  
- **ファイルが見つかりません** – `dataDir` が正しいフォルダーを指しているか、シェープファイル名が `.shp` 拡張子を含めて正確に綴られているか確認してください。  
- **ライセンス例外** – ライセンスエラーが発生した場合、API メソッドを呼び出す前に一時ライセンスまたはフルライセンスを適用してください。

## よくある質問
**Q: Aspose.GIS は .NET Core と互換性がありますか？**  
A: はい、Aspose.GIS は .NET Core を完全にサポートしており、Windows、Linux、macOS 上でクロスプラットフォーム GIS ソリューションを実現します。

**Q: Aspose.GIS で異なる GIS ファイルフォーマットを扱えますか？**  
A: もちろんです。このライブラリはシェープファイル、GeoJSON、KML、GML、CSV、その他 30 以上のフォーマットを追加プラグインなしで処理できます。

**Q: テスト用の一時ライセンスはどこで取得できますか？**  
A: 評価用の一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

**Q: Aspose.GIS の公式ドキュメントはどこですか？**  
A: 包括的なリファレンスは[こちら](https://reference.aspose.com/gis/net/)で利用できます。

**Q: 各フィーチャから “Name” 属性だけを取得するには？**  
A: `GetValues` を単一要素の配列で使用し、“Name” の列インデックスを渡すか、直接 `feature["Name"]` を呼び出してください。

**Q: `GetValues` と `GetValuesDump` の違いは何ですか？**  
A: `GetValues` は事前に確保した配列に生の値を格納しますが、`GetValuesDump` はスキーマを事前に知らなくても列挙可能な `object[]` を返します。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose GIS の[サポートフォーラム](https://forum.aspose.com/c/gis/33)でコミュニティの支援や公式サポートを受けられます。

**最終更新日:** 2026-06-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## 関連チュートリアル

- [レイヤ属性の取得 – Aspose.GIS for .NET でレイヤ属性情報を取得する](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [属性値の取得方法（デフォルト） – Aspose.GIS for .NET を使用](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [シェープファイル C# の読み取り – Aspose.GIS で属性でフィーチャをフィルタリング](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}