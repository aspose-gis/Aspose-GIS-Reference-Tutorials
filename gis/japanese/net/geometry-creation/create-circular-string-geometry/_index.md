---
date: 2026-08-30
description: Aspose.GIS for .NET を使用して circular string ジオメトリの shapefile を作成する方法を学びます。ステップバイステップのガイドでは、ベクターレイヤーの作成、ジオメトリの追加、そして
  Shapefile のエクスポートを示します。
keywords:
- how to create shapefile
- circular string geometry
- Aspose.GIS .NET
lastmod: 2026-08-30
linktitle: Circular String ジオメトリの作成
og_description: Aspose.GIS for .NET を使用して circular string ジオメトリの shapefile を作成する方法を学びます。ステップバイステップのチュートリアルに従ってベクターレイヤーを構築し、Shapefile
  をエクスポートしてください。
og_image_alt: 'Tutorial: create shapefile with circular string geometry using Aspose.GIS
  for .NET'
og_title: Aspose.GIS を使用した circular string で shapefile を作成する方法
schemas:
- author: Aspose
  dateModified: '2026-08-30'
  description: Learn how to create shapefile with circular string geometry using Aspose.GIS
    for .NET. Step-by-step guide shows vector layer creation, geometry addition, and
    Shapefile export.
  headline: How to create shapefile with circular string Aspose.GIS
  type: TechArticle
- description: Learn how to create shapefile with circular string geometry using Aspose.GIS
    for .NET. Step-by-step guide shows vector layer creation, geometry addition, and
    Shapefile export.
  name: How to create shapefile with circular string Aspose.GIS
  steps:
  - name: define the output file path
    text: Set the location where the Shapefile will be written. Replace `"Your Document
      Directory"` with the actual folder path on your system.
  - name: create vector layer
    text: Open a `VectorLayer` using the `Create` method. This is the core of the
      **create vector layer** operation.
  - name: construct a new feature
    text: A feature represents a single spatial record inside the layer.
  - name: build the circular string geometry
    text: Add the points that define the curved shape. The sequence of points creates
      an arc that starts and ends at the same location, forming a closed circular
      string.
  - name: assign geometry and add the feature to the layer
    text: Link the geometry to the feature and store it in the layer. When the `using`
      block ends, the layer is automatically flushed to the Shapefile on disk.
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
- shapefile creation
- Aspose.GIS
- GIS development
title: Aspose.GIS を使用した circular string で shapefile を作成する方法
url: /ja/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した円形ストリングの Shapefile の作成方法

## はじめに
もし .NET プラットフォーム上で GIS アプリケーションを構築しているなら、円形ストリングジオメトリを使用した **Shapefile の作成方法** を学ぶことは基本的なステップです。Aspose.GIS for .NET は全体のワークフローを簡素化します：ベクターレイヤーを作成し、拡張ジオメトリを付加し、数行の C# コードで結果を Shapefile に書き出します。

## クイック回答
- **「create vector layer」とは何ですか？** 新しいコンテナ（レイヤー）を作成し、ポイント、ライン、ポリゴンなどの空間フィーチャを保持できます。  
- **円形ストリングを表すクラスはどれですか？** `CircularString` は `Aspose.Gis.Geometries` からです。  
- **レイヤーを Shapefile として保存できますか？** はい – レイヤー作成時に `Drivers.Shapefile` を使用します。  
- **開発にライセンスは必要ですか？** 評価用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 「create vector layer」とは何ですか？
**vector layer** は、単一のデータソースにベクトルフィーチャ（ポイント、ライン、ポリゴン）を格納する論理コレクションです。  
*Direct answer:* `VectorLayer.Create(path, Drivers.Shapefile)` を `using` ブロック内で呼び出すことでベクターレイヤーを作成します。この呼び出しはディスク上にファイルを割り当て、フィーチャの挿入の準備を行います。レイヤーが存在したら、円形ストリングを含む任意のサポートされたジオメトリを追加でき、ライブラリが空間インデックスを自動的に処理します。

## なぜ円形ストリングを追加するのですか？
円形ストリングは、多数の短いラインセグメントを手動で生成することなく、滑らかな弧をモデル化できます。  
*Direct answer:* 円形ストリングを追加することで、曲線を表現するために必要な頂点数を最大 80 % 削減でき、ファイルサイズと描画パフォーマンスが向上し、道路や河川の曲がりなどの曲線フィーチャのジオメトリ精度を保ちます。

