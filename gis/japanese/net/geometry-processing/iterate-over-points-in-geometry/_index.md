---
date: 2026-06-10
description: Aspose.GIS for .NET を使用してジオメトリを反復処理しながら、ポイントを追加し、シェイプに座標を追加する方法を学びます。これは
  .NET 開発者向けの強力な GIS ツールキットです。
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: .NETでポイントを追加し、ジオメトリを反復処理する方法
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: .NETでポイントを追加し、ジオメトリを反復処理する方法
url: /ja/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET でジオメトリにポイントを追加し、反復処理する方法

## はじめに

.NET 環境で GIS データを扱う場合、最初に知っておくべきことの一つはジオメトリに **ポイントを追加する方法** です。その後、そのポイントを操作します。Aspose.GIS for .NET は、クリーンでオブジェクト指向の API を提供し、このプロセスをシンプルにします。このチュートリアルでは、`LineString` の作成、ポイントの追加、そしてそれらのポイントを反復処理して座標を取得したり、さらなる分析を行ったりする方法を解説します。また、**shape オブジェクトに座標を追加する** 方法も効率的に示します。

## クイック回答
- **ポイントコレクションの主要クラスは何ですか？** `LineString`
- **ポイントはどうやって追加しますか？** `AddPoint(longitude, latitude)` を使用します
- **foreach ループで反復できますか？** はい、`LineString` は `IEnumerable<IPoint>` を実装しています
- **前提条件は？** .NET 6+（または .NET Core 3.1/Framework 4.6+）と Aspose.GIS for .NET ライブラリ
- **典型的な使用例は？** ルートの構築、トラックの可視化、または空間分析のためのデータ前処理
- **IPoint** は X（経度）と Y（緯度）座標を持つ単一ポイントジオメトリを表します。

## GIS における「ポイントの追加」とは何ですか？

ポイントの追加とは、個々の座標ペア（経度、緯度）を `LineString`、`Polygon`、`MultiPoint` などのジオメトリコンテナに挿入することを指します。各ポイントは形状やパスを定義する頂点となり、空間操作や可視化を可能にします。これらの頂点は後で解析に利用したり、さまざまな GIS フォーマットへエクスポートしたり、距離測定や交差判定といった空間計算に使用したりできます。

## なぜ Aspose.GIS でポイントを追加するのか？

Aspose.GIS でポイントを追加する理由は、ライブラリが **型安全なジオメトリ処理** を保証し、**30 以上のベクタ・ラスタ形式** をサポートし、**数百ページ規模のデータセット** をメモリ全体にロードせずに処理できるからです。API は組み込みの反復処理、空間操作、フォーマット変換（Shapefile、GeoJSON、KML など）もすべての対応プラットフォームで提供します。

## 前提条件

- Visual Studio 2022（または任意の C# IDE）  
- Aspose.GIS for .NET の NuGet パッケージがインストールされていること  
- C# の構文に関する基本的な理解  

## 名前空間のインポート

.NET アプリケーションで Aspose.GIS の機能にアクセスできるよう、必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ジオメトリにポイントを追加する方法は？

ポイントは `LineString` インスタンスを作成し、各座標ペアに対して `AddPoint` メソッドを呼び出し、必要に応じてコレクションを反復処理することで追加します。この 3 ステップのパターンは、作成、データ投入、走査を簡潔かつ読みやすくカバーします。**LineString は、ポイントの順序付きコレクションでポリラインを構成するジオメトリ型です。** このアプローチにより、ジオメトリが有効な状態を保ち、長さ計算やエクスポートといったさらなる空間操作に備えることができます。

### 手順 1: `LineString` オブジェクトの作成  

`LineString` は Aspose.GIS のジオメトリ型で、ポリラインを構成するポイントの順序付きコレクションを表します。

```csharp
LineString line = new LineString();
```

### 手順 2: `LineString` にポイントを追加する  

`AddPoint` メソッドは新しい頂点（経度、緯度）をラインの末尾に挿入します。これを繰り返し呼び出すことで **shape オブジェクトに座標を追加** できます。

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### 手順 3: ポイントを反復処理する  

`LineString` は `IEnumerable<IPoint>` を実装しているため、`foreach` 文で各ポイントをループ処理できます。これにより X（経度）と Y（緯度）の値を簡単に取得できます。

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

このループは各ポイントの X（経度）と Y（緯度）をコンソールに出力し、ポイントが正しく追加されたことを確認できます。

## 一般的な使用例

- **ルート計画** – GPS ログからパスを構築し、ウェイポイント間の距離を分析します。  
- **データ検証** – ポイントを反復処理し、期待される範囲（例: 国境内）に収まっているか確認します。  
- **可視化** – `LineString` を GeoJSON または Shapefile にエクスポートし、マッピングツールで使用します。

## よくある質問

**Q1: Aspose.GIS for .NET は `LineString` 以外のジオメトリ形状も扱えますか？**  
A: はい、Aspose.GIS は `Point`、`Polygon`、`MultiLineString`、`MultiPolygon` など多数のジオメトリタイプをサポートしています。

**Q2: Aspose.GIS は商用プロジェクトと個人プロジェクトの両方に適していますか？**  
A: もちろんです。ライセンスオプションは商用、個人、教育用途をカバーしています。

**Q3: Aspose.GIS for .NET は初心者向けの包括的なドキュメントを提供していますか？**  
A: はい、製品には豊富なドキュメント、API リファレンス、そして多数のコード例が含まれており、すぐに始められます。

**Q4: カスタム開発で Aspose.GIS for .NET の機能を拡張できますか？**  
A: 拡張メソッドを作成したり、Aspose.GIS クラスをラップして特定のワークフローに合わせることができ、カスタム地理空間ソリューションを完全にコントロールできます。

**Q5: Aspose.GIS ユーザー向けにテクニカルサポートはありますか？**  
A: Aspose フォーラムとチケットシステムを通じて専用のテクニカルサポートが提供され、迅速な支援を受けられます。

**最終更新日:** 2026-06-10  
**テスト環境:** Aspose.GIS for .NET 24.5（執筆時点での最新）  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET でジオメトリのポイント数をカウントする方法](/gis/net/geometry-creation/count-points-in-geometry/)
- [Aspose.GIS を使用して LineString にポイントを追加し、ジオメトリを編集可能形式に変換する方法](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Aspose.GIS for .NET で MultiPoint ジオメトリを作成する](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}