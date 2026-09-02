---
date: 2026-08-24
description: Aspose.GIS for .NET を使用して曲線ラインジオメトリを作成し、曲線を追加する方法を学び、正確な地理空間データ処理を実現します。
keywords:
- create curved line
- how to add curves
- create compound curve
- circular arc geometry
lastmod: 2026-08-24
linktitle: 曲線の追加 – Compound Curve Geometry
og_description: Aspose.GIS for .NET を使用して曲線ラインジオメトリを作成する方法を学びます。このチュートリアルでは、数分で曲線を追加し、Compound
  Curve を構築する手順をステップバイステップで示します。
og_image_alt: Screenshot of Aspose.GIS creating a compound curved line geometry in
  a .NET project
og_title: Aspose.GIS を使用した曲線ラインジオメトリの作成方法
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  headline: How to create curved line geometry with Aspose.GIS
  type: TechArticle
- description: Learn how to create curved line geometry and add curves using Aspose.GIS
    for .NET, enabling precise geospatial data processing.
  name: How to create curved line geometry with Aspose.GIS
  steps:
  - name: define the output path
    text: First, specify where the resulting Shapefile will be saved. Replace the
      placeholder with a valid folder on your machine.
  - name: create a vector layer
    text: '`VectorLayer` represents a spatial layer that holds features and their
      geometries within a GIS dataset. The `using` block ensures the file is closed
      properly after writing.'
  - name: construct the compound curve feature
    text: The `CompoundCurve` class is Aspose.GIS's top‑level object for a geometry
      that consists of multiple connected curve parts. Here we instantiate an empty
      compound curve that will later receive individual components.
  - name: define component curves
    text: 'We prepare five pieces—two straight `LineString`s, two `CircularString`
      arcs, and a final `LineString`. `LineString` represents a simple straight line
      defined by an ordered list of points. `CircularString` is Aspose.GIS’s representation
      of a circular arc defined by three points (start, middle, end) '
  - name: add component curves to the compound curve
    text: Each component is appended in order, preserving continuity and orientation.
      The `Add` method automatically validates that the end point of one segment matches
      the start point of the next.
  - name: assign geometry to the feature
    text: Now the assembled `CompoundCurve` becomes the geometry of the feature we
      will store in the layer.
  - name: add the feature to the layer
    text: Finally, we write the feature into the Shapefile. When the `using` block
      ends, the file is closed and ready for use in any GIS application.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard,
      covering versions from 4.6 up to .NET 7.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. It reads and writes Shapefile, GeoJSON, KML, GML, and more
      than 30 additional formats.
    question: Does Aspose.GIS support reading and writing different geospatial file
      formats?
  - answer: Yes, the library can be used in desktop, web, and cloud services without
      any platform‑specific dependencies.
    question: Is Aspose.GIS suitable for both desktop and web applications?
  - answer: Yes, you can calculate distances, execute geometric operations, and run
      spatial queries directly on the geometries.
    question: Can I perform spatial analysis with Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) to ask
      questions and share ideas with other developers.
    question: Where can I get community help for Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS geometry
- Aspose.GIS
- .NET geospatial
- compound curve
title: Aspose.GIS を使用した曲線ラインジオメトリの作成方法
url: /ja/net/geometry-creation/create-compound-curve-geometry/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した曲線ジオメトリの作成方法

## はじめに
このガイドでは Aspose.GIS for .NET を使用して **曲線ジオメトリの作成方法** を学びます。インタラクティブマップの構築、空間分析の実行、GIS データセットの生成など、曲線を追加できるようになることで、曲がりくねった道路や蛇行する川といった実世界の特徴を高精度でモデル化できます。本チュートリアルは、プロジェクトの設定から再利用可能なコンパウンドカーブジオメトリのエクスポートまで、すべての手順を順を追って解説します。

