---
title: 量子化を使用して GeoJSON を TopoJSON に変換する
linktitle: 量子化を使用して GeoJSON を TopoJSON に変換する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して量子化を行い、ファイル サイズと精度を最適化して、GeoJSON を TopoJSON に効率的に変換する方法を学びます。
weight: 14
url: /ja/net/geo-data-conversion/convert-geojson-to-topojson-with-quantization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 量子化を使用して GeoJSON を TopoJSON に変換する

## 導入
地理情報システム (GIS) の領域では、特に特定の使用例に合わせて最適化する場合、データ形式の変換が一般的に必要になります。 TopoJSON は、地理データを表現する際のコンパクトさと効率性で知られており、そのような目的に貴重な形式を提供します。 Aspose.GIS for .NET は、この変換をシームレスに促進する堅牢なツールを提供します。
## 前提条件
変換プロセスに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.GIS for .NET: Aspose.GIS for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/gis/net/).
2. GeoJSON データ: 変換する GeoJSON ファイルを準備します。 .NET 環境からアクセスできることを確認してください。

## 名前空間のインポート
変換プロセスを開始するには、必要な名前空間をインポートします。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: パスと出力ファイルを定義する
まず、入力 GeoJSON ファイルと目的の出力 TopoJSON ファイルのパスを定義します。それに応じてファイル パスを調整します。
```csharp
string SampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithQuantization_out.topojson";
```
## ステップ 2: 変換オプションを指定する
特に TopoJSON の量子化に焦点を当てて、変換オプションを構成します。この手順により、要件に応じて出力ファイルのサイズと精度を最適化できます。
```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        QuantizationNumber = 100_000,
    }
};
```
## ステップ 3: 変換を実行する
 Aspose.GIS メソッドを使用して変換プロセスを実行します。このステップには、`Convert`からのメソッド`VectorLayer`適切なパラメータを使用して。
```csharp
VectorLayer.Convert(SampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

## 結論
結論として、Aspose.GIS for .NET を利用すると、量子化を使用した GeoJSON から TopoJSON への変換が簡素化されます。概要を示した手順に従うことで、特定のニーズに合わせてファイル サイズと精度を最適化しながら、地理データを効率的に変換できます。
## よくある質問
### Aspose.GIS for .NET はさまざまな GeoJSON 構造と互換性がありますか?
Aspose.GIS for .NET は幅広い GeoJSON 構造をサポートし、さまざまなデータセットとの互換性を保証します。
### TopoJSON 変換の量子化パラメータをカスタマイズできますか?
はい、量子化パラメータを微調整して、好みに応じてファイル サイズと精度のバランスをとることができます。
### Aspose.GIS for .NET は他の GIS 形式のサポートを提供しますか?
もちろん、Aspose.GIS for .NET は多数の GIS 形式をサポートし、多用途のデータ処理機能を可能にします。
### Aspose.GIS for .NET の試用版はありますか?
はい、利用可能な無料トライアルを通じて、Aspose.GIS for .NET の機能を探索できます。[ここ](https://releases.aspose.com/).
### Aspose.GIS for .NET に関連するサポートを求めたり、ディスカッションに参加したりできるのはどこですか?
 Aspose.GIS コミュニティ フォーラムに参加して、サポートやディスカッションを行うことができます。[ここ](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
