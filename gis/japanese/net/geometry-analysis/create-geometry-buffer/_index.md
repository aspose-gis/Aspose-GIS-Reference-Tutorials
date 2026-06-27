---
date: 2026-06-05
description: Aspose.GIS for .NET を使用してジオメトリをバッファリングし、spatial analysis バッファを実行する方法を学びます。インストール、名前空間のインポート、containment
  checks を含みます。
keywords:
- spatial analysis buffer
- how to buffer geometry
- Aspose.GIS buffering tutorial
- .NET spatial analysis
- geometry buffer example
linktitle: Aspose.GIS for .NET を使用したバッファ作成方法
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to buffer geometry with Aspose.GIS for .NET and perform spatial
    analysis buffers, including installation, namespace imports, and containment checks.
  headline: How to Buffer Geometry Using Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to buffer geometry with Aspose.GIS for .NET and perform spatial
    analysis buffers, including installation, namespace imports, and containment checks.
  name: How to Buffer Geometry Using Aspose.GIS for .NET
  steps:
  - name: Create a Geometry Buffer
    text: A `LineString` is an ordered collection of points forming a continuous line.
      First, we define a simple `LineString` geometry that will serve as the source
      for our buffer. In this snippet we create a `LineString` and add two points,
      forming a diagonal line from (0,0) to (3,3).
  - name: Generate Buffer for LineString
    text: 'The `GetBuffer` method creates a polygon representing all points within
      the specified distance from the source geometry. Next, we generate a buffer
      around the line with a **positive distance** of 1 unit. The `GetBuffer` method
      returns a polygon that includes every point located within 1 unit of the '
  - name: Check Spatial Containment
    text: The `SpatiallyContains` predicate returns true if the target geometry lies
      completely inside the source geometry. Now we demonstrate **how to check containment**
      by testing whether specific points fall inside the buffer. The `SpatiallyContains`
      predicate returns `true` if the point lies inside the b
  - name: Define a Polygon Geometry
    text: A `Polygon` represents a closed planar surface defined by a sequence of
      linear rings. We’ll also create a `Polygon` geometry to illustrate buffering
      with a **negative distance**, which shrinks the shape. The polygon represents
      a square with vertices at (0,0), (0,3), (3,3), and (3,0).
  - name: Generate Buffer for Polygon
    text: Applying a negative distance of –1 unit contracts the polygon inward. The
      resulting `polygonBuffer` is a smaller square, useful for creating interior
      zones.
  - name: Access Buffer Exterior Ring Points
    text: Finally, we retrieve and display the coordinates of the buffer’s exterior
      ring. This loop prints each vertex of the contracted polygon, confirming the
      buffer geometry.
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework, .NET Core, .NET 5, and .NET 6.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. The library supports buffering, intersecting, distance calculations,
      and more.
    question: Can I perform spatial analysis using Aspose.GIS for .NET?
  - answer: The API is optimized for large datasets and can handle **hundreds of thousands
      of geometries** without exhausting memory, provided you process them in reasonable
      batches.
    question: Are there limits on dataset size?
  - answer: Yes, it handles a wide range of coordinate systems and allows on‑the‑fly
      transformations.
    question: Does Aspose.GIS support different spatial reference systems?
  - answer: Visit the Aspose.GIS community forum at [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33)
      for assistance.
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用したジオメトリのバッファリング方法
url: /ja/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリのバッファリング方法

## はじめに
.NET 環境でジオスペーシャル データを扱う場合、**ジオメトリのバッファリング方法**を知っていることは、近接分析、ゾーニング、機能の一般化に不可欠です。このチュートリアルでは、Aspose.GIS for .NET を使用したインストールから、必要な名前空間のインポート、ラインおよびポリゴンジオメトリのバッファ生成、最後に空間的包含のチェックまで、全工程を順を追って説明します。最後まで読めば、**空間分析バッファ**を自分のアプリケーションに適用できるようになります。

## クイック回答
- **ジオメトリ バッファとは何ですか？** ソースジオメトリから指定された距離内のすべての点を囲むポリゴンです。  
- **なぜバッファリングに Aspose.GIS を使用するのですか？** .NET Framework、.NET Core、.NET 5/6+ で動作するシンプルで高性能な API を提供します。  
- **Aspose.GIS のインストール方法は？** 公式サイトからライブラリをダウンロードし、Visual Studio で参照として追加します。  
- **包含を確認する方法は？** `SpatiallyContains` メソッドを使用して、点が生成されたバッファ内にあるかどうかをテストします。  
- **バッファリング以外の空間分析は可能ですか？** はい、交差、結合、距離計算などの操作もサポートされています。

## ジオメトリ バッファとは
ジオメトリ バッファは、ユーザーが定義した距離でフィーチャ（点、ライン、またはポリゴン）の周囲に領域を作成します。この領域は、近隣フィーチャの特定、影響エリアの作成、または複雑な形状の単純化に役立ちます。バッファは近接クエリ、環境影響評価、ネットワーク分析で一般的に使用され、元のジオメトリから指定距離内にある領域を視覚的に明確に表現します。

## Aspose.GIS を使用したジオメトリのバッファリング
ソースジオメトリを読み込み、目的の距離で `GetBuffer` を呼び出すと、バッファ領域を表すポリゴンが即座に取得できます。この 2 ステップのパターンは点、ライン、ポリゴンすべてで機能し、API が座標系の細部を自動的に処理するため、独自の数式を書く必要はありません。

