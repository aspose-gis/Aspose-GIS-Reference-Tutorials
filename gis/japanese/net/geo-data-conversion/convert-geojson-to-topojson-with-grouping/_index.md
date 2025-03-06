---
title: グループ化を使用して GeoJSON を TopoJSON に変換する
linktitle: グループ化を使用して GeoJSON を TopoJSON に変換する
second_title: Aspose.GIS .NET API
description: この包括的なチュートリアルでは、Aspose.GIS for .NET を使用してグループ化を伴う GeoJSON を TopoJSON に変換する方法を学びます。
weight: 13
url: /ja/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# グループ化を使用して GeoJSON を TopoJSON に変換する

## 導入

Aspose.GIS for .NET を使用して、グループ化を使用して GeoJSON を TopoJSON に変換するためのステップバイステップ ガイドへようこそ。 Aspose.GIS は、開発者が地理データをシームレスに操作できるようにする強力な .NET API です。このチュートリアルでは、指定された属性に基づいてフィーチャをグループ化しながら、GeoJSON ファイルを TopoJSON に変換するプロセスについて説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

1.  Aspose.GIS for .NET: Aspose.GIS for .NET ライブラリをダウンロードしてインストールしていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/gis/net/).

2. 開発環境: Visual Studio またはその他の互換性のある IDE でセットアップされた作業用の開発環境が必要です。

3. サンプル GeoJSON ファイル: 変換するサンプル GeoJSON ファイルを準備します。サンプル GeoJSON ファイルをさまざまなソースから取得することも、独自のファイルを作成することもできます。

## 名前空間のインポート

まず、必要な名前空間がプロジェクトに含まれていることを確認してください。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```


次に、変換プロセスを複数のステップに分けてみましょう。

## ステップ 1: ファイル パスを定義する

入力 GeoJSON ファイルと出力 TopoJSON ファイルのパスを定義します。

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

交換する`"Your Document Directory"`ファイルが置かれている実際のディレクトリに置き換えます。

## ステップ 2: 変換オプションを構成する

変換オプションを構成して、グループ化の実行方法を指定します。この例では、特定の属性に基づいてフィーチャをグループ化します。

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // GeoJSON レイヤーでオブジェクトにグループ化する属性を指定します
        ObjectNameAttribute = "group",
        //属性値が不明なフィーチャのデフォルトのオブジェクト名を指定する
        DefaultObjectName = "unnamed",
    }
};
```

を調整します。`ObjectNameAttribute`そして`DefaultObjectName`GeoJSON データに応じたプロパティ。

## ステップ 3: 変換を実行する

Aspose.GIS API を使用して変換プロセスを実行します。

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

このコード行は、指定されたグループ化オプションを使用して GeoJSON ファイルを TopoJSON に変換します。

## 結論

このチュートリアルでは、Aspose.GIS for .NET を使用してグループ化を伴う GeoJSON を TopoJSON に変換する方法を学習しました。これらの簡単な手順に従うことで、.NET アプリケーションで地理データ形式を効率的に処理できます。

## よくある質問

### Q1: 複数の属性に基づいてフィーチャをグループ化できますか?
A: はい、変換オプションをカスタマイズして、複数の属性に基づいて機能をグループ化できます。

### Q2: Aspose.GIS は .NET Core と互換性がありますか?
A: はい、Aspose.GIS は、従来の .NET Framework とともに .NET Core をサポートしています。

### Q3: Aspose.GIS を使用して他の地理データ形式を変換できますか?
A: はい、Aspose.GIS は、GeoJSON や TopoJSON を超えたさまざまな地理データ形式をサポートしています。

### Q4: Aspose.GIS は無料トライアルを提供していますか?
 A: はい、Aspose.GIS の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).

### Q5: Aspose.GIS のサポートはどこで受けられますか?
 A: Aspose.GIS コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
