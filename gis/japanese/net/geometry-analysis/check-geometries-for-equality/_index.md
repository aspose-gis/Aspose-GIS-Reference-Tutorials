---
date: 2026-02-05
description: .NETでAspose.GISを使用してジオメトリを比較する方法を学び、アプリケーションでジオメトリの等価性を確認しましょう。
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してジオメトリの等価性を比較する方法
url: /ja/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリの等価比較方法

## Introduction
このチュートリアルでは、**ジオメトリを比較する方法** を Aspose.GIS for .NET で学びます。マッピングサービスの構築、空間分析の実行、または単に 2 つの形状が同じ位置を表すかどうかを検証する必要がある場合、ジオメトリの比較方法を知っておくことは不可欠です。C# の数行のコードでジオメトリの作成、変更、等価性テストを行う完全なエンドツーエンドの例を順を追って説明します。

## Quick Answers
- **“ジオメトリを比較する” とは何ですか？** 2 つの幾何オブジェクトが構築方法に関係なく同じ空間を占めているかどうかを確認します。  
- **使用されるメソッドはどれですか？** Aspose.GIS API の `SpatiallyEquals`。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にかかる目安の時間は？** 基本的な等価チェックで約 5〜10 分です。

## What is Geometry Equality?
ジオメトリ等価性（しばしば空間等価性と呼ばれる）とは、2 つのジオメトリが地表上の同一の点集合を表すことを意味します。2 つの形状は構築方法が異なっていても、たとえば MultiLineString と単一の LineString でも、空間的に等しい場合があります。

## Why Use Aspose.GIS to Compare Geometries?
Aspose.GIS は堅牢で高性能なジオメトリエンジンを提供し、次のことが可能です：
- WKT、GeoJSON、Shapefile など、幅広いベクターフォーマットに対応。  
- `SpatiallyEquals` のような精度対応比較メソッドを提供。  
- 外部サービス不要でオフラインでも動作し、セキュアまたは隔離された環境に最適。

### Why this matters for developers
バッチ処理や重複検出ルーチン、リアルタイム検証などで **ジオメトリを比較する方法** が必要な場合、信頼できるライブラリが推測を排除し、異なるデータソース間で一貫した結果を保証します。

## Prerequisites
開始する前に、以下が揃っていることを確認してください：

- **.NET Framework または .NET Core がインストール済み** – Aspose.GIS がサポートする任意のバージョン。  
- **Aspose.GIS for .NET ライブラリ** – [Aspose.GIS ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロード。  
- **開発 IDE** – Visual Studio、Rider、または C# 拡張機能付き VS Code。

## Import Namespaces
.NET プロジェクトで、GIS クラスを使用できるように必要な `using` 文を追加します：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define the Geometries
まず、比較対象となる 2 つのジオメトリを作成します。この例では `geometry1` は 2 つの線分からなる `MultiLineString`、`geometry2` は同じ開始点と終了点を持つ単一の `LineString` です。

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

## Step 2: Check Geometries for Equality
次に、`SpatiallyEquals` メソッドを使用して、2 つの形状が GIS エンジンによって等しいとみなされるか確認します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

コンソールは `True` を出力します。これは、構築方法は異なりますが、両ジオメトリが (0,0) から (2,2) までの同じ線分をカバーしているためです。

## Step 3: Modify One Geometry
変更が等価性にどのように影響するかを示すため、`geometry2` に余分な点を追加します。

```csharp
geometry2.AddPoint(3, 3);
```

## Step 4: Re‑check Equality After Modification
変更後、ジオメトリは同一ではなくなるため、`SpatiallyEquals` は `False` を返します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

出力の `False` は、追加した点により空間的等価性が失われたことを示しています。

## Common Issues & Tips
- **精度の問題** – 非常に高精度な座標を扱う場合は、丸め処理を行うか、`SpatiallyEquals` の許容誤差オーバーロードを使用してください。  
- **SRID が異なる** – 比較前に両ジオメトリが同じ Spatial Reference System Identifier (SRID) を持っていることを確認してください。  
- **パフォーマンス** – 大規模コレクションの場合、LINQ を用いたバッチ比較でオーバーヘッドを削減できます。

## Frequently Asked Questions
**Q: Aspose.GIS for .NET を他の .NET フレームワークと併用できますか？**  
A: はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard プロジェクトで動作します。

**Q: 無料トライアルはありますか？**  
A: もちろんです。トライアルは [Aspose.GIS リリースページ](https://releases.aspose.com/) からダウンロードできます。

**Q: 完全な API ドキュメントはどこで見られますか？**  
A: 詳細なドキュメントは [Aspose.GIS ドキュメントページ](https://reference.aspose.com/gis/net/) にあります。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: Aspose.GIS コミュニティフォーラム [こちら](https://forum.aspose.com/c/gis/33) に質問を投稿してください。

**Q: 評価用に一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは [購入ページ](https://purchase.aspose.com/temporary-license/) で入手可能です。

## Conclusion
これで、Aspose.GIS for .NET を使用した **ジオメトリの比較方法** が分かりました。オブジェクトの作成から空間等価性の確認、変更への対応まで、一連の流れを習得しました。この機能は、トポロジー検証、重複検出、ジオメトリベースのフィルタリングなど、より高度な空間分析の基礎となります。

---

**最終更新日:** 2026-02-05  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}