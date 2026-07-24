---
date: 2026-07-24
description: Aspose.GIS を使用して .NET で Shapefile を GeoJSON に簡単に変換し、C# で Shapefile を読み込む際にシームレスな地理空間データ相互運用性を実現する方法を学びましょう。
keywords:
- convert shapefile to geojson
- read shapefile c#
- c# shapefile to geojson
- export geojson c#
- convert shapefile to json
lastmod: 2026-07-24
linktitle: Shapefile を GeoJSON に変換
og_description: Aspose.GIS for .NET を使用して shapefile を geojson に素早く変換します。10 分以内でステップバイステップの
  C# コード、前提条件、トラブルシューティングを学びましょう。
og_image_alt: 'Developer guide: Convert Shapefile to GeoJSON in C# with Aspose.GIS'
og_title: Shapefile を GeoJSON に変換 – 高速 C# ガイド (50‑60 文字)
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to effortlessly convert Shapefile to GeoJSON in .NET using
    Aspose.GIS and achieve seamless geospatial data interoperability while reading
    Shapefile in C#.
  headline: Convert Shapefile to GeoJSON
  type: TechArticle
- questions:
  - answer: Yes. Place the conversion code inside a `foreach` loop that iterates over
      each `.shp` file in a directory, calling `VectorLayer.Convert` for every file.
    question: Can I convert multiple Shapefiles to GeoJSON in one go using Aspose.GIS
      for .NET?
  - answer: It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and
      .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV,
      and many more—over 60 in total.
    question: Does Aspose.GIS for .NET provide support for other geospatial formats
      apart from Shapefile and GeoJSON?
  - answer: Yes. The API offers overloads and properties to set target coordinate
      systems, filter attributes, and modify feature geometry during conversion.
    question: Can I customize the conversion process, such as specifying a coordinate
      system or attribute mappings?
  - answer: Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert shapefile
- Aspose.GIS
- C# geospatial processing
- geojson export
title: Shapefile を GeoJSON に変換
url: /ja/net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile を GeoJSON に変換

## はじめに
最新の地理情報システム (GIS) において、**ジオ空間データ相互運用性**は強力な空間分析を実現する鍵です。最も一般的な変換タスクのひとつは**Shapefile を GeoJSON に変換**することで、ウェブマップ、モバイルアプリ、クラウドサービスとの軽量データ交換が可能になります。このチュートリアルでは、**C# で Shapefile を読み取る**方法と、Aspose.GIS .NET ライブラリを使用して GeoJSON としてエクスポートする手順を示しますので、変換をアプリケーションに直接組み込むことができます。

## クイック回答
- **変換を処理するライブラリは何ですか？** Aspose.GIS for .NET  
- **実装にどれくらい時間がかかりますか？** 通常、単一ファイルで 10 分未満です  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作します。製品環境ではライセンスが必要です  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7  
- **複数のファイルを変換できますか？** はい – `VectorLayer.Convert` 呼び出しをループするだけです  

## “Shapefile を GeoJSON に変換” とは？
Shapefile（`.shp`、`.shx`、`.dbf` の 3 ファイル）を GeoJSON に変換すると、データが単一の JSON ベース形式に変換され、ブラウザでの読み取り、編集、レンダリングが容易になります。GeoJSON は特に Leaflet や Mapbox などの JavaScript マッピングライブラリに適しています。

## なぜ GIS データ形式変換に Aspose.GIS for .NET を使用するのか？
Aspose.GIS は包括的で純粋にマネージドされたソリューションを提供し、60 以上のベクタおよびラスタ形式をサポートし、外部依存関係を排除し、大規模データセットでも高速変換を実現します。信頼性とパフォーマンスが重要なエンタープライズやクラウド環境に最適です。

- **All‑in‑one API** – **60 以上** のジオ空間ベクタおよびラスタ形式をサポートし、KML、GML、CSV、GeoTIFF などを含みます。  
- **Zero‑dependency conversion** – GDAL、Proj4、またはネイティブバイナリは不要で、すべて純粋なマネージドコードで実行されます。  
- **High performance** – 典型的なサーバー VM で **500 MB** のファイルを **5 秒** 未満で処理し、過剰なメモリ使用なしでバッチジョブを処理できます。  
- **Rich customization** – ターゲット座標系の指定、属性のフィルタリング、ジオメトリのオンザフライ変換が可能です。  

## 前提条件
1. **Aspose.GIS for .NET がインストール済み** – 公式の [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) の手順に従って NuGet パッケージをプロジェクトに追加してください。  
2. **ソース Shapefile** – オープンデータポータル、政府機関から取得するか、QGIS/ArcGIS で作成してください。  
3. **基本的な C# の知識** – コードスニペットは C# 構文と .NET の慣習を使用しています。  

## 名前空間のインポート
`Aspose.GIS` 名前空間はベクタデータの読み書きに必要なクラスを提供します。

