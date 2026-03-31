---
date: 2025-12-28
description: Aspose.GIS for .NET を使用して File GDB レイヤーのグリッド設定方法を学び、レイヤーへのフィーチャ追加や座標範囲の検証を行う。
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Aspose.GIS の File GDB レイヤーにグリッドを設定する方法
url: /ja/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS で File GDB レイヤーのグリッドを設定する方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して File Geodatabase (GDB) レイヤーに **グリッドを設定する方法** を学びます。精度グリッドを設定すると、**座標範囲の検証** が行われ、範囲外エラーを防止でき、レイヤーに **フィーチャを追加** する際のデータの正確性と信頼性が保たれます。各手順を解説し、設定の重要性や一般的な落とし穴への対処方法も示します。

## クイック回答
- **「グリッドを設定する」とは何ですか？** GIS レイヤーの座標精度と有効範囲を定義することです。  
- **なぜ精度グリッドを使用するのですか？** 無効な座標からデータを保護し、ストレージ効率を向上させます。  
- **どのライブラリがこの機能を提供しますか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 試用版は利用可能ですが、商用利用にはライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.GIS は .NET Framework と .NET Core の両方をサポートしています。

## 精度グリッドとは何か、なぜ設定するのか
精度グリッドは、原点やスケールなどのパラメータの集合で、GIS エンジンが座標値をどのように丸めて保存するかを指示します。グリッドを定義すると **座標範囲の検証** が自動的に行われ、グリッド外のポイントを挿入しようとすると例外がスローされ、開発初期段階で **範囲外の処理** を行うことができます。

## 前提条件
作業を始める前に、以下がインストールされていることを確認してください。

1. **Visual Studio** – 最近のバージョン（Community、Professional、Enterprise のいずれか）。  
2. **Aspose.GIS for .NET** – [公式サイト](https://releases.aspose.com/gis/net/) からダウンロード。  
3. **基本的な C# の知識** – .NET コンソールプロジェクトを作成できること。

## 名前空間のインポート
Aspose.GIS を使用するために必要な名前空間をインポートします。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## File GDB レイヤーでグリッドを設定する方法
以下は、グリッドを構成し、レイヤーを作成し、**レイヤーにフィーチャを安全に追加** する手順を示すステップバイステップガイドです。

### 手順 1: データセットの作成
まず、新しい File Geodatabase データセットを作成します。ここにレイヤーが格納されます。

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### 手順 2: 精度グリッドオプションの定義
ここでグリッドパラメータを指定します。プロジェクトの座標系に合わせて原点やスケールを調整してください。

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

*`EnsureValidCoordinatesRange = true` フラグは、追加するすべてのフィーチャに対して **座標範囲の検証** を行うよう Aspose.GIS に指示します。*

### 手順 3: グリッド付きレイヤーの作成
先ほど定義したグリッドオプションを適用して、データセット内に新しいレイヤーを作成します。WGS84 空間参照系を使用します。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### 手順 4: レイヤーへのフィーチャ追加
2 つのポイントフィーチャを作成します。1 つ目はグリッド内に収まり、2 つ目は意図的にグリッド外に配置して **範囲外エラーの処理方法** を示します。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### 手順 5: 範囲外フィーチャ追加時の例外処理
2 番目のフィーチャを追加しようとすると、X 座標 (`-410`) が定義されたグリッド外であるため例外が発生します。例外を捕捉し、分かりやすいメッセージを出力します。

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### 手順 6: クリーンアップ
`using` ステートメントによりデータセットとレイヤーが自動的にクローズおよび破棄され、すべてのリソースが解放されます。

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|------|----------|------|
| **例外: “X value … is out of valid range.”** | 座標が精度グリッドの範囲外にある | `XOrigin`、`YOrigin`、または `XYScale` をデータが収まるように調整するか、入力データが定義範囲内であることを確認してください。 |
| **GIS ビューアにフィーチャが表示されない** | レイヤーが保存されていない、または空間参照が間違っている | `SpatialReferenceSystem.Wgs84` がビューアの CRS と一致しているか確認し、`Dataset.Create` が成功しているか確認してください。 |
| **M 値が無視される** | `MScale` が 0 または極端に小さい | 測定値を保存するために適切な `MScale`（例: `1e4`）を設定してください。 |

## FAQ

**Q: Aspose.GIS for .NET は他の GIS ファイル形式でも使用できますか？**  
A: はい、Shapefile、GeoJSON、KML など多数の形式をサポートしています。

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: 完全に対応しています。 .NET Framework、.NET Core、.NET 5/6+ で動作します。

**Q: バッファリングやインターセクションなどの空間演算は可能ですか？**  
A: はい、API にはバッファリング、インターセクション、距離計算などのメソッドが含まれています。

**Q: 座標変換機能は提供されていますか？**  
A: はい、組み込みの再投影ツールを使用してジオメトリを異なる空間参照系間で変換できます。

**Q: 試用版はありますか？**  
A: はい、[公式サイト](https://releases.aspose.com/gis/net/) から無料のトライアルをダウンロードできます。

---

**最終更新日:** 2025-12-28  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}