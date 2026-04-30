---
date: 2026-01-15
description: Aspose.GIS for .NET を探索して、空間参照系を持つベクトルレイヤーを作成しましょう。SRS の設定方法、レイヤーの作成、GIS
  データの管理方法を学べます。今すぐダウンロード！
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: SRSでベクトルレイヤーを作成
url: /ja/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# SRS を使用したベクトルレイヤーの作成

## はじめに
Aspose.GIS for .NET は、開発者が **vector layer** オブジェクトを作成し、.NET アプリケーションで地理情報システム (GIS) データをシームレスに扱える強力なライブラリです。このチュートリアルでは、空間参照系 (SRS) を使用したベクトルレイヤーの作成方法、空間参照を設定する理由、そして実際のプロジェクトにもたらすメリットについて解説します。ガイドの最後までに、.NET ソリューションに GIS 機能を自信を持って統合できるようになります。

## クイック回答
- **このチュートリアルの主な目的は何ですか？** Aspose.GIS for .NET を使用して、指定された SRS を持つ vector layer を作成する方法を示すことです。  
- **例で使用されている投影法は何ですか？** World Mercator (EPSG:3395)。  
- **コードを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **他の GIS フォーマットでも同じアプローチを使用できますか？** はい、同じ SRS の取り扱いは Shapefile、GeoJSON、KML などにも適用できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## ベクトルレイヤーとは何か、そして空間参照を設定する理由
**vector layer** は、幾何的なフィーチャ（ポイント、ライン、ポリゴン）と属性データを一緒に保存します。**spatial reference**（SRS）を割り当てることで、GIS ソフトウェアにこれらの座標が地球上でどのように解釈されるかを指示します。正しい SRS を設定することで、測定の精度が向上し、他のレイヤーとの正確なオーバーレイや信頼できるマップ表示が可能になります。

## 前提条件
本題に入る前に、以下が揃っていることを確認してください：

- C# と .NET 開発の基本的な知識。  
- Aspose.GIS for .NET ライブラリがインストールされていること。**[こちら](https://releases.aspose.com/gis/net/)** からダウンロードできます。  
- 開発環境（Visual Studio、VS Code、または任意の C# IDE）。

## 名前空間のインポート
C# ファイルの先頭で、必要な名前空間がインポートされていることを確認してください：

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

## 空間参照 (SRS) の設定方法 – ステップ 1
World Mercator 投影法を例に、**projected spatial reference system** を作成してみましょう。これにより、レイヤーに対して **srs の設定方法** が示されます。

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

## レイヤーの作成方法 – ステップ 2
次に、**vector layer**（Shapefile）を作成し、先ほど定義した SRS を使用するフィーチャを追加します。このセクションでは、Aspose.GIS を使用した **レイヤーの作成方法** を説明します。

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **プロのコツ:** フィーチャを追加する前に、ジオメトリの `SpatialReferenceSystem` がレイヤーの SRS と一致していることを必ず確認してください。SRS が一致しない場合、上記のように `GisException` がスローされます。

## 空間参照系の検証 – ステップ 3
最後に、レイヤーを開いて SRS が正しく適用されていることを確認します。

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

`IsEquivalent` 呼び出しが `true` を返せば、目的の空間参照を持つ **vector layer の作成** に成功したことになります。

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|------|----------|------|
| `GisException` がフィーチャ追加時に発生 | ジオメトリがレイヤーと異なる SRS を使用している | 追加する前に `feature.Geometry.SpatialReferenceSystem` をレイヤーの SRS に設定する |
| GIS ソフトウェアでレイヤーが空として表示される | shapefile が適切な `.prj` ファイルなしで作成された | レイヤー作成時に `projectedSrs` オブジェクトが渡されていることを確認する |
| 予期しない座標値 | 投影パラメータが誤っている（例: 中央子午線） | `AddProjectionParameter` に渡されたパラメータを再確認する |

## FAQ
### Aspose.GIS はすべての GIS ファイル形式に対応していますか？
Aspose.GIS は Shapefile、GeoJSON、KML などさまざまな GIS 形式をサポートしています。完全な一覧は **[ドキュメント](https://reference.aspose.com/gis/net/)** をご確認ください。

### Aspose.GIS をウェブアプリケーションで使用できますか？
もちろんです！Aspose.GIS for .NET は汎用性が高く、ウェブアプリ、デスクトップアプリ、さらにはモバイルアプリでも使用できます。

### Aspose.GIS のサポートはどこで受けられますか？
ご質問や問題がある場合は、**[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)** でコミュニティをご利用ください。

### 無料トライアルは利用できますか？
はい、**[こちら](https://releases.aspose.com/)** から無料トライアルを取得して Aspose.GIS の機能をお試しいただけます。

### Aspose.GIS のライセンスはどのように購入できますか？
ライセンス購入は **[購入ページ](https://purchase.aspose.com/buy)** へお進みください。

## 追加のよくある質問
**Q: 異なる SRS のジオメトリを追加しようとした場合はどうなりますか？**  
A: Aspose.GIS は `GisException` をスローします。ジオメトリを再投影するか、レイヤーと同じ SRS を使用する必要があります。

**Q: 既存のレイヤーの SRS を変更できますか？**  
A: はい、目的の SRS を持つ新しいレイヤーを作成し、フィーチャをコピーして必要に応じて再投影できます。

**Q: 3D 座標で作業できますか？**  
A: Aspose.GIS は Z 座標をサポートしています。Z 値を受け取るジオメトリコンストラクタを使用してください。

**Q: ライブラリはデータム変換を自動的に処理しますか？**  
A: `Geometry.Transform` を使用してジオメトリを再投影すると、Aspose.GIS が必要なデータムシフトを実行します。

**Q: 公式にテストされている .NET バージョンはどれですか？**  
A: ライブラリは .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 でテストされています。

## 結論
これで、Aspose.GIS for .NET を使用してカスタム空間参照系を持つ **vector layer の作成** 方法を学びました。正しい SRS を設定し、ジオメトリを一貫して扱い、レイヤーのメタデータを検証することで、標準的な GIS ソフトウェアと相互運用できる堅牢な GIS 機能を備えたアプリケーションを構築できます。

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}