## クイック回答
- **主な目的は何ですか？** 直線と円弧を組み合わせたコンパウンドカーブジオメトリを作成します。  
- **使用されているライブラリはどれですか？** Aspose.GIS for .NET。  
- **前提条件は？** Visual Studio、Aspose.GIS がインストールされた環境、そして .NET 6 以降を対象とした C# プロジェクト。  
- **一般的な実装時間は？** 動作例で約 10‑15 分。  
- **サポートされている出力形式は？** Shapefile（同じコードで GeoJSON、KML、その他の形式も書き出せます）。

## コンパウンドカーブとは何か？
コンパウンドカーブは、複数の接続された曲線コンポーネント（直線 `LineString` と円弧）で構成され、より複雑な形状を形成する単一のジオメトリです。単純な直線だけでは正確に表現できない道路の滑らかな曲がりや自然な弧を描く河川などのパスを表すのに最適です。

## 曲線追加に Aspose.GIS を使用する理由は？
Aspose.GIS は **リッチなジオメトリ API** を提供し、ラインストリング、サーキュラーストリング、コンパウンドカーブをネイティブにサポートします。外部 GIS ライブラリは不要です。ライブラリは **クロスプラットフォーム** で、.NET Framework 4.6+、.NET Core 2.0+、.NET 5/6/7+ で動作します。**最大 500 ページのベクターデータセットをメモリ全体にロードせずに処理** でき、速くメモリ効率の高い操作が可能です。エクスポートも簡単で、Shapefile、GeoJSON、KML、GML、その他 30 以上の形式に直接書き出せます。

## これが重要な理由
曲線を追加することで、実世界の特徴をより正確にモデル化でき、マップの描画品質が向上し、近接検索やネットワークルーティングといった空間分析の精度も高まります。したがって、**曲線ジオメトリの作成方法** を習得することは、あらゆる GIS 主導の .NET ソリューションの忠実度を向上させます。

## 主な使用例
- **交通ネットワーク:** 高速道路、鉄道、または自転車道を滑らかな曲線でモデル化します。  
- **水文学:** 自然な弧をたどる河川のコースを表現します。  
- **都市計画:** 曲線部分を含む土地境界を描画します。  
- **カスタムシンボル:** 地図凡例用の装飾的または概略的な形状を作成します。

