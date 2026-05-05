---
date: 2026-05-05
description: Aspose.GIS for .NET を使用して、ラスタセルサイズの取得方法とラスタ形式のワープ方法を学びます。空間データ可視化のためのステップバイステップガイド。
keywords:
- get raster cell size
- how to warp raster
- Aspose GIS raster
linktitle: ワープラスター形式
second_title: Aspose.GIS .NET API
title: ラスタセルサイズを取得 – Aspose.GISでラスタ形式をワープ
url: /ja/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ラスタセルサイズの取得 – ラスタ形式のワープ

## はじめに
Aspose.GIS for .NET を使用した地理空間プログラミングのエキサイティングな世界へようこそ！このチュートリアルでは、ラスタをワープした後に **ラスタセルサイズを取得** し、**ラスタ形式をワープする方法** をステップバイステップで学びます。経験豊富な開発者でも、これから始める方でも、GeoTIFF の操作の奥深さに踏み込み、空間データに新たな視点を提供します。

## クイック回答
- **主な目的は何ですか？** ワープ操作を実行した後にラスタセルサイズを取得することです。  
- **使用されているライブラリはどれですか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です；本番環境ではライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **サンプルの実行にどれくらい時間がかかりますか？** 一般的なマシンで1分未満です。

## 前提条件
この旅に出る前に、以下の前提条件が整っていることを確認してください：
- Aspose.GIS for .NET: まだインストールしていない場合は、Aspose.GIS ライブラリをダウンロードしてインストールしてください。最新バージョンは[here](https://releases.aspose.com/gis/net/)で見つけられます。  
- Your Document Directory: ドキュメントを保存するディレクトリを設定してください。これはラスタワープ処理中のファイル管理に重要です。  

これで準備が整ったので、コードに入りましょう。

## 名前空間のインポート
まず最初に、適切なツールが揃っていることを確認しましょう。地理空間の冒険を開始するために必要な名前空間をインポートしてください：

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## 手順 1: パスの初期化
まず、ドキュメントディレクトリへのパスを設定します。ここで全ての処理が行われます：

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: ラスタレイヤーのオープン
GeoTiff ラスタレイヤーを開き、変換の準備をします。このステップで次のワープ操作の土台が整います：

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## 手順 3: ラスタのワープ
それでは、ワープ操作を実行しましょう。ターゲットの寸法と空間参照系を指定して、ラスタデータに新たな命を吹き込みます：

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## 手順 4: ラスタ情報の抽出
変換されたラスタの秘密を明らかにする時です。セルサイズ、空間参照系、境界、バンド数などの重要な情報を抽出します：

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## 手順 5: ラスタ詳細の出力
取得した詳細情報を出力し、ワープされたラスタの洞察を提供しましょう：

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## 手順 6: ラスタバンドの探索
ラスタの個々のバンドに踏み込み、データ型、統計情報、ノーデータ値の有無を解明します：

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
ワープ後のセルサイズを把握することで、生成されたデータセットの空間分解能を理解できます。複数のレイヤーを整合させる必要がある場合や、地上距離に依存する解析を行う場合、あるいはワープが意図した詳細度を保持しているか確認する際に重要です。

## ラスタ形式を効率的にワープする方法
`Warp` メソッドは複雑な再投影ロジックを抽象化し、ターゲットの寸法やターゲット空間参照系といった入力パラメータに集中できるようにします。これにより、座標系間のデータ変換、異なる解像度へのリサンプリング、特定領域へのクリップがシンプルになります。

## よくある問題と解決策
- **予期しないセルサイズの値:** `Height` と `Width` パラメータが目的の出力解像度と一致していることを確認してください。  
- **空間参照が欠落:** `spatialRefSys` が null を返す場合、ソースの GeoTIFF に適切な CRS メタデータが含まれているか確認してください。  
- **NoData の処理:** `warped.NoDataValues.IsNull()` を使用して欠損データを検出できます。ワープ前にカスタムの NoData 値を割り当てることも可能です。

## よくある質問

**Q: Aspose.GIS はすべてのラスタ形式に対応していますか？**  
A: はい、Aspose.GIS は幅広いラスタ形式をサポートしており、さまざまな空間データセットを柔軟に扱えます。

**Q: ジオリファレンスされていない画像でもラスタのワープを実行できますか？**  
A: Aspose.GIS はジオリファレンスされたデータを扱うよう設計されており、正確な変換を保証します。ラスタ画像に適切な空間参照情報があることを確認してください。

**Q: Aspose.GIS コミュニティに貢献するにはどうすればよいですか？**  
A: [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)でディスカッションに参加し、経験を共有したり、質問したり、他の開発者と協力してください。

**Q: Aspose.GIS の無料トライアルは利用できますか？**  
A: はい、[here](https://releases.aspose.com/) から無料トライアルをダウンロードして Aspose.GIS の機能を試すことができます。

**Q: Aspose.GIS の一時ライセンスは入手可能ですか？**  
A: はい、一時ライセンスが必要な場合は[here](https://purchase.aspose.com/temporary-license/)で取得できます。

---

**最終更新日:** 2026-05-05  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}