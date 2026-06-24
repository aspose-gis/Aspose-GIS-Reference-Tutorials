---
date: 2026-05-31
description: Aspose.GIS for .NET を使用してジオメトリを書き込む際に精度を制限し、GeoJSON のサイズを削減し、座標の制御を保つ方法を学びます。
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: 精度を制限したジオメトリの書き込み
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Aspose.GIS を使用したジオメトリの書き込み時に精度を制限する方法
url: /ja/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用したジオメトリの精度制限書き込み方法

もし **精度を制限する方法** をお探しなら、Aspose.GIS for .NET は座標の丸めを制御するシンプルで高性能な方法を提供します。このチュートリアルでは、環境設定から出力が定義した精度ルールを遵守しているかの検証まで、全工程を順に解説します。

## クイック回答
- **“limit precision” とは何ですか？** 空間ファイルを書き込む際に、座標値を定義された小数桁数に丸めます。  
- **例で使用されているフォーマットは何ですか？** GeoJSON ですが、同じオプションは他のサポートされているフォーマットにも適用できます。  
- **これを試すのにライセンスは必要ですか？** 開発・テスト用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **Z 座標の精度を個別に制御できますか？** はい。`ZPrecisionModel` を使用して、正確な値または丸めた値を設定できます。

## ジオメトリを書き込む際の精度制限方法

目的の X/Y および Z の精度を指定した `GeoJsonOptions` オブジェクトで GeoJSON ライターをロードし、ジオメトリを書き込んでから読み戻します。この一連の作業はコード10行未満で収まり、すべての座標が定義通りに正確に丸められることが保証されます。

異なる GIS ツール間で一貫した座標表現が必要な場合や、ファイルサイズを削減したい場合、データ交換標準に準拠する必要がある場合など、精度の制限は重要です。以下では、精度オプションを定義し、ジオメトリを書き込み、丸めが正しく行われたことを確認するために読み戻します。

## 精度制限とは何か

精度制限とは、ジオメトリをファイル形式に保存する前に、座標値の小数部分を固定桁数に丸めるプロセスです。これにより、ファイルのすべての利用者が同じ数値を参照でき、トポロジーエラーを引き起こすような微小な不一致を防止します。

## 精度制御に Aspose.GIS を使用する理由

Aspose.GIS は **50 以上** の入出力フォーマット（GeoJSON、Shapefile、KML、GML など）をサポートし、**数十万のフィーチャ** を含むファイルでもデータ全体をメモリに読み込むことなく処理できます。組み込みの精度モデルにより、座標をワンコールで丸めることができ、手動のポストプロセススクリプトが不要になります。

## 前提条件

### 1. ダウンロードとインストール
公式サイトから最新の Aspose.GIS for .NET パッケージを取得してください: [ダウンロードリンク](https://releases.aspose.com/gis/net/)。インストールガイドに従って NuGet パッケージをプロジェクトに追加します。

### 2. 名前空間のインポート
必要な名前空間を追加し、GIS クラスやヘルパーユーティリティにアクセスできるようにします。

## ステップバイステップガイド

### 手順 1: 精度オプションの定義
`GeoJsonOptions` クラスを使用すると、X/Y および Z 座標の小数桁数を指定できます。

`PrecisionModel` は、書き込み時に座標値をどのように丸めるか、または正確に保持するかを定義します。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 手順 2: 出力パスの設定
生成される GeoJSON ファイルの保存先を指定します。

`VectorLayer` は、同一スキーマを共有するフィーチャのコレクションを保持する Aspose.GIS のコンテナで、先に設定したオプションを使用して指定したパスに書き込みます。  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### 手順 3: ジオメトリの作成と配置
上記で定義したオプションを使用して新しい `VectorLayer` を開き、`Point` ジオメトリを作成し、レイヤーに追加します。

`Point` は空間参照系における単一の座標 (X, Y、オプションで Z) を表します。最もシンプルなジオメトリタイプで、ここでは精度の丸めを示すために使用します。  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### 手順 4: 精度の読み取りと検証
作成したファイルを開き、座標を出力します。X/Y の値は小数第3位まで丸められ、Z の値はそのまま正確に保持されているはずです。

ファイルを再度読み込むと、Aspose.GIS は丸められた値を直接解析するため、メモリ上の `Point` は書き込み時に定義した精度を反映します。  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## よくある問題とヒント

- **パスエラー:** `path` のディレクトリが存在することを確認するか、`Path.Combine` と `Environment.CurrentDirectory` を使用して安全なファイルパスを構築してください。  
- **精度が適用されない:** レイヤー作成時に `GeoJsonOptions` オブジェクトを渡しているか確認してください。渡さない場合、デフォルトの精度（フル double）が使用されます。  
- **大規模データセット:** バルク操作の場合、単一の `VectorLayer` インスタンスを再利用し、フィーチャをバッチで追加することでパフォーマンスを向上させることを検討してください。

## よくある質問

**Q: Aspose.GIS for .NET は他の GIS フォーマットと互換性がありますか？**  
A: はい、**50 以上** のフォーマット（Shapefile、GeoJSON、KML、GML、CSV など）をサポートしており、シームレスに相互変換できます。

**Q: 購入前に Aspose.GIS for .NET を試すことはできますか？**  
A: もちろんです。ダウンロードページから無料トライアルが利用でき、評価のためにすべての機能にフルアクセスできます。

**Q: テスト用の一時ライセンスはどう取得しますか？**  
A: Aspose のライセンスポータルで一時評価ライセンスを生成でき、30 日間有効です。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose.GIS フォーラムや Stack Overflow のタグ `aspose-gis` が質問やコミュニティによる解決策を得るのに適しています。

**Q: このライブラリは小規模スクリプトからエンタープライズ規模のアプリケーションまで対応していますか？**  
A: はい、Aspose.GIS は迅速なプロトタイプから高スループットのサーバーワークロードまで対応できるよう設計されており、数ギガバイト規模のデータセットも低メモリオーバーヘッドで処理できます。

---

**最終更新日:** 2026-05-31  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET でベクターレイヤーを作成し、精度を制限する](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [GeoJSON の変換方法 – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [ジオメトリのチェック方法 – Aspose.GIS for .NET](/gis/net/geometry-analysis/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}