---
title: Aspose.GIS for .NET を使用して線形化許容値を設定する
linktitle: 線形化許容値の設定
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET をマスターして、地理空間データを簡単に処理します。このステップバイステップのチュートリアルに従って、.NET での GIS 開発の可能性を最大限に引き出してください。
weight: 17
url: /ja/net/geometry-processing/set-linearization-tolerance/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用して線形化許容値を設定する

## 導入
地理情報システム (GIS) 開発の世界では、Aspose.GIS for .NET は、空間データを簡単かつ効率的に処理するための強力なツールセットとして際立っています。経験豊富な GIS 開発者でも、初心者でも、Aspose.GIS をマスターすると、.NET 環境で地理空間データを操作する能力が大幅に向上します。
## 前提条件
Aspose.GIS for .NET の使用に入る前に、次の前提条件が満たされていることを確認してください。
### 1. Visual Studioをインストールする
システムに Visual Studio がインストールされていることを確認してください。 Aspose.GIS for .NET は Visual Studio とシームレスに統合し、.NET 開発者に使い慣れた開発環境を提供します。
### 2. Aspose.GIS ライセンスを取得する
Aspose.GIS の可能性を最大限に引き出すには、有効なライセンスが必要です。 Aspose Web サイトからライセンスを取得することも、評価目的で一時ライセンスを選択することもできます。
### 3. .NET 用の Aspose.GIS をダウンロードする
Aspose Web サイトから Aspose.GIS for .NET ライブラリをダウンロードします。ダウンロード リンクは、以下のリソース セクションにあります。
### 4. C# に精通していること
このチュートリアルで提供される例を理解して実装するには、C# プログラミング言語の基本的な知識が不可欠です。

## 名前空間のインポート
Aspose.GIS for .NET の使用を開始する前に、必要な名前空間をプロジェクトにインポートします。
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
#ここで、提供された例を複数のステップに分けてみましょう:
## ステップ 1: 線形化許容値を設定する
このステップでは、GeoJSON オプションの線形化許容値を設定します。
```csharp
var options = new GeoJsonOptions
{
    //線形化されたジオメトリは曲線ジオメトリから 1e-4 以内にある必要があります
    LinearizationTolerance = 1e-4,
};
```
## ステップ 2: 出力パスを指定する
出力 JSON ファイルを保存するパスを定義します。
```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```
交換する`"Your Document Directory"`ファイルを保存する実際のディレクトリ パスに置き換えます。
## ステップ 3: ベクターレイヤーを作成する
指定されたオプションと出力パスを使用してベクター レイヤーを作成します。
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    //コードはここにあります
}
```
このコード スニペットは、`using`声明。
## ステップ 4: ジオメトリの構築
レイヤーに追加するジオメトリ (この場合は円形の文字列) を作成します。
```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```
ジオメトリ定義を目的のジオメトリに置き換えます。
## ステップ 5: フィーチャをレイヤーに追加する
フィーチャを構築し、それにジオメトリを割り当ててから、そのフィーチャをベクター レイヤーに追加します。
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

## 結論
Aspose.GIS for .NET をマスターすると、地理空間データの処理と操作の可能性が広がります。このチュートリアルに従い、Aspose が提供する広範なドキュメントとリソースを調べることで、GIS 開発スキルを新たな高みに高めることができます。
## よくある質問
### Aspose.GIS for .NET は他の .NET フレームワークと互換性がありますか?
はい、Aspose.GIS for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Aspose.GIS for .NET を商用プロジェクトで使用できますか?
絶対に！ Aspose.GIS for .NET は、商用プロジェクトで使用するための商用ライセンスを提供します。
### Aspose.GIS for .NET はさまざまな GIS データ形式をサポートしていますか?
はい、Aspose.GIS for .NET は、GeoJSON、Shapefile、KML などを含む幅広い GIS データ形式をサポートしています。
### Aspose.GIS for .NET の試用版はありますか?
はい、Aspose Web サイトから Aspose.GIS for .NET の無料試用版をダウンロードできます。
### Aspose.GIS for .NET のサポートはどこで入手できますか?
Aspose フォーラムから Aspose.GIS for .NET のサポートを得ることができます。以下のリソースセクションにあるサポートリンクにアクセスしてください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
