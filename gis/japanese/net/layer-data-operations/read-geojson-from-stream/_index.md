---
title: Aspose.GIS for .NET を使用したストリームからの GeoJSON の読み取り
linktitle: ストリームから GeoJSON を読み取る
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用してストリームから GeoJSON を読み取る方法を学びます。地理空間をアプリケーションにシームレスに統合するには、ステップバイステップのガイドに従ってください。
weight: 14
url: /ja/net/layer-data-operations/read-geojson-from-stream/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したストリームからの GeoJSON の読み取り

## 導入
Aspose.GIS for .NET を使用してストリームから GeoJSON を読み取るためのステップバイステップ ガイドへようこそ。 Aspose.GIS は、.NET アプリケーションに地理空間機能を提供する強力な API であり、さまざまな GIS 形式をシームレスに操作できるようになります。このチュートリアルでは、Aspose.GIS を使用してストリームから GeoJSON データを読み取るプロセスを説明し、明確さと理解を容易にするために各ステップに分けて説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
1. C# の基本知識: C# プログラミング言語とその構文に精通している必要があります。
2.  Aspose.GIS のインストール: Aspose.GIS for .NET がインストールされていることを確認します。そうでない場合は、からダウンロードできます[ここ](https://releases.aspose.com/gis/net/).
3. 開発環境: Visual Studio や JetBrains Rider など、好みの開発環境をセットアップします。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートしましょう。
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ステップ 1: GeoJSON データを定義する
まず、C# コードで GeoJSON データを文字列として定義する必要があります。例えば：
```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```
## ステップ 2: ストリームから GeoJSON を読み取る
次に、Aspose.GIS を使用してストリームから GeoJSON データを読み取ります。
```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); //出力: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); //出力: メアリー
}
```

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用してストリームから GeoJSON データを読み取る方法を学習しました。上記の手順に従うことで、地理空間機能を .NET アプリケーションに簡単に統合できます。
## よくある質問
### Aspose.GIS は他の GIS 形式と互換性がありますか?
はい、Aspose.GIS は、GeoJSON、Shapefile、KML などのさまざまな GIS 形式をサポートしています。
### 購入する前に Aspose.GIS を試してみることはできますか?
はい、Aspose.GIS の無料トライアルを次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).
### Aspose.GIS のドキュメントはどこで見つけられますか?
 Aspose.GIS のドキュメントを見つけることができます。[ここ](https://reference.aspose.com/gis/net/).
### Aspose.GIS のサポートを受けるにはどうすればよいですか?
 Aspose フォーラムで Aspose.GIS のサポートを受けることができます。[ここ](https://forum.aspose.com/c/gis/33).
### Aspose.GIS を使用するには一時ライセンスが必要ですか?
 Aspose.GIS の一時ライセンスは、以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
