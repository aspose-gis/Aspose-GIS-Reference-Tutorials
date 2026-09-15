---
date: 2026-09-15
description: Aspose.GIS for .NET を使用した C# で、ポイントジオメトリを作成する際に座標系を割り当て、WKT バリアントを設定し、小数点精度を制御する方法を学びます。
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: 変換時に WKT バリアントを指定
og_description: Aspose.GIS for .NET を使用した C# で、ポイントジオメトリを作成する際に座標系を割り当て、WKT バリアントを設定し、小数点精度を制御する方法を学びます。
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Aspose.GIS を使用して座標系を割り当て、WKT バリアントを設定する
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Aspose.GIS を使用して座標系を割り当て、WKT バリアントを設定する
url: /ja/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 座標系を割り当て、Aspose.GIS を使用して WKT バリアントを設定する

## はじめに
このチュートリアルでは、**座標系を割り当て**、適切な WKT バリアントを選択し、C# と Aspose.GIS for .NET を使用して **ポイントジオメトリを作成**する際に小数点精度を制御する方法を学びます。マッピングサービスの構築、空間分析の実行、または GIS プラットフォーム間でのデータ交換を行う場合でも、これらの設定により出力が相互運用可能で読みやすくなります。プロセスをステップバイステップで見ていきましょう。

## クイック回答
- **“assign coordinate system” とは何ですか？** ジオメトリを WGS‑84 のような特定の座標参照系に結び付けます。  
- **どの WKT バリアントがサポートされていますか？** Iso、SimpleFeatureAccessOutdated、ExtendedPostGis。  
- **小数点精度はどのように制御できますか？** `NumericFormat` 列挙体（`General`、`RoundTrip`、`Flat`）を使用します。  
- **Aspose.GIS のライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **対応している .NET バージョンは何ですか？** .NET Framework 4.0 以上および .NET Core/5/6+。

## “assign coordinate system” とは何か
空間参照（または空間参照系、SRS）を割り当てることで、GIS ソフトウェアにジオメトリの座標値の解釈方法を指示し、数値を WGS‑84 のような実世界の座標系に結び付けます。SRS がない場合、ポイントの緯度・経度の数値は実世界の意味を持ちません。

## なぜ WKT バリアントと数値フォーマットを制御するのか
30 以上の GIS ツールが特定の WKT 構文を期待しているため、適切なバリアントを選択するとインポートエラーを防げます。数値フォーマットを設定すると丸め誤差が減り、出力が簡潔になるため、ログやファイルをプログラムで解析する際に特に重要です。

## 前提条件
1. Aspose.GIS for .NET – [download page](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
2. .NET 開発環境（Visual Studio、VS Code、または Rider）。  
3. C# と .NET フレームワークの基本的な知識。

## 名前空間のインポート
任意の Aspose.GIS クラスを使用する前に、必要な名前空間をインポートしてください：

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

## ポイントに座標系を割り当てる方法は？
`Point` インスタンスをロードし、`SpatialReference` クラスを使用して空間参照系 (SRS) を付与します。この 2 段階のパターンにより、ジオメトリがエクスポート時に座標系メタデータを保持し、下流ツールが座標を正しく解釈できるようになります。`Point` クラスは X（経度）と Y（緯度）で定義された単一の位置を表します。

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## 手順 2: 空間参照系 (SRS) を割り当てる
ここでポイントに **空間参照** を割り当てます。`SpatialReference` は SRID で識別される座標参照系を表します。ここでは広くサポートされている WGS‑84 システム (SRID 4326) を使用します：

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## 手順 3: 目的の WKT バリアントを指定する
下流アプリケーションに合わせた WKT バリアントを選択します：

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## WKT 出力の小数点精度を設定する方法は？
`NumericFormat` 列挙体を使用して最終文字列に表示する桁数を制御します。この列挙体は `General`、`RoundTrip`、`Flat` などの書式規則を定義します。`RoundTrip` を選択するとラウンドトリップシナリオで座標の完全な忠実度が保たれ、`General` は多くの可視化タスクに適した簡潔な表現を提供します。`NumericFormat` 列挙体は WKT 出力で座標数値がどのようにフォーマットされるかを制御します。

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### よくある落とし穴とヒント
- **落とし穴:** `AsText` を呼び出す前に SRS を設定し忘れると、SRID 情報が欠落する可能性があります。  
- **ヒント:** 座標のロスレスなラウンドトリップが必要な場合は `NumericFormat.RoundTrip` を使用してください。  
- **ヒント:** `Iso` バリアントが最も汎用性が高く、SRID を埋め込む必要がある場合のみ `ExtendedPostGis` を選択してください。

## 結論
これで、Aspose.GIS を使用して **座標系を割り当て**、適切な WKT バリアントを選択し、**ポイントジオメトリを作成**する際に **小数点精度を設定**する方法が分かりました。これらの制御により、シンプルな可視化から高精度の空間分析まで、あらゆる GIS ワークフローの正確な要件を満たす柔軟性が得られます。

## よくある質問

**Q:** Aspose.GIS はすべての .NET バージョンと互換性がありますか？  
**A:** はい、Aspose.GIS は .NET Framework 4.0 以上、および .NET Core/5/6 をサポートしています。

**Q:** 商用プロジェクトで Aspose.GIS を使用できますか？  
**A:** もちろんです。商用利用には商用ライセンスが必要ですが、評価用に無料トライアルが利用可能です。

**Q:** Aspose.GIS は他の空間データ形式もサポートしていますか？  
**A:** はい、ESRI Shapefile、GeoJSON、KML、CSV など 30 以上の形式に対応しています。

**Q:** 無料トライアルはどこからダウンロードできますか？  
**A:** Aspose.GIS の無料トライアル版は [Aspose.GIS free trial download page](https://releases.aspose.com/) からダウンロードできます。

**Q:** 問題が発生した場合、どのようにサポートを受けられますか？  
**A:** Aspose.GIS コミュニティの [forum](https://forum.aspose.com/c/gis/33) に質問を投稿してください。Aspose のスタッフとコミュニティメンバーが支援します。

---

**最終更新日:** 2026-09-15  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose

## 関連チュートリアル

- [ベクトルレイヤーを作成し、空間参照系を設定する](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS for .NET を使用してジオメトリを WKT に変換する方法](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Aspose.GIS でジオメトリの精度を書き込む制限方法](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}