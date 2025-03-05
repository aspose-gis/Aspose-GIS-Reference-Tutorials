---
title: Aspose.GIS for .NET によるジオメトリの正確な読み取りを制限する
linktitle: ジオメトリの読み取り精度を制限する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用してジオメトリを読み取る際の精度を効率的に管理する方法を学びます。最適なデータ処理については、ステップバイステップのガイドに従ってください。
type: docs
weight: 12
url: /ja/net/geometry-processing/limit-precision-reading-geometries/
---
## 導入
地理空間データ操作の分野では、Aspose.GIS for .NET は強力なツールとして機能し、開発者やエンジニアに同様に無数の機能を提供します。そのような機能の 1 つは、ジオメトリを読み取るときに精度を制限する機能です。これは、精度が最優先ではない特定のアプリケーションでは重要な側面です。このチュートリアルでは、Aspose.GIS for .NET を使用してこれを実現する方法を詳しく説明し、プロセスを管理可能な手順に分割します。
## 前提条件
この作業を開始する前に、次の前提条件が満たされていることを確認してください。
1. インストール: Aspose.GIS for .NET ライブラリを開発環境にインストールする必要があります。そうでない場合は、からダウンロードできます。[リリースページ](https://releases.aspose.com/gis/net/).
2. .NET に精通していること: 提供されているコード例を理解して実装するには、C# と .NET フレームワークの基本的な知識が必要です。
3. 開発環境: Visual Studio などの動作する .NET 開発環境が必要です。
4. ドキュメント ディレクトリ: プロセス中に生成されたシェープファイルを保存してアクセスできるディレクトリを設定します。

## 名前空間のインポート
ジオメトリの読み取り時に精度を制限する機能の実装を開始する前に、必要な名前空間をインポートしていることを確認してください。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ベクターレイヤーの作成
まず、ジオメトリを追加できるベクター レイヤーを作成する必要があります。これは、次のコード スニペットを使用して実現できます。
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```
## ステップ 2: 精度オプションの設定
次に、ジオメトリを読み取るためのオプションを定義し、必要な精度モデルを指定する必要があります。これは次のようにして実行できます。
```csharp
var options = new ShapefileOptions();
//データをそのまま読み取ります。
options.XYPrecisionModel = PrecisionModel.Exact;
```
## ステップ 3: 正確な精度でジオメトリを読み取る
次に、指定されたオプションを使用してベクター レイヤーを開いて、正確な精度でジオメトリを読み取りましょう。
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234、2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```
## ステップ 4: 切り捨ての精度
最後に、精度を特定の小数点以下の桁数に切り捨てたい場合は、それに応じて精度モデルを調整できます。
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1、2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 結論
結論として、ジオメトリを読み取る際の精度の管理は、地理空間データ操作の重要な側面です。 Aspose.GIS for .NET は、これを効率的に実現するための堅牢な機能を提供します。このチュートリアルで概説されている手順に従うことで、要件に応じて精度をシームレスに制限し、アプリケーションでの最適なデータ処理を確保できます。
## よくある質問
### Aspose.GIS for .NET を .NET Core や .NET Standard などの他の .NET フレームワークと一緒に使用できますか?
はい、Aspose.GIS for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Aspose.GIS for .NET の試用版はありますか?
はい、無料試用版は次のサイトから入手できます。[リリースページ](https://releases.aspose.com/).
### Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか?
を参照できます。[ドキュメンテーション](https://reference.aspose.com/gis/net/)詳細な情報と例については、
### Aspose.GIS for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは以下から取得できます。[購入ページ](https://purchase.aspose.com/temporary-license/) Aspose.GIS 用。
### Aspose.GIS for .NET のサポートまたはサポートはどこに求めればよいですか?
 Aspose.GIS にアクセスできます。[フォーラム](https://forum.aspose.com/c/gis/33)ご質問、ディスカッション、サポートのニーズにお応えします。