### なぜ Aspose.GIS を空間分析バッファに使用するのか？
- **クロスプラットフォーム対応:** Windows、Linux、macOS で動作します。  
- **外部依存性ゼロ:** ネイティブ GIS ライブラリは不要です。  
- **リッチな API:** バッファリング、空間述語、座標系変換を含みます。  
- **パフォーマンス最適化:** 典型的な 8 コアサーバー上で、最大 **500 000 個** のフィーチャを **2 秒未満**で処理でき、重負荷の空間分析バッファに最適です。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- **Visual Studio 2019 以降**（または互換性のある .NET IDE）。  
- **.NET 6 SDK**（または .NET Core 3.1 以上）。  
- **Aspose.GIS for .NET ライブラリ** – 以下のインストール手順をご参照ください。  

### Aspose.GIS for .NET のインストール方法
1. Aspose.GIS for .NET ライブラリを [ダウンロードリンク](https://releases.aspose.com/gis/net/) からダウンロードします。  
2. Visual Studio でプロジェクトを右クリック → **Add** → **Reference…** → ダウンロードした DLL を参照して追加します。  
3. [Aspose](https://purchase.aspose.com/buy) からライセンスを取得するか、評価用に [一時ライセンス](https://purchase.aspose.com/temporary-license/) を使用します。

## 名前空間のインポート
`Aspose.Gis` 名前空間には、ジオメトリ作成、バッファリング、空間述語に必要なすべてのコアクラスが含まれています。

`GeometryFactory` クラスは、`LineString` や `Polygon` などのジオメトリオブジェクトを構築するエントリーポイントです。これらの名前空間をインポートすると、ファイル全体で API が利用可能になります。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Now let’s break down the buffer creation process step‑by‑step.

## ステップバイステップ ガイド

### ステップ 1: ジオメトリ バッファの作成
`LineString` は連続した線を構成する点の順序付きコレクションです。  
まず、バッファのソースとなるシンプルな `LineString` ジオメトリを定義します。

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

このスニペットでは `LineString` を作成し、2 つの点を追加して (0,0) から (3,3) への対角線を形成しています。

### ステップ 2: LineString のバッファ生成
`GetBuffer` メソッドは、ソースジオメトリから指定された距離内のすべての点を表すポリゴンを作成します。  
次に、**正の距離** 1 単位でラインの周囲にバッファを生成します。

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

`GetBuffer` メソッドは、元のラインから 1 単位以内にあるすべての点を含むポリゴンを返します。

### ステップ 3: 空間的包含の確認
`SpatiallyContains` 述語は、対象ジオメトリがソースジオメトリの内部に完全に収まっている場合に true を返します。  
ここでは、特定の点がバッファ内に入るかどうかをテストして **包含の確認方法** を示します。

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

`SpatiallyContains` 述語は、点がバッファポリゴンの内部にある場合に `true` を返します。

### ステップ 4: ポリゴンジオメトリの定義
`Polygon` は、線環のシーケンスで定義された閉じた平面領域を表します。  
**負の距離** でバッファリングし形状を縮小する例として、`Polygon` ジオメトリも作成します。

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

このポリゴンは、頂点が (0,0)、(0,3)、(3,3)、(3,0) の正方形を表します。

### ステップ 5: ポリゴンのバッファ生成
-1 単位の負の距離を適用すると、ポリゴンが内側に収縮します。

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

結果として得られる `polygonBuffer` は、内部ゾーンの作成に役立つ小さな正方形です。

### ステップ 6: バッファの外周リングのポイント取得
最後に、バッファの外周リングの座標を取得して表示します。

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

このループは、縮小されたポリゴンの各頂点を出力し、バッファジオメトリが正しく生成されたことを確認します。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **バッファが `null` を返す** | ジオメトリの座標系に対して距離値が適切であることを確認してください。 |
| **`SpatiallyContains` が常に `false` を返す** | 両方のジオメトリが同じ空間参照系（CRS）を共有していることを確認してください。 |
| **大規模データセットでのパフォーマンス低下** | ジオメトリをバッチ処理し、同じ `GeometryFactory` インスタンスを再利用してください。 |

## よくある質問

**Q: Aspose.GIS for .NET は他の .NET フレームワークと互換性がありますか？**  
A: はい、.NET Framework、.NET Core、.NET 5、.NET 6 で動作します。

**Q: Aspose.GIS for .NET を使用して空間分析を実行できますか？**  
A: もちろんです。ライブラリはバッファリング、交差、距離計算などをサポートしています。

**Q: データセットサイズに制限はありますか？**  
A: API は大規模データセットに最適化されており、バッチ処理を行えば **数十万件** のジオメトリをメモリ不足になることなく処理できます。

**Q: Aspose.GIS は異なる空間参照系をサポートしていますか？**  
A: はい、幅広い座標系に対応しており、オンザフライでの変換も可能です。

**Q: 技術サポートはどこで受けられますか？**  
A: サポートは [https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33) の Aspose.GIS コミュニティフォーラムで受けられます。

---

**最終更新日:** 2026-06-05  
**テスト済み:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したポリゴンジオメトリの作成方法](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aspose.GIS for .NET を使用したジオメトリの空間重複分析の実行方法](/gis/net/geometry-analysis/check-geometries-overlap/)
- [Aspose.GIS for .NET を使用したジオメトリの重心取得方法](/gis/net/geometry-analysis/get-geometry-centroid/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}