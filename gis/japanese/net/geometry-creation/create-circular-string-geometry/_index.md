---
date: 2026-08-24
description: Aspose.GIS を使用してベクトルレイヤー .NET を作成し、円形ストリングジオメトリを追加する方法を学びましょう – GIS アプリケーションを構築するための高速で本番対応の方法です。
keywords:
- create vector layer .net
- circular string geometry
- Aspose.GIS .NET
- GIS vector layer
- C# geometry
lastmod: 2026-08-24
linktitle: 円形ストリングジオメトリの作成
og_description: Aspose.GIS を使用してベクトルレイヤー .NET を作成し、円形ストリングジオメトリを追加する方法を学びましょう – GIS
  アプリケーションを構築するための高速で本番対応の方法です。
og_image_alt: Tutorial showing how to create a vector layer and circular string geometry
  in Aspose.GIS for .NET
og_title: ベクトルレイヤー .NET と円形ストリングジオメトリを作成する
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  headline: Create vector layer .NET with circular string geometry
  type: TechArticle
- description: Learn how to create vector layer .NET and add circular string geometry
    with Aspose.GIS – a fast, production‑ready way to build GIS applications.
  name: Create vector layer .NET with circular string geometry
  steps:
  - name: Define the output file path
    text: Set the location where the Shapefile will be written. Use an absolute or
      relative path that your application can write to. Replace `"Your Document Directory"`
      with the actual folder path on your system.
  - name: Create vector layer
    text: '`VectorLayer.Create` opens (or creates) a new vector layer backed by the
      specified driver. This is the core of the **create vector layer .NET** operation.'
  - name: Construct a new feature
    text: A feature represents a single spatial record inside the layer. The `Feature`
      class holds attribute data and a geometry object.
  - name: Build the circular string geometry
    text: '`CircularString` is the class that models an arc‑based line. You add points
      with `AddPoint(x, y)`; the first and last points should be identical for a closed
      shape.'
  - name: Assign geometry and add the feature to the layer
    text: Link the geometry to the feature and store it in the layer. When the `using`
      block ends, the layer is automatically flushed to the Shapefile on disk. When
      the `using` block ends, the layer is automatically flushed to the Shapefile
      on disk.
  type: HowTo
- questions:
  - answer: It creates a new container (layer) that can hold spatial features like
      points, lines, or polygons.
    question: What does “create vector layer” mean?
  - answer: '`CircularString` from `Aspose.Gis.Geometries`.'
    question: Which class represents a circular string?
  - answer: Yes – use `Drivers.Shapefile` when creating the layer.
    question: Can I save the layer as a Shapefile?
  - answer: A temporary license works for evaluation; a full license is required for
      production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create vector layer
- circular string
- Aspose.GIS
- .NET GIS
- C# geometry
title: ベクトルレイヤー .NET と円形ストリングジオメトリを作成する
url: /ja/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ベクトルレイヤー .NET を円形文字列ジオメトリで作成する

## はじめに
.NET プラットフォーム上で GIS アプリケーションを構築する場合、最初のステップは **ベクトルレイヤー .NET** オブジェクトを作成し、空間フィーチャを格納することです。Aspose.GIS for .NET を使用すれば、このプロセスはシンプルになり、円形文字列などの高度なジオメトリでレイヤーを拡張できます。このチュートリアルでは、**ベクトルレイヤーを作成し**、**円形文字列ジオメトリを追加**し、結果を Shapefile として保存する方法を、クリーンで本番環境向けの C# コードとともに学びます。

## クイック回答
- **「ベクトルレイヤーを作成する」とは何ですか？** 空間フィーチャ（ポイント、ライン、ポリゴン）を保持できる新しいコンテナ（レイヤー）を作成します。  
- **円形文字列を表すクラスはどれですか？** `Aspose.Gis.Geometries` の `CircularString`。  
- **レイヤーを Shapefile として保存できますか？** はい – レイヤー作成時に `Drivers.Shapefile` を使用します。  
- **開発用にライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 「ベクトルレイヤーを作成する」とは？
ベクトルレイヤーは、ポイント、ライン、ポリゴンといったベクトルフィーチャを単一のデータソースにまとめて格納する論理的なグループです。コンテナとして機能し、空間レコードの管理、クエリ、永続化を効率的に行えます。Aspose.GIS では、`VectorLayer.Create` に対象ファイルパスとドライバ（例: Shapefile）を指定して作成します。

## なぜ円形文字列を追加するのか？
円形文字列は、従来のポリラインに比べてはるかに少ない頂点で滑らかな弧を表現できます。**曲線道路や河川の曲がり角など、真の曲線が必要なフィーチャをファイルサイズを増やさずに表現するのに最適です。**円形文字列を使用すると、密なラインストリング近似に比べて保存ポイント数を最大 80 % 削減でき、ストレージ効率と多くの GIS ビューアでの描画性能が向上します。

## 前提条件
開始する前に以下を確認してください。

