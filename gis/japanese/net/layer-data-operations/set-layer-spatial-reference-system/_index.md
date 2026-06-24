---
date: 2026-06-15
description: Aspose.GIS for .NET を使用してベクトルレイヤーを作成し、レイヤー空間参照系を設定する方法を学びます。空間参照の定義、ポイントフィーチャの追加、EPSG
  コードの取得をマスターしましょう。
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: レイヤー空間参照系の設定
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: ベクトルレイヤーの作成とレイヤー空間参照系の設定
url: /ja/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ベクトルレイヤーの作成とレイヤー空間参照系の設定

## はじめに
広大な地理情報システム（GIS）の領域で、**Aspose.GIS for .NET** は、**70+** のベクトルおよびラスタ形式をサポートし、メモリに全データセットをロードせずに **10 GB** を超えるファイルを処理できる、堅牢で高性能なライブラリとして際立っています。このチュートリアルでは、**ベクトルレイヤーを作成**し、空間参照を定義し、**ポイントフィーチャーを追加**し、EPSG コードを取得します—すべて明確なステップバイステップのガイダンスで提供します。マッピングサービス、データ変換パイプライン、または空間分析エンジンを構築する場合でも、これらの基礎を習得すれば、シェープファイルの座標系を正確に保ち、GIS ワークフローの信頼性を確保できます。

## クイック回答
- **What does “create vector layer” mean?** 新しい GIS レイヤー（例: Shapefile）を作成し、ポイント、ライン、ポリゴンなどのジオメトリを格納できるようにします。  
- **Which EPSG code is used in the example?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Can I add a point feature after creating the layer?** はい—`ConstructFeature()` を使用し、`Point` ジオメトリを割り当てます。  
- **How do I retrieve the layer’s CRS?** `layer.SpatialReferenceSystem.EpsgCode` または `.Name` を読み取ります。  
- **Do I need a license for Aspose.GIS?** 無料トライアルが利用可能です。製品版の使用にはライセンスが必要です。

## ベクトルレイヤーの作成とは？
**create vector layer** 操作は、ジオメトリフィーチャーと属性データを保持できる新しいベクトルデータセット（例: Shapefile）を作成します。Aspose.GIS では、ドライバーと空間参照系を指定して `VectorLayer` オブジェクトをインスタンス化することで実現します。

## なぜレイヤーの座標系（CRS）を正しく設定する必要があるのか？
正しい座標参照系（CRS）を設定することで、保存するすべてのジオメトリが他の空間データセットと整合します。Aspose.GIS では、標準の EPSG コードを使用して CRS を定義でき、世界中の GIS ソフトウェアとの相互運用性が保証されます。例えば、EPSG 26918 は NAD83 / UTM ゾーン 18N を定義し、米国東部のデータで一般的に使用される投影です。

