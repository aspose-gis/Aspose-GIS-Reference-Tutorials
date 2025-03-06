---
title: Aspose.GIS でファイル GDB レイヤーの精度グリッドを定義する
linktitle: ファイル GDB レイヤーの高精度グリッドの定義
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用してファイル GDB レイヤーの高精度グリッドを定義する方法を学習します。ステップバイステップのチュートリアルに従ってください。
weight: 21
url: /ja/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS でファイル GDB レイヤーの精度グリッドを定義する

## 導入
このチュートリアルでは、Aspose.GIS for .NET を使用してファイル ジオデータベース (GDB) レイヤーの精密グリッドを定義する方法を検討します。 Aspose.GIS は、さまざまな GIS ファイル形式で動作する包括的な地理空間機能を提供する強力な .NET ライブラリです。
## 前提条件
始める前に、次の前提条件がインストールされていることを確認してください。
1. Visual Studio: システムに Visual Studio がインストールされていることを確認します。
2.  Aspose.GIS for .NET ライブラリ: Aspose.GIS for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/gis/net/).
3. C# の基礎知識: C# プログラミング言語に精通していると、コード例を理解するのに役立ちます。
## 名前空間のインポート
まず、Aspose.GIS を操作するために必要な名前空間をインポートしましょう。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```
ここで、ファイル GDB レイヤーの高精度グリッドを定義する各ステップを詳しく見てみましょう。
## ステップ 1: データセットを作成する
```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```
ここでは、パスを指定し、`Dataset.Create`方法。
## ステップ 2: 精密グリッド オプションを定義する
```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```
このステップでは、ファイル GDB レイヤーの精度グリッド オプションを定義します。 X と Y の原点、XY スケール、M 原点、M スケールを指定し、有効な座標範囲が適用されるようにします。
## ステップ 3: レイヤーを作成する
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```
ここでは、指定した名前とオプションを使用してデータセット内に新しいレイヤーを作成します。 WGS84 空間参照系を使用します。
## ステップ 4: フィーチャをレイヤーに追加する
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```
このステップでは、ポイント ジオメトリを使用してフィーチャを構築し、それらをレイヤーに追加します。定義された精度グリッド外の座標を持つフィーチャを追加すると、例外がスローされることに注意してください。
## ステップ 5: 例外を処理する
```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // 値 -410 は有効範囲外です。
}
```
ここでは、有効な座標範囲外のレイヤーにフィーチャを追加するときに発生する可能性のある例外を処理します。
## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用してファイル GDB レイヤーの高精度グリッドを定義する方法を学びました。ステップバイステップのガイドに従うことで、.NET アプリケーションで地理空間データを効率的に操作できます。
## よくある質問
### Aspose.GIS for .NET を他の GIS ファイル形式で使用できますか?
はい、Aspose.GIS for .NET は、Shapefile、GeoJSON、KML などを含むさまざまな GIS ファイル形式をサポートしています。
### Aspose.GIS for .NET は .NET Core と互換性がありますか?
はい、Aspose.GIS for .NET は .NET Framework と .NET Core の両方と互換性があります。
### Aspose.GIS for .NET を使用して空間操作を実行できますか?
はい、Aspose.GIS for .NET を使用して、バッファリング、交差、距離計算などの空間操作を実行できます。
### Aspose.GIS for .NET は座標変換をサポートしていますか?
はい、Aspose.GIS for .NET は、異なる空間参照系間の座標変換をサポートします。
### Aspose.GIS for .NET の試用版はありますか?
はい、Aspose.GIS for .NET の無料試用版を次のサイトからダウンロードできます。[Webサイト](https://releases.aspose.com/gis/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
