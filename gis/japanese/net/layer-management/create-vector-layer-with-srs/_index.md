---
date: 2026-06-30
description: Aspose.GIS for .NET を使用して空間参照系付きのベクトルレイヤーを作成する方法を学びます。ステップバイステップのガイド、コード不要の解説、FAQ
  を掲載しています。
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Aspose.GIS for .NET を使用した SRS 付きベクトルレイヤーの作成方法
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用した SRS 付きベクトルレイヤーの作成方法
url: /ja/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した SRS 付きベクトルレイヤの作成方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して空間参照系 (SRS) を含む **ベクトルレイヤ** オブジェクトの作成方法を学びます。SRS を割り当てる理由の説明、設定手順の詳細、正確な測定や他の GIS データとのシームレスなオーバーレイなど、実際の利点を解説します。最後まで読むと、任意の .NET アプリケーションに堅牢な GIS 機能を組み込む準備が整います。

## クイック回答
- **このチュートリアルの主な目的は何ですか？** Aspose.GIS for .NET を使用して、指定された SRS を持つベクトルレイヤを作成する方法を示すことです。  
- **例で使用されている投影法は何ですか？** ワールド メルカトル (EPSG:3395)。  
- **コードを実行するのにライセンスは必要ですか？** 開発には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **他の GIS フォーマットでも同じアプローチを使用できますか？** はい、同じ SRS の取り扱いは Shapefile、GeoJSON、KML などにも適用できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## ベクトルレイヤとは何か、なぜ空間参照を設定するのか
**ベクトルレイヤ** は、ジオメトリ（ポイント、ライン、ポリゴン）と属性データを一緒に保存します。**空間参照系** を割り当てることで、GIS ソフトウェアはこれらの座標を地球表面にどのようにマッピングするかを認識し、正確な距離計算、正しいレイヤの位置合わせ、信頼できるマップ描画を保証します。

## なぜ空間参照系を設定するのか
定義された SRS を使用すると、異なるソースからのレイヤをオーバーレイする際の座標変換エラーを最大 95 % 減少させることができます。Aspose.GIS は **20+** の入力および出力フォーマット（Shapefile、GeoJSON、KML、GML など）をサポートし、ファイル全体をメモリに読み込むことなく数百ページに及ぶデータセットを処理できます。

## 前提条件
- C# と .NET 開発の基本的な知識。  
- Aspose.GIS for .NET ライブラリがインストールされていること。**[here](https://releases.aspose.com/gis/net/)** からダウンロードできます。  
- 開発環境（Visual Studio、VS Code、または任意の C# IDE）。

## 名前空間のインポート
C# ファイルの先頭で必要な名前空間がインポートされていることを確認してください：

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
2 行で投影 SRS をロードします：`ProjectedSpatialReferenceSystem` インスタンスを作成し、メルカトル投影のパラメータを設定すれば、レイヤに付与できる状態になります。

`ProjectedSpatialReferenceSystem` は投影座標参照系を表すクラスです。  
`ProjectedSpatialReferenceSystemParameters` は、中央子午線やスケールファクタなど、投影 SRS を設定するために必要なパラメータを保持します。

例として World Mercator 投影を使用して **投影空間参照系** を作成しましょう。これによりレイヤの **srs の設定方法** が示されます。

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

## レイヤの作成方法 – ステップ 2
`projectedSrs` を渡して Shapefile レイヤをインスタンス化し、レイヤの SRS と一致する `SpatialReferenceSystem` を持つジオメトリを追加します。

`Layer`（例：Shapefile）は、単一の GIS ファイルに保存されたフィーチャのコレクションを表します。  
ここでは **ベクトルレイヤ**（Shapefile）を **作成**し、先ほど定義した SRS を使用するフィーチャを追加します。この部分は Aspose.GIS で **レイヤの作成方法** に答えます。

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

## 空間参照系の検証 – ステップ 3
新しく作成したレイヤを開き、その `SpatialReferenceSystem` を取得し、`IsEquivalent` を使って元の `projectedSrs` と比較します。`true` が返れば、SRS が正しく適用されたことが確認できます。

`IsEquivalent` は、2 つの空間参照系が同じ座標系を表すかどうかをチェックします。  
最後にレイヤを開き、SRS が正しく適用されたことを確認します。

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

`IsEquivalent` の呼び出しが `true` を返せば、目的の空間参照を持つ **ベクトルレイヤの作成** に成功したことになります。

## よくある問題と解決策
| 問題 | 発生理由 | 解決策 |
|------|----------|--------|
| `GisException` がフィーチャ追加時に発生 | ジオメトリがレイヤと異なる SRS を使用している | フィーチャを追加する前に `feature.Geometry.SpatialReferenceSystem` をレイヤの SRS に設定する |
| GIS ソフトでレイヤが空として表示される | shapefile が適切な `.prj` ファイルなしで作成された | レイヤ作成時に `projectedSrs` オブジェクトが渡されていることを確認する |
| 予期しない座標値 | 投影パラメータが誤っている（例：中央子午線） | `AddProjectionParameter` に渡したパラメータを再確認する |

## FAQ
### Aspose.GIS はすべての GIS ファイル形式に対応していますか？
Aspose.GIS は **20+** の GIS フォーマットに対応しており、Shapefile、GeoJSON、KML、GML などが含まれます。全リストは **[documentation](https://reference.aspose.com/gis/net/)** をご確認ください。

### Aspose.GIS を Web アプリケーションで使用できますか？
もちろんです！Aspose.GIS for .NET は ASP.NET、ASP.NET Core、その他すべてのサーバーサイド .NET 環境で動作します。

### Aspose.GIS のサポートはどこで受けられますか？
ご質問や問題がある場合は、**[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)** でコミュニティをご利用いただけます。

### 無料トライアルは利用可能ですか？
はい、**[here](https://releases.aspose.com/)** から無料トライアルを取得して Aspose.GIS の機能を体験できます。

### Aspose.GIS のライセンスはどのように購入できますか？
ライセンスを購入するには、**[purchase page](https://purchase.aspose.com/buy)** にアクセスしてください。

## 追加のよくある質問
**Q: 異なる SRS のジオメトリを追加しようとした場合はどうなりますか？**  
A: Aspose.GIS は `GisException` をスローします。ジオメトリを再投影するか、レイヤの SRS と共有していることを確認する必要があります。

**Q: 既存のレイヤの SRS を変更できますか？**  
A: はい、目的の SRS で新しいレイヤを作成し、フィーチャをコピーして必要に応じて再投影できます。

**Q: 3D 座標で作業できますか？**  
A: Aspose.GIS は Z 座標をサポートしています。Z 値を受け取るジオメトリコンストラクタを使用してください。

**Q: ライブラリはデータム変換を自動的に処理しますか？**  
A: `Geometry.Transform` を使用してジオメトリを再投影すると、Aspose.GIS が必要なデータムシフトを実行します。

**Q: 公式にテストされている .NET バージョンはどれですか？**  
A: ライブラリは .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7 でテストされています。

## 結論
これで、Aspose.GIS for .NET を使用してカスタム空間参照系を持つ **ベクトルレイヤの作成方法** を学びました。正しい SRS を設定し、ジオメトリを一貫して扱い、レイヤのメタデータを検証することで、任意の標準 GIS ソフトウェアと連携できる堅牢な GIS 機能を備えたアプリケーションを構築できます。

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [ベクトルレイヤの作成とレイヤ空間参照系の設定](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [File GDB でベクトルレイヤを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [レイヤの変更方法 – Aspose.GIS .NET レイヤ相互作用](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}