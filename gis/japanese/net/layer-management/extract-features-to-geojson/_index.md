---
title: 特徴を GeoJSON に抽出する
linktitle: 特徴を GeoJSON に抽出する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用してフィーチャを GeoJSON に抽出するためのステップバイステップ ガイドをご覧ください。 GIS のパワーを簡単に活用しましょう。 #アスポーズ #GIS
type: docs
weight: 23
url: /ja/net/layer-management/extract-features-to-geojson/
---
## 導入
Aspose.GIS for .NET を使用して地物を GeoJSON に抽出するステップバイステップのチュートリアルへようこそ。経験豊富な開発者であっても、GIS プログラミングを始めたばかりであっても、このガイドではプロセスを順を追って説明し、Aspose.GIS for .NET の機能を最大限に活用できるようにします。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
-  Aspose.GIS for .NET: ライブラリがインストールされていることを確認してください。そうでない場合は、からダウンロードできます。[Aspose.GIS for .NET ページ](https://releases.aspose.com/gis/net/).
- シェープファイル データ: 入力可能なシェープファイルを用意します。サンプル データが必要な場合は、次の場所にあります。[Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/).
- .NET 環境: 提供されたコードを実行するために .NET 環境をセットアップします。
- ドキュメント ディレクトリ: コード スニペットでドキュメント ディレクトリへのパスを定義します。
これですべての準備が整ったので、GeoJSON への特徴の抽出を開始しましょう。
## 名前空間のインポート
まず、必要な名前空間をコードに含めます。
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
これらの名前空間は、Aspose.GIS 機能を操作するために不可欠です。
## ステップ 1: 入力シェープファイルを開く
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    //入力シェープファイルを処理するコードはここに記述します
}
```
次のコマンドを使用して、入力シェープファイルを開きます。`VectorLayer.Open`方法。
## ステップ 2: 出力 GeoJSON を作成する
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    //出力 GeoJSON を作成するコードはここにあります
}
```
を使用して出力 GeoJSON を作成します。`VectorLayer.Create`方法。
## ステップ 3: 属性をコピーする
```csharp
outputLayer.CopyAttributes(inputLayer);
```
を使用して、入力レイヤーから出力レイヤーに属性をコピーします。`CopyAttributes`方法。
## ステップ 4: プロセスの特徴
```csharp
foreach (Feature inputFeature in inputLayer)
{
    //各入力特徴を処理するコードはここに記述します
}
```
入力レイヤーの各フィーチャを反復処理し、個別に処理します。
## ステップ 5: 日付で機能をフィルタリングする
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
日付条件に基づいてフィーチャをフィルターします。この例では、生年月日が 1982 年より前の特徴をスキップします。
## ステップ 6: 新しいフィーチャーを構築する
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
入力フィーチャからジオメトリと値をコピーして、出力レイヤーの新しいフィーチャを構築します。
おめでとう！ Aspose.GIS for .NET を使用して地物を GeoJSON に抽出することに成功しました。
## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用してフィーチャを GeoJSON に抽出するプロセスについて説明しました。この強力なライブラリは、GIS 開発の可能性の世界を開きます。 Aspose.GIS の可能性を最大限に引き出すために、さまざまなデータセットと機能を試してください。
## よくある質問
### Q: 詳しいドキュメントはどこで入手できますか?
訪問[Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/)詳細な情報については。
### Q: 一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Q: どこにサポートを求めればよいですか?
に参加してください[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)コミュニティのサポートとディスカッションのために。
### Q: 無料トライアルはありますか?
はい、無料トライアルを見つけることができます[ここ](https://releases.aspose.com/).
### Q: Aspose.GIS for .NET はどこで購入できますか?
製品を購入できます[ここ](https://purchase.aspose.com/buy).