## 前提条件
- .NET 開発経験（C# または VB.NET）。  
- Visual Studio 2022 以降。  
- Aspose.GIS for .NET ライブラリ – ダウンロードは **[here](https://releases.aspose.com/gis/net/)**。  
- 空間参照系（CRS/EPSG）に関する基本的な知識。

## 名前空間のインポート
`Aspose.Gis` 名前空間はコア GIS クラスを提供し、`Aspose.Gis.Geometries` は `Point` などのジオメトリ型を提供します。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Aspose.GIS for .NET でベクトルレイヤーを作成するには？
VectorLayer は Shapefile のようなベクトルデータセットを表し、フィーチャーの作成、読み取り、編集のメソッドを提供します。  
SpatialReferenceSystem は EPSG コードを使用して座標参照系を定義します。  

対象フォルダーをロードし、EPSG コードで `SpatialReferenceSystem` を定義し、Shapefile ドライバーで `VectorLayer.Create` を呼び出します。この単一呼び出しで新しい `.shp` ファイルが作成され、対応する `.shx` と `.dbf` ファイルが書き込まれ、CRS メタデータが埋め込まれ、効率的にフィーチャー挿入の準備が整います。

### 手順 1: ドキュメントディレクトリの指定
まず、ドキュメントディレクトリへのパスを指定します。ここが空間データファイルの保存場所となります。

```csharp
string dataDir = "Your Document Directory";
```

### 手順 2: 空間参照の定義と Shapefile の座標系設定
SpatialReferenceSystem は EPSG コードで識別されるレイヤーの CRS を表します。  

Shapefile のパスを定義し、EPSG コード（この例では 26918）を使用して **空間参照を定義**します。この手順でレイヤーの **Shapefile 座標系が設定**されます。

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## ベクトルレイヤーにポイントフィーチャーを追加するには？
`Point` は単一の X/Y 座標ペアを表すジオメトリ型です。  

新しいフィーチャーを作成し、目的の X/Y 座標を持つ `Point` ジオメトリを割り当て、開いている `VectorLayer` にフィーチャーを追加します。この操作はジオメトリを `.shp` ファイルに、属性レコードを `.dbf` ファイルに単一のトランザクションで書き込みます。

### 手順 3: ベクトルレイヤーの作成
`ConstructFeature` はジオメトリと属性データを保持できる新しいフィーチャーオブジェクトを作成します。  

これで、指定した Shapefile パス、ドライバータイプ（Shapefile）、先ほど定義した空間参照系を使用して **ベクトルレイヤーを作成**します。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### 手順 4: レイヤーにポイントフィーチャーを追加
新しいフィーチャーを作成し、ジオメトリ（座標 60, 24 の `Point`）を設定して **ポイントフィーチャーを追加**します。その後、フィーチャーをベクトルレイヤーに追加します。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### 手順 5: 空間参照系情報の取得（EPSG コードの取得）
ベクトルレイヤーを開き、空間参照系に関する情報（EPSG コードや人が読める名前）を取得します。これにより、**EPSG コードの取得**と **レイヤーの CRS 設定**の方法が示されます。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|-------|----------------|-----|
| **レイヤーが開けません** | ドライバーが間違っているか、ファイルパスが破損しています | `Drivers.Shapefile` を確認し、`path` が既存の `.shp` ファイルを指していることを確認してください。 |
| **表示された CRS が正しくない** | 間違った EPSG コードを使用しています | 権威ある情報源（例: EPSG.io）で EPSG コードを再確認してください。 |
| **フィーチャーが保存されません** | `using` ブロック内で `layer.Add(feature)` を呼び出していない | レイヤーが破棄される前に `Add` メソッドが実行されていることを確認してください。 |

## よくある質問
**Q: 既存の Shapefile の CRS を変更するには？**  
A: レイヤーを開き、目的の EPSG コードで新しい `SpatialReferenceSystem` を作成し、`layer.SpatialReferenceSystem` に割り当て、レイヤーを保存します。

**Q: 同じ手法で他のジオメトリタイプ（例: ポリゴン）を追加できますか？**  
A: はい—必要に応じて `new Point(x, y)` を `new Polygon(...)` または `new LineString(...)` に置き換えます。

**Q: 大規模データセットを効率的に扱うことは可能ですか？**  
A: ストリーミング API（`VectorLayer.Create` と `FeatureCollection`）を使用し、レイヤーを速やかに破棄してリソースを解放します。

**Q: Aspose.GIS は座標変換をサポートしていますか？**  
A: はい—`Geometry.Transform(targetSrs)` を使用して、異なる空間参照間でジオメトリを再投影できます。

**Q: サポートされている .NET バージョンは何ですか？**  
A: Aspose.GIS は .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6/7 と互換性があります。

---

**最終更新日:** 2026-06-15  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用してベクトルレイヤーを作成し、線形化許容誤差を設定](/gis/net/geometry-processing/set-linearization-tolerance/)
- [File GDB にベクトルレイヤーを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [spatial reference wgs84 – Aspose.GIS を使用して GDB にレイヤーを追加](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}