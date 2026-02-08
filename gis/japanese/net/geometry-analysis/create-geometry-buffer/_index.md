---
date: 2026-02-08
description: Aspose.GIS for .NET を使用してジオメトリのバッファリング方法を学び、インストール、名前空間のインポート、包含チェックを含む空間分析バッファを実行します。
linktitle: How to Create Buffer Using Aspose.GIS for .NET
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用したジオメトリのバッファリング方法
url: /ja/net/geometry-analysis/create-geometry-buffer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET 用 Aspose.GIS でジオメトリをバッファリングする方法

## はじめに
.NET 環境で地理空間データを扱う場合、**ジオメトリのバッファリング方法**を知っていることは、近接分析、ゾーニング、フィーチャの一般化に不可欠です。このチュートリアルでは、Aspose.GIS for .NET を使ったインストール手順、必要な名前空間のインポート、ラインおよびポリゴンジオメトリのバッファ生成、そして空間的包含の確認まで、プロセス全体を順を追って解説します。最後まで読めば、**空間分析バッファ**を自分のアプリケーションに適用できるようになります。

## クイック回答
- **ジオメトリバッファとは？** ソースジオメトリから指定距離内のすべての点を囲むポリゴンです。  
- **Aspose.GIS をバッファリングに使う理由は？** .NET Framework、.NET Core、.NET 5/6+ で動作するシンプルで高性能な API を提供します。  
- **Aspose.GIS のインストール方法は？** 公式サイトからライブラリをダウンロードし、Visual Studio で参照として追加します。  
- **包含判定はどう行う？** `SpatiallyContains` メソッドを使用して、点が生成したバッファ内にあるかテストします。  
- **バッファ以外の空間分析は可能か？** はい。インターセクト、ユニオン、距離計算などの操作もサポートされています。

## ジオメトリバッファとは？
ジオメトリバッファは、ポイント、ライン、またはポリゴンといったフィーチャの周囲に、ユーザーが定義した距離だけ広がる領域を作ります。この領域は、近隣フィーチャの特定、影響範囲の作成、複雑な形状の単純化に役立ちます。

## Aspose.GIS でジオメトリをバッファリングする方法
### 空間分析バッファに Aspose.GIS を使う理由
- **クロスプラットフォーム対応:** Windows、Linux、macOS で動作します。  
- **外部依存なし:** ネイティブ GIS ライブラリは不要です。  
- **豊富な API:** バッファリング、空間述語、座標系変換を含みます。  
- **パフォーマンス最適化:** 大規模データセットを効率的に処理でき、重厚な空間分析バッファに最適です。

## 前提条件
作業を始める前に、以下を用意してください。

- **Visual Studio 2019 以降**（または互換性のある .NET IDE）。  
- **.NET 6 SDK**（または .NET Core 3.1 以上）。  
- **Aspose.GIS for .NET ライブラリ** – 以下のインストール手順を参照してください。  

### Aspose.GIS for .NET のインストール方法
1. [ダウンロードリンク](https://releases.aspose.com/gis/net/) から Aspose.GIS for .NET ライブラリを取得します。  
2. Visual Studio でプロジェクトを右クリック → **Add** → **Reference…** → ダウンロードした DLL を参照して追加します。  
3. [Aspose](https://purchase.aspose.com/buy) からライセンスを取得するか、評価用に [一時ライセンス](https://purchase.aspose.com/temporary-license/) を使用します。

## 名前空間のインポート
API を使用開始するには、C# ファイルに必要な名前空間をインポートします。

### Aspose.GIS のインポート方法
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、バッファ作成プロセスをステップバイステップで見ていきましょう。

## 手順ガイド

### 手順 1: ジオメトリバッファの作成
まず、バッファのソースとなるシンプルな `LineString` ジオメトリを定義します。

```csharp
// Define a LineString geometry
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```

このスニペットでは `LineString` を作成し、2 つのポイントを追加して (0,0) から (3,3) への対角線を構成しています。

### 手順 2: LineString のバッファ生成
次に、**正の距離** 1 単位でラインの周囲にバッファを生成します。

```csharp
// Generate a buffer for the LineString with a positive distance
var lineBuffer = line.GetBuffer(distance: 1);
```

`GetBuffer` メソッドは、元のラインから 1 単位以内にあるすべての点を含むポリゴンを返します。

### 手順 3: 空間的包含の確認
ここでは、**包含判定の方法** を示すために、特定のポイントがバッファ内に入っているかテストします。

```csharp
// Check spatial containment of points within the buffer
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     // True
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); // True
```

`SpatiallyContains` 述語は、ポイントがバッファポリゴン内部にある場合に `true` を返します。

### 手順 4: ポリゴンジオメトリの定義
次に、**負の距離** でバッファリングする例として `Polygon` ジオメトリを作成します。負の距離は形状を縮小します。

```csharp
// Define a Polygon geometry
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```

このポリゴンは、頂点が (0,0)、(0,3)、(3,3)、(3,0) の正方形を表します。

### 手順 5: ポリゴンのバッファ生成
距離 –1 単位を適用すると、ポリゴンは内側へ収縮します。

```csharp
// Generate a buffer for the Polygon with a negative distance
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```

結果として得られる `polygonBuffer` は、内部領域を作るために使える小さな正方形です。

### 手順 6: バッファ外周リングの座標取得
最後に、バッファの外周リングの座標を取得して表示します。

```csharp
// Access points of the exterior ring of the buffer Polygon
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```

このループは、縮小されたポリゴンの各頂点を出力し、バッファジオメトリが正しく生成されたことを確認します。

## よくある問題と対策
| 問題 | 対策 |
|------|------|
| **バッファが `null` を返す** | ジオメトリの座標系に対して距離値が適切か確認してください。 |
| **`SpatiallyContains` が常に `false` を返す** | 両ジオメトリが同じ空間参照系 (CRS) を使用しているか確認してください。 |
| **大規模データセットでパフォーマンスが低下する** | ジオメトリをバッチ処理し、同一の `GeometryFactory` インスタンスを再利用してください。 |

## FAQ

**Q: Aspose.GIS for .NET は他の .NET フレームワークでも使用できますか？**  
A: はい、.NET Framework、.NET Core、.NET 5、.NET 6 で動作します。

**Q: Aspose.GIS for .NET で空間分析は可能ですか？**  
A: もちろんです。バッファリング、インターセクト、距離計算など多数の機能をサポートしています。

**Q: データセットサイズに制限はありますか？**  
A: API は大規模データセット向けに最適化されていますが、メモリ使用量はロードするジオメトリのサイズに依存します。

**Q: 異なる空間参照系はサポートされていますか？**  
A: はい、幅広い座標系を扱い、オンザフライでの変換も可能です。

**Q: 技術サポートはどこで受けられますか？**  
A: サポートは Aspose.GIS コミュニティフォーラム（[https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33)）で受けられます。

---

**最終更新日:** 2026-02-08  
**テスト環境:** Aspose.GIS for .NET（最新バージョン）  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}