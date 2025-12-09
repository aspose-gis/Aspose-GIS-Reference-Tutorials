---
date: 2025-12-09
description: Aspose.GIS for .NET を使用してポリゴン内の点をチェックする方法を学びましょう。表面上の点を取得し、C# でポリゴンを作成し、ポリゴン上の点を取得するステップバイステップガイドです。
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: ポリゴン内の点をチェックし、表面上の点を取得
url: /ja/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ポリゴン内の点のチェックと表面上の点の取得

## Introduction
このチュートリアルでは、Aspose.GIS for .NET を使用して **ポリゴン内の点をチェックする方法** を学び、ジオメトリの **表面上の点を取得する方法** も確認します。C# でポリゴンを作成し、ポリゴンの表面上にある点を取得し、その点が実際にポリゴン内部にあるかを検証する手順を解説します。最後まで読むと、任意の .NET ジオスペーシャル アプリケーションにすぐに組み込めるコードスニペットが手に入ります。

## Quick Answers
- **「ポリゴン内の点をチェックする」とは何ですか？**  
  指定した座標がポリゴンジオメトリの境界内にあるかどうかを確認することです。  
- **ポリゴンの内部にある点を返すメソッドはどれですか？**  
  `GetPointOnSurface()` がポリゴン内部に必ず存在する点を返します。  
- **サンプルを実行するのにライセンスは必要ですか？**  
  評価用の無料トライアルで動作しますが、本番環境では正式ライセンスが必要です。  
- **対応している .NET バージョンは？**  
  .NET Framework、.NET Core、.NET Standard のすべてに対応しています。  
- **実装にかかる時間はどれくらいですか？**  
  コピー、コンパイル、実行までおおよそ 5〜10 分です。

## Prerequisites
開始する前に、以下の項目を準備してください。

### Environment Setup
1. Aspose.GIS for .NET をインストール: [こちら](https://releases.aspose.com/gis/net/) から Aspose.GIS for .NET ライブラリをダウンロードしてインストールします。  
2. 開発環境の設定: .NET 開発用の環境が整っていることを確認してください。Visual Studio など、お好みの .NET 開発環境をセットアップします。  
3. C# の基礎知識: まだ慣れていない場合は、C# の基本文法を復習しておきましょう。  
4. ドキュメントへのアクセス: チュートリアル中に参照できるよう、[ドキュメント](https://reference.aspose.com/gis/net/) を手元に用意しておきます。

## Import Namespaces
実装に入る前に、必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

環境設定と名前空間のインポートが完了したので、例を複数のステップに分解して詳しく見ていきます。

## How to Create Polygon C#  
まず、**ポリゴンジオメトリを作成** します。ポリゴンの外周リングを頂点で定義します。

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

## How to Get Point on Surface  
次に、`GetPointOnSurface()` メソッドを使用してポリゴンの表面上の点を取得します。これが **表面上の点を取得** するステップです。

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## How to Check Point Inside Polygon  
取得した点がポリゴン内部にあるかどうかを `SpatiallyContains()` メソッドで検証します。これにより **ポリゴン上の点を取得** し、続いてその点が内部にあるかをチェックできます。

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Common Issues and Solutions
- **空のポリゴン** – 外周リングに少なくとも 3 つの異なる頂点が必要です。足りないと `GetPointOnSurface()` が未定義の点を返す可能性があります。  
- **時計回り vs 反時計回り** – リングの向きは包含チェックには影響しませんが、他の空間演算で一貫した winding order を保つと安全です。  
- **座標系** – 本例は単純なデカルト平面を使用しています。実世界の座標を扱う場合は、CRS（座標参照系）が正しく定義されていることを確認してください。

## Conclusion
このチュートリアルでは、Aspose.GIS for .NET を使って **ポリゴン内の点をチェック** し、**表面上の点を取得** してその包含性を検証する方法を学びました。Aspose.GIS を利用すれば、ジオスペーシャル データの取り扱いが効率的かつシンプルになり、開発者は堅牢なジオスペーシャル アプリケーションを構築できます。

## FAQ's
### Aspose.GIS は他の .NET フレームワークと互換性がありますか？
はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard など、さまざまな .NET フレームワークをサポートしています。

### 購入前に Aspose.GIS を試すことはできますか？
はい、[こちら](https://releases.aspose.com/) から Aspose.GIS の無料トライアルをダウンロードできます。

### Aspose.GIS のサポートはどこで受けられますか？
Aspose.GIS フォーラムは [こちら](https://forum.aspose.com/c/gis/33) で利用でき、他のユーザーや開発者と情報交換や質問が可能です。

### Aspose.GIS は一時ライセンスを提供していますか？
はい、[こちら](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Aspose.GIS はどこで購入できますか？
購入ページは [こちら](https://purchase.aspose.com/buy) です。

**Additional Q&A**

**Q:** 大規模なポリゴン データセットを扱うベストプラクティスは何ですか？  
**A:** ジオメトリを遅延ロードし、`GeometryFactory` のインスタンスを単一で再利用することでメモリ使用量を削減できます。

**Q:** 表面上の点を複数取得できますか？  
**A:** `GetPointOnSurface()` は単一の内部点を返します。複数の内部点が必要な場合は、ポリゴンのバウンディングボックス内でランダムに点を生成し、各点に対して `SpatiallyContains()` でテストしてください。

**Q:** 作成したポリゴンを Shapefile にエクスポートできますか？  
**A:** はい、Aspose.GIS は `FeatureSet` と `ShapefileWriter` クラスを提供しており、ジオメトリを Shapefile 形式で書き出すことが可能です。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---