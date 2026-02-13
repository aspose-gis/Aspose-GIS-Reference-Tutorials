---
date: 2026-02-13
description: Aspose.GIS for .NET を使用してポリゴン内に点があるかを確認する方法、ポリゴンジオメトリの作成、C# でサーフェス上の点を取得する方法を学びましょう。ステップバイステップのガイドと完全なコード例付き。
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

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **ポリゴン内の点をチェックする方法** を学び、ジオメトリの **表面上の点を取得する方法** も確認します。C# でポリゴンジオメトリを作成し、ポリゴンの表面上にある点を取得し、その点が実際にポリゴン内部にあるかを検証します。最後まで読むと、任意の .NET 地理空間アプリケーションにすぐに組み込めるコードスニペットが手に入ります。

## クイック回答
- **「ポリゴン内の点をチェックする」とは何ですか？** 指定した座標がポリゴンジオメトリの境界内にあるかどうかを確認します。  
- **ポリゴン内部の点を返すメソッドはどれですか？** `GetPointOnSurface()` はポリゴン内部に必ず存在する点を返します。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境では正式ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework、.NET Core、.NET Standard のすべてに対応しています。  
- **実装にかかる時間は？** コピー、コンパイル、実行まで約 5‑10 分です。

## 「ポリゴン内の点をチェックする」とは？
ポリゴン内の点をチェックすることは、基本的な空間演算です。「この座標はポリゴンで定義された領域内に位置していますか？」という質問に答えます。ジオフェンシング、マップ分析、空間検証などのタスクに不可欠です。

## なぜ Aspose.GIS を使うのか？
Aspose.GIS は高性能で完全にマネージドな API を提供し、外部依存なしで複雑なジオメトリ操作を処理します。多数の座標参照系をサポートし、すべての主要 .NET ランタイムで動作し、`SpatiallyContains()` や `GetPointOnSurface()` といった直感的でチェーン可能なメソッドを備えています。

## 前提条件
開始する前に以下を用意してください。

### 環境設定
1. Aspose.GIS for .NET をインストール: [here](https://releases.aspose.com/gis/net/) から Aspose.GIS for .NET ライブラリをダウンロードしてインストールします。  
2. 開発環境の構築: .NET プログラミング用の開発環境が整っていることを確認してください。Visual Studio など、お好みの .NET 開発環境をセットアップできます。  
3. C# の基礎知識: まだ慣れていない場合は、C# 言語の基本を学んでおいてください。  
4. ドキュメントへのアクセス: チュートリアル中に参照できるよう、[documentation](https://reference.aspose.com/gis/net/) を手元に置いておきましょう。

## 名前空間のインポート
実装に入る前に、必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順ガイド

### 手順 1: C# でポリゴンジオメトリを作成
まず、**ポリゴン** ジオメトリを作成します。ポリゴンの外周リングを頂点で指定します。

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

### 手順 2: 表面上の点を取得
次に、`GetPointOnSurface()` メソッドを使用してポリゴンの表面上の点を取得します。これが **表面上の点を取得** するステップです。

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### 手順 3: ポリゴン内の点をチェック
取得した点がポリゴン内部にあるかどうかを `SpatiallyContains()` メソッドで検証します。これにより **ポリゴン上の点を取得** し、続いてチェックする流れが示されます。

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## よくある問題と対策
- **空のポリゴン** – 外周リングに少なくとも 3 つの異なる頂点があることを確認してください。そうでないと `GetPointOnSurface()` が未定義の点を返す可能性があります。  
- **時計回り vs 反時計回り** – リングの向きは包含チェックに影響しませんが、他の空間演算のために一貫した winding order を保つと便利です。  
- **座標系** – サンプルは単純なデカルト平面を使用しています。実世界の座標を扱う場合は、CRS（座標参照系）が正しく定義されていることを確認してください。

## FAQ

### FAQ
#### Aspose.GIS は他の .NET フレームワークと互換性がありますか？
はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard など、さまざまな .NET フレームワークをサポートしています。

#### 購入前に Aspose.GIS を試すことはできますか？
はい、[here](https://releases.aspose.com/) から Aspose.GIS の無料トライアルをダウンロードできます。

#### Aspose.GIS のサポートはどこで受けられますか？
Aspose.GIS フォーラムは [here](https://forum.aspose.com/c/gis/33) で利用でき、他のユーザーや開発者とやり取りしながら支援を受けられます。

#### Aspose.GIS は一時ライセンスを提供していますか？
はい、[here](https://purchase.aspose.com/temporary-license/) から Aspose.GIS の一時ライセンスを取得できます。

#### Aspose.GIS はどこで購入できますか？
購入ページは [here](https://purchase.aspose.com/buy) です。

### 追加 Q&A

**Q:** 大規模なポリゴンデータセットを扱う最適な方法は？  
**A:** ジオメトリを遅延ロードし、`GeometryFactory` のインスタンスを 1 つだけ再利用することでメモリ使用量を削減できます。

**Q:** 表面上の点を複数取得できますか？  
**A:** `GetPointOnSurface()` は単一の内部点を返します。複数の内部点が必要な場合は、ポリゴンのバウンディングボックス内でランダム点を生成し、各点を `SpatiallyContains()` でテストする方法があります。

**Q:** 作成したポリゴンを shapefile にエクスポートできますか？  
**A:** はい、Aspose.GIS は `FeatureSet` と `ShapefileWriter` クラスを提供しており、ジオメトリを Shapefile 形式で書き出すことが可能です。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して **ポリゴン内の点をチェック** し、**表面上の点を取得** し、その包含性を検証する方法を学びました。Aspose.GIS を活用すれば、地理空間データの取り扱いが効率的かつシンプルになり、開発者は堅牢な地理空間アプリケーションを構築できます。

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}