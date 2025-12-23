---
date: 2025-12-23
description: Aspose.GIS for .NET を使用して、ジオメトリをさまざまなオプションで WKT に変換し、数値形式を設定し、小数点以下の精度を調整する方法を学びましょう。
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Aspose.GIS を使用してジオメトリを WKT バリアント オプションに変換
url: /ja/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用したジオメトリの WKT バリアントオプションへの変換

## Introduction
最新の .NET アプリケーションでは、**ジオメトリを WKT に変換**することは、空間データを他システムとやり取りしたり、テキストベースの形式で保存したりする際の一般的な手順です。Aspose.GIS for .NET を使用すれば、この変換は非常に簡単に行え、WKT バリアント、数値形式、少数点精度を完全に制御できます。このチュートリアルでは、ジオメトリを WKT に変換する方法、適切なバリアントの選択方法、プロジェクトの正確な要件に合わせて出力を微調整する方法を学びます。

## Quick Answers
- **“ジオメトリを WKT に変換” とは何ですか？** ジオメトリオブジェクト（ポイント、ライン、ポリゴン）を Well‑Known Text 表現に変換します。  
- **サポートされている WKT バリアントはどれですか？** `Iso`、`SimpleFeatureAccessOutdated`、`ExtendedPostGis`。  
- **小数点精度はどのように制御しますか？** `General`、`RoundTrip`、`Flat` などの `NumericFormat` オプションを使用します。  
- **本番環境でライセンスは必要ですか？** はい、トライアル以外の使用には商用ライセンスが必要です。  
- **対応している .NET バージョンは何ですか？** .NET Framework 4.0 以上および .NET 5/6/7。

## What is “convert geometry to WKT”?
ジオメトリを WKT に変換すると、空間オブジェクトを記述する人間が読める文字列が生成されます。この形式は GIS ツール、データベース、Web サービスで広く受け入れられており、データ交換に最適です。

## Why use Aspose.GIS for this conversion?
- **精度制御** – 小数点以下の桁数を選択できます。  
- **バリアントの柔軟性** – 下流システムが要求する正確な WKT 方言に合わせられます。  
- **外部依存なし** – 純粋な .NET ライブラリで、ネイティブバイナリは不要です。

## Prerequisites
開始する前に、以下が揃っていることを確認してください：

1. **Aspose.GIS for .NET** – [ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロードしてインストールしてください。  
2. **開発環境** – .NET SDK がインストールされた Visual Studio または VS Code の最新バージョン。  
3. **基本的な C# の知識** – クラス、オブジェクト、.NET フレームワークに慣れていること。

## Import Namespaces
まず、必要な名前空間をスコープにインポートします：

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

## Step 1: Create a Point Object
後で **ジオメトリを WKT に変換** する `Point` を作成します。ポイントは緯度、経度、オプションの測定値 (M) を含みます：

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Step 2: Set Spatial Reference System (SRS)
空間参照系 (SRS) を設定し、WKT 出力がどの座標系を参照すべきかを指定します。ここでは一般的な WGS84 系を使用します：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Step 3: Specify WKT Variant
**ジオメトリを WKT に変換** する際に適切な WKT バリアントを選択します。各バリアントは出力を若干異なる形式でフォーマットします：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Step 4: Control Numeric Format (Set Numeric Format & Adjust Decimal Precision)
座標の数値表現を微調整します。`NumericFormat` クラスを使用して **数値形式を設定** し、**小数点精度を調整** できます：

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Common Issues & Tips
- **M 値が欠落** – 測定値が不要な場合は `M` プロパティを省略してください。ISO バリアントは自動的に除外します。  
- **予期しない精度** – 正しい `NumericFormat` を使用しているか確認してください。`General` はフルダブル精度を保持し、`Flat` は指定した小数点桁数に丸めます。  
- **SRID が表示されない** – `ExtendedPostGis` バリアントのみが出力の先頭に `SRID=` を付加します。対象システムが SRID を期待する場合はこのバリアントを選択してください。

## Conclusion
これらの手順に従うことで、**ジオメトリを WKT に変換**する方法、適切なバリアントの選択、数値出力の正確な制御ができるようになりました。これにより、Aspose.GIS を任意の GIS ワークフロー、データベース、WKT を受け取る Web サービスと柔軟に統合できます。

## FAQ's
### Is Aspose.GIS compatible with all versions of .NET?
はい、Aspose.GIS は .NET Framework 4.0 以降をサポートしています。  

### Can I use Aspose.GIS for commercial projects?
はい、Aspose.GIS は個人・商用プロジェクトの両方で使用できます。  

### Does Aspose.GIS provide support for other spatial data formats?
はい、Aspose.GIS は ESRI Shapefile、GeoJSON、KML など、幅広い空間データ形式をサポートしています。  

### Is there a free trial available for Aspose.GIS?
はい、[こちら](https://releases.aspose.com/) から Aspose.GIS の無料トライアル版をダウンロードできます。  

### Where can I get help or support for Aspose.GIS?
Aspose.GIS コミュニティの[フォーラム](https://forum.aspose.com/c/gis/33)で質問やサポートを受けることができます。

## Frequently Asked Questions
**Q: ジオメトリコレクションを単一の WKT 文字列にエクスポートするにはどうすればよいですか？**  
A: コレクション内の各ジオメトリを反復処理し、`AsText` の結果を連結します。必要に応じてカンマや改行で区切ることができます。

**Q: 座標を変更せずに SRID を変更できますか？**  
A: はい、`SpatialReferenceSystem` プロパティに目的の SRID を設定すれば、座標値はそのまま保持されます。

**Q: サポートされていない WKT バリアントを使用した場合はどうなりますか？**  
A: Aspose.GIS は `ArgumentException` をスローします。必ず `WktVariant` 列挙体の値と照合してバリアントを検証してください。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}