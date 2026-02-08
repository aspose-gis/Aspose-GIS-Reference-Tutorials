---
date: 2026-02-08
description: Aspose.GIS for .NET を使用して接触ジオメトリを検出し、ネットワークルーティングチェックを実行する方法を学びましょう。このライブラリは空間データの処理と空間分析を可能にする強力なツールです。
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: ネットワークルーティングチェック：Aspose.GISでの接触ジオメトリ
url: /ja/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ネットワークルーティングチェック: Aspose.GIS for .NET でタッチジオメトリを使用する方法

## Introduction
2 つの空間オブジェクト間で **ネットワークルーティングチェックを実行** する必要があるとき、Aspose.GIS for .NET はクリーンで型安全な API を提供し、作業を簡単にします。このチュートリアルでは、ラインストリングやポイントを作成し、`Touches` メソッドを使用してジオメトリが境界だけを共有しているかどうかを判定する方法を紹介します。この操作は、ルート検証、マップオーバーレイの検証、近接クエリなど、多くの **spatial analysis .NET** シナリオの基礎となります。

## Quick Answers
- **「タッチ (touching)」とは何ですか？** 2 つのジオメトリが少なくとも 1 つの境界点を共有しますが、内部は交差しません。  
- **どのメソッドでチェックしますか？** `Geometry.Touches(otherGeometry)`。  
- **この機能にライセンスは必要ですか？** 開発用にはトライアルで動作しますが、本番環境では永続ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework、.NET Core、.NET 5/6/7 すべてが Aspose.GIS によってカバーされています。  
- **実装にかかる時間は？** 基本的な例で約 5〜10 分です。  

## How to Perform a Network Routing Check Using Touching Geometries
以下では、**タッチしているジオメトリをチェックする方法** と、その結果をルーティング検証ワークフローに組み込む手順を詳しく説明します。

### What is “Touching” in Spatial Analysis?
GIS 用語で *touching* は、2 つのジオメトリがエッジで接触しているが、内部は重なっていない空間関係を指します。*intersects*（内部の重なりを含む）とは異なり、境界だけで接続していることを検証したい場合に使用されます。たとえば、道路セグメントが交差せずに交差点で接続しているかどうかを確認する際に利用されます。

## Why Use Aspose.GIS for Spatial Analysis .NET?
Aspose.GIS は、ネイティブ GIS のインストールが不要な完全マネージド .NET ライブラリで、**空間データの取り扱い** を容易にします。Shapefile、GeoJSON、KML など多数のフォーマットに対応し、`Touches`、`Intersects`、`Contains` などの高性能ジオメトリ演算を提供します。純粋な .NET 実装なので、Web サービス、デスクトップアプリ、クラウドファンクションに直接組み込むことができます。

## Prerequisites
開始する前に以下を用意してください。

1. **Visual Studio**（最新バージョンのいずれか）をマシンにインストール。  
2. **Aspose.GIS for .NET** – 最新パッケージを [official download page](https://releases.aspose.com/gis/net/) からダウンロード。  
3. **有効なライセンス**（または無料トライアル） – [here](https://releases.aspose.com/) から取得。  

### Setting Up Your Environment
1. まだインストールしていない場合は Visual Studio をインストールします。  
2. 上記リンクから Aspose.GIS for .NET をダウンロードし、NuGet パッケージをプロジェクトに追加します。  
3. コード内でライセンスファイルを適用する（テスト用に一時ライセンスを使用しても可）。

## Import Namespaces
API を使用するために必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create Line Strings (and a Point)
以下で **ラインストリング** オブジェクトと、タッチ関係をテストするポイントを作成します。

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Explanation*:  
- `geometry1` と `geometry2` は端点 `(2, 2)` を共有しています。  
- `geometry3` はその共有端点に正確に位置するポイントです。  
- `geometry4` は同じ領域を横切りますが、`geometry1` とは境界を共有してい **ません**。

## Step 2: Check Touching Relationships
`Touches` メソッドを呼び出して、どのペアがタッチしているかを確認します。

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Result*:  
- 最初の 3 つのチェックは **True** を返します。ジオメトリは内部の重なりなしに単一の点で接触しているためです。  
- 最後のチェックは **False** を返します。2 本のラインストリングが線分上で交差しており、単なる境界点での接触ではないためです。

## Common Issues & Tips
- **Precision problems** – GIS 計算は浮動小数点ベースです。予期しない `False` が出た場合は、座標を正規化するか、`Geometry.EqualsExact(other, tolerance)` で許容誤差を指定してください。  
- **Mixed geometry types** – `Touches` はポイント、ライン、ポリゴン間でも機能しますが、意味合いが異なるため、データモデルで期待する関係を必ず確認してください。  
- **Performance** – 大規模データセットの場合はバッチ処理や Aspose.GIS が提供する空間インデックス（例: R‑tree）を利用し、O(N²) の比較を回避しましょう。

## Frequently Asked Questions

**Q: Aspose.GIS はすべての .NET フレームワークに対応していますか？**  
A: はい。.NET Framework、.NET Core、.NET 5+、.NET 6+ をサポートしており、デスクトップ、Web、クラウドプロジェクトで柔軟に利用できます。

**Q: ライセンスを購入する前に Aspose.GIS を試すことはできますか？**  
A: もちろんです。Aspose のウェブサイトから無料トライアルを取得できます。詳細は [here](https://purchase.aspose.com/temporary-license/) をご覧ください。`Touches` 操作を含むすべての機能を試すことができます。

**Q: Aspose.GIS 関連の質問はどこでサポートを受けられますか？**  
A: 公式 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) で質問を投稿できます。コミュニティや Aspose エンジニアからの支援が受けられます。

**Q: Aspose.GIS のアップデートはどのくらいの頻度で行われますか？**  
A: 定期的に新しいフォーマットサポート、パフォーマンス改善、バグ修正を含むアップデートがリリースされ、最新の .NET リリースとの互換性が保たれます。

**Q: Aspose.GIS の一時ライセンスは取得できますか？**  
A: はい、評価目的で使用できる一時ライセンスが [here](https://purchase.aspose.com/temporary-license/) から入手可能です。

**Q: `Touches` メソッドはネットワークルーティングチェックにどのように役立ちますか？**  
A: 道路セグメントが共有エンドポイント（タッチ）でのみ接続していることを確認することで、ルーティングネットワークが意図しない重なりなしに正しく接続されているかを検証できます。

---

**最終更新日:** 2026-02-08  
**テスト環境:** Aspose.GIS for .NET 24.11（執筆時点での最新）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}