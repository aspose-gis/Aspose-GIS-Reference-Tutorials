---
date: 2026-04-03
description: .NET 用 Aspose.GIS を使用して、穴のあるポリゴンジオメトリの作成方法を学びましょう。このガイドでは、ポリゴンに穴を作成し、ジオスペーシャル
  データを扱う方法を示します。
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: 穴付きポリゴンジオメトリを作成
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
このチュートリアルでは、Aspose.GIS for .NET を使用して **穴付きポリゴンを作成** ジオメトリを作成します。マッピングアプリケーションの構築、空間分析の実施、または GIS サービス向けデータの準備を行う場合、ポリゴン内に穴を埋め込む方法を知っていることは不可欠です。環境設定から最終的なポリゴンオブジェクトの生成まで、ステップバイステップで全プロセスを解説します。

## クイック回答
- **“create polygon with hole”とは何ですか？** それは、領域から除外される1つ以上の内部リング（穴）を含むポリゴンを構築することを意味します。  
- **どのライブラリがこれを処理しますか？** Aspose.GIS for .NET は外部リングと内部リングの完全なサポートを提供します。  
- **ライセンスは必要ですか？** 開発には無料トライアルで動作しますが、製品環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **どのくらい時間がかかりますか？** 実装とテストは通常10分未満です。

## Aspose.GIS を使用してポリゴンに穴を追加する方法
穴を追加するのは、**内部リング** を定義してポリゴンに付加するだけです。ライブラリが向きと有効性を処理してくれるので、空洞を表す座標に集中できます。

## “create polygon with hole”とは何ですか？
穴付きポリゴンを作成するには、外部境界を示す **外部リング** と、空白領域を切り取る **内部リング**（複数可）を定義します。内部リングはしばしば *穴* と呼ばれ、ポリゴンの表面の一部ではない領域を表します。

## なぜ Aspose.GIS を使用してポリゴンに穴を作成するのか？
- **正確な空間モデリング:** 土地区画内の湖や建物内の中庭など、実世界の機能は穴が必要です。  
- **相互運用性:** Shapefile、GeoJSON、GML などのフォーマットは内部リングをネイティブにサポートしており、Aspose.GIS はそれらを保持します。  
- **パフォーマンス:** ライブラリがジオメトリの有効性を管理するため、カスタム検証コードを書く必要がありません。

## 穴付きポリゴンの実世界シナリオ
1. **内部に湖がある土地区画** – 湖は穴としてモデル化され、区画面積にカウントされません。  
2. **中庭付きの建物輪郭** – 中庭は建物の輪郭から除外されます。  
3. **大規模保護地域内の保護ゾーン** – 別レイヤーを作成せずに制限区域を除外できます。

## 前提条件
開始する前に、以下の前提条件を確認してください：
1. Aspose.GIS for .NET ライブラリ: [here](https://releases.aspose.com/gis/net/) からダウンロードできます。  
2. 開発環境: Visual Studio またはその他の .NET IDE がインストールされた開発環境が整っていることを確認してください。

## 名前空間のインポート
まず、Aspose.GIS の機能を使用するために必要な名前空間をインポートします。方法は以下の通りです：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、Aspose.GIS for .NET を使用して穴付きポリゴンジオメトリの作成に進みましょう。

## 手順 1: ポリゴンオブジェクトの作成
空の `Polygon` オブジェクトをインスタンス化します。後で外部リングと内部リングの両方を保持します。

```csharp
Polygon polygon = new Polygon();
```

## 手順 2: 外部リングの定義
外部リングはポリゴンの外側境界を定義します。時計回りの順序で点を追加して閉じた形状を作ります。

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 手順 3: 内部リング（穴）の定義
次に内部リングを作成します—これはポリゴンの面積から除外される **穴** です。点は通常反時計回りで追加しますが、Aspose.GIS は向きを自動で処理します。

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 手順 4: 外部リングの割り当てと内部リングのポリゴンへの追加
最後に外部リングをポリゴンに割り当て、続いて内部リング（穴）を追加します。複数の穴が必要な場合は `AddInteriorRing` メソッドを複数回呼び出すことができます。

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## ヒントとベストプラクティス
- **可読性のための向きの重要性** – Aspose.GIS は自動で向きを修正しますが、外部リングは時計回り、内部リングは反時計回りに保つことで GIS ビューアでジオメトリの検査が容易になります。  
- **各リングを閉じる** – 常に最初の座標を最後の点として繰り返すことで、有効な閉じた形状が保証されます。  
- **作成後に検証** – 保存前にジオメトリが OGC 標準に準拠しているか `polygon.IsValid` を呼び出して確認できます。  

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| GIS ビューアに穴が表示されない | 内部リングの向きが逆になっている | 外部リングと反対方向（反時計回り）に点を追加してください。 |
| ポリゴンが無効エラー | リングが閉じていない（最初 ≠ 最後の点） | 各リングで最初の点を最後の点として繰り返してください（上記参照）。 |
| 予期しない空ジオメトリ | `ExteriorRing` を内部リング追加前に割り当て忘れ | `polygon.ExteriorRing` を先に設定し、次に `AddInteriorRing` を呼び出してください。 |

## よくある質問
### 1. Aspose.GIS とは何ですか？
Aspose.GIS は .NET ライブラリで、開発者が地理空間データを操作できるようにし、さまざまな地理空間ファイル形式の作成、読み取り、操作を可能にします。

### 2. Aspose.GIS を商用プロジェクトで使用できますか？
はい、ライセンスを購入することで個人・商用プロジェクトの両方で Aspose.GIS を使用できます。詳細は [here](https://purchase.aspose.com/buy) をご覧ください。

### 3. Aspose.GIS の無料トライアルはありますか？
はい、[here](https://releases.aspose.com/) から Aspose.GIS の無料トライアルをご利用いただけます。

### 4. Aspose.GIS のサポートはどこで見つけられますか？
[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でサポートをご確認ください。

### 5. Aspose.GIS の一時ライセンスはどのように取得できますか？
[here](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

---

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}