- **.NET Framework または .NET Core** がマシンにインストールされていること。  
- **Aspose.GIS for .NET** ライブラリ – 公式サイトから **[download Aspose.GIS for .NET](https://releases.aspose.com/gis/net/)** をダウンロード。  
- **Visual Studio** または **JetBrains Rider** などの IDE。  
- **C#** プログラミングの基本的な知識。

## 名前空間のインポート
C# ファイルに必要な名前空間を追加します。

`Aspose.Gis` 名前空間はコア GIS 型を提供し、`Aspose.Gis.Geometries` は `CircularString` などのジオメトリ クラスを提供します。これらをインポートすることで、API がファイル全体で利用可能になります。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順別ガイド

### 手順 1: 出力ファイルパスの定義
Shapefile が書き込まれる場所を設定します。アプリケーションが書き込み可能な絶対パスまたは相対パスを使用してください。

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"` を実際のフォルダー パスに置き換えます。

### 手順 2: ベクトルレイヤーの作成
`VectorLayer.Create` は指定したドライバに裏付けられた新しいベクトルレイヤーを開く（または作成する）メソッドです。これが **ベクトルレイヤー .NET を作成する** 操作の核心です。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 手順 3: 新しいフィーチャの構築
フィーチャはレイヤー内の単一の空間レコードを表します。`Feature` クラスは属性データとジオメトリ オブジェクトを保持します。

```csharp
    var feature = layer.ConstructFeature();
```

### 手順 4: 円形文字列ジオメトリの構築
`CircularString` は弧ベースのラインをモデル化するクラスです。`AddPoint(x, y)` でポイントを追加します。閉じた形状にする場合、最初と最後のポイントは同一にしてください。

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 手順 5: ジオメトリを割り当て、フィーチャをレイヤーに追加
ジオメトリをフィーチャにリンクし、レイヤーに格納します。`using` ブロックが終了すると、レイヤーは自動的にディスク上の Shapefile にフラッシュされます。

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` ブロックが終了すると、レイヤーは自動的にディスク上の Shapefile にフラッシュされます。

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **ファイルパスが無効** | ディレクトリが存在し、書き込み権限があることを確認してください。 |
| **CircularString が直線として表示される** | ポイントが正しい順序で追加されているか確認してください。閉じた形状の場合、最初と最後のポイントは同一である必要があります。 |
| **ライセンス例外** | 開発中は一時ライセンスを適用し、本番環境ではフルライセンスを購入してください。 |
| **大規模データセットでのパフォーマンス低下** | Aspose.GIS はデータをストリーミング処理するため、全データをメモリにロードせずに 500 件以上のフィーチャを安全に処理できます。 |

## FAQ

### Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？
はい、Aspose.GIS for .NET は Framework 4.5 から最新の .NET 8 まで、幅広い .NET バージョンで動作するよう設計されています。

### Aspose.GIS for .NET を他の GIS ライブラリと統合できますか？
もちろんです。別のライブラリでデータを読み取り、Aspose.GIS で操作し、再度書き戻すことが可能です。柔軟な API がそれを支えます。

### Aspose.GIS for .NET は空間データの可視化をサポートしていますか？
はい、ライブラリにはマップやジオメトリの視覚表現を生成するレンダリングユーティリティが含まれています。

### Aspose.GIS for .NET に関する質問はどこでできますか？
はい、Aspose.GIS フォーラム **[Aspose GIS forum](https://forum.aspose.com/c/gis/33)** で質問や経験を共有できます。

### Aspose.GIS for .NET の評価用一時ライセンスは取得できますか？
もちろんです！評価用の一時ライセンスは **[temporary license page](https://purchase.aspose.com/temporary-license/)** から入手できます。

### 同じレイヤーに複雑なジオメトリ（例: MultiLineString）を追加するには？
適切なジオメトリ オブジェクト（例: `MultiLineString`）を作成し、個々の `LineString` を追加して `feature.Geometry` に割り当て、円形文字列と同様にフィーチャをレイヤーに追加します。

## FAQ（クイックリファレンス）

**Q:** プログラムで **ベクトルレイヤーを作成**する方法は？  
**A:** `using` ブロック内で `VectorLayer.Create(path, Drivers.Shapefile)`（または別のドライバ）を呼び出します。

**Q:** 円形文字列にポイントを追加するメソッドは？  
**A:** 各座標に対して `circularString.AddPoint(x, y)` を使用します。

**Q:** 同じレイヤーに複数のジオメトリを格納できますか？  
**A:** はい、ジオメトリごとに新しいフィーチャを作成し、`layer.Add(feature)` で追加します。

**Q:** Shapefile が作成されない場合の対処法は？  
**A:** 出力ディレクトリが存在し、書き込み権限があり、ドライバ (`Drivers.Shapefile`) が正しく参照されているか確認してください。

**Q:** 評価ビルドでライセンスは必須ですか？  
**A:** 開発・テストには一時ライセンスで十分ですが、本番展開にはフルライセンスが必要です。

## 結論
この手順に従うことで、Aspose.GIS for .NET を使用して **ベクトルレイヤー** オブジェクトを作成し、**円形文字列** ジオメトリで拡張する方法が習得できました。この基盤を活用すれば、交通ネットワークのマッピング、環境データの可視化、カスタム空間分析ツールの開発など、よりリッチな GIS ソリューションを構築できます。次は `MultiPolygon` などの他ジオメトリタイプを試したり、空間インデックスを活用してクエリ性能を向上させてみてください。

---

**最終更新日:** 2026-08-24  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [How to Create Vector Layer with SRS using Aspose.GIS for .NET](/gis/net/layer-management/create-vector-layer-with-srs/)
- [Create vector layer and curve polygon with Aspose.GIS](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Learn How to Create LineString Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}