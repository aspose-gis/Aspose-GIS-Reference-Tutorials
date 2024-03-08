---
title: GeoJSON からファイル GDB への変換をわかりやすく解説
linktitle: GeoJSON レイヤーをファイル GDB に変換
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET で地理空間の驚異を解き放ちましょう! GeoJSON レイヤーをファイル ジオデータベースに簡単に変換します。やってみよう！ #アスポーズ #GIS
type: docs
weight: 17
url: /ja/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## 導入
地理情報システム (GIS) の動的な領域では、異なる形式間でデータをシームレスに変換する機能が重要です。 Aspose.GIS for .NET は強力な味方として登場し、地理空間データを簡単に処理するための包括的なツール スイートを提供します。このチュートリアルでは、Aspose.GIS for .NET を使用して GeoJSON レイヤーをファイル ジオデータベース (ファイル GDB) に変換するプロセスを詳しく説明します。
## 前提条件
この地理空間の旅を開始する前に、次の前提条件が満たされていることを確認してください。
- .NET プログラミングに関する実践的な知識。
-  Aspose.GIS for .NET がインストールされています。そうでない場合は、からダウンロードしてください[ここ](https://releases.aspose.com/gis/net/)インストール手順に従ってください。
## 名前空間のインポート
変換プロセスを開始するには、必要な名前空間をインポートすることから始めます。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
ここで、プロセスをステップバイステップのガイドに分解してみましょう。
## ステップ 1: GeoJSON レイヤーをセットアップする
まず、関連する属性と機能を備えた GeoJSON レイヤーを作成します。以下にガイドとなるスニペットを示します。
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    //属性の追加
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //機能の構築と追加
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## ステップ 2: テスト データセットをコピーする
テスト データの整合性を維持するには、データセットのコピーを作成します。次のコード スニペットを使用します。
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## ステップ 3: GeoJSON をファイル GDB に変換する
次に、変換を実行します。次のコードを利用します。
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        //属性をコピーする
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        //機能を追加する
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して GeoJSON レイヤーをファイル ジオデータベースに変換するという興味深い領域をナビゲートしました。この知識を身につければ、.NET アプリケーションで地理空間データをシームレスに操作できるようになります。
## よくある質問
### Aspose.GIS は最新の .NET Framework と互換性がありますか?
はい、Aspose.GIS は最新の .NET Framework バージョンと互換性があります。
### Aspose.GIS を使用して他の地理空間形式を変換できますか?
絶対に！ Aspose.GIS は、多用途なデータ操作のための幅広い地理空間形式をサポートしています。
### Aspose.GIS の試用版はありますか?
はい、試用版をダウンロードすると、Aspose.GIS の機能を探索できます。[ここ](https://releases.aspose.com/).
### Aspose.GIS 関連のクエリのサポートを受けるにはどうすればよいですか?
 Aspose.GIS にアクセスします。[フォーラム](https://forum.aspose.com/c/gis/33)専用のサポートを提供します。
### Aspose.GIS の一時ライセンスを取得できますか?
はい、一時ライセンスを確保できます[ここ](https://purchase.aspose.com/temporary-license/).