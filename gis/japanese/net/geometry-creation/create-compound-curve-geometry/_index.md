---
date: 2026-02-15
description: Aspose.GIS を使用して .NET で曲線を追加し、複合曲線ジオメトリを作成する方法を学び、シームレスな地理空間データ処理を実現しましょう。
linktitle: How to Add Curves – Compound Curve Geometry
second_title: Aspose.GIS .NET API
title: 曲線の追加方法 - Aspose.GIS を使用した複合曲線ジオメトリ
url: /ja/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 曲線の追加方法: Aspose.GIS を使用した複合曲線ジオメトリ

## Introduction
.NET 開発の世界では、Aspose.GIS を使用して **曲線を追加する方法** を学ぶことは、洗練された地理空間アプリケーションを構築する上で不可欠です。インタラクティブなマップの作成、空間分析の実施、複雑な GIS データセットの生成など、Aspose.GIS は高度なジオメトリを迅速かつ確実に扱うためのツールを提供します。このガイドでは、**曲線を追加する方法** の全プロセスと、単一の再利用可能な複合曲線ジオメトリへ組み立てる手順を解説します。

## Quick Answers
- **What is the primary goal?** Shapefile に曲線を追加し、複合曲線ジオメトリを構築すること。  
- **Which library is used?** Aspose.GIS for .NET。  
- **Prerequisites?** Visual Studio、Aspose.GIS のインストール、基本的な C# プロジェクト。  
- **Typical implementation time?** 動作例を作成するのに約 10‑15 分。  
- **Supported output format?** Shapefile（同様の手法で GeoJSON、KML なども利用可能）。

## What is a Compound Curve?
**複合曲線** とは、複数の接続された曲線コンポーネント（直線ストリングと円弧）から構成され、より複雑な形状を形成する単一のジオメトリです。単純な直線だけでは正確に表現できない道路の曲がりや河川の蛇行などに有用です。

## Why Use Aspose.GIS for Adding Curves?
- **Rich geometry API:** ラインストリング、サーキュラーストリング、複合曲線を標準でサポート。  
- **Cross‑platform:** .NET Framework、.NET Core、.NET 5/6+ で動作。  
- **No external dependencies:** ネイティブ GIS ライブラリや COM インターロップは不要。  
- **Easy to export:** Shapefile、GeoJSON、KML など多数のフォーマットへ直接書き出し可能。

## Why This Matters
曲線を追加することで、実世界の特徴をより正確にモデル化でき、マップ描画の視覚品質が向上し、近接検索やネットワークルーティングといった空間分析の精度も高まります。**曲線を追加する方法** を習得すれば、GIS 主導の .NET ソリューションの忠実度を大幅に向上させることができます。

## Common Use Cases
- **Transportation networks:** 曲がりくねった高速道路、鉄道、サイクリングパスのモデリング。  
- **Hydrology:** 自然な弧を描く河川コースの表現。  
- **Urban planning:** 曲線部分を含む土地境界の描画。  
- **Custom symbols:** 地図凡例用の装飾的または概略的なシンボル作成。

## Prerequisites
- **Visual Studio** がワークステーションにインストールされていること。  
- **Aspose.GIS for .NET** を [download page](https://releases.aspose.com/gis/net/) から取得。  
- .NET 6（またはサポート対象の任意のバージョン）をターゲットにした C# プロジェクト。

## Import Namespaces
Aspose.GIS を使用するために、C# ファイルの先頭で必要な名前空間をインポートします。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide to Create Compound Curve Geometry

### Step 1: Define the Output Path
まず、ライブラリに結果を書き込む場所を指定します。プレースホルダーは実際のフォルダーに置き換えてください。

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### Step 2: Create a Vector Layer
`VectorLayer` は空間フィーチャのコンテナとして機能します。すべてのジオメトリ操作はこの `using` ブロック内で行われ、リソースの解放も自動的に行われます。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### Step 3: Construct the Compound Curve Feature
レイヤー内で新しいフィーチャと、個々の曲線パーツを保持する空の `CompoundCurve` オブジェクトを作成します。

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### Step 4: Define Component Curves
ここでは、2 本の直線 `LineString`、2 本の `CircularString` 弧、そして最後の `LineString` の計 5 つのパーツを用意します。これらを組み合わせて完全な複合曲線を構成します。

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### Step 5: Add Component Curves to the Compound Curve
各コンポーネントを順番に追加し、ジオメトリが連続かつ正しい向きになるようにします。

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### Step 6: Assign Geometry to the Feature
組み立てた `CompoundCurve` を、保存対象となるフィーチャのジオメトリとして設定します。

```csharp
feature.Geometry = compoundCurve;
```

### Step 7: Add the Feature to the Layer
最後にフィーチャを Shapefile に書き込みます。`using` ブロックが終了するとファイルが閉じられ、任意の GIS アプリケーションで使用できる状態になります。

```csharp
layer.Add(feature);
```

## Common Issues & Tips
- **Coordinate order:** Aspose.GIS は `X Y`（経度、緯度）の順序で座標を期待します。順序が逆になるとジオメトリが反転します。  
- **CircularString syntax:** `CircularString` の中点が意図した弧上にあることを確認してください。そうでないと曲線が平坦化されます。  
- **File overwrite:** 既存の Shapefile がある場合、`VectorLayer.Create` は警告なしで上書きします。開発中はユニークなファイル名を使用しましょう。  
- **Performance:** 大規模データセットでは、`using` ブロック内で 1 件ずつ追加するのではなく、バッチでフィーチャを追加する方が効率的です。  
- **Pro tip:** 複数の類似フィーチャを作成する際は同じ `CompoundCurve` オブジェクトを再利用し、再利用前に `compoundCurve.Clear()` で曲線をクリアすると便利です。

## Frequently Asked Questions

**Q: Can I use Aspose.GIS for .NET with other .NET frameworks?**  
A: Yes, Aspose.GIS for .NET works with .NET Framework, .NET Core, and .NET Standard.

**Q: Does Aspose.GIS support reading and writing different geospatial file formats?**  
A: Absolutely! It supports Shapefile, GeoJSON, KML, GML, and many more formats.

**Q: Is Aspose.GIS suitable for both desktop and web applications?**  
A: Yes, the library can be used in desktop, web, and cloud services alike.

**Q: Can I perform spatial analysis with Aspose.GIS for .NET?**  
A: Yes, you can calculate distances, perform geometric operations, and execute spatial queries.

**Q: Where can I get community help for Aspose.GIS?**  
A: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask questions and share ideas.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}