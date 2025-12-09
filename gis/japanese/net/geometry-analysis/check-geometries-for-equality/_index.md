---
date: 2025-12-03
description: Aspose.GIS for .NET を使用してジオメトリを比較する方法を学び、.NET アプリケーションでジオメトリの等価性を確認しましょう。
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してジオメトリの等価性を比較する方法
url: /ja/net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリの等価性比較方法

## Introduction
このチュートリアルでは、Aspose.GIS for .NET を使用して **ジオメトリを比較する方法** を学びます。マッピングサービスの構築、空間分析の実行、または単に2つの形状が同じ位置を表すかどうかを確認する必要がある場合、ジオメトリの比較方法を知っておくことは不可欠です。C# の数行のコードでジオメトリの作成、変更、等価性テストを行う完全なエンドツーエンドの例を順を追って説明します。

## Quick Answers
- **「ジオメトリを比較する」とは何ですか？** 2つのジオメトリオブジェクトが構築方法に関係なく同じ空間を占めているかどうかを確認します。  
- **使用されるメソッドはどれですか？** Aspose.GIS API の `SpatiallyEquals`。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **一般的な実装時間は？** 基本的な等価性チェックで約 5〜10 分です。

## What is Geometry Equality?
ジオメトリの等価性（空間等価性とも呼ばれます）とは、2つのジオメトリが地表上の全く同じ点集合を表すことを意味します。形状は異なる方法で構築されても構いません。たとえば MultiLineString と単一の LineString でも、空間的に等価である場合があります。

## Why Use Aspose.GIS to Compare Geometries?
ジオメトリ比較に Aspose.GIS を使用する理由
- WKT、GeoJSON、Shapefile など、幅広いベクターフォーマットに対応します。  
- `SpatiallyEquals` のような精度対応比較メソッドを提供します。  
- 外部サービスを必要とせずオフラインで動作するため、セキュアまたは隔離された環境に最適です。

## Prerequisites
前提条件
- **.NET Framework または .NET Core がインストールされていること** – Aspose.GIS がサポートする任意のバージョン。  
- **Aspose.GIS for .NET ライブラリ** – [Aspose.GIS ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
- **開発用 IDE** – Visual Studio、Rider、または C# 拡張機能が入った VS Code。

## Import Namespaces
名前空間のインポート
In your .NET project, add the required `using` statements so the compiler knows where to find the GIS classes:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define the Geometries
ステップ 1: ジオメトリの定義
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

## Step 2: Check Geometries for Equality
ステップ 2: ジオメトリの等価性をチェック
次に、GIS エンジンが 2 つの形状を等価とみなすかどうかを確認するために `SpatiallyEquals` メソッドを使用します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

コンソールは `True` と出力します。これは、構築方法は異なりますが、両ジオメトリが (0,0) から (2,2) までの同じ線分をカバーしているためです。

## Step 3: Modify One Geometry
ステップ 3: 1 つのジオメトリを変更
変更が等価性にどのように影響するかを示すために、`geometry2` に余分な点を追加します```csharp
geometry2.AddPoint(3, 3);
```

## Step 4: Re‑check Equality After Modification
ステップ 4: 変更後に等価性を再チェック
変更後、ジオメトリは同一ではなくなるため、`SpatiallyEquals` は `False` を返します。

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

出力された `False` は、追加された点により空間的等価性が失われたことを示しています。

## Common Issues & Tips
一般的な問題とヒント
- **精度の問題** – 非常に高精度な座標を扱う場合は、丸め処理を行うか、`SpatiallyEquals` の許容誤差オーバーロードを使用してください。  
- **異なる SRID** – 比較する前に、両ジオメトリが同じ Spatial Reference System Identifier (SRID) を持っていることを確認してください。  
- **パフォーマンス** – 大規模コレクションの場合、LINQ を使用したバッチ比較でオーバーヘッドを削減できます。

## Frequently Asked Questions
よくある質問
**Q: Aspose.GIS for .NET を他の .NET フレームワークと併用できますか？**  
A: はい、Aspose.GIS は .NET Framework、.NET Core、.NET Standard プロジェクトで動作します。

**Q: 無料トライアルは利用できますか？**  
A: もちろんです。トライアルは [Aspose.GIS リリースページ](https://releases.aspose.com/) からダウンロードできます。

**Q: 完全な API ドキュメントはどこで見つけられますか？**  
A: 詳細なドュメントは [Aspose.GIS ドキュメントページ](https://reference.aspose.com/gis/net/) にあります。

**Q: 問題が発生した場合、どのようにサポートを受けられますか？**  
A: Aspose.GIS コミュニティフォーラム [こちら](https://forum.aspose.com/c/gis/33) に質問を投稿してください。

**Q: 評価用に一時ライセンスを購入できますか？**  
A: はい、一時ライセンスは [購入ページ](https://purchase.aspose.com/temporary-license/) で手可能です。

## Conclusion
結論
これで、Aspose.GIS for .NET を使用して **ジオメトリを比較する方法** が分かりました。オブジェクトの作成から空間的等価性のチェック、変更の取り扱いまで。この機能は、トポロジー検証、重複検出、ジオメトリベースのフィルタリングなど、より高度な空間分析の基礎となります。

---

**最終更新日:** 2025-12-03  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}