---
date: 2026-04-09
description: Aspose.GIS for .NET を使用してジオメトリの精度を下げ、Z 値を丸める方法を学び、GIS のパフォーマンスを向上させ、メモリを節約します。
keywords:
- how to reduce geometry
- how to round z
- geometry precision .NET
linktitle: ジオメトリ精度を低減
second_title: Aspose.GIS .NET API
title: .NETでジオメトリの精度を下げ、Z座標を丸める方法
url: /ja/net/geometry-processing/reduce-geometry-precision/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET でジオメトリの精度を削減し Z を丸める方法

## はじめに
大規模な空間データセットを扱っていると、ジオメトリ データの小数点以下の桁が増えるほど、ファイル サイズや処理時間が増加することに気付くでしょう。このチュートリアルでは、Aspose.GIS for .NET を使用して **how to reduce geometry** の精度と **how to round Z** の値を削減する方法を学びます。ガイドの最後までに、ジオメトリ ファイルを縮小し、空間操作を高速化し、メモリ フットプリントを低く保つことが、いくつかのシンプルなメソッド呼び出しだけでできるようになります。

## クイック回答
- **What does “how to round Z” mean?** ジオメトリ オブジェクトの Z 座標の小数点以下の桁数を削減することを指します。  
- **Why reduce geometry precision?** 頂点ごとに保存されるデータ量が減少し、空間クエリが高速化され、メモリ使用量が削減されます。  
- **Which library handles this?** Aspose.GIS for .NET は組み込みの `RoundZ` と `RoundXY` メソッドを提供します。  
- **Do I need a license?** 無料トライアルでテストは可能ですが、商用利用にはライセンスが必要です。  
- **Can I control the number of decimal places?** はい、`Round*` メソッドで希望する桁数を指定できます。

## .NET でジオメトリの精度を削減する方法
ジオメトリの精度を削減するのは、任意のジオメトリ オブジェクトに対して `RoundXY` を呼び出すだけです。このメソッドは X と Y 座標に保持したい小数点以下の桁数を受け取ります。分析でサブメートル単位の正確さが不要な場合に特に有用です。

## .NET で Z 値を丸める方法
データに Z（標高）成分が含まれる場合、`RoundZ` を呼び出して精度を制限できます。これは **how to round z** のステップで、3‑D データセットでは標高値に多くの小数点が含まれるため、ファイル サイズ削減効果が最大になります。

## GIS における “how to round Z” とは何か
Z 座標を丸めることで余分な小数点精度が削除され、たとえば 3.345 が 3.3（または指定した精度）に変換されます。このシンプルな操作は、特に第3次元が分析に重要でない場合、ファイル サイズを劇的に縮小し、計算を高速化します。

## なぜ Aspose.GIS でジオメトリの精度を削減するのか
- **Performance boost:** 処理データが減ることで空間クエリや変換が高速化します。  
- **Memory savings:** 小さな頂点表現により RAM が解放され、より大きなデータセットをメモリ上に保持できます。  
- **Flexibility:** 正確さと速度のバランスを取る精度レベルを自分で決められます。

## 前提条件
作業を始める前に、以下の前提条件を満たしていることを確認してください：
1. Aspose.GIS for .NET Library: [Aspose.GIS website](https://releases.aspose.com/gis/net/) からダウンロードしてインストールしてください。  
2. Basic Knowledge of C# Programming: C# プログラミング言語に慣れていると役立ちます。

## 名前空間のインポート
まず、Aspose.GIS のクラスとメソッドを使用できるように必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順 1: ポイントの作成
特定の座標を持つポイントを作成します。

```csharp
Point point = new Point(1.344, 2.345, 3.345, 4.345);
```

## 手順 2: XY の精度を削減
次に、ポイントの X と Y 座標の精度を小数点以下 2 桁に削減します。

```csharp
point.RoundXY(digits: 2);
```

## 手順 3: 座標の表示
ポイントの更新された座標を表示します。

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## 手順 4: Z の精度を削減 – **how to round z**
次に、ポイントの Z 座標の精度を小数点以下 1 桁に削減します。これが **how to round z** の核心です。

```csharp
point.RoundZ(digits: 1);
```

## 手順 5: 更新された座標の表示
Z 精度を削減した後のポイントの更新された座標を表示します。

```csharp
Console.WriteLine("{0}, {1}, {2}, {3}", point.X, point.Y, point.Z, point.M);
```

## 手順 6: LineString の作成
次に、`LineString` を作成し、ポイントを追加します。

```csharp
LineString line = new LineString();
line.AddPoint(1.2, 2.3);
line.AddPoint(2.4, 3.1);
```

## 手順 7: LineString の XY 精度を削減
`LineString` の X と Y 座標の精度を小数点以下 0 桁に削減します。

```csharp
line.RoundXY(digits: 0);
```

## 手順 8: LineString の更新された座標の表示
XY 精度を削減した後の `LineString` の更新された座標を表示します。

```csharp
Console.WriteLine("{0}, {1}", line[0].X, line[0].Y);
Console.WriteLine("{0}, {1}", line[1].X, line[1].Y);
```

## 一般的な使用例とヒント
- **Large raster‑vector conversions:** Z を丸めることで中間ジオメトリ ファイルを縮小できます。  
- **Mobile GIS apps:** 精度を下げることで、ネットワーク経由でジオメトリを送信する際の帯域幅が削減されます。  
- **Pro tip:** ワークフローを一貫させるために、`RoundXY` を先に適用し、その後で `RoundZ` を適用してください。

## よくある質問

**Q: Why is geometry precision reduction important in GIS?**  
A: ジオメトリの精度を削減することで、メモリ使用量の最適化とパフォーマンス向上が図れ、特に大規模データセットを扱う GIS アプリケーションで効果的です。

**Q: Does reducing geometry precision affect accuracy?**  
A: 若干の精度低下はありますが、ほとんどの空間分析においては、精度とパフォーマンスのバランスが取れた良好な結果が得られます。

**Q: Can I customize the precision reduction level in Aspose.GIS for .NET?**  
A: はい、`RoundXY` と `RoundZ` メソッドを使用して、XY および Z 座標の希望する小数点以下桁数を指定できます。

**Q: Are there measurable performance benefits?**  
A: 確実にあります。頂点ごとのデータが減ることで、空間クエリが高速化し、I/O が削減され、メモリ消費も低減します。

**Q: Where can I get support for Aspose.GIS for .NET?**  
A: [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) でサポートを受けられます。また、[here](https://reference.aspose.com/gis/net/) にあるドキュメントもご利用ください。

---

**最終更新日:** 2026-04-09  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}