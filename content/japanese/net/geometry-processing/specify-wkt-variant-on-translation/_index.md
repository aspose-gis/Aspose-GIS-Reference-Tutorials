---
title: Aspose.GIS を使用して翻訳時に WKT バリアントを指定する
linktitle: 翻訳時に WKT バリアントを指定する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET で WKT バリアントを指定して、空間データ表現の形式と精度を効果的に制御する方法を学びます。
type: docs
weight: 19
url: /ja/net/geometry-processing/specify-wkt-variant-on-translation/
---
## 導入
Aspose.GIS for .NET は、開発者が .NET アプリケーションで地理情報システム (GIS) データを簡単に操作できるようにする強力なライブラリです。 Aspose.GIS が提供する重要な機能の 1 つは、翻訳中に Well-Known Text (WKT) バリアントを指定する機能であり、ユーザーが空間データ表現の形式と精度を制御できるようになります。このチュートリアルでは、Aspose.GIS for .NET を使用して WKT バリアントを指定する方法を段階的に説明します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1. Aspose.GIS for .NET: Aspose.GIS for .NET を次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/gis/net/).
2. 開発環境: .NET 開発環境がセットアップされていることを確認してください。
3. 基本的な知識: C# プログラミング言語と .NET フレームワークに関する知識。

## 名前空間のインポート
コードで Aspose.GIS 機能を使用する前に、必要な名前空間をインポートします。
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## ステップ 1: ポイント オブジェクトを作成する
まず、`Point`緯度、経度、およびオプションのメジャー (M) 値を含むオブジェクト:
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## ステップ 2: 空間参照系 (SRS) を設定する
空間参照系 (SRS) を点オブジェクトに割り当てます。この例では、WGS84 空間参照系を使用します。
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## ステップ 3: WKT バリアントを指定する
次に、翻訳用の WKT バリアントを指定します。 Aspose.GIS は、次のようなさまざまな WKT バリアントをサポートしています。`Iso`, `SimpleFeatureAccessOutdated` 、 そして`ExtendedPostGis`。要件に基づいて適切なバリエーションを選択してください。
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); //ポイント M (23.5732、25.3421、40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); //ポイント (23.5732、25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732、25.3421、40.3)
```
## ステップ 4: 数値フォーマットを制御する
WKT 表現における座標の数値形式を制御できます。 Aspose.GIS には、小数精度を指定するオプションが用意されています。
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); //ポイント M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); //ポイント M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); //ポイントM (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); //ポイント M (23.573 25.342 40.3)
```

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して翻訳時に WKT バリアントを指定する方法を学習しました。上記の手順に従うことで、開発者は .NET アプリケーションの空間データ表現の形式と精度を効果的に制御でき、地理情報システムの柔軟性と使いやすさが向上します。
## よくある質問
### Aspose.GIS は .NET のすべてのバージョンと互換性がありますか?
はい、Aspose.GIS は .NET Framework 4.0 以降をサポートしています。
### Aspose.GIS を商用プロジェクトに使用できますか?
はい、Aspose.GIS は個人プロジェクトと商用プロジェクトの両方に使用できます。
### Aspose.GIS は他の空間データ形式をサポートしていますか?
はい、Aspose.GIS は、ESRI Shapefile、GeoJSON、KML などの幅広い空間データ形式をサポートしています。
### Aspose.GIS に利用できる無料トライアルはありますか?
はい、Aspose.GIS の無料試用版を次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.GIS のヘルプやサポートはどこで入手できますか?
クエリを投稿したり、Aspose.GIS コミュニティから支援を求めることができます。[フォーラム](https://forum.aspose.com/c/gis/33).