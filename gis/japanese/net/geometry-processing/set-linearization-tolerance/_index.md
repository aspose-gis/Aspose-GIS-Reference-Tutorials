---
date: 2026-05-31
description: Aspose.GIS for .NET を使用して GeoJSON を作成し、GeoJSON オプションを設定し、レイヤーにフィーチャを追加する方法を学びます。ステップバイステップのガイドに従ってください。
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Linearization Tolerance の設定
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用した許容範囲付き GeoJSON の作成方法
url: /ja/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET でトレランスを設定して GeoJSON を作成する方法

## はじめに
GeoJSON ファイルの **作成方法** を学び、曲線の精度を制御し、結果をすぐに使用できるドキュメントとしてエクスポートしたい場合、Aspose.GIS for .NET を使用すれば簡単です。このチュートリアルでは、GeoJSON オプションの設定方法、線形化トレランスの設定方法、そしてコードをクリーンで本番環境向けに保ちながら **add feature to layer** オブジェクトを追加する方法を紹介します。

## クイック回答
- **“create vector layer” とは何ですか？** 新しい GIS ベクターデータセット（例: GeoJSON ファイル）を作成し、ジオメトリと属性を格納できるようにします。  
- **線形化トレランスはどう設定しますか？** レイヤーを作成する前に、`GeoJsonOptions` インスタンスの `LinearizationTolerance` プロパティを設定します。  
- **GeoJSON ファイルを直接エクスポートできますか？** はい。`VectorLayer.Create` を `Drivers.GeoJson` ドライバーと設定したオプションと共に使用します。  
- **ライセンスは必要ですか？** 有効な Aspose.GIS ライセンスを取得するとすべての機能が利用可能になります。評価用の一時キーでもテストは可能です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## “create vector layer” とは何ですか？
ベクターレイヤーを作成することは、ポイント、ライン、ポリゴン、および関連する属性データを保持できる新しい GIS コンテナ（例: GeoJSON ファイル）を初期化することを意味します。このレイヤーは、作成するすべてのジオメトリと付加するすべての属性の対象となります。

## なぜ GeoJSON オプションを設定するのか？
GeoJSON オプション、特に **linearization tolerance** を設定することで、曲線ジオメトリ（例: `CircularString`）がアプリケーションの精度要件を満たすように近似されます。適切な設定により、ファイルサイズを削減しつつ視覚的忠実度を保つことができ、Web マップや空間分析ツールで GeoJSON を使用する際に重要です。

## 前提条件
1. **Visual Studio**（任意の最新バージョン）。  
2. **Aspose.GIS ライセンス**（または一時的な評価キー）。  
3. プロジェクトで参照されている **Aspose.GIS for .NET** ライブラリ。  
4. **C#** の基本的な知識。

## 名前空間のインポート
まず、必要な名前空間をインポートして、コンパイラが GIS クラスの所在を認識できるようにします。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップバイステップガイド

### ステップ 1: GeoJSON オプションの設定（トレランスの設定方法）
`GeoJsonOptions` は GeoJSON ファイルを書き出す際に使用されるシリアライズ設定を指定します。  
`GeoJsonOptions` は Aspose.GIS が GeoJSON をシリアライズする方法を定義し、線形化トレランス、座標精度、その他の出力設定を含みます。  
ここでは `GeoJsonOptions` オブジェクトを作成し、線形化されたジオメトリが元の曲線にどれだけ近い必要があるかを Aspose.GIS に指示します。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### ステップ 2: 出力パスの定義（GeoJSON のエクスポート方法）
生成された GeoJSON を保存するフルパスを指定します。フォルダーが存在し、アプリケーションに書き込み権限があることを確認してください。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### ステップ 3: 設定したオプションで **Create Vector Layer**
`VectorLayer` クラスは空間データの読み書きが可能な GIS コンテナを表します。  
`Drivers.GeoJson` は GeoJSON 形式のファイルを書き込むためのドライバー識別子です。  
`VectorLayer.Create` を `Drivers.GeoJson` ドライバーと事前に設定した `GeoJsonOptions` と組み合わせて使用することで、フィーチャー挿入の準備ができた新しい GeoJSON ファイルが作成されます。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### ステップ 4: ジオメトリの構築（例: CircularString）
`CircularString` は、設定したトレランスに基づいて Aspose.GIS が線形化できる曲線ラインジオメトリです。これを `POINT`、`LINESTRING`、`POLYGON` などの有効な WKT 表現に置き換えることも可能です。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### ステップ 5: **Add Feature to Layer** と保存
`Feature` はジオメトリと属性データを結び付けるオブジェクトです。`Feature` インスタンスを作成したらジオメトリを割り当て、必要に応じて属性値を追加し、`layer.Add(feature)` を呼び出して永続化します。`using` ブロックが終了すると、レイヤーは自動的に `path` で定義されたファイルに書き込まれます。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

`using` ブロックが終了すると、レイヤーは自動的に `path` で定義されたファイルに書き込まれ、すぐに使用できる GeoJSON ファイルが得られます。

## よくある問題とヒント
- **パスが間違っている** – ディレクトリが存在し、書き込み権限があることを確認してください。  
- **トレランスが低すぎる** – `LinearizationTolerance` を極小に設定するとファイルサイズが大幅に増加する可能性があります。通常、0.001 のトレランスが精度とサイズのバランスを取ります。  
- **ライセンスエラー** – ライセンス警告が表示された場合、Aspose.GIS の呼び出しの前にライセンスファイルがロードされていることを確認してください。  
- **パフォーマンスに関する注意** – Aspose.GIS はストリーミングアーキテクチャにより、ドキュメント全体をメモリに読み込まずに最大 2 GB のファイルを処理できます。

## よくある質問

**Q: Aspose.GIS for .NET は他の .NET フレームワークと互換性がありますか？**  
A: はい、.NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 で動作します。

**Q: 商用プロジェクトで Aspose.GIS を使用できますか？**  
A: もちろんです。商用ライセンスを取得すれば、すべての評価制限が解除され、フルテクニカルサポートが提供されます。

**Q: GeoJSON 以外の GIS フォーマットも Aspose.GIS はサポートしていますか？**  
A: はい、30 種類以上のフォーマット（Shapefile、KML、GML、CSV など）をサポートしており、間のシームレスな変換が可能です。

**Q: 試用版はありますか？**  
A: Aspose のウェブサイトから 30 日間の無料トライアルをダウンロードできます。すべての機能が含まれています。

**Q: サポートはどこで受けられますか？**  
A: Aspose フォーラム、専用サポートポータル、または製品ダッシュボードの “Contact Support” リンクをご利用ください。

## 結論
これらの手順に従うことで、**GeoJSON の作成方法**、線形化トレランスの設定方法、そしてシームレスな GeoJSON エクスポートのための **add feature to layer** が理解できました。追加のジオメトリタイプ、属性処理、バルク処理シナリオを検討し、.NET GIS プロジェクトで Aspose.GIS を最大限に活用してください。

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [GeoJSON の変換方法 – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [ベクターレイヤーの作成、精度制限 – Aspose.GIS for .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [File GDB でベクターレイヤーを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}