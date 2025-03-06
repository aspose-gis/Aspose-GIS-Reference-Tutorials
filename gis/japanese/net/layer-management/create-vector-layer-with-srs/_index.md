---
title: SRSでベクターレイヤーを作成
linktitle: SRSでベクターレイヤーを作成
second_title: Aspose.GIS .NET API
description: シームレスな GIS 統合の鍵となる Aspose.GIS for .NET を探索してください。指定された空間参照系を使用してベクター レイヤーを簡単に作成します。ダウンロード中！
weight: 13
url: /ja/net/layer-management/create-vector-layer-with-srs/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# SRSでベクターレイヤーを作成

## 導入
Aspose.GIS for .NET は、開発者が .NET アプリケーションで地理情報システム (GIS) データをシームレスに操作できるようにする強力なライブラリです。このチュートリアルでは、空間参照システム (SRS) を使用したベクター レイヤーの作成に焦点を当てます。このガイドを終えると、GIS 機能を .NET プロジェクトに簡単に統合できるようになります。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# および .NET 開発の基本的な知識。
-  Aspose.GIS for .NET ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/gis/net/).
- 開発環境がセットアップされ、準備が整いました。
## 名前空間のインポート
必要な名前空間が C# ファイルの先頭にインポートされていることを確認します。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: 投影空間参照系を設定する
例として世界メルカトル図法を使用して、投影空間参照系 (SRS) を作成してみましょう。次の手順を実行します：
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## ステップ 2: ベクターレイヤーを作成し、機能を追加する
次に、シェープファイルを作成し、指定された SRS を使用してフィーチャを追加しましょう。
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); //ジオメトリに異なる SRS があるため、例外がスローされます。
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## ステップ 3: 空間参照系を検証する
最後に、レイヤーを開いてその空間参照系を確認してみましょう。
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // 「WGS 84 / ワールドメルカトル」
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // true を返す必要があります
}
```
これらの手順に従うことで、Aspose.GIS for .NET を使用して、指定された空間参照系を持つベクター レイヤーを正常に作成できました。
## 結論
Aspose.GIS のおかげで、GIS 機能を .NET アプリケーションに統合することがかつてないほど簡単になりました。ベクター レイヤーを簡単に作成し、空間参照系を管理できるため、強力な地理空間機能でプロジェクトを強化できます。
## よくある質問
### Aspose.GIS はすべての GIS ファイル形式と互換性がありますか?
 Aspose.GIS は、Shapefile、GeoJSON、KML などを含むさまざまな GIS 形式をサポートしています。チェックしてください[ドキュメンテーション](https://reference.aspose.com/gis/net/)完全なリストについては、
### Web アプリケーションで Aspose.GIS を使用できますか?
絶対に！ Aspose.GIS for .NET は多用途であり、Web アプリケーション、デスクトップ アプリケーション、さらにはモバイル アプリケーションでも使用できます。
### Aspose.GIS のサポートはどこで入手できますか?
役立つコミュニティは次の場所にあります。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)発生する可能性のある質問や問題については、
### 無料トライアルはありますか?
はい、無料トライアルを入手して、Aspose.GIS の機能を探索できます。[ここ](https://releases.aspose.com/).
### Aspose.GIS のライセンスを購入するにはどうすればよいですか?
ライセンスを購入するには、次のサイトにアクセスしてください。[購入ページ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
