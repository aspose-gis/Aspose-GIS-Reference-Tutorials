---
date: 2025-12-20
description: Aspose.GIS for .NET を使用してジオメトリを書き込む際に精度を制限する方法を学びましょう。このステップバイステップガイドは、正確な座標制御で空間データを管理するのに役立ちます。
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GISでジオメトリを書き込む際の精度を制限する方法
url: /ja/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用してジオメトリを書き込む際の精度制限方法

.NET GIS アプリケーションでジオメトリを書き込む際に **精度を制限する方法** をお探しなら、Aspose.GIS for .NET は座標の丸めを制御するシンプルで高性能な手段を提供します。このチュートリアルでは、環境のセットアップから出力が定義した精度ルールに従っているかの検証まで、全工程を順に解説します。

## Quick Answers
- **「精度を制限する」とは何ですか？** 空間ファイルを書き込む際に、座標値を指定した小数桁数に丸めます。  
- **例で使用しているフォーマットはどれですか？** GeoJSON ですが、同じオプションは他のサポートフォーマットでも適用できます。  
- **試すのにライセンスは必要ですか？** 開発・テスト用の無料トライアルが利用可能です。商用利用には製品ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **Z 座標の精度だけ別に制御できますか？** はい、`ZPrecisionModel` を使用して正確な値または丸めた値を設定できます。

## How to Limit Precision When Writing Geometries
精度を制限することは、異なる GIS ツール間で座標表現を統一したり、ファイルサイズを削減したり、データ交換標準に準拠したりする際に重要です。以下では、精度オプションを定義しジオメトリを書き込み、丸めが正しく行われたかを読み戻して確認します。

## Prerequisites

### 1. Download and Installation
公式サイトから最新の Aspose.GIS for .NET パッケージを取得してください: [download link](https://releases.aspose.com/gis/net/)。インストールガイドに従い、NuGet パッケージをプロジェクトに追加します。

### 2. Namespace Import
GIS クラスやヘルパーユーティリティにアクセスできるよう、必要な名前空間をインポートします。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Define Precision Options
`GeoJsonOptions` インスタンスを作成し、X/Y および Z 座標の小数桁数を Aspose.GIS に指示します。

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Step 2: Set Output Path
生成される GeoJSON ファイルの保存先を指定します。

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Step 3: Create and Populate Geometry
上記で定義したオプションを使用して新しい `VectorLayer` を開き、`Point` ジオメトリを構築してレイヤーに追加します。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

### Step 4: Read and Verify Precision
作成したファイルを開き座標を出力します。X/Y の値が小数点以下 3 桁に丸められ、Z の値はそのまま正確に保持されていることが確認できるはずです。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Common Issues & Tips

- **Path Errors:** `path` に指定したディレクトリが存在することを確認するか、`Path.Combine` と `Environment.CurrentDirectory` を組み合わせて安全なファイルパスを構築してください。  
- **Precision Not Applied:** レイヤー作成時に `GeoJsonOptions` オブジェクトを渡しているか確認してください。渡さない場合はデフォルトのフルダブル精度が使用されます。  
- **Large Datasets:** 大量データを処理する場合は、単一の `VectorLayer` インスタンスを再利用し、フィーチャをバッチ追加することでパフォーマンスを向上させます。

## Frequently Asked Questions

**Q: Aspose.GIS for .NET は他の GIS フォーマットと互換性がありますか？**  
A: はい、Shapefile、GeoJSON、KML、GML など多数のフォーマットをサポートしており、フォーマット間のシームレスな変換が可能です。

**Q: 購入前に Aspose.GIS for .NET を試すことはできますか？**  
A: もちろんです。ダウンロードページから無料トライアルを入手でき、評価のためにすべての機能にフルアクセスできます。

**Q: テスト用の一時ライセンスはどう取得しますか？**  
A: Aspose ライセンスポータルで一時評価ライセンスを生成できます。有効期間は 30 日です。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose.GIS フォーラムや Stack Overflow の `aspose-gis` タグが質問やコミュニティによる解決策を得るのに適しています。

**Q: ライブラリは小規模スクリプトとエンタープライズ規模のアプリケーションの両方で動作しますか？**  
A: はい、Aspose.GIS はクイックプロトタイプから高スループットのサーバーアプリケーションまで、あらゆる規模の開発に対応できるよう設計されています。

## Conclusion
上記の手順に従うことで、Aspose.GIS for .NET を使用してジオメトリを書き込む際の **精度制限方法** が理解できました。座標の丸めを制御することで、空間データをクリーンに保ち、相互運用性とストレージ効率を高めることができます。これは GIS 中心のプロジェクトにとって重要な利点です。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose