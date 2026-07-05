---
date: 2026-07-05
description: Aspose.GIS for .NET を使用してレイヤ機能をクロップする方法を学びます。ポリゴンで raster をクロップする方法、raster
  の cell size を抽出する方法、raster の extent を取得する方法が含まれます。今すぐ free trial をダウンロードしてください。
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: レイヤ機能のクロップ方法
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用したレイヤ機能のクロップ方法
url: /ja/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# レイヤー機能のクロップ方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **how to crop layer** 機能を学びます。この強力なライブラリを使うと、**crop raster with polygon**、**extract raster cell size**、**retrieve raster extent** を行い、正確なジオスペーシャル分析が可能です。ウェブマップ用にデータを準備したり、衛星画像をトリミングしたり、関心領域を抽出したりする場合でも、このステップバイステップガイドは、作業を迅速かつ確実に実行する方法を正確に示します。

## クイック回答
- **What does “crop layer” mean?** 提供されたジオメトリの境界に合わせてラスタまたはベクターレイヤーをトリミングし、外側のすべてを破棄します。  
- **Which geometry is used in this example?** この例で使用されているジオメトリは、WKT（Well‑Known Text）形式で定義されたポリゴンです。  
- **Can I extract cell size after cropping?** はい – `CellSize` プロパティはラスタセルの幅と高さを返します。  
- **Do I need a license to run the code?** 評価には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **What .NET versions are supported?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7 がサポートされています。

## “how to crop layer” とは何ですか？
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** この操作はファイルサイズを削減し、後続の処理を高速化し、関心のある領域に分析を集中させます。データを関心領域に限定することで、スタイリング、分析、公開などの下流ワークフローも簡素化され、元の座標参照系とメタデータは保持されます。

## なぜ Aspose.GIS をクロップに使用するのか？
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** このライブラリは単一行の `Crop` 呼び出し、自動 CRS ハンドリング、マルチスレッド性能を提供し、典型的なサーバー上で 500 MB の GeoTIFF を 1 秒未満でトリミングできます。

## 前提条件
ジオスペーシャル操作の魔法に入る前に、以下の前提条件が整っていることを確認してください。

- Aspose.GIS for .NET Library: .NET プロジェクトに Aspose.GIS ライブラリがインストールされていることを確認してください。ダウンロードは [こちら](https://releases.aspose.com/gis/net/) から。  
- Document Directory: ドキュメントを保存するディレクトリを設定します。提供されたコード内の `"Your Document Directory"` を実際のドキュメントディレクトリのパスに置き換えてください。

それでは、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート
`Aspose.Gis` 名前空間にはラスタとベクタの処理に必要なすべてのコア型が含まれています。これをインポートすると、`Layer`、`Geometry`、および関連クラスにアクセスできます。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ポリゴンでレイヤーをクロップするには？
`Crop` は `Layer` クラスのメソッドで、ジオメトリで定義されたラスタのサブセットを抽出します。ソースラスタを読み込み、ポリゴンジオメトリを定義し、`Crop` メソッドを呼び出すだけで、操作は単一行のコードで実行されます。このメソッドは、ポリゴン内部のピクセルのみを含む新しいラスタを返し、元の空間参照を自動的に保持します。

## 手順 1: レイヤーを開いてクロップする（ポリゴンでラスタをクロップ）
`Layer` は開く、クエリ実行、編集が可能なラスタデータセットを表します。`Layer` クラスは開く、クエリ実行、編集が可能なラスタデータセットを表します。GeoTIFF を開き、ポリゴンでクロップすることで、関心領域を数行のコードで抽出できます。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 手順 2: ラスタ情報の取得（ラスタセルサイズの抽出とラスタ範囲の取得）
`CellSize` は各ラスタセルの幅と高さ（座標単位）を提供します。  
`Extent` はラスタの地理的バウンディングボックスを返します。  
`CellSize` プロパティは各ラスタセルの幅と高さ（座標単位）を提供し、`Extent` プロパティはクロップされたラスタの地理的バウンディングボックスを返します。これらの情報は、面積測定や再投影などの下流計算に不可欠です。

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 手順 3: 情報の表示
抽出した情報を出力して、クロップ処理がジオスペーシャルデータに与える影響を確認します。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

必要に応じてこれらの手順を繰り返し、ジオスペーシャルデータを洗練・調整し、特定のプロジェクト要件に合わせてください。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **ポリゴンの向きが正しくない** | WKT ポリゴンが右手規則（外側リングは反時計回り）に従っていることを確認してください。 |
| **空間参照が欠如している** | ソースの GeoTiff に CRS が含まれているか確認してください。含まれていない場合は、クロップ前に手動で設定してください。 |
| **巨大ラスタでのパフォーマンス低下** | `layer.Crop` をダウンサンプルしたコピーで使用するか、ラスタをタイル単位で処理してください。 |

## よくある質問
**Q: Aspose.GIS for .NET の一時ライセンスは利用可能ですか？**  
A: はい、[こちら](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか？**  
A: ドキュメントは[こちら](https://reference.aspose.com/gis/net/) で利用できます。

**Q: Aspose.GIS for .NET のサポートを受けるか、コミュニティとつながるにはどうすればよいですか？**  
A: サポートやコミュニティ参加は [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) をご覧ください。

**Q: Aspose.GIS for .NET の無料トライアルをダウンロードできますか？**  
A: はい、[こちら](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

**Q: Aspose.GIS for .NET はどこで購入できますか？**  
A: ライブラリは[こちら](https://purchase.aspose.com/buy) から購入できます。

**Q: 1 回の実行で複数のレイヤーをクロップできますか？**  
A: はい、各レイヤーをループし、目的のジオメトリで同じ `Crop` 呼び出しを適用できます。

**Q: API は他のラスタ形式（例: JPEG2000）をサポートしていますか？**  
A: Aspose.GIS は基盤となる GDAL ドライバーが提供するすべての形式、JPEG2000、PNG などをサポートしています。

## 結論
このガイドに従うことで、Aspose.GIS for .NET を使用して **how to crop layer** 機能を効率的に実行できるようになりました。**crop raster with polygon**、**extract raster cell size**、**retrieve raster extent** を簡単に行い、あらゆるプロジェクトの要件に合わせられます。再投影、ラスタスタイリング、ベクトル分析などの API もさらに探求し、ジオスペーシャルワークフローの可能性を最大限に引き出してください。

---

**最終更新日:** 2026-07-05  
**テスト環境:** Aspose.GIS 24.10 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET でポリゴンジオメトリを作成する方法](/gis/net/geometry-creation/create-polygon-geometry/)
- [レイヤー属性の取得 – Aspose.GIS for .NET でレイヤー属性情報を取得する方法](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [C# でポリゴンジオメトリを作成し、Aspose.GIS for .NET で交差をチェックする方法](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}