`Aspose.GIS.Geometries` 名前空間にはジオメトリ型が含まれ、`Aspose.GIS.VectorLayers` には形式変換を実行する `VectorLayer` クラスが格納されています。`Aspose.GIS.VectorLayers` 名前空間には形式変換に使用される `VectorLayer` クラスが含まれています。

## C# で Shapefile を GeoJSON に変換する方法は？
`VectorLayer.Open` メソッドはファイルからベクタデータセットを読み込み、`VectorLayer` オブジェクトを生成します。  
`VectorLayer.Convert` は静的メソッドで、ソースベクタファイルを直接 GeoJSON などのターゲット形式に変換します。

`VectorLayer.Open` でソース Shapefile を読み込み、静的 `VectorLayer.Convert` メソッドを呼び出して GeoJSON ファイルを書き出すだけです。このアプローチはソースを読み取り、必要に応じて再投影し、結果を直接ディスクにストリームし、中間オブジェクトを不要にします。

### 手順 1: 入力と出力のパスを定義
Shapefile が格納されたフォルダーと GeoJSON ファイルの出力先フォルダーを設定します。環境に合わせてパスを調整してください。

プラットフォームに依存しないパス構築には `Path.Combine(dataDir, "InputShapeFile.shp")` を、結果ファイルには `Path.Combine(outputDir, "output.geojson")` を使用します。

> **Pro tip:** 3 つの Shapefile コンポーネント（`.shp`、`.shx`、`.dbf`）を同じフォルダーに保管してください。`VectorLayer.Open` が自動的に関連ファイルを検出します。

### 手順 2: 変換を実行
`VectorLayer.Convert(inputPath, outputPath, OutputFormat.GeoJSON)` を呼び出します。この 1 行で Shapefile を読み取り、変換し、有効な GeoJSON FeatureCollection を書き出します。

実行後、`output.geojson` には任意のウェブマップビューア、GIS サーバー、または分析パイプラインで読み込める完全に準拠した GeoJSON ドキュメントが格納されます。

## これが重要な理由
- **Interoperability:** GeoJSON に変換することで、プロプライエタリ形式を気にせず、幅広いウェブベース GIS ツールとデータを共有できます。  
- **Performance:** Aspose.GIS はメモリ内で変換を処理するため、外部コマンドラインユーティリティを呼び出すよりも高速です。  
- **Scalability:** 同じアプローチをループやバックグラウンドサービスでラップすれば、データパイプライン向けの大量変換も容易に処理できます。  

## よくある問題と解決策
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **ファイルが見つかりません** | `dataDir` が間違っているか `.shp` ファイルが欠落しています | パスを確認し、3 つの Shapefile コンポーネント（`.shp`, `.shx`, `.dbf`）がすべて存在することを確認してください。 |
| **座標系の不一致** | ソースの Shapefile が、利用側で認識されない投影を使用しています | `VectorLayer.Open(...).CoordinateSystem` を使用して変換前に再投影してください。 |
| **大きなファイルでメモリ圧迫が発生** | データセット全体がメモリに読み込まれます | フィーチャをチャンクで処理するか、`VectorLayer.Stream` を使用してストリーミング変換を行ってください。 |

## よくある質問

**Q: Aspose.GIS for .NET を使用して、複数の Shapefile を一括で GeoJSON に変換できますか？**  
A: はい。ディレクトリ内の各 `.shp` ファイルを走査する `foreach` ループに変換コードを配置し、各ファイルに対して `VectorLayer.Convert` を呼び出します。

**Q: Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？**  
A: .NET Framework 4.5 以上、.NET Core 3.1+、および .NET 5/6/7 をサポートしています。

**Q: Aspose.GIS for .NET は Shapefile と GeoJSON 以外のジオ空間形式もサポートしていますか？**  
A: もちろんです。ライブラリは GeoTIFF、KML、GML、CSV など、合計で 60 以上の形式を扱えます。

**Q: 変換プロセスをカスタマイズできますか？たとえば座標系や属性マッピングを指定することは可能ですか？**  
A: はい。API はオーバーロードやプロパティを提供しており、ターゲット座標系の設定、属性のフィルタリング、変換中のフィーチャジオメトリの変更が可能です。

**Q: Aspose.GIS for .NET のトライアル版はありますか？**  
A: はい、[Aspose のウェブサイト](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

## 結論
これらの手順に従うことで、**Aspose.GIS for .NET** を使用した **Shapefile を GeoJSON に効率的に変換** する方法が分かります。この機能により **ジオ空間データ相互運用性** が実現し、最新のウェブマップ、API、分析パイプラインに空間データをシームレスに供給できます。プロジェクトが進化するにつれて、KML、GML、ラスタ形式など、Aspose.GIS の幅広い **GIS データ形式変換** 機能もぜひ活用してください。

---

**最終更新日:** 2026-07-24  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

## 関連チュートリアル

- [Aspose.GIS for .NET でストリームから GeoJSON を読み取る方法](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS で GeoJSON を TopoJSON に変換する方法](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS で Shapefile C# を読み取り – 属性でフィーチャをフィルタリングする方法](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}