## 前提条件
- **.NET Framework または .NET Core** がマシンにインストールされていること。  
- **Aspose.GIS for .NET** ライブラリ – 公式サイトから **[こちら](https://releases.aspose.com/gis/net/)** でダウンロードしてください。  
- **Visual Studio** や **JetBrains Rider** などの IDE。  
- **C#** プログラミングの基本的な知識。

## 名前空間のインポート
以下の名前空間をインポートすると、コア GIS クラスにアクセスできます。

`Aspose.Gis` 名前空間はドライバ基盤を含み、`Aspose.Gis.Geometries` は `CircularString` などのジオメトリ型を提供します。

## Aspose.GIS を使用して Shapefile を作成する方法は？
VectorLayer はベクターデータソースの作成と管理に使用されるクラスです。  
出力パスを設定し、ベクターレイヤーを開き、円形ストリングを構築し、フィーチャを書き込む—これらを簡潔な手順で実行します。  
*Direct answer:* `using` ブロック内で `VectorLayer.Create(outputPath, Drivers.Shapefile)` を呼び出し、`Feature` をインスタンス化し、`AddPoint` で構築した `CircularString` ジオメトリを割り当て、レイヤーにフィーチャを追加します。ブロックが終了するとレイヤーは自動的にフラッシュされ、使用可能な Shapefile が生成されます。

### Step 1: 出力ファイルパスを定義する
Shapefile が書き込まれる場所を設定します。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

`"Your Document Directory"` をシステム上の実際のフォルダー パスに置き換えてください。

### Step 2: ベクターレイヤーを作成する
`Create` メソッドを使用して `VectorLayer` を開きます。これは **create vector layer** 操作の核心です。

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

### Step 3: 新しいフィーチャを構築する
フィーチャはレイヤー内の単一の空間レコードを表します。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 4: 円形ストリングジオメトリを構築する
曲線形状を定義するポイントを追加します。ポイントの順序により、同じ位置で開始・終了する弧が作成され、閉じた円形ストリングが形成されます。

```csharp
    var feature = layer.ConstructFeature();
```

### Step 5: ジオメトリを割り当て、フィーチャをレイヤーに追加する
ジオメトリをフィーチャにリンクし、レイヤーに保存します。

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

`using` ブロックが終了すると、レイヤーは自動的にディスク上の Shapefile にフラッシュされます。

## 一般的な問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **ファイルパスが無効** | ディレクトリが存在し、書き込み権限があることを確認してください。 |
| **CircularString が直線として表示される** | ポイントが正しい順序で追加されているか確認してください。閉じた形状の場合、最初と最後のポイントは同一である必要があります。 |
| **ライセンス例外** | 開発中は一時ライセンスを適用し、本番使用にはフルライセンスを購入してください。 |

## よくある質問

### Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？
はい、Aspose.GIS for .NET は .NET Framework 4.5 から最新の .NET 8 リリースまで、幅広い .NET バージョンで動作するよう設計されています。

### Aspose.GIS for .NET を他の GIS ライブラリと統合できますか？
もちろんです！他のライブラリでデータを読み取り、Aspose.GIS で操作し、再び書き戻すことができます。柔軟な API がそれを可能にします。

### Aspose.GIS for .NET は空間データの可視化をサポートしていますか？
はい、ライブラリにはレンダリングユーティリティが含まれており、ジオメトリのマップやビジュアル表現を生成できます。

### Aspose.GIS for .NET に関するサポートを求められるコミュニティフォーラムはありますか？
はい、質問や経験を共有できる Aspose.GIS フォーラムは **[こちら](https://forum.aspose.com/c/gis/33)** です。

### Aspose.GIS for .NET の評価用に一時ライセンスを取得できますか？
もちろんです！評価用の一時ライセンスは **[こちら](https://purchase.aspose.com/temporary-license/)** から入手できます。

### 同じレイヤーにより複雑なジオメトリ（例: MultiLineString）を追加するにはどうすればよいですか？
適切なジオメトリオブジェクト（例: `MultiLineString`）を作成し、個々の `LineString` オブジェクトで構成し、`feature.Geometry` に割り当てて、円形ストリングと同様にフィーチャを追加します。

## FAQ（クイックリファレンス）

**Q:** プログラムで **create vector layer** を作成するには？  
**A:** `using` ブロック内で `VectorLayer.Create(path, Drivers.Shapefile)`（または別のドライバ）を呼び出します。

**Q:** 円形ストリングにポイントを追加するメソッドは？  
**A:** 各座標に対して `circularString.AddPoint(x, y)` を使用します。

**Q:** 同じレイヤーに複数のジオメトリを保存できますか？  
**A:** はい、各ジオメトリごとに新しいフィーチャを作成し、`layer.Add(feature)` で追加します。

**Q:** Shapefile が作成されない場合はどうすればよいですか？  
**A:** 出力ディレクトリが存在し、書き込み権限があり、ドライバ（`Drivers.Shapefile`）が正しく参照されているか確認してください。

**Q:** 評価ビルドにライセンスは必要ですか？  
**A:** 開発・テストには一時ライセンスで十分ですが、本番展開にはフルライセンスが必要です。

## 結論
これらの手順に従うことで、Aspose.GIS for .NET を使用して **Shapefile** オブジェクトを作成し、**円形ストリング** ジオメトリで拡張する方法が分かります。この基盤により、交通ネットワークのマッピング、環境データの可視化、カスタム空間分析ツールの開発など、より高度な GIS ソリューションを構築できます。

---

**最終更新日:** 2026-08-30  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

## 関連チュートリアル

- [Aspose.GIS for .NET を使用した Shapefile の作成方法](/gis/net/layer-management/create-new-shapefile/)
- [Aspose.GIS を使用したベクターレイヤーと曲線ポリゴンの作成](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Aspose.GIS for .NET を使用した SRS 付きベクターレイヤーの作成方法](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}