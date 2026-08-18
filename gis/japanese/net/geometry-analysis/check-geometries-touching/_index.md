---
date: 2026-06-05
description: ASP.NETで line string を作成し、Aspose.GIS for .NET を使用して Touching Geometries
  を検出することでネットワークルーティングチェックを実行する方法を学びます。このライブラリは空間データの処理と分析に強力です。
keywords:
- create line string asp.net
- touching geometries
- Aspose.GIS spatial analysis
linktitle: Touching Geometries のチェック方法
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  headline: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  type: TechArticle
- description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  name: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  steps:
  - name: '**Visual Studio** (any recent version).'
    text: '**Visual Studio** (any recent version).'
  - name: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
  - name: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
    text: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
  - name: Install Visual Studio if you haven’t already.
    text: Install Visual Studio if you haven’t already.
  - name: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
    text: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
  - name: Apply your license file in code (or use a temporary license for testing).
    text: Apply your license file in code (or use a temporary license for testing).
  type: HowTo
- questions:
  - answer: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving
      you flexibility across desktop, web, and cloud projects.
    question: Is Aspose.GIS compatible with all .NET frameworks?
  - answer: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/)
      to explore all features, including the `Touches` operation.
    question: Can I try Aspose.GIS before purchasing a license?
  - answer: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to ask questions, share examples, and get help from both the community and Aspose
      engineers.
    question: Where can I find support for Aspose.GIS‑related queries?
  - answer: Aspose releases regular updates that add new format support, performance
      improvements, and bug fixes, ensuring compatibility with the latest .NET releases.
    question: How often are updates released for Aspose.GIS?
  - answer: By confirming that road segments only meet at shared endpoints (touch),
      you can validate that a routing network is correctly connected without unintended
      overlaps.
    question: How does the `Touches` method help with a network routing check?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: ASP.NETで line string を作成 – Aspose.GISによる Touching Geometries のチェック
url: /ja/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ASP.NETでラインストリングを作成 – Aspose.GISによるタッチジオメトリチェック

## はじめに
2つの空間オブジェクト間で **ネットワークルーティングチェック** を実行する必要がある場合、最初のステップは道路セグメントをモデル化する **line string ASP.NET** オブジェクトを作成することです。Aspose.GIS for .NET は、クリーンで型安全な API を提供し、この操作を簡単に行えるようにし、低レベルのジオメトリ計算ではなくビジネスロジックに集中できます。このチュートリアルでは、ラインストリングの作成、ポイントの追加、そして `Touches` メソッドを使用してジオメトリが境界上でのみ接触することを確認する手順を説明します – ルート検証、マップオーバーレイ検証、近接クエリにおける重要な要件です。

## クイック回答
- **“touching” とは何ですか？** 2つのジオメトリは少なくとも1つの境界点を共有しますが、内部は交差しません。  
- **どのメソッドがチェックしますか？** `Geometry.Touches(otherGeometry)`。  
- **この機能にライセンスは必要ですか？** 開発にはトライアルで動作しますが、本番環境では永続ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework、.NET Core、.NET 5/6/7 – すべて Aspose.GIS がカバーしています。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約5〜10分です。  

## 空間分析における “Touching” とは何ですか？
**Touching** は、2つのジオメトリが内部を重ねずにエッジで接触する空間関係を表します。これは、内部の重なりも含む *intersects* とは異なり、道路セグメントが交差点でのみ接続されていることを確認する際に不可欠です。  
`Touches` メソッドは、ジオメトリが境界点を共有し内部点を持たない場合に **true** を返し、意図しない交差がないネットワーク接続性の検証に最適です。

## .NET の空間分析で Aspose.GIS を使用する理由
Aspose.GIS は **30 以上の入力および出力フォーマット**（Shapefile、GeoJSON、KML、GML など）をサポートし、ストリーミングアーキテクチャによりドキュメント全体をメモリに読み込まずに **2 GB** までのファイルを処理できます。このライブラリは、`Touches`、`Intersects`、`Contains`、`Distance` といった高性能ジオメトリ操作を提供し、すべて .NET で完全に管理されているため、外部 GIS のインストールなしでウェブサービス、デスクトップアプリ、Azure Functions に空間分析を直接組み込むことができます。

