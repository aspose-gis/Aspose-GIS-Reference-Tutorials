---
date: 2025-12-04
description: Aspose.GIS for .NET を使用して、接触しているジオメトリのチェック方法を学びましょう。これは、空間データを扱い、空間分析を実行するための強力なライブラリです。.NET
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NETで接触ジオメトリをチェックする方法
url: /ja/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 接触ジオメトリの確認方法

## はじめに
2つの空間オブジェクト間の**接触の確認方法**が必要な場合、Aspose.GIS for .NET はクリーンで型安全な API を提供し、作業を簡単にします。このチュートリアルでは、ラインストリングやポイントを作成し、`Touches` メソッドを使用してジオメトリが境界のみを共有しているかどうかを判定する方法を示します。これは、ネットワークルーティング、マップオーバーレイの検証、近接チェックなど、多くの空間分析 .NET シナリオでのコア操作です。

## クイック回答
- **“touching” は何を意味しますか？** 2つのジオメトリは少なくとも1つの境界点を共有しますが、内部は交差しません。  
- **どのメソッドでチェックしますか？** `Geometry.Touches(otherGeometry)`。  
- **この機能にライセンスは必要ですか？** 開発にはトライアルで動作しますが、本番環境では永続ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework、.NET Core、.NET 5/6/7 – すべて Aspose.GIS がカバーしています。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約5〜10分です。

## 空間分析における “Touching” とは何ですか？
GIS 用語で、*touching* は2つのジオメトリがエッジで接触し、重なり合わない空間関係を指します。*intersects*（内部の重なりを含む）とは異なり、特徴が境界でのみ接触していることを検証する必要がある場合に使用されます。例えば、交差せずにジャンクションで接続する道路セグメントなどです。

## なぜ Aspose.GIS for Spatial Analysis .NET を使用するのか？
Aspose.GIS は、ネイティブ GIS のインストールなしで **空間データを扱える** 完全に管理された .NET ライブラリを提供します。Shapefile、GeoJSON、KML など幅広いフォーマットをサポートし、`Touches`、`Intersects`、`Contains` などの高性能ジオメトリ操作を提供します。純粋な .NET であるため、Web サービス、デスクトップアプリ、クラウド関数に直接組み込むことができます。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **Visual Studio**（任意の最新バージョン）をマシンにインストールしてください。  
2. **Aspose.GIS for .NET** – 最新パッケージを [公式ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
3. **有効なライセンス**（または無料トライアル） – [こちら](https://releases.aspose.com/) から取得してください。  

### 環境の設定
1. まだインストールしていない場合は Visual Studio をインストールします。  
2. 上記リンクから Aspose.GIS for .NET をダウンロードし、NuGet パッケージをプロジェクトに追加します。  
3. コード内でライセンスファイルを適用します（テスト用に一時ライセンスを使用することも可能です）。

## 名前空間のインポート
API を使用開始するには、必要な名前空間をインポートします：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ラインストリング（およびポイント）の作成
以下では、**ラインストリング** オブジェクトと、タッチ関係のテストに使用するポイントを作成します。

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

*説明*：  
- `geometry1` と `geometry2` はエンドポイント `(2, 2)` を共有しています。  
- `geometry3` はその共有エンドポイントに正確に位置するポイントです。  
- `geometry4` は同じ領域を横切りますが、`geometry1` とは境界を共有 **していません**。

## ステップ 2: タッチ関係の確認
ここで `Touches` メソッドを呼び出し、どのペアがタッチと見なされるかを確認します。

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*結果*：  
- 最初の3つのチェックは、ジオメトリが内部の重なりなしに単一のポイントで接触しているため **True** を返します。  
- 最後のチェックは、2つのラインストリングが境界ポイントだけでなく線分上で交差しているため **False** を返します。

## 一般的な問題とヒント
- **精度の問題** – GIS 計算は浮動小数点ベースです。予期しない `False` 結果が出た場合は、座標を正規化するか、`Geometry.EqualsExact(other, tolerance)` を使用して許容誤差を設定してください。  
- **混合ジオメトリタイプ** – `Touches` はポイント、ライン、ポリゴン間で機能しますが、意味合いは異なります。データモデルで期待される関係を常に確認してください。  
- **パフォーマンス** – 大規模データセットの場合、チェックをバッチ処理するか、Aspose.GIS が提供する空間インデックス（例: R‑tree）を使用して O(N²) の比較を回避してください。

## よくある質問

**Q: Aspose.GIS はすべての .NET フレームワークと互換性がありますか？**  
A: はい。.NET Framework、.NET Core、.NET 5+、.NET 6+ をサポートしており、デスクトップ、Web、クラウドプロジェクトで柔軟に使用できます。

**Q: ライセンスを購入する前に Aspose.GIS を試すことはできますか？**  
A: もちろんです。Aspose のウェブサイト [こちら](https://purchase.aspose.com/temporary-license/) から無料トライアルを取得し、`Touches` 操作を含むすべての機能を体験できます。

**Q: Aspose.GIS に関する質問のサポートはどこで受けられますか？**  
A: 公式 [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) にアクセスして質問したり、例を共有したり、コミュニティや Aspose エンジニアから支援を受けたりできます。

**Q: Aspose.GIS のアップデートはどのくらいの頻度でリリースされますか？**  
A: Aspose は定期的にアップデートをリリースし、新しいフォーマットサポート、パフォーマンス向上、バグ修正を追加して、最新の .NET リリースとの互換性を保ちます。

**Q: Aspose.GIS の一時ライセンスを取得できますか？**  
A: はい、評価目的で使用できる一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から入手可能です。

---

**最終更新日:** 2025-12-04  
**テスト環境:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}