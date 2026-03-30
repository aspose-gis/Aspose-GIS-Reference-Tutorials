---
date: 2025-12-20
description: .NET 用 Aspose.GIS を使用して、穴のあるポリゴンジオメトリの作成方法を学びましょう。このガイドでは、ポリゴンに穴を作成し、地理空間データを扱う方法を示します。
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS を使用して穴のあるポリゴンジオメトリを作成する
url: /ja/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した穴付きポリゴンジオメトリの作成

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **穴付きポリゴン** ジオメトリを **作成** します。マッピングアプリケーションの構築、空間分析の実施、または GIS サービス向けデータの準備を行う際に、ポリゴン内部に穴を埋め込む方法を知っておくことは不可欠です。環境設定から最終的なポリゴンオブジェクトの生成まで、ステップバイステップで解説します。

## クイック回答
- **「穴付きポリゴンを作成する」とは何ですか？** それは、面積から除外される 1 つ以上の内部リング（穴）を含むポリゴンを構築することを意味します。  
- **どのライブラリがこれを処理しますか？** Aspose.GIS for .NET は外部リングと内部リングの両方をフルサポートします。  
- **ライセンスは必要ですか？** 開発目的であれば無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7。  
- **どのくらい時間がかかりますか？** 実装とテストは通常 10 分未満で完了します。

## 「穴付きポリゴンを作成する」とは何ですか？
穴付きポリゴンの作成は、外部境界を示す **外部リング** と、空白領域を切り取る 1 つ以上の **内部リング** を定義することを含みます。内部リングはしばしば *穴* と呼ばれ、ポリゴンの表面の一部ではない領域を表します。

## なぜ Aspose.GIS を使用してポリゴンに穴を作成するのか？
- **正確な空間モデリング：** 土地区画内の湖や建物内の中庭など、実世界の特徴は穴が必要です。  
- **相互運用性：** Shapefile、GeoJSON、GML などのフォーマットは内部リングをネイティブにサポートしており、Aspose.GIS はそれらを保持します。  
- **パフォーマンス：** ライブラリがジオメトリの有効性を管理するため、独自の検証コードを書く必要がありません。

## 前提条件
開始する前に、以下の前提条件を確認してください：
1. Aspose.GIS for .NET ライブラリ：ダウンロードは [here](https://releases.aspose.com/gis/net/) から。  
2. 開発環境：Visual Studio もしくはその他の .NET IDE がインストールされた開発環境を用意してください。

## 名前空間のインポート
まず、Aspose.GIS の機能を使用するために必要な名前空間をインポートします。手順は以下の通りです：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、Aspose.GIS for .NET を使用して穴付きポリゴンジオメトリを作成していきましょう。

## ステップ 1: ポリゴンオブジェクトの作成
外部リングと内部リングの両方を保持できる空の `Polygon` オブジェクトをインスタンス化します。

```csharp
Polygon polygon = new Polygon();
```

## ステップ 2: 外部リングの定義
外部リングはポリゴンの外側境界を定義します。時計回りの順序でポイントを追加し、閉じた形状を作ります。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## ステップ 3: 内部リング（穴）の定義
次に内部リングを作成します—これはポリゴンの面積から除外される **穴** です。ポイントは通常反時計回りで追加しますが、Aspose.GIS は向きを自動的に処理します。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## ステップ 4: 外部リングを割り当て、内部リングをポリゴンに追加
最後に外部リングをポリゴンに設定し、続いて内部リング（穴）を追加します。複数の穴が必要な場合は `AddInteriorRing` メソッドを複数回呼び出すことができます。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| GIS ビューアで穴が表示されない | 内部リングの向きが逆になっている | 外部リングとは逆方向（反時計回り）でポイントを追加してください。 |
| ポリゴンが無効なエラー | リングが閉じていない（最初の点 ≠ 最後の点） | 各リングの最初の点を最後の点として繰り返してください（上記参照）。 |
| 予期しない空ジオメトリ | `ExteriorRing` を内部リング追加前に設定し忘れた | まず `polygon.ExteriorRing` を設定し、その後 `AddInteriorRing` を呼び出してください。 |

## 結論
おめでとうございます！Aspose.GIS for .NET を使用して **穴付きポリゴン** ジオメトリの **作成** 方法を習得できました。このテクニックは、内部に空洞を持つ複雑な形状を表現する必要がある多くの地理空間シナリオで基本となります。

## よくある質問
### 1. Aspose.GIS とは？
Aspose.GIS は .NET ライブラリで、開発者が地理空間データを操作できるようにし、さまざまな地理空間ファイル形式の作成、読み取り、操作を可能にします。

### 2. 商用プロジェクトで Aspose.GIS を使用できますか？
はい、ライセンスを購入すれば個人・商用プロジェクトのどちらでも Aspose.GIS を使用できます。詳細は [here](https://purchase.aspose.com/buy) をご覧ください。

### 3. Aspose.GIS の無料トライアルはありますか？
はい、[here](https://releases.aspose.com/) から Aspose.GIS の無料トライアルをご利用いただけます。

### 4. Aspose.GIS のサポートはどこで得られますか？
[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でサポートをご確認いただけます。

### 5. Aspose.GIS の一時ライセンスはどのように取得できますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}