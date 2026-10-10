---
date: 2026-10-10
description: Aspose.GIS for .NET を使用してラスタ形式をワープし、ラスタセルサイズを取得し、ラスタ解像度を変更する方法を学びます –
  空間データ可視化のためのステップバイステップガイド。
keywords:
- get raster cell size
- change raster resolution
- convert geotiff .net
lastmod: 2026-10-10
linktitle: ラスタ形式のワープ
og_description: Aspose.GIS for .NET を使用してラスタをワープした後のラスタセルサイズを取得します。このチュートリアルでは、ラスタ解像度の変更、GeoTIFF
  ファイルの変換、詳細なラスタメタデータの抽出を数ステップで行う方法を示します。
og_image_alt: 'Developer guide: Get raster cell size and warp raster formats using
  Aspose.GIS for .NET'
og_title: Aspose.GIS でラスタセルサイズを取得し、ラスタをワープ
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to get raster cell size and change raster resolution by warping
    raster formats using Aspose.GIS for .NET – a step‑by‑step guide for spatial data
    visualization.
  headline: Get raster cell size – warp raster formats
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS supports a wide range of raster formats, providing flexibility
      in handling various spatial datasets.
    question: Is Aspose.GIS compatible with all raster formats?
  - answer: Aspose.GIS is designed to handle georeferenced data, ensuring accurate
      transformations. Ensure your raster images have proper spatial reference information.
    question: Can I perform raster warping on non‑georeferenced images?
  - answer: Join the discussion on the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to share your experiences, ask questions, and collaborate with other developers.
    question: How can I contribute to the Aspose.GIS community?
  - answer: Yes, you can explore the capabilities of Aspose.GIS by downloading a free
      trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- raster processing
- Aspose.GIS
- .NET GIS
- geotiff warp
title: ラスタセルサイズを取得 – ラスタ形式のワープ
url: /ja/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ラスタセルサイズの取得 – ラスタ形式のワープ

## はじめに
このチュートリアルでは、ワープ操作を実行した後に **get raster cell size** を取得し、Aspose.GIS for .NET を使用して任意の GeoTIFF の **change raster resolution** 方法を学びます。ウェブマップサービス用にデータを準備する場合や、空間解析のためにレイヤーを揃える場合、または再投影が意図した詳細を保持したかを確認するだけの場合でも、これらの手順によりラスタのジオメトリとメタデータを完全に制御できます。ラスタの読み込みからセルサイズやその他の主要プロパティの抽出まで、プロセスを順に見ていきましょう。

## 簡単な回答
- **What is the primary goal?** ワープ操作を実行した後に raster cell size を取得します。  
- **Which library is used?** Aspose.GIS for .NET.  
- **Do I need a license?** 無料トライアルが利用可能です。製品版ではライセンスが必要です。  
- **What .NET versions are supported?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **How long does the example take to run?** 一般的なマシンで1分未満です。  

## 前提条件
この作業を始める前に、以下の前提条件が整っていることを確認してください。

