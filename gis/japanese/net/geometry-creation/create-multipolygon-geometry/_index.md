---
date: 2025-12-17
description: Aspose.GIS for .NET を使用して ASP.NET でマルチポリゴンジオメトリを作成する方法を学びましょう。ステップバイステップのガイド、無料トライアル、ライセンス情報。
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS を使用した ASP.NET でのマルチポリゴンジオメトリの作成方法
url: /ja/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS で MultiPolygon ジオメトリを作成する

## はじめに
If you need to **create multipolygon geometry asp.net**, Aspose.GIS for .NET は、任意の .NET プラットフォームで動作するクリーンで型安全な API を提供します。このチュートリアルでは、ライブラリのインストールから、Shapefile、GeoJSON、その他のサポートされている形式へエクスポートできる MultiPolygon オブジェクトの構築まで、全工程を解説します。マッピング Web サービスやデスクトップ GIS ツールの開発において、このワークフローを習得すれば、時間の節約とバグの削減につながります。

## クイック回答
- **What can I build with this?** 複雑なポリゴン領域が必要な GIS アプリケーション全般、例えば土地利用マップや配達エリアなど。  
- **Do I need a license?** 開発には無料トライアルが利用可能です。製品版の本番環境では永続ライセンスが必要です。  
- **Which .NET versions are supported?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7 がサポートされています。  
- **How long does the code take to write?** 基本的な MultiPolygon の作成には約 5‑10 分程度です。  
- **Can I export the result?** はい。組み込みの `Save` メソッドを使用して Shapefile、GeoJSON などに書き出すことができます。

## MultiPolygon ジオメトリとは？
**MultiPolygon** は、離散している場合や穴を含む場合がある個々のポリゴンの集合です。GIS 用語では、同じ属性を共有しながら幾何的に分離された空間フィーチャの集合を表し、島からなる国や複数の部分からなる区画の表現に最適です。

## なぜ Aspose.GIS for .NET を使用するのか？
- **Full‑featured API** – 外部のネイティブ依存関係がなく、純粋なマネージドコードです。  
- **Cross‑platform** – Windows、Linux、macOS で動作します。  
- **Rich format support** – 多数のベクターフォーマットを箱から出すだけで読み書きできます。  
- **Performance‑optimized** – 大規模データセットを低メモリオーバーヘッドで処理します。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

1. **Visual Studio 2022**（または任意の C# IDE）に .NET 6 SDK がインストールされていること。  
2. **Aspose.GIS for .NET** パッケージ – [download page](https://releases.aspose.com/gis/net/) からダウンロードし、ドキュメントのインストールガイドに従ってください。

## 名前空間のインポート
プロジェクトに必要な `using` ディレクティブを追加し、コンパイラが GIS 型の所在を認識できるようにします:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順 1: Linear Ring の作成
**LinearRing** は、ポリゴンの外周または内周を定義する閉じた `LineString` です。ここでは 2 つのシンプルなリングを作成します:

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

> **Pro tip:** 最初と最後の点は同一である必要があります。Aspose.GIS は最後の点が省略された場合に自動で閉じますが、明示的に指定しておくと混乱を防げます。

## 手順 2: ポリゴンの作成
各 `Polygon` は `LinearRing` から構築されます。必要に応じて内部リング（穴）を後から追加することも可能です。

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## 手順 3: MultiPolygon の作成
次に、2 つのポリゴンを単一の `MultiPolygon` オブジェクトに結合します—これが **create multipolygon geometry asp.net** を実現する正確な手順です。

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

これで、操作・クエリ・シリアライズが可能な完全な機能を持つ `MultiPolygon` が作成できました。

## よくある問題と解決策
| Issue | Cause | Fix |
|-------|-------|-----|
| **Ring not closed** | 最初の点の複製が欠如している | 最初と最後の点が同一であることを確認するか、`LinearRing.Close()` を明示的に呼び出してください。 |
| **Incorrect coordinate order** | 緯度と経度が入れ替わっている | Aspose.GIS は **X = 経度**, **Y = 緯度** を期待します。データソースを確認してください。 |
| **Exception on `Add`** | null のポリゴンを追加しようとしている | 各 `Polygon` インスタンスが生成されていることを確認してから `MultiPolygon` に追加してください。 |

## 結論
これらの手順に従うことで、Aspose.GIS for .NET を使用して **create multipolygon geometry asp.net** を行う方法を習得しました。この基盤により、よりリッチな空間モデルの構築、空間クエリの実行、任意のサポート GIS 形式へのデータエクスポートが可能になります。次は `Contains`、`Intersects`、`Transform` などのメソッドを活用し、アプリケーションに分析機能を追加してみてください。

## FAQ
### Aspose.GIS for .NET は初心者に適していますか？
Absolutely! Aspose.GIS は、あらゆるスキルレベルの開発者がすぐに始められるよう、包括的なドキュメントとチュートリアルを提供しています。

### 購入前に Aspose.GIS を試すことはできますか？
Yes, you can download a free trial from [here](https://releases.aspose.com/) to explore its features before making a purchase.

### Aspose.GIS のサポートはどこで得られますか？
You can visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) to ask questions and get assistance from the community.

### Aspose.GIS の一時ライセンスはありますか？
Yes, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

### Aspose.GIS を直接購入できますか？
Yes, you can purchase Aspose.GIS from the website [here](https://purchase.aspose.com/buy).

## よくある質問
**Q: How do I save the MultiPolygon to a file?**  
A: Use the `Feature` class to wrap the geometry and call `feature.Save("output.shp", Drivers.Shapefile);`.

**Q: Can I add interior rings (holes) to a polygon?**  
A: Yes—create a second `LinearRing` and pass it as the second argument to the `Polygon` constructor.

**Q: Is it possible to transform coordinates to another spatial reference?**  
A: Absolutely. Call `multiPolygon.Transform(sourceCRS, targetCRS);` where CRS objects are defined via EPSG codes.

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}