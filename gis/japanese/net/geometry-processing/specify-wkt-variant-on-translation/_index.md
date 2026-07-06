---
date: 2026-04-09
description: .NET アプリケーションで Aspose.GIS for .NET を使用して C# でポイントを作成する際に、空間参照を割り当て、十進精度を設定する方法を学びましょう。
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: 変換時にWKTバリアントを指定する
second_title: Aspose.GIS .NET API
title: Aspose.GIS を使用した空間参照の割り当てと WKT バリアントの設定
url: /ja/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した空間参照の割り当てと WKT バリアントの設定

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用してジオメトリに **空間参照を割り当て**、正確な WKT 出力形式を制御する方法を学びます。マッピング、分析、データ交換のために **create point C#** オブジェクトを作成する際、適切な WKT バリアントと数値精度を選択できれば、空間データの相互運用性が高まり、読みやすくなります。ステップバイステップで進めていきましょう。

## クイック回答
- **「空間参照を割り当てる」とは何ですか？** ジオメトリを WGS‑84 のような特定の座標系に結び付けます。  
- **サポートされている WKT バリアントはどれですか？** Iso、SimpleFeatureAccessOutdated、ExtendedPostGis。  
- **小数点の精度はどのように制御できますか？** `NumericFormat` の `General`、`RoundTrip`、`Flat` などのオプションを使用します。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **対応している .NET バージョンは何ですか？** .NET Framework 4.0 以降、.NET Core/5/6+。

## 「空間参照を割り当てる」とは何ですか？
空間参照（または空間参照系、SRS）を割り当てることで、GIS ソフトウェアはジオメトリの座標値をどのように解釈すべきかを認識します。SRS がなければ、ポイントの緯度・経度は実世界の意味を持ちません。

## なぜ WKT バリアントと数値フォーマットを制御する必要があるのか？
異なる GIS ツールは若干異なる WKT 構文を期待します。適切なバリアントを選択すればシームレスなデータ交換が可能になり、数値精度を設定すれば丸め誤差や過度に長い数値がログやファイルを乱雑にするのを防げます。

## 前提条件
1. Aspose.GIS for .NET – [download page](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
2. .NET 開発環境 (Visual Studio、VS Code、または Rider)。  
3. C# と .NET フレームワークの基本的な知識。

## 名前空間のインポート
Aspose.GIS のクラスを使用する前に、必要な名前空間をインポートします:

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

## ステップ 1: Point オブジェクトの作成 (create point C#)
緯度、経度、オプションの測定値 (M) を持つ `Point` を構築します:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## ステップ 2: 空間参照システム (SRS) の割り当て
ここでポイントに **空間参照** を割り当てます。広くサポートされている WGS‑84 システム (SRID 4326) を使用します:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## ステップ 3: 目的の WKT バリアントを指定
下流アプリケーションに合わせた WKT バリアントを選択します:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## ステップ 4: WKT 出力の小数点精度を設定
`NumericFormat` を使用して最終文字列に表示される桁数を制御します:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### よくある落とし穴とヒント
- **落とし穴:** `AsText` を呼び出す前に SRS を設定し忘れると、SRID 情報が欠落する可能性があります。  
- **ヒント:** 座標のロスレスな往復が必要な場合は `NumericFormat.RoundTrip` を使用してください。  
- **ヒント:** `Iso` バリアントが最も汎用性が高く、SRID を埋め込む必要がある場合のみ `ExtendedPostGis` を選択してください。

## 結論
これで **空間参照を割り当て**、適切な WKT バリアントを選択し、**create point C#** オブジェクトを作成する際に **小数点精度を設定** する方法が分かりました。これらの制御により、単純な可視化から高精度の空間分析まで、あらゆる GIS ワークフローの正確な要件に対応できる柔軟性が得られます。

## よくある質問

**Q:** Aspose.GIS はすべての .NET バージョンと互換性がありますか？  
**A:** はい、Aspose.GIS は .NET Framework 4.0 以降、および .NET Core/5/6 をサポートしています。

**Q:** 商用プロジェクトで Aspose.GIS を使用できますか？  
**A:** もちろんです。商用利用には商用ライセンスが必要ですが、評価用の無料トライアルが利用可能です。

**Q:** Aspose.GIS は他の空間データ形式もサポートしていますか？  
**A:** はい、ESRI Shapefile、GeoJSON、KML など多数の形式に対応しています。

**Q:** 無料トライアルはどこからダウンロードできますか？  
**A:** 無料トライアル版は [here](https://releases.aspose.com/) からダウンロードできます。

**Q:** 問題が発生した場合、どのようにサポートを受けられますか？  
**A:** Aspose.GIS コミュニティの [forum](https://forum.aspose.com/c/gis/33) に質問を投稿してください。Aspose のスタッフとコミュニティメンバーが支援します。

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}