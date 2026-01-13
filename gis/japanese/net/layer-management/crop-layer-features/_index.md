---
date: 2026-01-13
description: Aspose.GIS for .NET を使用してレイヤー機能をクロップする方法を学びましょう。ポリゴンでラスタをクロップする方法、ラスタのセルサイズを抽出する方法、ラスタの範囲を取得する方法が含まれます。今すぐ無料トライアルをダウンロードしてください。
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET でレイヤー機能をクロップする方法
url: /ja/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# レイヤー機能のクロップ方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **how to crop layer** 機能を学びます。この強力なアプローチにより、**crop raster with polygon**、**extract raster cell size**、**retrieve raster extent** を行い、正確な地理空間分析が可能になります。ウェブマップ用のデータ準備、衛星画像のトリミング、関心領域の抽出など、ステップバイステップのガイドで作業手順を正確に示します。

## クイック回答
- **「crop layer」とは何ですか？** 提供されたジオメトリの境界に合わせてラスタまたはベクターレイヤーをトリムします。  
- **この例で使用されているジオメトリは何ですか？** WKT 形式で定義されたポリゴンです。  
- **クロップ後にセルサイズを抽出できますか？** はい、`CellSize` プロパティで取得できます。  
- **コード実行にライセンスは必要ですか？** 評価用に一時ライセンスが使用できますが、本番環境では正式ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 「how to crop layer」とは何ですか？
レイヤーをクロップするとは、データセットを特定の地理領域に限定し、定義された形状の外側にあるすべてを破棄することです。これによりファイルサイズが削減され、処理が高速化し、関心のある領域に分析を集中させることができます。

## なぜ Aspose.GIS をクロップに使用するのか？
- **High‑performance raster handling** – 大規模な GeoTiff ファイルに最適です。  
- **Simple API** – 任意のジオメトリでワンラインの `Crop` 呼び出しが可能です。  
- **Full .NET compatibility** – デスクトップ、サーバー、クラウドアプリで動作します。  
- **Accurate spatial reference handling** – CRS 情報を自動的に保持します。

## 前提条件
ジオスペーシャル操作の魔法に入る前に、以下の前提条件が整っていることを確認してください。

- Aspose.GIS for .NET Library: Aspose.GIS ライブラリが .NET プロジェクトにインストールされていることを確認してください。ダウンロードは [here](https://releases.aspose.com/gis/net/) から可能です。  
- Document Directory: ドキュメントを保存するディレクトリを設定します。提供されたコード内の `"Your Document Directory"` を実際のパスに置き換えてください。

それでは、ステップバイステップのガイドに進みましょう。

## 名前空間のインポート
Aspose.GIS のフルパワーを活用するために、必要な名前空間をインポートします。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ステップ 1: レイヤーを開いてクロップする（crop raster with polygon）
GeoTiff レイヤーを開き、定義したポリゴンに基づいてクロップします。これにより、地理空間データが関心領域に絞り込まれます。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## ステップ 2: ラスター情報の取得（extract raster cell size & retrieve raster extent）
レイヤーがクロップされたら、セルサイズ、空間参照系、境界など、ラスターデータに関する重要情報を抽出します。

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## ステップ 3: 情報の表示
抽出した情報を出力し、クロップ処理が地理空間データに与える影響を確認します。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

必要に応じてこれらの手順を繰り返し、プロジェクト固有の要件に合わせて地理空間データを調整してください。

## 一般的な問題と解決策
| 問題 | 解決策 |
|------|--------|
| **ポリゴンの向きが正しくない** | WKT ポリゴンが右手系ルール（外側リングは反時計回り）に従っていることを確認してください。 |
| **空間参照が欠如している** | ソース GeoTiff に CRS が含まれているか確認し、無い場合はクロップ前に手動で設定してください。 |
| **巨大ラスタでのパフォーマンス低下** | `layer.Crop` をダウンサンプルしたコピーで使用するか、タイル単位で処理してください。 |

## よくある質問
### Q: Aspose.GIS for .NET 用の一時ライセンスは利用できますか？
A: はい、[here](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Q: Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか？
A: ドキュメントは [here](https://reference.aspose.com/gis/net/) にあります。

### Q: Aspose.GIS for .NET のサポートやコミュニティに参加するにはどうすればよいですか？
A: サポートとコミュニティ交流は [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) をご利用ください。

### Q: Aspose.GIS for .NET の無料トライアルをダウンロードできますか？
A: はい、[here](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

### Q: Aspose.GIS for .NET はどこで購入できますか？
A: ライブラリは [here](https://purchase.aspose.com/buy) で購入できます。

### Q: 1 回の実行で複数のレイヤーをクロップできますか？
A: はい。各レイヤーをループし、同じ `Crop` 呼び出しに目的のジオメトリを渡すだけです。

### Q: API は他のラスターフォーマット（例: JPEG2000）をサポートしていますか？
A: Aspose.GIS は GDAL ドライバーが提供するすべてのフォーマットをサポートしており、JPEG2000、PNG なども含まれます。

## 結論
このガイドに従うことで、Aspose.GIS for .NET を使用した **how to crop layer** 機能を効率的に実装できるようになりました。**crop raster with polygon**、**extract raster cell size**、**retrieve raster extent** を簡単に行い、あらゆるプロジェクトのニーズに対応できます。再投影、ラスタースタイリング、ベクトル解析など、さらに高度な API を活用して地理空間ワークフローの可能性を最大限に引き出してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-01-13  
**テスト環境:** Aspose.GIS 24.10 for .NET  
**作者:** Aspose  

---