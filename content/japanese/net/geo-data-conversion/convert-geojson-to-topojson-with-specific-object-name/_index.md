---
title: 特定のオブジェクト名を使用して GeoJSON を TopoJSON に変換する
linktitle: 特定のオブジェクト名を使用して GeoJSON を TopoJSON に変換する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して、GeoJSON を特定のオブジェクト名を持つ TopoJSON に変換する方法を学びます。このチュートリアルでは、地理データを効率的に操作するためのステップバイステップのガイドを提供します。
type: docs
weight: 12
url: /ja/net/geo-data-conversion/convert-geojson-to-topojson-with-specific-object-name/
---
## 導入
Aspose.GIS for .NET は、.NET アプリケーションで地理データを操作するための強力なツールです。マッピング アプリケーションの開発、空間データの分析、または geojson ファイルの操作のいずれの場合でも、Aspose.GIS はワークフローを合理化するための包括的な機能セットを提供します。
## 前提条件
Aspose.GIS for .NET を使用して GeoJSON を特定のオブジェクト名を持つ TopoJSON に変換する前に、次のものが揃っていることを確認してください。
### 1. Aspose.GIS for .NET をインストールする
に向かう[ダウンロードページ](https://releases.aspose.com/gis/net/)最新バージョンの Aspose.GIS for .NET を入手します。
### 2. 開発環境をセットアップする
Visual Studio またはその他の .NET 開発環境がシステムにセットアップされていることを確認してください。
### 3. GeoJSON ファイルを準備する
TopoJSON に変換したい GeoJSON ファイルがあります。お持ちでない場合は、このチュートリアルで任意のサンプル GeoJSON ファイルを使用できます。

## 名前空間のインポート
変換プロセスを開始する前に、必要な名前空間をインポートしましょう。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ファイル パスを定義する
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithObjectName_out.topojson";
```
交換する`"Your Document Directory"`GeoJSON ファイルが存在する実際のディレクトリ パスと、変換された TopoJSON ファイルを保存する場所を指定します。
## ステップ 2: 変換オプションを設定する
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        //機能を書き込むオブジェクトの名前を指定します
        DefaultObjectName = "name_of_the_object",
    }
};
```
このステップでは、`ConversionOptions`対象にして指定する`DefaultObjectName`これは、結果として得られる TopoJSON ファイルにフィーチャを書き込むオブジェクトの名前です。
## ステップ 3: 変換を実行する
```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```
最後に、`Convert`の方法`VectorLayer`クラスを使用して、入力 GeoJSON ファイル、入出力ドライバー、変換オプションのパスを渡します。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して、GeoJSON を特定のオブジェクト名を持つ TopoJSON に変換する方法を学習しました。これらの手順に従うことで、.NET アプリケーションで地理データを効率的に管理および操作できます。
## よくある質問
### Aspose.GIS for .NET を商用プロジェクトで使用できますか?
はい、商用プロジェクトと個人プロジェクトの両方で Aspose.GIS for .NET を使用できます。
### Aspose.GIS for .NET に利用できる無料トライアルはありますか?
はい、次のサイトから無料トライアルを利用できます。[ここ](https://releases.aspose.com/).
### Aspose.GIS for .NET のサポートはどこで見つけられますか?
からサポートを受けることができます。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33).
### Aspose.GIS for .NET のライセンスを購入するにはどうすればよいですか?
ライセンスは以下から購入できます[ここ](https://purchase.aspose.com/buy).
### 評価には一時ライセンスが必要ですか?
はい、次から一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).