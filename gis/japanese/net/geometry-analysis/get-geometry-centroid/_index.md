---
date: 2026-02-10
description: Aspose.GIS for .NET を使用してジオメトリの重心を計算し、ポリゴンの中心点を取得し、空間分析のためにマルチポリゴンの重心を計算する方法を学びましょう。
linktitle: Get Geometry Centroid
second_title: Aspose.GIS .NET API
title: .NET 用 Aspose.GIS でジオメトリの重心を計算する方法
url: /ja/net/geometry-analysis/get-geometry-centroid/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリの重心の計算方法

## 導入
**C# 空間分析**を行っていて、任意の形状の**重心の計算方法**を知りたい場合は、ここが最適です。このチュートリアルでは、Aspose.GIS for .NET を使用して**ポリゴンの重心を計算**し、その重心を取得し、ラベル配置、クラスタリング、距離計算などの強力な**統合空間分析**シナリオを実現する方法をご紹介します。

## クイック回答
- **主なメソッドは何ですか？** `IGeometry` オブジェクトの `GetCentroid()`。  
- **どのライブラリが提供していますか？** Aspose.GIS for .NET。  
- **コード行数は？** 合計で 15 行未満（using 文を除く）。  
- **ライセンスは必要ですか？** テスト用に一時ライセンスが利用可能です。製品版には正式ライセンスが必要です。  
- **.NET 6 以上で実行できますか？** はい – API は .NET Core および .NET 5/6 と完全に互換性があります。  

## 重心とは何か、そしてなぜ重要か
重心は形状の幾何学的中心、いわば「バランスポイント」です。ポリゴンの場合、重心（**ポリゴンの中心点**）はラベル配置、平均位置の算出、空間クエリの基準点として頻繁に使用されます。**重心の計算方法**をすばやく把握すれば、複雑な数式を書かずに空間分析機能を統合できます。

## なぜマルチポリゴンの重心を計算するのか
複数のポリゴン（例: 島々からなる国境）を扱う際、**マルチポリゴンの重心を計算**する必要があります。Aspose.GIS では `MultiPolygon` に対して `GetCentroid()` を呼び出すだけで、結合された形状の重心が取得でき、バッチ処理やマップ可視化が簡素化されます。

## 前提条件
以下を事前に用意してください。

### 1. Aspose.GIS for .NET のインストール
ライブラリは [Aspose.GIS for .NET website](https://releases.aspose.com/gis/net/) からダウンロードします。インストール手順に従い、NuGet パッケージをプロジェクトに追加してください。

### 2. C# プログラミングの基礎知識
基本的な C# コードが書けることが前提です。初心者の場合は、変数、クラス、コンソール出力の復習をおすすめします。

### 3. 地理概念の基本的な理解
必須ではありませんが、ポイント、ライン、ポリゴンの違いを知っているとサンプルが理解しやすくなります。

## 名前空間のインポート
Aspose.GIS のクラスを使用できるように名前空間をインポートします。C# ファイルの先頭に以下の `using` ディレクティブを追加してください。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

これらの名前空間により、ジオメトリ型、`GetCentroid()` メソッド、標準 .NET ユーティリティが利用可能になります。

## ジオメトリの重心を計算する方法
以下は **ポリゴンジオメトリを作成**し、重心を計算し、結果を表示する手順です。

### 手順 1: ポリゴンの定義
まず、頂点を指定して **ポリゴンジオメトリを作成**します。この例は自己交差しないシンプルなポリゴンを構築します。

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(1, 0),
    new Point(2, 2),
    new Point(0, 4),
    new Point(5, 5),
    new Point(6, 1),
    new Point(1, 0),
});
```

### 手順 2: ポリゴンの重心（ポリゴンの中心点）を取得
ポリゴンが定義できたら、`GetCentroid()` を呼び出して **ポリゴンの重心を取得**します。

```csharp
IPoint centroid = polygon.GetCentroid();
```

### 手順 3: 重心座標を表示
最後に、重心の X 座標と Y 座標を出力します。書式文字列は小数点以下 2 桁に丸めます。

```csharp
Console.WriteLine("{0:F} {1:F}", centroid.X, centroid.Y); // Output: 3.33 2.58
```

プログラムを実行すると、コンソールに重心座標が表示され、ジオメトリが正しく処理されたことが確認できます。

## よくある落とし穴とプロのコツ
- **落とし穴:** 自己交差するポリゴンを指定すると、予期しない重心が得られることがあります。  
  **コツ:** `GetCentroid()` を呼び出す前に、（利用可能なら）`IsValid` などでポリゴンの妥当性を検証してください。
- **落とし穴:** リングを閉じ忘れる（最初と最後の点が同一でない）。  
  **コツ:** `LinearRing` を構築する際は、最初の点を最後の点として必ず繰り返してください。
- **プロのコツ:** 大規模データセットの場合、`Parallel.ForEach` を使って重心計算を並列化するとバッチ処理が高速化します。
- **プロのコツ:** `MultiPolygon` を扱う際は、コレクション全体に対して直接 `GetCentroid()` を呼び出すことで、**マルチポリゴンの重心を一括計算**できます。

## FAQ
### Q: Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？
A: Aspose.GIS for .NET は .NET Framework 4.6 以降と互換性があり、幅広いバージョンで使用できます。

### Q: Aspose.GIS for .NET の一時ライセンスは取得できますか？
A: はい、テスト目的の一時ライセンスが提供されています。取得は [temporary license page](https://purchase.aspose.com/temporary-license/) から行えます。

### Q: Aspose.GIS for .NET はデスクトップとウェブの両方のアプリケーションに適していますか？
A: もちろんです。Aspose.GIS for .NET はデスクトップアプリでもウェブアプリでもシームレスに統合でき、開発の柔軟性を提供します。

### Q: Aspose.GIS for .NET は充実したドキュメントを提供していますか？
A: はい、包括的なドキュメントが [documentation page](https://reference.aspose.com/gis/net/) に掲載されており、機能や使用方法を詳しく解説しています。

### Q: Aspose.GIS for .NET に関するサポートやコミュニティ参加はどこで行えますか？
A: ご質問やサポート、コミュニティ交流は Aspose.GIS 専用フォーラム [here](https://forum.aspose.com/c/gis/33) で行えます。

## よくある質問

**Q: マルチポリゴンの重心を計算できますか？**  
A: はい。各ポリゴンに対して個別に `GetCentroid()` を呼び出すか、`MultiPolygon` オブジェクトに対して直接呼び出すことで、結合形状の重心が取得できます。

**Q: 重心計算は地球の曲率を考慮しますか？**  
A: 組み込みの `GetCentroid()` はジオメトリの座標空間（平面）で動作します。測地データの場合は、計算前に適切な平面座標系に再投影してください。

**Q: ジオメトリコレクションの重心を一度の呼び出しで取得する方法はありますか？**  
A: コレクションを走査して個別に重心を計算するか、`GeometryFactory` でジオメトリをマージし、マージ結果に対して `GetCentroid()` を呼び出すことができます。

**Q: 非常に大きなポリゴンの重心はどの程度正確ですか？**  
A: 正確性は座標の精度と投影法に依存します。極めて大規模または複雑なポリゴンの場合、パフォーマンス向上のためにジオメトリを簡略化することを検討してください。

**Q: 重心の出力を GeoJSON 形式にフォーマットできますか？**  
A: はい。`IPoint` を取得した後、Aspose.GIS の `GeoJsonWriter` または任意の JSON シリアライザーを使用して GeoJSON にシリアライズできます。

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}