- Aspose.GIS for .NET: まだインストールしていない場合は、Aspose.GIS ライブラリをダウンロードしてインストールしてください。最新バージョンは[here](https://releases.aspose.com/gis/net/)で確認できます。
- Your Document Directory: ドキュメントを保存するディレクトリを設定してください。ラスタのワープ処理中のファイル管理に重要です。

準備が整ったので、コードに入りましょう。

## 名前空間のインポート
`Aspose.GIS` 名前空間は、ラスタとベクタ操作のコアクラスを提供します。必要な名前空間をインポートして、地理空間の冒険を始めましょう。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## ステップ 1: パスの初期化
まず、ドキュメントディレクトリへのパスを設定します。ここがすべての処理が行われる場所です：

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: ラスター レイヤーを開く
`RasterLayer` クラスは、メモリにロードされた単一のラスタデータセットを表します。GeoTIFF を開くことで、以降の変換の準備が整います。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## ステップ 3: ラスターをワープする
`Warp` メソッドは、ラスタを新しい座標参照系と解像度に再投影およびリサンプリングします。複雑な計算を抽象化し、1 回の呼び出しで対象の寸法と対象空間参照系を指定できます。  
`WarpOptions` を使用すると、出力幅・高さ、対象空間参照系などのパラメータを定義できます。

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## ステップ 4: ラスター情報の抽出
ワープ後、結果のラスタからセルサイズ、空間参照系、境界、バンド数などの重要なメタデータを問い合わせることができます。これらのプロパティにより、変換が期待通りに動作したかを検証できます。

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## ステップ 5: ラスターの詳細を出力
抽出した主要な詳細を出力しましょう。これにより、ワープされたラスタのジオメトリと内容の簡易スナップショットが得られます。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## ステップ 6: ラスタバンドの探索
`RasterBand` は、赤、緑、青、標高値など、ラスタデータの個々のバンド（レイヤー）を表します。各バンドは別個のデータチャンネルを保持し、データ型、統計、NoData の取り扱いを検査できます。

```csharp
for (int i = 0; i < warped.BandCount; i++)
{
    var dataType = warped.GetBand(i).DataType;
    var hasNoData = !warped.NoDataValues.IsNull();
    var statistics = warped.GetStatistics(i);
    Console.WriteLine();
    Console.WriteLine($"Band: {i}");
    Console.WriteLine($"dataType: {dataType}");
    Console.WriteLine($"statistics: {statistics}");
    Console.WriteLine($"hasNoData: {hasNoData}");
    if (hasNoData)
        Console.WriteLine($"noData: {warped.NoDataValues[i]}");
}
```

## なぜラスタセルサイズを取得するのか？
ワープ後にラスタセルサイズを取得すると、各ピクセルが表す地上距離が分かります。この情報は、複数のレイヤーを揃える必要がある場合や、距離ベースの解析を行う場合、またはワープが必要な空間解像度を保持したことを確認する際に不可欠です。

## ラスタ形式を効率的にワープする方法
`Warp` メソッドは複雑な再投影ロジックを抽象化し、対象の寸法や対象空間参照系といった入力パラメータに集中できるようにします。これにより、座標系間のデータ変換、別解像度へのリサンプリング、特定領域へのクリップが簡単に行えます。

## Aspose.GIS の具体的なメリット
Aspose.GIS は **30 以上のラスタ形式** をサポートし、**2 GB** までのファイルを画像全体をメモリにロードせずに処理でき、一般的なサーバハードウェア上で高速かつメモリ効率の良い変換を実現します。

## 一般的な問題と解決策
- **Unexpected cell size values:** `Height` と `Width` パラメータが目的の出力解像度と一致していることを確認してください。  
- **Missing spatial reference:** `spatialRefSys` が null を返す場合、元の GeoTIFF に適切な CRS メタデータが含まれているか確認してください。  
- **NoData handling:** `warped.NoDataValues.IsNull()` を使用して欠損データを検出できます。また、ワープ前にカスタム NoData 値を設定することも可能です。  

## よくある質問

**Q: Is Aspose.GIS compatible with all raster formats?**  
A: はい、Aspose.GIS は幅広いラスタ形式に対応しており、さまざまな空間データセットの取り扱いに柔軟性があります。

**Q: Can I perform raster warping on non‑georeferenced images?**  
A: Aspose.GIS はジオリファレンスされたデータを扱うよう設計されており、正確な変換を保証します。ラスタ画像に適切な空間参照情報があることを確認してください。

**Q: How can I contribute to the Aspose.GIS community?**  
A: [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) に参加して、経験を共有したり、質問したり、他の開発者と協力したりしてください。

**Q: Is there a free trial available for Aspose.GIS?**  
A: はい、無料トライアルをダウンロードして Aspose.GIS の機能を試すことができます。[here](https://releases.aspose.com/)。

**Q: Are temporary licenses available for Aspose.GIS?**  
A: はい、一時的なライセンスが必要な場合は、[here](https://purchase.aspose.com/temporary-license/) から取得できます。

---

**最終更新日:** 2026-10-10  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose

## 関連チュートリアル

- [レイヤーデータ操作](/gis/net/layer-data-operations/)
- [Aspose.GIS を使用して空間参照 WGS84 の File GDB データセットにレイヤーを追加する方法](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Aspose.GIS for .NET を使用して SRS 付きベクターレイヤーを作成する方法](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}