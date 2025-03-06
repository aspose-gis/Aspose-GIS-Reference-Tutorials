---
title: Aspose.GIS for .NET を使用したジオメトリ オーバーレイのマスタリング
linktitle: ジオメトリ オーバーレイの検索
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して幾何学的なオーバーレイ操作を実行する方法を学びます。マスター交差、和集合、差分、対称差分演算。
weight: 16
url: /ja/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリ オーバーレイのマスタリング

## 導入
地理情報システム (GIS) の領域では、オーバーレイ操作は空間分析の基本です。これらにより、さまざまな空間データセットを比較および組み合わせて、貴重な洞察を得ることができます。 Aspose.GIS for .NET は、幾何学的オーバーレイを効率的に実行するための堅牢な機能を提供します。このチュートリアルでは、Aspose.GIS for .NET を使用した、交差、結合、差分、対称差分などのさまざまなオーバーレイ操作を詳しく説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
### 1..NET開発環境
マシン上に .NET 開発環境がセットアップされていることを確認してください。 .NET Web サイトから .NET SDK をダウンロードしてインストールできます。
### 2. .NET ライブラリ用の Aspose.GIS
 Aspose.GIS for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/gis/net/).
## 名前空間のインポート
Aspose.GIS for .NET の使用を開始する前に、必要な名前空間をプロジェクトにインポートする必要があります。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ポリゴン オブジェクトを作成する
まず、空間領域を表す 2 つのポリゴン オブジェクトを定義します。
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## ステップ 2: 交差点操作の実行
次に、2 つの多角形の交点を見つけてみましょう。
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); //ポリゴン
```
## ステップ 3: 交点を印刷する
交差多角形の点を印刷します。
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## ステップ 4: ユニオン操作を実行する
次に、2 つの多角形の結合を見つけてみましょう。
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); //ポリゴン
```
## ステップ 5: ユニオン ポイントを印刷する
和多角形の点を出力します。
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## ステップ 6: 差分演算を実行する
次に、2 つの多角形の違いを見つけてみましょう。
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); //ポリゴン
```
## ステップ 7: 差分ポイントを出力する
差分多角形の点を出力します。
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## ステップ 8: 対称差分演算を実行する
最後に、2 つの多角形間の対称性の差を見つけてみましょう。
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); //マルチポリゴン
```
## ステップ 9: 対称差分ポリゴンを印刷する
対称差分の各多角形の点を出力します。
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## 結論
ジオメトリ オーバーレイをマスターすることは空間解析において重要であり、Aspose.GIS for .NET はこれらの操作を効率的に実行するための包括的なツール セットを提供します。このチュートリアルに従うことで、Aspose.GIS for .NET を利用して、幾何学的形状に対して交差、和集合、差分、対称差分演算を実行する方法を学習しました。
## よくある質問
### Q: Aspose.GIS for .NET を商用プロジェクトで使用できますか?
はい、Aspose.GIS for .NET は商用プロジェクトと非商用プロジェクトの両方で使用できます。
### Q: Aspose.GIS for .NET の試用版はありますか?
はい、無料試用版を次からダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.GIS for .NET のサポートを受けるにはどうすればよいですか?
Aspose.GIS コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/gis/33).
### Q: Aspose.GIS for .NET で利用できる一時ライセンスはありますか?
はい、一時ライセンスはテストと評価の目的で利用できます。から入手できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.GIS for .NET を直接購入できますか?
はい、Web サイトから Aspose.GIS for .NET を購入できます。[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
