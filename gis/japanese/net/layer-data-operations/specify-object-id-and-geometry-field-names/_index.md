---
title: オブジェクト ID とジオメトリ フィールド名の指定
linktitle: オブジェクト ID とジオメトリ フィールド名の指定
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET で GIS の魔法を体験してください!地理空間データを簡単に管理します。今すぐダウンロードして、空間インテリジェンスのパワーを解放してください。
type: docs
weight: 20
url: /ja/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## 導入
Aspose.GIS for .NET を使用して地理情報システム (GIS) の領域への旅に乗り出すと、開発者と愛好家にとって同様に可能性の世界が開かれます。この強力なライブラリにより、地理空間データを簡単に処理できるようになります。このチュートリアルでは、オブジェクト ID とジオメトリ フィールド名を指定するプロセスをガイドし、GIS 作業の基礎を築きます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.GIS for .NET: からライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/gis/net/).
- ドキュメント ディレクトリ: ジオデータベースを保存するドキュメント用のディレクトリを設定します。
- .NET 環境: .NET 環境が動作していることを確認してください。
## 名前空間のインポート
作業を開始するには、必要な名前空間をプロジェクトにインポートする必要があります。これらの名前空間は、Aspose.GIS for .NET と対話するための必須のクラスとメソッドを提供します。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## ステップ 1: オブジェクト ID とジオメトリ フィールド名の指定
このステップでは、GIS データのオブジェクト ID とジオメトリ フィールド名を設定する方法を学習します。これは効率的なデータ管理にとって非常に重要です。
## ステップ 1.1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを定義します。
```csharp
string dataDir = "Your Document Directory";
```
## ステップ 1.2: GeoDatabase の作成とオプションの定義
指定したオブジェクト ID とジオメトリ フィールド名を使用して GeoDatabase を作成します。
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         //オブジェクトIDフィールド名を指定します
        GeometryFieldName = "POINT",       //ジオメトリフィールド名を指定します
    };
```
## ステップ 1.3: レイヤーの作成と追加
GeoDatabase 内にレイヤーを作成し、特定のジオメトリを持つフィーチャを追加します。
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //ジオメトリ (この場合は点) を指定します
    layer.Add(feature);
}
```
## ステップ 1.4: レイヤーを開いてデータを取得する
レイヤーを開いて、指定されたオブジェクト ID に基づいてそこからデータを取得します。
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); //出力: 1
}
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用してオブジェクト ID とジオメトリ フィールド名を指定するプロセスを正常に完了しました。これにより GIS プロジェクトの強固な基盤が築かれ、地理空間データを簡単に管理できるようになります。
## よくある質問
### Q: Web アプリケーションで Aspose.GIS for .NET を使用できますか?
A: はい、Aspose.GIS for .NET はデスクトップ アプリケーションと Web アプリケーションの両方に適しており、多用途の地理空間機能を提供します。
### Q: 購入前に利用できる試用版はありますか?
 A: はい、無料トライアルを利用して、Aspose.GIS for .NET の機能を探索できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.GIS for .NET の一時ライセンスを取得するにはどうすればよいですか?
 A: 仮免許を取得できます。[ここ](https://purchase.aspose.com/temporary-license/)評価目的のため。
### Q: Aspose.GIS for .NET はどのような空間参照系をサポートしていますか?
A: Aspose.GIS for .NET はさまざまな空間参照系をサポートし、さまざまな地理データセットに柔軟性を提供します。
### Q: Aspose.GIS 関連の質問については、どこに相談したり、相談したりできますか?
 A: Aspose.GIS フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/gis/33)サポートとディスカッションのため。