---
title: クロップレイヤーの機能
linktitle: クロップレイヤーの機能
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET で地理空間の魔法を解き放ちましょう!レイヤー フィーチャを簡単にトリミングします。今すぐ無料トライアルをダウンロードしてください。 #Aspose #GIS #地理空間
type: docs
weight: 19
url: /ja/net/layer-management/crop-layer-features/
---
## 導入
地理空間データ処理の広大な領域において、Aspose.GIS for .NET は強力なツールとして登場し、開発者に地理情報の処理におけるシームレスなエクスペリエンスを提供します。このチュートリアルでは、Aspose.GIS を使用してレイヤー フィーチャをトリミングするプロセスを説明し、特定の要件を満たすように地理空間データを調整できるようにします。
## 前提条件
地理空間操作の魅力を深く掘り下げる前に、次の前提条件が満たされていることを確認してください。
-  Aspose.GIS for .NET ライブラリ: Aspose.GIS ライブラリが .NET プロジェクトにインストールされていることを確認します。からダウンロードできます[ここ](https://releases.aspose.com/gis/net/).
- ドキュメント ディレクトリ: ドキュメントを保存するディレクトリを設定します。交換する`"Your Document Directory"`提供されたコード内で、ドキュメント ディレクトリへの実際のパスを指定します。
それでは、ステップバイステップのガイドを見てみましょう。
## 名前空間のインポート
まず、Aspose.GIS の機能を最大限に活用するために必要な名前空間をインポートします。
```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
## ステップ 1: レイヤーを開いてトリミングする
まず、GeoTiff レイヤーを開いて、定義されたポリゴンに基づいてトリミングします。これにより、地理空間データが特定の関心領域に合わせて絞り込まれることが保証されます。
```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```
## ステップ 2: ラスター情報を取得する
レイヤーがトリミングされたら、セル サイズ、空間参照系、境界などのラスター データに関する重要な情報を抽出します。
```csharp
//ラスターの読み取りと印刷
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```
## ステップ 3: 情報を表示する
抽出された情報を印刷して、地理空間データに対するトリミング プロセスの影響を理解します。
```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```
必要に応じてこれらの手順を繰り返し、特定のプロジェクト要件を満たすように地理空間データを調整および調整します。
## 結論
Aspose.GIS for .NET は、地理空間データを扱う開発者に可能性の領域を開きます。このステップバイステップ ガイドに従うことで、レイヤー フィーチャを効率的にトリミングして、より高度な地理空間操作の基礎を提供する方法を学習しました。
## よくある質問
### Q: Aspose.GIS for .NET の一時ライセンスは利用できますか?
 A: はい、一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか?
 A: ドキュメントは入手可能です[ここ](https://reference.aspose.com/gis/net/).
### Q: Aspose.GIS for .NET のサポートを求めたり、コミュニティに接続するにはどうすればよいですか?
 A: にアクセスしてください。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)サポートとコミュニティへの参加のために。
### Q: Aspose.GIS for .NET の無料トライアルをダウンロードできますか?
 A: はい、無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.GIS for .NET はどこで購入できますか?
 A: ライブラリを購入できます。[ここ](https://purchase.aspose.com/buy).