## 前提条件
- Visual Studio（いずれかの最新エディション）。  
- Aspose.GIS for .NET を [download page](https://releases.aspose.com/gis/net/) からダウンロードします。  
- .NET 6（またはサポートされている任意のバージョン）を対象とした C# プロジェクト。

## 名前空間のインポート
`using` ディレクティブは必要な Aspose.GIS の型をスコープに持ち込みます。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## コンパウンドカーブジオメトリ作成のステップバイステップガイド

### 手順 1: 出力パスの定義
まず、生成された Shapefile を保存する場所を指定します。プレースホルダーを実際に使用できるフォルダーに置き換えてください。

```csharp
string path = "Your Document Directory" + "CreateCompoundCurve_out.shp";
```

### 手順 2: ベクターレイヤーの作成
`VectorLayer` は GIS データセット内でフィーチャとそのジオメトリを保持する空間レイヤーを表します。`using` ブロックは書き込み後にファイルが正しく閉じられることを保証します。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block for creating the compound curve geometry will be inserted here.
}
```

### 手順 3: コンパウンドカーブフィーチャの構築
`CompoundCurve` クラスは、複数の接続された曲線部分からなるジオメトリを表す Aspose.GIS の最上位オブジェクトです。ここでは、後で個々のコンポーネントを追加する空のコンパウンドカーブをインスタンス化します。

```csharp
var feature = layer.ConstructFeature();
var compoundCurve = new CompoundCurve();
```

### 手順 4: コンポーネント曲線の定義
5 つのパーツ（2 本の直線 `LineString`、2 本の `CircularString` 弧、最後の `LineString`）を用意します。`LineString` は順序付けられた点のリストで定義された単純な直線です。`CircularString` は 3 点（開始点、途中点、終了点）で定義され、同一円上にある必要がある円弧を表します。

```csharp
var bottom = (ILineString)Geometry.FromText("LineString (0 0, 3 0)");
var firstArc = (ICircularString)Geometry.FromText("CircularString (3 0, 4 1, 3 2)");
var middle = (ILineString)Geometry.FromText("LineString (3 2, 1 2)");
var secondArc = (ICircularString)Geometry.FromText("CircularString (1 2, 0 3, 1 4)");
var top = (ILineString)Geometry.FromText("LineString (1 4, 4 4)");
```

### 手順 5: コンポーネント曲線をコンパウンドカーブに追加
各コンポーネントを順番に追加し、連続性と向きを保持します。`Add` メソッドは、あるセグメントの終点が次のセグメントの始点と一致することを自動的に検証します。

```csharp
compoundCurve.AddCurve(bottom);
compoundCurve.AddCurve(firstArc);
compoundCurve.AddCurve(middle);
compoundCurve.AddCurve(secondArc);
compoundCurve.AddCurve(top);
```

### 手順 6: フィーチャにジオメトリを割り当てる
組み立てた `CompoundCurve` を、レイヤーに格納するフィーチャのジオメトリとして設定します。

```csharp
feature.Geometry = compoundCurve;
```

### 手順 7: フィーチャをレイヤーに追加
最後に、フィーチャを Shapefile に書き込みます。`using` ブロックが終了すると、ファイルは閉じられ、任意の GIS アプリケーションで使用できる状態になります。

```csharp
layer.Add(feature);
```

## よくある問題とヒント
- **座標順序:** Aspose.GIS は `X Y`（経度、緯度）の順序で座標を期待します。順序を入れ替えるとジオメトリが反転します。  
- **CircularString の構文:** 中間点は対象の弧上にある必要があります。そうでないと曲線は直線に崩れます。  
- **ファイル上書き:** `VectorLayer.Create` は既存の Shapefile を警告なしに上書きします。開発中は一意のファイル名を使用してください。  
- **パフォーマンス:** 大規模データセットでは、`using` ブロック内で1つずつ追加するのではなく、バッチでフィーチャを追加してください。  
- **プロのコツ:** 多数の類似フィーチャを作成する際は同じ `CompoundCurve` インスタンスを再利用し、再構築前に `compoundCurve.Clear()` を呼び出して割り当てを削減します。

## よくある質問

**Q: Aspose.GIS for .NET を他の .NET フレームワークと併用できますか？**  
A: はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard と互換性があり、バージョン 4.6 から .NET 7 までサポートしています。

**Q: Aspose.GIS はさまざまな地理空間ファイル形式の読み書きをサポートしていますか？**  
A: もちろんです。Shapefile、GeoJSON、KML、GML など、30 以上の追加形式を読み書きできます。

**Q: Aspose.GIS はデスクトップとウェブの両方のアプリケーションに適していますか？**  
A: はい、プラットフォーム固有の依存関係がないため、デスクトップ、ウェブ、クラウドサービスのいずれでも使用できます。

**Q: Aspose.GIS for .NET で空間分析を実行できますか？**  
A: はい、距離計算、ジオメトリ演算、空間クエリなどをジオメトリ上で直接実行できます。

**Q: Aspose.GIS のコミュニティサポートはどこで得られますか？**  
A: 他の開発者と質問やアイデアを共有するには、[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) をご利用ください。

---

**最終更新日:** 2026-08-24  
**テスト環境:** Aspose.GIS for .NET（最新の安定版リリース）  
**著者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET でベクターレイヤーとサーキュラーストリングを作成](/gis/net/geometry-creation/create-circular-string-geometry/)
- [Aspose.GIS でベクターレイヤーと曲線ポリゴンを作成](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [WKT からジオメトリへ変換: Aspose.GIS .NET で MultiCurve を作成](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}