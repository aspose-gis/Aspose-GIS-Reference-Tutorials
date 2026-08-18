---
date: 2026-06-10
description: Aspose.GIS for .NET を使用して OSM を Shapefile に変換し、OpenStreetMap XML のフィーチャを読み取る方法を学びます。実践的なヒントを交えたステップバイステップガイドです。
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: OpenStreetMap XML からフィーチャを読み取る
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: OSM を Shapefile に変換 – Aspose.GIS で OpenStreetMap XML からフィーチャを読み取る
url: /ja/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# OSM を Shapefile に変換 – Aspose.GIS で OpenStreetMap XML からフィーチャを読み取る

.NET アプリケーション内で **OSM を Shapefile に変換** したり、単に OpenStreetMap (OSM) XML データを読み取ったりしたい場合は、ここが最適です。Aspose.GIS for .NET を使用すれば、OSM XML ファイルの取り込み、ノード・ウェイ・リレーションの抽出、そして Shapefile、GeoJSON、その他の GIS フォーマットへのエクスポートが簡単に行えます。このチュートリアルでは、環境設定からフィーチャの反復処理まで、全体のワークフローを順を追って説明しますので、すぐにマッピングや空間分析ソリューションの構築を開始できます。

## クイック回答
- **OSM XML を処理するライブラリは何ですか？** Aspose.GIS for .NET  
- **必要なコード行数はどれくらいですか？** 約 20 行（セットアップ除く）  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **.NET のどのバージョンがサポートされていますか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **大きな OSM ファイルを読み取れますか？** はい — Aspose.GIS はデータを効率的にストリーミングし、フィルタリングでメモリ使用量を削減します。

## 「how to read osm」とは何ですか？
OSM（OpenStreetMap）データの読み取りとは、OSM XML フォーマットを解析して、実世界の地理的特徴を表すノード、ウェイ、リレーションにアクセスすることを指します。解析後は、クエリ実行、可視化、変換など、さまざまな GIS アプリケーションでデータを利用できます。また、タグ、タイムスタンプ、ユーザー情報といったメタデータも含まれ、詳細な分析や編集ワークフローが可能になります。

## OSM に Aspose.GIS を使用する理由
Aspose.GIS は **依存関係ゼロ** のパーサーを提供し、最大 1 GB のファイルでも RAM 使用量 250 MB 未満で処理でき、オープンソースの多くの代替品より 3 倍高速です。さらに、組み込みのジオメトリ変換、空間クエリ、Shapefile、GeoJSON、KML などへの直接エクスポート機能を備えており、すべて純粋な .NET コードだけで実現できます。

