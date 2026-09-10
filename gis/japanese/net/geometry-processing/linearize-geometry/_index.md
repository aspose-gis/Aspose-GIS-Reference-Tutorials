---
date: 2026-09-10
description: Aspose.GIS for .NET を使用して曲線を直線に変換（linearize geometry）し、.NET アプリで efficient
  geospatial processing と analysis を実現します。
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: ジオメトリを linearize
og_description: Aspose.GIS for .NET を使用して曲線を直線に変換（linearize geometry）します。step‑by‑step
  で simplify geometries し、faster rendering と broader compatibility を実現する方法を学びます。
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Aspose.GIS for .NET で曲線を直線に変換
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET を使用した曲線を直線に変換する方法
url: /ja/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した曲線を直線に変換（ジオメトリの線形化）

## はじめに
マッピング、空間分析、またはデータ交換タスクのために **曲線を直線に変換** する必要がある場合、Aspose.GIS for .NET はクリーンでプログラム的な方法を提供します。このチュートリアルでは、曲線や複合形状を含む複雑なジオメトリを取得し、任意の GIS システムで動作するシンプルな線形表現に変換する完全な実例を順に解説します。

## クイック回答
- **「曲線を直線に変換」とは何ですか？」** 曲線ジオメトリを直線セグメントに変換します。  
- **なぜ Aspose.GIS を選ぶのですか？** このライブラリは 30 以上の GIS フォーマットをサポートし、外部ツールなしでジオメトリ変換を処理します。  
- **事前に必要なものは何ですか？** .NET Framework または .NET Core、Visual Studio（または任意の C# IDE）、および Aspose.GIS NuGet パッケージ。  
- **サンプルの実行時間はどれくらいですか？** ライブラリをインストールすれば、5 分未満で完了します。  
- **他のフォーマットにエクスポートできますか？** もちろんです—KML ドライバーを Shapefile、GeoJSON などに置き換えるだけです。  
完全な製品スイートは [Aspose のウェブサイト](https://releases.aspose.com/) からダウンロードできます。

## 「曲線を直線に変換」とは何か
曲線を直線に変換（**ジオメトリの線形化** とも呼ばれます）は、すべての曲線セグメントを短い直線の連続に置き換え、*線形ジオメトリ* を作成します。これにより、レンダリングが最大で5倍高速化され、メモリ使用量が削減され、線形フィーチャのみを受け付けるレガシー GIS サービスでもデータを利用できるようになります。

## なぜ曲線を直線に変換するのか
線形ジオメトリは、曲線ジオメトリに比べてレンダリングおよびクエリが最大 **5 倍速く** なり、**30 以上の GIS プラットフォーム** が線形フィーチャのみを受け入れます。ジオメトリを単純化することで、ウェブプレビュー用のファイルサイズも縮小され、ネットワーク分析やクラスタリングなど、直線入力を必要とするアルゴリズムを利用できるようになります。

## ジオメトリを線形化する方法
Aspose.GIS が提供する `ToLinearGeometry()` メソッドを使用します。このメソッドはジオメトリ内のすべての曲線を自動的にテッセレーションし、直線セグメントに変換すると同時に Z 値を保持するため、標高データを失うことなく線形近似が得られます。また、許容誤差を指定して元の曲線と生成されたセグメント間の最大偏差を制御でき、精度とファイルサイズのバランスを取ることができます。このメソッドは 2D および 3D ジオメトリの両方で機能します。

## 前提条件
1. **Aspose.GIS for .NET** – [Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
2. 開発マシンに **.NET Framework**（または .NET Core）がインストールされていること。  
3. サンプルの作成と実行のために **Visual Studio**（または任意の C# 対応 IDE）が必要です。

## 名前空間のインポート
Aspose.GIS の機能を使用し始めるには、必要な名前空間をインポートします。

### Core Aspose.GIS 名前空間
`Aspose.Gis` 名前空間には、すべての GIS 操作に必要なコアジオメトリクラス、ドライバー、ユーティリティが含まれています。  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### ターゲット形式用ドライバー
`Aspose.Gis.Drivers` はサポートされている各ファイル形式の静的ファクトリを提供します。`Drivers.Kml` は KML ライターを作成します。  
```csharp
using Aspose.GIS.Kml;
```

## 曲線を直線に変換するステップバイステップガイド
以下はコードの各行を詳細に解説したものです。**曲線を直線に変換する方法** と各ステップの重要性を説明します。

### 手順 1: 出力パスの定義
`Path.Combine` はプラットフォームに依存しないファイルパスを構築し、Windows のバックスラッシュと Unix のスラッシュを自動的に処理します。  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` を、KML ファイルを保存したいフォルダーに置き換えてください。

### 手順 2: 出力ファイル用レイヤーの作成
*レイヤー* は同じタイプの地理的フィーチャをグループ化します。ここでは、線形化されたジオメトリを格納する新しい KML レイヤーをインスタンス化します。  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### 手順 3: 新しいフィーチャの構築
*フィーチャ* は単一の地理オブジェクト（ポイント、ライン、ポリゴンなど）を表します。このフィーチャに線形ジオメトリを付与します。  
```csharp
var feature = layer.ConstructFeature();
```

### 手順 4: 元の複雑ジオメトリの定義
`Geometry.FromWkt` は Well‑Known Text（WKT）文字列をジオメトリオブジェクトに解析します。サンプルの WKT には、曲線処理を示すために `LineString`、`CompoundCurve`、`CircularString` が含まれています。  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### 手順 5: 曲線を直線に変換
`ToLinearGeometry()` はソースジオメトリ内のすべての曲線をテッセレーションし、直線セグメントに変換して、Z 座標を保持した新しい線形ジオメトリを返します。  
```csharp
var linear = geometry.ToLinearGeometry();
```

### 手順 6: 線形ジオメトリをフィーチャに割り当て
フィーチャの `Geometry` プロパティには、元の形状の簡略化された線形バージョンが格納されます。  
```csharp
feature.Geometry = linear;
```

### 手順 7: フィーチャをレイヤーに追加
フィーチャを KML レイヤーに追加すると、書き込みキューに入ります。`using` ブロックが終了すると、レイヤーはデータを出力ファイルにフラッシュします。  
```csharp
layer.Add(feature);
```

## よくある落とし穴とプロのコツ
- **パス区切り文字:** Windows と Linux の問題を回避するために `Path.Combine` を使用してください。  
- **非常に大きなジオメトリ:** 複雑な形状を線形化すると数千の頂点が生成される可能性があります。線形化後に `Simplify()` を呼び出してポイント数を削減することを検討してください。  
- **ドライバーの選択:** 別の出力フォーマットが必要な場合は、`Drivers.Kml` を `Drivers.Shapefile`、`Drivers.GeoJson` などに置き換え、ファイル拡張子もそれに合わせて変更してください。  
- **Z 値の保持:** `ToLinearGeometry()` は 3D（Z）座標を保持するため、標高データが失われません。

## よくある質問 (FAQ)

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: はい、Aspose.GIS は .NET Core で動作し、クロスプラットフォームアプリケーションを可能にします。

**Q: Aspose.GIS for .NET で異なる GIS ファイルフォーマットを扱えますか？**  
A: もちろんです！このライブラリは KML、Shapefile、GeoJSON など多数のフォーマットをサポートしており、合計で 30 以上の形式に対応しています。

**Q: Aspose.GIS は空間操作や分析を提供していますか？**  
A: はい、バッファリングから空間結合まで、幅広い空間機能を提供しています。

**Q: 無料トライアルは利用できますか？**  
A: はい、[Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/) から無料トライアルをダウンロードできます。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: コミュニティとスタッフのサポートは、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) をご覧ください。

### 追加の一般的な質問

**Q: 3D（Z）座標を含むジオメトリを線形化できますか？**  
A: はい、`ToLinearGeometry()` は 2D と 3D のジオメトリの両方で動作し、Z 値は保持されます。

**Q: 線形化はファイルサイズにどのように影響しますか？**  
A: 曲線を多数の短い線分に変換するとファイルサイズが増加する可能性があります。サイズが問題になる場合は、線形化後に `Simplify()` を実行してください。

**Q: 曲線を直線に変換する際にセグメントの長さを制御できますか？**  
A: デフォルトのメソッドは内部の許容誤差を使用します。カスタムのセグメンテーションが必要な場合は、`ToLinearGeometry()` を呼び出す前に曲線を手動でテッセレーションできます。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して **曲線を直線に変換する方法**（ジオメトリの線形化）を、環境設定から線形化された結果を KML ファイルに書き出すまでカバーしました。これで、マッピングアプリケーションやデータ処理パイプライン、または簡略化されたジオメトリが必要なあらゆる GIS 関連プロジェクトにこのワークフローを組み込むことができます。

---

**最終更新日:** 2026-09-10  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET で許容誤差付き GeoJSON を作成する方法](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Aspose.GIS for .NET でポリゴンをラインに変換する](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Aspose.GIS for .NET で LineString ジオメトリを作成する方法](/gis/net/geometry-creation/create-linestring-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}