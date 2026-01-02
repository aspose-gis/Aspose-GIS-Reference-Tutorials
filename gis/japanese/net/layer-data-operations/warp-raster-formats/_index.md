---
date: 2026-01-02
description: .NET 用 Aspose.GIS を使用してラスタをワープする方法を学びましょう。このステップバイステップガイドでは、ラスタ形式のワープ、メタデータの抽出、ラスタバンドの操作方法を示します。
linktitle: How to Warp Raster Formats
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET でラスタ形式を変形する方法
url: /ja/net/layer-data-operations/warp-raster-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ラスター形式のワープ方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **ラスタをワープ** する方法を学びます。GeoTIFF の再投影や解像度の変更、あるいはラスタの内部詳細を調べるだけでも、以下の手順でファイルの読み込みから各バンドの統計情報の検査まで、全プロセスを案内します。さっそく始めましょう！

## クイック回答
- **“warp raster” とは何ですか？** 新しい空間参照系または解像度にラスターデータを再投影およびリサンプリングするプロセスです。  
- **どのライブラリがワープを処理しますか？** Aspose.GIS for .NET はラスターレイヤー上の `Warp` メソッドを提供します。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている入力形式は？** 例では GeoTIFF を使用していますが、Aspose.GIS は多数のラスタ形式をサポートしています。  
- **典型的な実行時間は？** 小さな 40 × 40 ラスターのワープは、最新の PC で 1 秒未満で完了します。

## ラスター ワープとは何か？
ラスターワープ（または再投影）とは、ラスタセルをある座標系から別の座標系へ変換し、必要に応じてピクセルサイズも調整することです。異なる空間参照系を使用するレイヤーを組み合わせる場合や、特定の地図スケールに合わせたラスタが必要な場合に不可欠です。

## なぜ Aspose.GIS をラスターワープに使用するのか？
- **Pure .NET API** – ネイティブ依存がなく、Windows、Linux、macOS で動作します。  
- **フル機能** – GeoTIFF、JPEG2000、PNG などを扱えます。  
- **高精度リサンプリング** – 最近傍、バイリニア、キュービック補間をサポート（デフォルトはバイリニア）。  
- **統合が容易** – ASP.NET、コンソールアプリ、任意の .NET サービスで使用できます。

## 前提条件
- Aspose.GIS for .NET をインストールします。公式ダウンロードページ **[here](https://releases.aspose.com/gis/net/)** から最新パッケージを取得してください。  
- サンプル GeoTIFF（`raster_float32.tif`）を保存するフォルダーを用意します。  
- .NET 6（またはそれ以降）SDK がインストールされていること。

## 名前空間のインポート
まず、必要な .NET 名前空間をスコープに持ち込みます。

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Raster;
using Aspose.Gis.SpatialReferencing;
```

## ステップ 1: パスの初期化
ラスターファイルが格納されているディレクトリを指すパスを設定します。

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: ラスターレイヤーを開く
GeoTIFF ラスターレイヤーを開きます。これにより、画像が以降の操作のために準備されます。

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_float32.tif")))
```

## ステップ 3: ラスターをワープする
ワープ操作を適用します。ここでは、WGS‑84 座標系で 40 × 40 のラスタを要求しています。

```csharp
using (var warped = layer.Warp(new WarpOptions(){Height = 40, Width = 40, TargetSpatialReferenceSystem = SpatialReferenceSystem.Wgs84}))
```

## ステップ 4: ラスター情報の抽出
ワープされたラスタから有用なメタデータを取得します。

```csharp
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
var bandCount = warped.BandCount;
```

## ステップ 5: ラスターの詳細を出力する
抽出した情報をコンソールに出力します。

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
Console.WriteLine($"bandCount: {bandCount}");
```

## ステップ 6: ラスターバンドを調査する
各バンドを反復処理し、データ型、統計情報、NoData の取り扱いを確認します。

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

## よくある問題と解決策
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **出力ラスタが空** | ターゲット SRS が認識されません | EPSG コード（`SpatialReferenceSystem.Wgs84` = 4326）を確認し、ソースラスタに有効な SRS が含まれていることを確認してください。 |
| **NoData 値がゼロとして表示される** | ソースで `NoDataValues` が設定されていない | `warped.NoDataValues` を使用して、元のラスタで明示的に NoData を設定するか、ワープ後に処理してください。 |
| **大規模ラスタでのパフォーマンス低下** | デフォルトのバイリニアリサンプリングは CPU に負荷がかかります | より高速（ただし滑らかさは低下）な結果を得るには、`WarpOptions.Interpolation = InterpolationMode.NearestNeighbour` を使用してください。 |

## 結論
これで、Aspose.GIS for .NET を使用して **ラスタをワープ** する方法、メタデータの抽出、各バンドの統計の確認ができるようになりました。この機能により、高度な空間解析、マップ作成、異種の地理空間データセットのシームレスな統合が可能になります。

## FAQ
### Aspose.GIS はすべてのラスタ形式に対応していますか？
はい、Aspose.GIS は幅広いラスタ形式をサポートしており、さまざまな空間データセットの取り扱いに柔軟性があります。

### ジオリファレンスされていない画像でもラスターワープは可能ですか？
Aspose.GIS はジオリファレンスされたデータを扱うよう設計されており、正確な変換を保証します。ラスタ画像に適切な空間参照情報があることを確認してください。

### Aspose.GIS コミュニティに貢献するには？
経験を共有したり質問したり、他の開発者と協力したりするために、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) に参加してください。

### Aspose.GIS の無料トライアルはありますか？
はい、**[here](https://releases.aspose.com/)** から無料トライアルをダウンロードして Aspose.GIS の機能を体験できます。

### Aspose.GIS の一時ライセンスは利用できますか？
はい、一時ライセンスが必要な場合は **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

## よくある質問

**Q: GeoTIFF 以外にどのラスタ形式をワープできますか？**  
A: Aspose.GIS は JPEG、PNG、BMP など多数の一般的なラスタ形式をサポートしています。`Warp` メソッドはライブラリが開くことのできるすべての形式で使用できます。

**Q: ワープ操作は元のファイルを変更しますか？**  
A: いいえ。`Warp` メソッドは新しいインメモリラスタ（`warped`）を作成し、ソースファイルはそのままです。

**Q: 出力解像度を変更するには？**  
A: `WarpOptions` の `Height` と `Width` プロパティを目的のピクセルサイズに調整してください。

**Q: ワープしたラスタをディスクに保存できますか？**  
A: はい。ワープ後に `warped.Save("output.tif", Drivers.GeoTiff)` を使用して結果をファイルに書き出せます。

**Q: カスタム座標系のサポートはありますか？**  
A: もちろんです。適切な EPSG コードまたは WKT 定義を持つカスタム `SpatialReferenceSystem` インスタンスを指定してください。

**最終更新日:** 2026-01-02  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}