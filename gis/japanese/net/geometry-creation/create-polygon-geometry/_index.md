---
date: 2026-05-31
description: Aspose.GIS for .NET を使用してポリゴンを作成する方法を学びます。.NET 開発者向けのステップバイステップガイドで、ポリゴンジオメトリの構築とポリゴン
  shapefile のエクスポート方法を解説します。
keywords:
- how to create polygon
- export polygon shapefile
- add vertices polygon
- build polygon coordinates
linktitle: ポリゴンジオメトリの作成
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  headline: How to Create Polygon Geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create polygon using Aspose.GIS for .NET. Step‑by‑step
    guide for .NET developers to build polygon geometry and export polygon shapefile.
  name: How to Create Polygon Geometry with Aspose.GIS for .NET
  steps:
  - name: Create a Polygon Object
    text: The `Polygon` class is the top‑level container that represents a single
      polygon geometry. **The `Polygon` class represents a closed geometric shape
      consisting of an exterior ring and optional interior rings.**
  - name: Define Exterior Ring
    text: A `LinearRing` holds the sequence of points that form the outer boundary.
      **The `LinearRing` class stores an ordered list of coordinate pairs that must
      form a closed loop.**
  - name: Add Points to the Exterior Ring
    text: Now we **add vertices polygon** by feeding latitude‑longitude pairs (or
      any coordinate system you prefer) into the ring. The points must form a closed
      loop, so the first and last coordinates are identical. **`LinearRing.AddPoint(x,
      y)` adds a single vertex to the ring; repeat for each coordinate.**
  - name: Set Exterior Ring on the Polygon
    text: Finally, assign the prepared ring to the polygon’s `ExteriorRing` property.
      The polygon is now a complete, valid geometry object. **The `ExteriorRing` property
      links the constructed `LinearRing` to the `Polygon` instance, finalizing the
      shape.** Congratulations! You have just **created polygon geome
  type: HowTo
- questions:
  - answer: Yes – simply iterate through your coordinate collection and call `ring.AddPoint(x,
      y)` for each item.
    question: Can I create a polygon from an existing list of coordinates?
  - answer: Create another `LinearRing`, add points, and assign it to `polygon.InteriorRings.Add(yourRing);`.
    question: How do I add an interior ring (hole) to the polygon?
  - answer: Use `polygon.IsValid` property; it returns `true` if the geometry complies
      with OGC standards.
    question: Is there a way to validate the polygon after creation?
  - answer: Absolutely. Use `FeatureWriter` with `GeoJson` format to write the polygon
      to a file, or choose `Shapefile` to **export polygon shapefile**.
    question: Can I export the polygon directly to GeoJSON?
  - answer: The library currently focuses on 2‑D geometries; for 3‑D you’ll need to
      manage Z‑values manually or use another specialized library.
    question: Does Aspose.GIS support 3‑D polygons?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用したポリゴンジオメトリの作成方法
url: /ja/net/geometry-creation/create-polygon-geometry/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したポリゴンジオメトリの作成方法

## はじめに  
`Polygon` は Aspose.GIS におけるポリゴンジオメトリを表すクラスです。`LinearRing.AddPoint` は線形リングに頂点を追加します。  

- **ポリゴンの主要クラスは何ですか？** `Polygon` は `Aspose.Gis.Geometries` からです。  
- **どのメソッドが頂点を追加しますか？** `LinearRing.AddPoint(x, y)` – ポリゴンの頂点を一つずつ追加します。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **ポリゴンをファイルにエクスポートできますか？** はい – `FeatureWriter` を使用して Shapefile、GeoJSON などを書き出し、簡単に **ポリゴンシェープファイルのエクスポート** が可能です。

## ポリゴンジオメトリとは何ですか？  
ポリゴンは外部リング（外周）と、必要に応じて1つ以上の内部リング（穴）で構成された閉じた形状です。GIS では、湖、区画、行政境界などの実世界の領域をモデル化します。Aspose.GIS は、C# の数行だけで **ポリゴン座標を構築** できるシンプルなオブジェクトモデルを提供します。

## なぜ Aspose.GIS を使用してポリゴンジオメトリを作成するのか？  
Aspose.GIS は、エンタープライズレベルのパフォーマンスを提供しながら、ポリゴンジオメトリを迅速に作成できます。**50 以上の入力および出力フォーマット** をサポートし、ファイル全体をメモリに読み込まずに数百ページ規模のデータセットを処理でき、.NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6 上で動作します。これにより、コードから直接 **ポリゴンシェープファイルのエクスポート** や GeoJSON、KML など多数のフォーマットにエクスポートでき、サードパーティのコンバータが不要になります。

