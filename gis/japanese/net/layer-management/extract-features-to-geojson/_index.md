---
date: 2026-07-05
description: Aspose.GIS for .NET を使用して shapefile を geojson に変換する方法を学びます。このガイドでは、レイヤー間で属性をコピーする方法や、C#
  で geojson ファイルを生成する方法もカバーしています。
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: 機能を GeoJSON に抽出する
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して Shapefile を GeoJSON に変換する
url: /ja/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した Shapefile の GeoJSON への変換

## はじめに
この包括的なステップバイステップのチュートリアルでは、強力な Aspose.GIS ライブラリ for .NET を使用して **shapefile を geojson に変換する方法** を学びます。マッピング Web サービスを構築する場合、モバイル GIS アプリ用にデータを準備する場合、または単にフォーマット間でデータをやり取りする必要がある場合でも、本ガイドは具体的な手順、各ステップの重要性、一般的な落とし穴の回避方法を示します。

## クイック回答
- **このチュートリアルの対象は何ですか？** Shapefile を GeoJSON ファイルに変換し、レイヤー間で属性をコピーし、C# で出力を生成します。
- **必要なライブラリはどれですか？** Aspose.GIS for .NET。
- **ライセンスは必要ですか？** 本番環境では一時ライセンスまたはフルライセンスが必要です。評価目的は無料トライアルで動作します。
- **実装にどれくらい時間がかかりますか？** 基本的な変換で約 10〜15 分です。
- **.NET Core/.NET 6 で実行できますか？** はい – コードはすべてのサポート対象 .NET バージョンで動作します。

## Shapefile を GeoJSON に変換するとは何ですか？
Shapefile を GeoJSON に変換するとは、従来の ESRI Shapefile 形式からベクトルフィーチャを読み取り、最新の Web フレンドリーな GeoJSON ドキュメントとして書き出すことを意味します。この変換により、Leaflet や Mapbox GL などの JavaScript マッピングライブラリに GIS データを直接供給でき、デスクトップ GIS ツールと Web API 間のデータ交換が簡素化されます。

## なぜこの変換に Aspose.GIS を使用するのか？
Aspose.GIS は低レベルのバイナリ解析を抽象化し、50 以上の入力・出力フォーマットをサポートします。また、ファイル全体をメモリに読み込むことなく数百ページ規模のデータセットを処理でき、.NET Framework、.NET Core、.NET 5/6 で共通のオブジェクト指向 API を提供します。これにより、フォーマット固有の問題に時間を取られることなくビジネスロジックに集中できます。

## 前提条件
- Aspose.GIS for .NET: ライブラリがインストールされていることを確認してください。未インストールの場合は、[Aspose.GIS for .NET ページ](https://releases.aspose.com/gis/net/)からダウンロードできます。
- Shapefile データ: 入力用の Shapefile を用意してください。サンプルデータが必要な場合は、[Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/)で入手できます。
- .NET 環境: 提供されたコードを実行できる .NET 環境をセットアップしてください。
- ドキュメントディレクトリ: コードスニペット内でドキュメントディレクトリへのパスを定義します。

これで準備が整ったので、shapefile を geojson に変換し始めましょう！

## Shapefile を GeoJSON に変換する方法
ソース Shapefile を読み込み、ターゲット GeoJSON レイヤーを作成し、属性スキーマをコピーし、レコードをフィルタリングして結果を書き出す—すべてを数行の簡潔なコードで実現できます。完全なワークフローは単一の `using` ブロックに収まり、リソースは自動的に解放されます。

### 手順 1: 入力 Shapefile を開く
`VectorLayer.Open` メソッドは Shapefile を読み取り、反復可能な `Feature` オブジェクトのコレクションを返します。

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### 手順 2: 出力 GeoJSON を作成する
`Drivers.GeoJson` ドライバを指定して `VectorLayer.Create` を呼び出すと、フィーチャを受け取る準備ができた空の GeoJSON ファイルが作成されます。

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### 手順 3: レイヤー間で属性をコピーする
`CopyAttributes` は、ソース Shapefile から新しい GeoJSON レイヤーへ属性スキーマ（フィールド名とデータ型）を一括でコピーします。

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### 手順 4: フィーチャを処理する
Shapefile の各フィーチャを反復処理し、書き出す前に任意のカスタムロジックを適用できます。

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### 手順 5: 日付でフィーチャをフィルタリングする
この例では、`dob`（生年月日）フィールドが欠落しているか 1982 年 1 月 1 日以前のレコードをスキップします。フィルタはご自身のデータ要件に合わせて調整してください。

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### 手順 6: 新しいフィーチャを構築する (C# で GeoJSON ファイルを生成)
`Feature` はジオメトリと属性データを含む単一の空間要素を表します。  
ここでは GeoJSON レイヤー用に新しい `Feature` を作成し、ジオメトリと属性値をコピーして出力に追加します。これが *c# generate geojson file* の核心です。

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

おめでとうございます！ **shapefile を geojson に変換する** に成功し、途中で **レイヤー間で属性をコピーする** 方法も習得しました。

## よくある問題と解決策
| 問題 | 発生理由 | 対策 |
|------|----------|------|
| 出力ファイルが空 | `CopyAttributes` を出力レイヤーが閉じた後に呼び出している | `outputLayer` の `using` ブロックを、すべてのフィーチャを追加した後まで開いたままにしてください。 |
| 日付フィルタで全レコードが除外される | フィールド名が間違っている、または日付形式が予期せぬもの | 属性名 (`dob`) を確認し、日付が文字列として保存されている場合は `GetValue<string>` を使用してください。 |
| ライセンス例外 | 本番環境で有効な Aspose.GIS ライセンスなしで実行している | Aspose のドキュメントに記載の手順で、一時またはフルライセンスを適用してください。 |

## よくある質問
**Q: さらに詳しいドキュメントはどこで見つけられますか？**  
A: 詳細情報は [Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/)をご覧ください。

**Q: 一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

**Q: サポートはどこで受けられますか？**  
A: コミュニティサポートやディスカッションは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)に参加してください。

**Q: 無料トライアルはありますか？**  
A: はい、無料トライアルは [こちら](https://releases.aspose.com/)で入手できます。

**Q: Aspose.GIS for .NET はどこで購入できますか？**  
A: 製品は [こちら](https://purchase.aspose.com/buy)から購入できます。

## 結論
本チュートリアルでは Aspose.GIS for .NET を使用した **shapefile を geojson に変換する** 完全なプロセスを解説し、**レイヤー間で属性をコピーする** 方法と *c# generate geojson file* の実装例を示しました。さまざまなフィルタや大規模データセット、追加のジオメトリ変換を試して、ライブラリの機能を最大限に活用してください。

---

**最終更新日:** 2026-07-05  
**テスト環境:** Aspose.GIS for .NET (latest stable release)  
**作者:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 関連チュートリアル

- [Aspose.GIS for .NET を使用した GeoJSON を File GDB に変換する方法](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Aspose.GIS for .NET でストリームから GeoJSON を読み取る方法](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS で GeoJSON を TopoJSON に変換する方法](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}