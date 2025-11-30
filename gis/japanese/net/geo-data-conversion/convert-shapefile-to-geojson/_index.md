---
date: 2025-11-30
description: Aspose.GIS を使用して .NET で Shapefile を GeoJSON に簡単に変換する方法を学びましょう。シームレスな地理空間データの相互運用性のために、ステップバイステップのガイドに従ってください。
language: ja
linktitle: Convert Shapefile to GeoJSON
second_title: Aspose.GIS .NET API
title: シェープファイルをGeoJSONに変換
url: /net/geo-data-conversion/convert-shapefile-to-geojson/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile を GeoJSON に変換する

## はじめに
現代の地理情報システム（GIS）では、**geospatial data interoperability** が強力な空間分析を実現する鍵です。最も一般的な変換タスクの一つは **convert shapefile to geojson** で、ウェブマップ、モバイルアプリ、クラウドサービスとの軽量データ交換を可能にします。このチュートリアルでは **Aspose.GIS .NET** ライブラリを使用した全プロセスを案内し、変換を C# アプリケーションに直接組み込む方法を示します。

## クイック回答
- **変換を処理するライブラリは何ですか？** Aspose.GIS for .NET  
- **実装にどれくらい時間がかかりますか？** Typically under 10 minutes for a single file  
- **ライセンスは必要ですか？** A free trial works for development; a license is required for production  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **複数のファイルを変換できますか？** Yes – just loop over the `VectorLayer.Convert` call  

## “convert shapefile to geojson” とは何ですか？
Shapefile（`.shp`、`.shx`、`.dbf` ファイルのコレクション）を GeoJSON に変換すると、データが単一の JSON ベース形式に変わり、ウェブブラウザで読み取り、編集、レンダリングが容易になります。JSON は特に Leaflet や Mapbox などの JavaScript マッピングライブラリに適しています。

## なぜ GIS データ形式変換に Aspose.GIS for .NET を使用するのですか？
- **All‑in‑one API** – 外部ツールなしで多数の形式（GeoTIFF、KML、GML など）を処理します。  
- **Zero‑dependency conversion** – GDAL や他のネイティブライブラリは不要です。  
- **High performance** – 大規模データセットやバッチ処理に最適化されています。  
- **Rich customization** – 座標系、属性フィルタなどを指定できます。  

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Aspose.GIS for .NET installed** – 公式の [Aspose.GIS for .NET documentation](https://reference.aspose.com/gis/net/) の手順に従って、NuGet パッケージをプロジェクトに追加してください。  
2. **A source Shapefile** – オープンデータポータル、政府機関から取得するか、QGIS/ArcGIS で作成してください。  
3. **Basic C# knowledge** – コードスニペットは C# の構文と .NET の慣習を使用しています。  

## 名前空間のインポート
まず、Aspose.GIS クラスと標準 .NET ユーティリティにアクセスできる名前空間をインポートします：

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップバイステップガイド

### ステップ 1: 入力と出力のパスを定義する
Shapefile が格納されているフォルダーと GeoJSON ファイルの出力先を設定します。環境に合わせてパスを調整してください。

```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```

> **プロのコツ:** `Path.Combine(dataDir, "InputShapeFile.shp")` を使用して、プラットフォームに依存しないパス構築を行います。

### ステップ 2: 変換を実行する
静的メソッド `VectorLayer.Convert` を呼び出します。この1行で Shapefile を読み取り、変換し、GeoJSON ファイルを書き出します。

```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```

実行後、`output_out.json` には有効な GeoJSON FeatureCollection が含まれ、任意のウェブマップビューアにロードできます。

## よくある問題と解決策
| 問題 | 発生原因 | 解決策 |
|------|----------|--------|
| **ファイルが見つかりません** | `dataDir` が間違っているか `.shp` ファイルが欠如しています | パスを確認し、3つの Shapefile コンポーネント（`.shp`、`.shx`、`.dbf`）がすべて存在することを確認してください。 |
| **座標系の不一致** | ソース Shapefile が、利用側で認識されない投影法を使用しています | `VectorLayer.Open(...).CoordinateSystem` を使用して、変換前に再投影してください。 |
| **大きなファイルでメモリ圧迫が発生** | データ全体がメモリにロードされます | フィーチャをチャンクで処理するか、`VectorLayer.Stream` を使用してストリーミング変換を行います。 |

## よくある質問

**Q: Aspose.GIS for .NET を使用して、複数の Shapefile を一度に GeoJSON に変換できますか？**  
**A:** Yes. Place the conversion code inside a `foreach` loop that iterates over each `.shp` file in a directory.

**Q: Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？**  
**A:** It supports .NET Framework 4.5 and higher, as well as .NET Core 3.1+ and .NET 5/6/7.

**Q: Aspose.GIS for .NET は Shapefile と GeoJSON 以外の地理空間フォーマットもサポートしていますか？**  
**A:** Absolutely. The library handles formats such as GeoTIFF, KML, GML, CSV, and many more.

**Q: 座標系や属性マッピングなど、変換プロセスをカスタマイズできますか？**  
**A:** Yes. The API offers overloads and properties to set target coordinate systems, filter attributes, and modify feature geometry during conversion.

**Q: Aspose.GIS for .NET のトライアル版は利用可能ですか？**  
**A:** Yes, you can download a free trial from the [Aspose website](https://releases.aspose.com/).

## 結論
これらの手順に従うことで、**Aspose.GIS for .NET** を使用して **shapefile を geojson に変換する方法** を効率的に習得しました。この機能によりシームレスな **geospatial data interoperability** が実現し、空間データを最新のウェブマップ、API、分析パイプラインに供給できます。プロジェクトが拡大するにつれ、KML、GML、ラスタ形式などを処理できる Aspose.GIS の幅広い **GIS data format conversion** 機能もぜひご活用ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-11-30  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose