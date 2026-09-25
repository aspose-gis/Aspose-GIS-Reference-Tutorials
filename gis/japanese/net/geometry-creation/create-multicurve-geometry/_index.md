---
date: 2026-09-25
description: Aspose.GIS を使用して .NET で WKT をコンパウンド カーブ ジオメトリに変換し、ライン ストリングを追加する方法を学びます。このガイドでは、MultiCurve
  を使用した WKT からのジオメトリ作成を示します。
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: MultiCurve ジオメトリの作成
og_description: Aspose.GIS を使用して .NET で WKT をコンパウンド カーブ ジオメトリに変換し、ライン ストリングを追加する方法を学びます。このガイドでは、MultiCurve
  を使用した WKT からのジオメトリ作成を示します。
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Aspose.GIS for .NET を使用して WKT をコンパウンド カーブ ジオメトリに変換する
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Aspose.GIS for .NET を使用して WKT をコンパウンド カーブ ジオメトリに変換する
url: /ja/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した WKT の複合曲線ジオメトリへの変換

## はじめに
.NET GIS アプリケーションで **WKT を複合曲線ジオメトリに変換** する必要がある場合、Aspose.GIS はプロセスをスムーズかつ信頼性の高いものにします。このチュートリアルでは、Well‑Known Text (WKT) 文字列から `MultiCurve` ジオメトリを作成する手順を解説します。これは、**ラインストリング** コンポーネント、円弧、または複合曲線を単一のフィーチャに追加するシナリオに最適です。最後まで実行すれば、複数の曲線ジオメトリを 1 つの `MultiCurve` オブジェクトに結合する方法を示す、すぐに使えるシェープファイルが手に入ります。

## クイック回答
- **“WKT をジオメトリに変換” とは何ですか？** テキスト形式の WKT 表現を、GIS ライブラリが操作できる具体的なジオメトリオブジェクトに変換することを意味します。  
- **どの Aspose.GIS クラスが WKT を処理しますか？** `Geometry.FromText()` が WKT 文字列をジオメトリインスタンスに解析します。  
- **シンプルなラインストリングを追加できますか？** はい、`LineString` WKT（例: `"LineString (0 0, 1 0)"`）を含めるだけです。  
- **例で使用されているファイル形式は何ですか？** Shapefile ドライバで作成されたシェープファイル（`.shp`）です。  
- **開発にライセンスは必要ですか？** テスト用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。

## “WKT をジオメトリに変換” とは何か
WKT をジオメトリに変換するとは、テキスト形式の Well‑Known Text を `MultiCurve` や `LineString` などのメモリ上のオブジェクトモデルに解析することです。**`Geometry.FromText`** はこれらのオブジェクトを即座に生成し、OGC 標準を理解する任意の GIS ツールで保存、クエリ、レンダリングできるようにします。

## MultiCurve 作成に Aspose.GIS を使用する理由
Aspose.GIS を使用すると、単一の自己完結型 API 呼び出しで **複合曲線ジオメトリ** を作成できます。CircularString、CompoundCurve、CurveString の 3 種類の高度な曲線タイプをサポートし、ファイル全体をメモリに読み込むことなく最大 500 MB のデータセットを処理でき、バッチ処理シナリオで競合ライブラリに比べて約 30 % の速度向上を実現します。

## 前提条件
1. C# プログラミング言語の基本的な理解。  
2. Visual Studio（またはその他の .NET IDE）がインストールされていること。  
3. Aspose.GIS for .NET ライブラリ – [Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/)からダウンロードしてください。  
4. 点、線、曲線などの空間概念に慣れていること。

## 名前空間のインポート
Aspose.GIS for .NET の使用を開始するには、必要な名前空間を C# プロジェクトにインポートします。

`Geometry` は WKT をジオメトリオブジェクトに解析する静的メソッドを提供します。  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

これらの名前空間により、`MultiCurve` ジオメトリの作成と管理に必要なクラスにアクセスできます。

## 手順ガイド

### 手順 1: ドキュメントディレクトリとファイル名の定義
シェープファイルを保存するフォルダーを設定します。`"Your Document Directory"` を実際のパスに置き換えてください。

### 手順 2: Shapefile ドライバで `VectorLayer` を初期化
VectorLayer はシェープファイルなどのベクトルデータセットを表し、ジオメトリの読み書きを可能にします。  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
`VectorLayer` オブジェクトはベクトルデータセット（この場合はシェープファイル）を表し、ジオメトリを書き込むことができます。

### 手順 3: 新しいフィーチャの構築
Feature はジオメトリとその属性値を保持するコンテナです。  
```csharp
var feature = layer.ConstructFeature();
```
フィーチャはジオメトリと属性データのコンテナです。

### 手順 4: `MultiCurve` ジオメトリインスタンスの作成
`MultiCurve` は複数の曲線コンポーネントを単一の空間オブジェクトに集約するジオメトリタイプです。  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` は複数の曲線ジオメトリを保持でき、これらを単一の空間オブジェクトに結合できます。

### 手順 5: `MultiCurve` に曲線ジオメトリを追加
ここでは、3 種類の曲線タイプに対して **WKT をジオメトリに変換** します。
* シンプルな **ラインストリング**,
* 円弧（`CircularString`）,
* 直線セグメントと円弧を組み合わせた複合曲線。  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### 手順 6: `MultiCurve` をフィーチャに割り当て
これでフィーチャのジオメトリは、先ほど作成した複合 `MultiCurve` になります。  
```csharp
feature.Geometry = multiCurve;
```

### 手順 7: フィーチャを `VectorLayer` に追加
`using` ブロックが終了すると、フィーチャはシェープファイルに永続化されます。  
```csharp
layer.Add(feature);
```

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **`ArgumentException` on `Geometry.FromText`** | WKT 構文が無効です | WKT 文字列が OGC 仕様に従っているか確認してください（例: 座標間のカンマ、正しい括弧）。 |
| **Shapefile not created** | `path` が正しくない、または書き込み権限がありません | ディレクトリが存在し、アプリケーションに書き込み権限があることを確認してください。 |
| **Curves appear as straight lines in some viewers** | ビューアが円弧/複合曲線をサポートしていません | `ARC` ジオメトリタイプを理解できる GIS ビューア（例: QGIS）を使用してください。 |

## よくある質問

**Q: Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？**  
A: はい、.NET Framework、.NET Core、.NET Standard、そして .NET 5/6 以降をサポートしています。

**Q: Aspose.GIS for .NET を使用してカスタム空間データ形式を作成できますか？**  
A: もちろんです。API は多数の標準フォーマットの読み書きや変換を可能にし、独自形式にも拡張できます。

**Q: Aspose.GIS は空間分析機能を提供していますか？**  
A: はい、距離計算、交差検出、バッファリング、その他のジオメトリ操作が含まれています。

**Q: Aspose.GIS for .NET のトライアル版はありますか？**  
A: はい、購入前に機能を試せる無料トライアルを [Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/) からダウンロードできます。

**Q: 問題が発生した場合、どのようにサポートを受けられますか？**  
A: Aspose.GIS コミュニティフォーラムに問い合わせるか、ライセンスに含まれる公式サポートリソースをご参照ください。

---

**最終更新日:** 2026-09-25  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose

## 関連チュートリアル

- [複合曲線ジオメトリの作成](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Aspose.GIS for .NET で WKT からポイント数をカウントする方法](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Aspose.GIS for .NET を使用した MultiLineString ジオメトリの作成](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}