## 前提条件
1. **Visual Studio**（任意の最新バージョン）。  
2. **Aspose.GIS for .NET** – 最新パッケージは[公式ダウンロードページ](https://releases.aspose.com/gis/net/)から取得してください。  
3. **有効なライセンス**（または無料トライアル） – [こちら](https://purchase.aspose.com/temporary-license/)から取得するか、すべてのリリースは[こちら](https://releases.aspose.com/)で確認できます。  

### 環境設定
1. まだインストールしていない場合は Visual Studio をインストールしてください。  
2. プロジェクトに Aspose.GIS NuGet パッケージを追加します（例: `Install-Package Aspose.GIS`）。  
3. コード内でライセンスファイルを適用します（テスト用に一時ライセンスを使用することも可能です）。  

## 名前空間のインポート
API を使用開始するには、必要な名前空間をインポートします:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Aspose.GIS でタッチジオメトリをチェックする方法
`Touches` は、2つのジオメトリが境界点のみを共有し内部点を持たない場合に true を返すメソッドです。  
ジオメトリをロードまたは作成し、`Touches` を呼び出して関係を評価します。このメソッドは、2つの形状が境界点のみを共有しているかどうかを示す Boolean を返します。このワンラインチェックは、ほとんどのルーティング検証シナリオに十分で、大規模ネットワークでも高速にループ実行できます。

## 手順 1: ラインストリングの作成（およびポイント）
`LineString` は、順序付けられたポイントで定義された連続した線分の系列を表すジオメトリタイプです。  

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

*説明*:
- `geometry1` と `geometry2` はエンドポイント `(2, 2)` を共有しています。  
- `geometry3` はその共有エンドポイントに正確に位置するポイントです。  
- `geometry4` は同じ領域を横切りますが、`geometry1` と境界を **共有しません**。  

## 手順 2: タッチ関係のチェック
ここで `Touches` メソッドを呼び出し、どのペアがタッチと見なされるかを確認します。

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*結果*:
- 最初の3つのチェックは、ジオメトリが内部の重なりなしに単一のポイントで接触するため **True** を返します。  
- 最後のチェックは、2つのラインストリングが境界点だけでなく線分上で交差するため **False** を返します。  

## よくある問題とヒント
- **精度の問題** – GIS 計算は浮動小数点ベースです。予期しない `False` 結果が出た場合は、座標を正規化するか、`Geometry.EqualsExact(other, tolerance)` で許容誤差を使用することを検討してください。  
- **混合ジオメトリタイプ** – `Touches` はポイント、ライン、ポリゴン間で機能しますが、意味は異なります。データモデルで期待される関係を常に確認してください。  
- **パフォーマンス** – 大規模データセットでは、チェックをバッチ処理するか、Aspose.GIS が提供する空間インデックス（例: R‑tree）を使用して O(N²) の比較を回避してください。  

## よくある質問

**Q: Aspose.GIS はすべての .NET フレームワークと互換性がありますか？**  
A: はい。.NET Framework、.NET Core、.NET 5+、.NET 6+ をサポートしており、デスクトップ、ウェブ、クラウドプロジェクトで柔軟に使用できます。

**Q: ライセンスを購入する前に Aspose.GIS を試すことはできますか？**  
A: もちろんです。Aspose のウェブサイトから無料トライアルを取得でき（[こちら](https://purchase.aspose.com/temporary-license/)）、`Touches` 操作を含むすべての機能を試すことができます。

**Q: Aspose.GIS に関する質問のサポートはどこで受けられますか？**  
A: 公式の [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) にアクセスして質問したり、例を共有したり、コミュニティや Aspose エンジニアから支援を受けたりできます。

**Q: Aspose.GIS のアップデートはどのくらいの頻度で行われますか？**  
A: Aspose は定期的にアップデートをリリースし、新しいフォーマットのサポート、パフォーマンス向上、バグ修正を追加して、最新の .NET リリースとの互換性を確保しています。

**Q: `Touches` メソッドはネットワークルーティングチェックにどのように役立ちますか？**  
A: 道路セグメントが共有エンドポイント（タッチ）でのみ接続されていることを確認することで、意図しない重なりがない正しいルーティングネットワークであることを検証できます。

---

**最終更新日:** 2026-06-05  
**テスト環境:** Aspose.GIS for .NET 24.11（執筆時点の最新）  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したジオスペーシャルデータ処理](/gis/net/geometry-creation/create-linestring-geometry/)
- [C# でポリゴンジオメトリを作成し、Aspose.GIS for .NET で交差をチェック](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Aspose.GIS を使用して .NET でジオメトリの長さを計算する方法](/gis/net/geometry-analysis/get-geometry-length/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}