---
title: シェープファイルを GeoJSON に変換する
linktitle: シェープファイルを GeoJSON に変換する
second_title: Aspose.GIS .NET API
description: Aspose.GIS を使用して、.NET で Shapefile を GeoJSON に簡単に変換する方法を学びます。シームレスなデータ相互運用性については、ステップバイステップのガイドに従ってください。
weight: 15
url: /ja/net/geo-data-conversion/convert-shapefile-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# シェープファイルを GeoJSON に変換する

## 導入
地理情報システム (GIS) の領域では、シームレスな統合と分析のためにデータの相互運用性が重要です。一般的なタスクの 1 つは、広く使用されている地理空間ベクトル データ形式であるシェープファイルを、地理空間データ交換用の軽量形式である GeoJSON に変換することです。このチュートリアルでは、Aspose.GIS for .NET ライブラリを使用して、Shapefile を GeoJSON に簡単に変換するプロセスを説明します。
## 前提条件
変換プロセスに入る前に、次の前提条件を満たしていることを確認してください。
### 1. Aspose.GIS for .NET ライブラリのインストール
訪問[Aspose.GIS for .NET ドキュメント](https://reference.aspose.com/gis/net/).NET 環境にライブラリをインストールしてセットアップする方法の詳細な手順を参照してください。
### 2. 入力シェープファイルのダウンロード
GeoJSON に変換する入力シェープファイルをダウンロードします。政府機関、オープン データ ポータルなどのさまざまなソースからシェープファイルを取得したり、QGIS や ArcGIS などの GIS ソフトウェアを使用して独自のシェープファイルを作成したりできます。
### 3. C# プログラミングの基礎知識
このチュートリアルでは変換プロセスに C# コード例を使用するため、C# プログラミング言語の基礎を理解してください。

## 名前空間のインポート
変換を続行する前に、Aspose.GIS for .NET の機能にアクセスするために必要な名前空間をインポートしていることを確認してください。
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ここで、変換プロセスを複数のステップに分けてみましょう。
## ステップ 1: 入力パスと出力パスを定義する
まず、入力シェープファイルと出力 GeoJSON ファイルのパスを指定します。
```csharp
string dataDir = "Your Document Directory";
string shapefilePath = dataDir + "InputShapeFile.shp";
string jsonPath = dataDir + "output_out.json";
```
必ず交換してください`"Your Document Directory"`ファイルが配置されている実際のディレクトリ パスに置き換えます。
## ステップ 2: 変換を実行する
を活用してください。`VectorLayer.Convert`変換処理を実行するメソッド:
```csharp
VectorLayer.Convert(shapefilePath, Drivers.Shapefile, jsonPath, Drivers.GeoJson);
```
このコード行は、入力シェープファイル (`shapefilePath` ) を GeoJSON 形式に変換し、出力を指定された場所に保存します`jsonPath`.

## 結論
シェープファイルを GeoJSON 形式に変換することは、GIS データ処理の基本的なタスクです。 Aspose.GIS for .NET ライブラリの助けを借りて、このプロセスは合理化され、効率的になります。このチュートリアルに従うことで、.NET アプリケーション内でこの変換を簡単に実行でき、シームレスな相互運用性と地理空間データの分析が可能になります。
## よくある質問
### Aspose.GIS for .NET を使用して、複数の Shapefile を一度に GeoJSON に変換できますか?
はい、このチュートリアルで説明したのと同様のアプローチを使用して、複数のシェープファイルをループし、GeoJSON 形式に変換できます。
### Aspose.GIS for .NET は、.NET Framework のすべてのバージョンと互換性がありますか?
Aspose.GIS for .NET は、.NET Framework 4.5 以降のバージョンをサポートしています。
### Aspose.GIS for .NET は、Shapefile と GeoJSON 以外の他の地理空間形式のサポートを提供しますか?
はい、Aspose.GIS for .NET は、GeoTIFF、KML、GML などを含む幅広い地理空間形式をサポートしています。
### 座標系や属性マッピングを指定するなど、変換プロセスをカスタマイズできますか?
はい、Aspose.GIS for .NET は、要件に応じて変換プロセスをカスタマイズするための広範なオプションを提供します。
### Aspose.GIS for .NET の試用版はありますか?
はい、Aspose.GIS for .NET の無料試用版を次のサイトから利用できます。[Webサイト](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