## 前提条件  
1. **C# プログラミングの知識** – クラスやメソッドの基本的な理解。  
2. **Aspose.GIS for .NET のインストール** – [here](https://releases.aspose.com/gis/net/) からダウンロードできます。  
3. **開発環境の設定** – Visual Studio、Rider、または .NET をサポートする任意の IDE。  

## 名前空間のインポート  
GIS クラスをスコープに持ち込む必要があります。以下の `using` ディレクティブがこの例に必要なすべてです。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Aspose.GIS でポリゴンジオメトリを作成する方法  

プロジェクトを読み込み、必要な名前空間を追加し、`Polygon` オブジェクトをインスタンス化し、外部リングを構築し、ポリゴンの頂点を追加し、最後にリングを割り当てます—すべて数ステップで実行できます。このアプローチはすべてのサポート対象 .NET ランタイムで動作し、エクスポート可能な有効な OGC 準拠ポリゴンを生成します。

### ステップ 1: ポリゴンオブジェクトの作成  
`Polygon` クラスは単一のポリゴンジオメトリを表す最上位コンテナです。  
**`Polygon` クラスは、外部リングとオプションの内部リングで構成された閉じた幾何形状を表します。**  

```csharp
Polygon polygon = new Polygon();
```

### ステップ 2: 外部リングの定義  
`LinearRing` は外部境界を構成するポイントのシーケンスを保持します。  
**`LinearRing` クラスは、閉じたループを形成する必要がある座標ペアの順序付けられたリストを格納します。**  

```csharp
LinearRing ring = new LinearRing();
```

### ステップ 3: 外部リングにポイントを追加  
ここでは、緯度‑経度ペア（または任意の座標系）をリングに入力して **ポリゴンの頂点を追加** します。ポイントは閉じたループを形成する必要があるため、最初と最後の座標は同一です。  
**`LinearRing.AddPoint(x, y)` はリングに単一の頂点を追加します。各座標について繰り返してください。**  

```csharp
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

### ステップ 4: ポリゴンに外部リングを設定  
最後に、作成したリングをポリゴンの `ExteriorRing` プロパティに割り当てます。これでポリゴンは完全な有効ジオメトリオブジェクトになります。  
**`ExteriorRing` プロパティは構築された `LinearRing` を `Polygon` インスタンスにリンクし、形状を完成させます。**  

```csharp
polygon.ExteriorRing = ring;
```

おめでとうございます！Aspose.GIS for .NET を使用して **ポリゴンジオメトリを作成** しました。ここからは、ポリゴンをフィーチャに付与したり、ファイルに書き出したり、空間分析を実行したりできます。

## 一般的な問題とヒント  

| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| **リングが閉じていない** | 最初と最後のポイントが異なり、ジオメトリが無効になります。 | 最初の座標を最後のポイントとして繰り返します（上記参照）。 |
| **座標順序が間違っている** | GIS ライブラリは X（経度）→Y（緯度）の順序を期待します。 | `AddPoint` には `(longitude, latitude)` を渡すようにしてください。 |
| **ライセンスがない** | トライアルモードでは特定の操作が制限されることがあります。 | テスト用に無料トライアルライセンスを適用し、本番環境では有料ライセンスを使用してください。 |

## よくある質問  

**Q: 既存の座標リストからポリゴンを作成できますか？**  
A: はい – 座標コレクションを反復処理し、各項目に対して `ring.AddPoint(x, y)` を呼び出すだけです。

**Q: ポリゴンに内部リング（穴）を追加するには？**  
A: 別の `LinearRing` を作成し、ポイントを追加してから `polygon.InteriorRings.Add(yourRing);` に割り当てます。

**Q: 作成後にポリゴンを検証する方法はありますか？**  
A: `polygon.IsValid` プロパティを使用します。ジオメトリが OGC 標準に準拠していれば `true` を返します。

**Q: ポリゴンを直接 GeoJSON にエクスポートできますか？**  
A: もちろんです。`FeatureWriter` を `GeoJson` フォーマットで使用してポリゴンをファイルに書き出すか、`Shapefile` を選択して **ポリゴンシェープファイルのエクスポート** が可能です。

**Q: Aspose.GIS は 3‑D ポリゴンをサポートしていますか？**  
A: 現在のライブラリは 2‑D ジオメトリに焦点を当てており、3‑D の場合は Z 値を手動で管理するか、別の専門ライブラリを使用する必要があります。

---

**最終更新日:** 2026-05-31  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS を使用した穴付きポリゴンの作成](/gis/net/geometry-creation/create-polygon-with-hole-geometry/)
- [C# でポリゴンジオメトリを作成し、Aspose.GIS for .NET で交差をチェック](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Aspose.GIS for .NET を使用したバッファの作成方法](/gis/net/geometry-analysis/create-geometry-buffer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}