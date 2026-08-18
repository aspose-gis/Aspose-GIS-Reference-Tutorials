---
date: 2026-06-05
description: Aspose.GIS を使用して .NET で geometries を比較する方法、duplicate geometries を検出する方法、アプリケーションで
  geometry の等価性をチェックする方法を学びます。
keywords:
- how to compare geometries
- detect duplicate geometries
- Aspose.GIS geometry equality
linktitle: geometries の等価性を比較する方法
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to compare geometries in .NET using Aspose.GIS, detect duplicate
    geometries, and check geometry equality in your applications.
  headline: How to Compare Geometries for Equality using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.GIS works with .NET Framework, .NET Core, and .NET Standard
      projects.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. Download a trial from the [Aspose.GIS releases page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Detailed docs are on the [Aspose.GIS documentation page](https://reference.aspose.com/gis/net/).
    question: Where can I find the full API documentation?
  - answer: Post your question on the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How do I get help if I run into an issue?
  - answer: Yes, temporary licenses are available on the [purchase page](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して geometries の等価性を比較する方法
url: /ja/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリの等価性比較方法

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **ジオメトリの比較方法** を学びます。これは、重複ジオメトリの検出、空間データの検証、トポロジールールの適用が必要な場合に重要な作業です。マッピングサービスの構築、バッチでの空間解析の実行、または単に2つの形状が同じ位置にあるかを確認する場合でも、本ガイドではジオメトリ等価性の作成、変更、テストをクリーンで本番対応の C# コードで解説します。

## クイック回答
- **「ジオメトリを比較する」とは何ですか？** 2つのジオメトリオブジェクトが構築方法に関係なく同じ空間を占めているかどうかを確認します。  
- **どのメソッドを使用しますか？** Aspose.GIS API の `SpatiallyEquals`。  
- **開発にライセンスは必要ですか？** テストには無料トライアルが使用でき、商用利用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にかかる典型的な時間は？** 基本的な等価性チェックで約 5〜10 分です。

## ジオメトリ等価性とは？
ジオメトリ等価性（空間等価性とも呼ばれる）とは、2つのジオメトリが地表上の全く同じ点集合を表すことを意味します。たとえ一方が `MultiLineString`、もう一方が単一の `LineString` で構築されていても、すべての座標が定義された許容誤差内で一致すれば等価とみなされます。この定義により、開発者は異種データソース間で重複ジオメトリを確実に検出できます。

## なぜ Aspose.GIS を使ってジオメトリを比較するのか？
Aspose.GIS は高性能なオフラインジオメトリエンジンを提供し、外部サービスへの依存を排除します。**30 以上のベクタおよびラスタ形式**（WKT、GeoJSON、Shapefile、KML、GML など）をサポートし、**数十万点の頂点**を持つファイルでもメモリ使用量を 50 MB 未満に抑えて処理できます。ライブラリの `SpatiallyEquals` メソッドは精度に配慮しており、浮動小数点座標でも決定的な結果を提供します。

### 開発者にとっての重要性
バッチ処理、リアルタイム検証パイプライン、または GIS データの移行で **重複ジオメトリを検出** する必要がある場合、実績のあるライブラリを使用することで推測を排除し、異なるデータプロバイダー間で一貫した結果を保証できます。

## 前提条件
- **.NET Framework または .NET Core がインストールされていること** – Aspose.GIS がサポートする任意のバージョン。  
- **Aspose.GIS for .NET ライブラリ** – [Aspose.GIS ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロード。  
- **開発用 IDE** – Visual Studio、Rider、または C# 拡張機能がインストールされた VS Code。

## 名前空間のインポート
.NET プロジェクトに必要な `using` 文を追加し、コンパイラが GIS クラスの場所を認識できるようにします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順 1: ジオメトリの定義
`MultiLineString` は複数の線分のコレクションを表し、`LineString` は単一の連続した線を定義します。両クラスは基底クラス `Geometry` を継承しています。

まず、比較対象となる 2 つのジオメトリを作成します。この例では `geometry1` は 2 本の線分からなる `MultiLineString`、`geometry2` は同じ開始点と終了点を持つ単一の `LineString` です。

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## 手順 2: ジオメトリの等価性をチェック
`SpatiallyEquals` は、2 つのジオメトリが同じ点集合を占めているかを評価し、必要に応じて浮動小数点の誤差に対する許容値を受け取ります。

ここでは `SpatiallyEquals` メソッドを使用して、GIS エンジンが 2 つの形状を等価とみなすか確認します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

コンソールは `True` を出力します。構造は異なりますが、両ジオメトリは (0,0) から (2,2) までの同じ線をカバーしているためです。

## 手順 3: 1つのジオメトリを変更
変更が等価性に与える影響を示すため、`geometry2` に余分な点を追加します。

```csharp
geometry2.AddPoint(3, 3);
```

## 手順 4: 変更後に等価性を再チェック
変更後、ジオメトリは同一ではなくなるため、`SpatiallyEquals` は `False` を返します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

出力された `False` は、追加された点により空間等価性が失われたことを示しています。

## 重複ジオメトリの検出方法
各ジオメトリを読み込み、適切な許容値で `SpatiallyEquals` を呼び出し、`True` を返すものを除外します。このパターンは LINQ と相性が良く、数行のコードで大規模コレクション内の重複形状を特定できます。また、`GroupBy` と組み合わせて同一ジオメトリを集約し、ストレージコストを削減することも可能です。

## よくある問題とヒント
- **精度の問題** – 非常に高精度な座標を扱う場合は、丸め処理を行うか `SpatiallyEquals` の許容値オーバーロードを使用してください。  
- **異なる SRID** – 比較前に両ジオメトリが同じ空間参照系識別子（SRID）を持つことを確認してください。  
- **パフォーマンス** – 大規模コレクションでは、LINQ や並列ループを用いたバッチ比較によりオーバーヘッドを大幅に削減できます。

## よくある質問
**Q: Aspose.GIS for .NET を他の .NET フレームワークと併用できますか？**  
A: はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard のプロジェクトで動作します。

**Q: 無料トライアルは利用できますか？**  
A: もちろんです。トライアルは [Aspose.GIS リリースページ](https://releases.aspose.com/) からダウンロードできます。

**Q: 完全な API ドキュメントはどこで見られますか？**  
A: 詳細なドキュメントは [Aspose.GIS ドキュメントページ](https://reference.aspose.com/gis/net/) にあります。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose.GIS コミュニティフォーラムに質問を投稿してください。[こちら](https://forum.aspose.com/c/gis/33)。

**Q: 評価用に一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは [購入ページ](https://purchase.aspose.com/temporary-license/) で入手可能です。

## 結論
これで、Aspose.GIS for .NET を使用した **ジオメトリの比較方法**（オブジェクトの作成から空間等価性のチェック、変更の処理まで）を理解できました。この機能は、トポロジー検証、重複検出、ジオメトリベースのフィルタリングなど、より高度な空間解析の基礎となります。

---

**最終更新日:** 2026-06-05  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [C# でポリゴンジオメトリを作成し、Aspose.GIS for .NET で交差をチェック](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Aspose.GIS for .NET を使用したジオメトリの空間重なり解析方法](/gis/net/geometry-analysis/check-geometries-overlap/)
- [ネットワークルーティングチェック: Aspose.GIS で接触ジオメトリを確認](/gis/net/geometry-analysis/check-geometries-touching/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}