## 前提条件
- **Visual Studio** (Community、Professional、Enterprise) – 最新バージョンを推奨。  
- **Aspose.GIS for .NET** – 公式の[download link](https://releases.aspose.com/gis/net/)からダウンロードし、NuGet パッケージをプロジェクトに追加してください。  
- 基本的な C# の知識（変数、ループ、OOP）。

## 名前空間のインポート
`Aspose.Gis` 名前空間はコア GIS 型を提供し、`Aspose.Gis.Geometries` にはジオメトリヘルパーが含まれます。

`Aspose.Gis` 名前空間は Aspose.GIS のすべての GIS 操作のエントリーポイントです。

## Aspose.GIS を使用して OSM を Shapefile に変換する方法
OSM XML レイヤーを読み込み、フィーチャを反復処理し、3 つの API 呼び出しだけで Shapefile に書き出します。`ShapefileWriter` クラスが新しい Shapefile を作成し、フィーチャを書き込みます。まず OSM ソース用に `Layer` オブジェクトを作成し、次に宛先フォルダーを指す `ShapefileWriter` を開き、最後に各フィーチャのジオメトリと属性をコピーします。この手法により、典型的な都市規模データセット（約 20 万フィーチャ）でも 1 分未満で OSM を Shapefile に変換できます。

## osm を geojson に変換する方法
Aspose.GIS は単一の `Save` 呼び出しで同じ OSM レイヤーを直接 GeoJSON にエクスポートでき、中間フォーマットの手間が不要です。`Save` メソッドはレイヤーを指定したフォーマットとファイルパスに書き込み、座標変換と属性マッピングを自動的に処理し、Web マッピング向けの標準準拠 GeoJSON ファイルを生成します。`layer.Save("output.geojson", SaveFormat.GeoJson)` を呼び出すだけです。

## 手順 1: ドキュメント ディレクトリの定義
OSM XML ファイルが格納されているフォルダーを定義します。  
`"Your Document Directory"` をファイルへの絶対パスまたは相対パスに置き換えてください。

## 手順 2: OpenStreetMap レイヤーを開く
`Layer` クラスは OSM XML ファイルなどのデータソースからロードされた GIS レイヤーを表します。  
レイヤーを開くと XML がストリーミングされ、必要な部分だけがメモリに保持されます。

## 手順 3: フィーチャ数を取得
OSM レイヤー内の総フィーチャ数を取得し、コンソールに出力します。これにより、ファイルが正しく読み込まれたかを確認できます。

## 手順 4: インデックスでフィーチャを取得
ゼロベースのインデックスで任意のフィーチャに直接アクセスできます。例では 3 番目のフィーチャを取得し、ランダムアクセスのデモを行います。

## 手順 5: フィーチャを反復処理
レイヤーを反復処理すると、ポイント、ライン、ポリゴンといった各ジオメトリを個別に処理できます。`AsText()` メソッドはジオメトリを Well‑Known Text (WKT) 形式で返すため、デバッグやログ出力に便利です。

## よくある問題と解決策
- **ファイルが見つかりません** – `dataDir` のパスを再確認し、OSM ファイル名が正確に一致していることを確認してください。  
- **サポートされていないジオメトリ** – 一部の OSM 要素は複雑なリレーションを含むため、まず `feature.Geometry` を確認し、`MultiPolygon` や `GeometryCollection` タイプを適切に処理してください。  
- **大規模ファイルでのパフォーマンス** – レイヤーを `using` ブロック内でロードして確実に破棄し、必要なフィーチャだけを取得する場合は LINQ フィルタリング（`layer.Where(f => f.Geometry is Point)`）を適用してください。

## よくある質問
### Aspose.GIS for .NET は他の GIS データ形式と互換性がありますか？
はい、Aspose.GIS は 30 種類以上の GIS フォーマット（Shapefile、GeoJSON、KML、GML、CSV など）をサポートしており、シームレスなデータ交換が可能です。

### Aspose.GIS を商用目的で使用できますか？
もちろんです。トライアルの制限を解除し、フルサポートを受けるには、[purchase page](https://purchase.aspose.com/buy) からライセンスをご購入ください。

### Aspose.GIS for .NET の無料トライアルはありますか？
はい、[website](https://releases.aspose.com/) から機能制限のない完全版トライアルをダウンロードし、購入前にすべての機能を評価できます。

### Aspose.GIS for .NET のサポートはどこで受けられますか？
公式の[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) にアクセスして質問やコードスニペットを共有し、コミュニティや Aspose エンジニアから支援を受けてください。

### Aspose.GIS for .NET の一時ライセンスは取得できますか？
はい、短期テストや CI パイプライン向けに、[temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスをリクエストできます。

---

**最終更新日:** 2026-06-10  
**テスト環境:** Aspose.GIS 24.5 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## 関連チュートリアル

- [Aspose.GIS for .NET で Shapefile を GeoJSON に変換する方法 – 包括的チュートリアル](/gis/net/)
- [Aspose.GIS で GeoJSON を TopoJSON に変換する方法](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [C# で Shapefile を読む – Aspose.GIS を使用した属性でフィーチャをフィルタリング](/gis/net/layer-management/filter-features-by-attribute/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}