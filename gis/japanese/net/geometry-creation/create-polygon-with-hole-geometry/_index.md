---
date: 2026-09-05
description: Aspose.GIS for .NET を使用して、穴のあるポリゴン内部リングの作成方法を学びます。このガイドでは、ポリゴンに穴を追加し、データを操作する方法を示します。
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: 穴付きジオメトリでポリゴンを作成
og_description: Aspose.GIS for .NET を使用して、穴のあるポリゴン内部リングの作成方法を学びます。このガイドでは、ポリゴンに穴を追加し、データを操作する方法を示します。
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Aspose.GIS を使用して、穴のあるポリゴン内部リングを作成する
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Aspose.GIS を使用して、穴のあるポリゴン内部リングを作成する
url: /ja/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用して、穴のあるポリゴン内部リングを作成する

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して、穴を含む **ポリゴン内部リング** の作成方法を学びます。マッピングアプリケーションの構築、空間分析の実施、または GIS サービス向けのデータ準備を行う場合でも、ポリゴン内に穴を埋め込むことは基本的なスキルです。開発環境の設定から、サポートされている任意の地理空間フォーマットに保存できる有効なポリゴンオブジェクトの生成まで、全体のワークフローを順に説明します。

## クイック回答
- **「穴のあるポリゴンを作成する」とは何ですか？** それは、領域から除外される1つ以上の内部リング（穴）を含むポリゴンを構築することを意味します。  
- **どのライブラリがこれを扱いますか？** Aspose.GIS for .NET は外部リングと内部リングの完全なサポートを提供します。  
- **ライセンスは必要ですか？** 開発には無料トライアルが利用可能です。製品環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **どのくらい時間がかかりますか？** 実装とテストは通常 10 分未満です。

## Aspose.GIS を使用してポリゴンに穴を追加する方法
GIS 環境をロードし、外部リングを定義した後、1 つまたは複数の内部リングを付加します。Aspose.GIS はリングの向きを自動的に調整しジオメトリを検証するため、必要な空洞を表す座標に集中できます。

## ポリゴン内部リングとは何ですか？
**ポリゴン内部リング** は、ポリゴンの外形から面積を差し引く内部境界です。  
Aspose.GIS が穴として扱う閉じた点のシーケンスを定義することで作成され、面積計算や形状の描画時に除外されます。

## なぜ Aspose.GIS を使用してポリゴン内部リングを作成するのか？
Aspose.GIS は、典型的な 200 点ポリゴンに対して 5 ms 未満でリングの向きを検証・修正し、カスタム検証コードの必要性を排除します。また、**30 以上の地理空間ファイル形式**（Shapefile、GeoJSON、GML、KML など）をサポートし、ファイル全体をメモリに読み込まずに最大 10,000 点のポリゴンを処理できるため、速度とスケーラビリティの両方を提供します。

## 穴のあるポリゴンの実世界シナリオ
1. **内部に湖がある土地区画** – 湖は穴としてモデル化され、区画の面積にカウントされません。  
2. **中庭を持つ建物のフットプリント** – 中庭は建物のフットプリントから除外されます。  
3. **大規模保護地域内の保護ゾーン** – 別個のレイヤーを作成せずに制限区域を除外できます。

## 前提条件
開始する前に、以下の前提条件が揃っていることを確認してください:
1. Aspose.GIS for .NET ライブラリ: **Aspose.GIS for .NET ダウンロードページ**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) からダウンロードできます。  
2. 開発環境: Visual Studio またはその他の .NET IDE がインストールされた開発環境が整っていることを確認してください。

## 名前空間のインポート
`Aspose.Gis` 名前空間には、`Polygon`、`LinearRing`、検証用ヘルパーメソッドなど、必要なすべてのジオメトリ型が含まれています。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、Aspose.GIS for .NET を使用して、穴のあるポリゴンジオメトリの作成に進みましょう。

## ステップ 1: ポリゴンオブジェクトの作成
`Polygon` は、オプションの内部リングを持つ平面ポリゴンを表す Aspose.GIS のジオメトリ型です。まず、外部リングと内部リングの両方を保持できる空の `Polygon` オブジェクトをインスタンス化します。

```csharp
Polygon polygon = new Polygon();
```

## ステップ 2: 外部リングの定義
`LinearRing` は外部境界と内部境界の両方に使用されるクラスです。外部リングはポリゴンの外側境界を定義します。時計回りの順序でポイントを追加して閉じた形状を作ります。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## ステップ 3: 内部リング（穴）の定義
`LinearRing` は内部リングも表します。内部リングはポリゴンの面積から除外される **穴** です。ポイントは通常、反時計回りの順序で追加しますが、Aspose.GIS が自動的に向きを処理します。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## ステップ 4: 外部リングを割り当て、内部リングをポリゴンに追加する
`AddInteriorRing` メソッドは、1 つまたは複数の内部リングを `Polygon` に付加します。`ExteriorRing` プロパティを設定した後に呼び出します。複数の穴を追加したい場合は、この呼び出しを繰り返すことができます。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## ヒントとベストプラクティス
- **可読性のために向きは重要です** – Aspose.GIS が自動で向きを修正しますが、外部リングは時計回り、内部リングは反時計回りに保つことで、GIS ビューアでジオメトリの検査が容易になります。  
- **各リングを閉じる** – 常に最初の座標を最後のポイントとして繰り返してください。これにより有効な閉じた形状が保証されます。  
- **作成後に検証** – 保存前にジオメトリが OGC 標準に準拠しているか `polygon.IsValid` を呼び出して確認できます。

## 一般的な問題と解決策
| Issue | Reason | Fix |
|-------|--------|-----|
| GIS ビューアに穴が表示されない | 内部リングの向きが逆 | 外部リングと反対方向（反時計回り）でポイントを追加してください。 |
| ポリゴンが無効エラーになる | リングが閉じていない（最初 ≠ 最後のポイント） | 各リングで最初のポイントを最後に繰り返してください（上記参照）。 |
| 予期しない空ジオメトリ | `ExteriorRing` を設定せずに内部リングを追加した | まず `polygon.ExteriorRing` を設定し、次に `AddInteriorRing` を呼び出してください。 |

## よくある質問
### 1. Aspose.GIS とは何ですか？
Aspose.GIS は、開発者が地理空間データを扱えるようにする .NET ライブラリで、さまざまな地理空間ファイル形式の作成、読み取り、操作が可能です。

### 2. 商用プロジェクトで Aspose.GIS を使用できますか？
はい、ライセンスを購入すれば、個人・商用プロジェクトの両方で Aspose.GIS を使用できます。詳細は **Aspose.GIS 購入ページ**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) をご覧ください。

### 3. Aspose.GIS の無料トライアルは利用可能ですか？
はい、**Aspose.GIS 無料トライアルダウンロードページ**([https://releases.aspose.com/](https://releases.aspose.com/)) から無料トライアルをご利用いただけます。

### 4. Aspose.GIS のサポートはどこで見つけられますか？
Aspose.GIS のサポートは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) で見つけられます。

### 5. Aspose.GIS の一時ライセンスはどのように取得できますか？
**Aspose.GIS 一時ライセンスページ**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)) から一時ライセンスを取得できます。

**最終更新日:** 2026-09-05  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したポリゴンジオメトリの作成方法](/gis/net/geometry-creation/create-polygon-geometry/)
- [Aspose.GIS を使用したマルチポリゴンジオメトリの作成方法](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Aspose.GIS for .NET でポリゴンをラインに変換する](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}