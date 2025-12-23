---
date: 2025-12-23
description: Aspose.GIS for .NET を使用して WKT をジオメトリに変換する方法と、ポイントをカウントする方法を学びましょう。開発者向けのステップバイステップガイドです。
linktitle: Translate Geometry from WKT
second_title: Aspose.GIS .NET API
title: .NETでAspose.GISを使用してWKTをジオメトリに変換する方法
url: /ja/net/geometry-processing/translate-geometry-from-wkt/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した WKT のジオメトリへの変換

## Introduction
このチュートリアルでは、Aspose.GIS for .NET を使用して **WKT をジオメトリに変換する方法** を学び、結果のシェイプ内の **ポイント数をカウントする方法** の実例をご紹介します。マッピングサービスの構築、GIS データの処理、または .NET アプリケーションで Well‑Known Text を読み取る必要がある場合でも、これらの手順で迅速に始められます。

## Quick Answers
- **Aspose.GIS は WKT を読み取れますか？** はい – `Geometry.FromText` メソッドは WKT 文字列を直接解析します。  
- **必要なコード行数は？** 基本的な変換とポイントカウントのために約 5〜6 行です。  
- **本番環境でライセンスが必要ですか？** はい、トライアル以外の使用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **ポイント数のカウントは組み込みですか？** もちろんです – ジオメトリオブジェクトは `Count` プロパティを提供します。

## What is “convert WKT to geometry”?
Well‑Known Text（WKT）は、幾何オブジェクトを表現するプレーンテキストのマークアップです。WKT をジオメトリに変換することは、そのテキストをオブジェクトモデル（例: `ILineString`、`IPolygon`）に変換し、プログラムから操作できるようにすることを意味します。

## Why use Aspose.GIS for this conversion?
- **ゼロ依存のパース** – 外部ライブラリは不要です。  
- **フル GIS 機能セット** – 2D/3D 座標、SRID の取り扱い、さまざまなファイル形式をサポートします。  
- **高性能** – 大規模データセットやマルチスレッドシナリオ向けに最適化されています。  

## Prerequisites
開始する前に、以下が揃っていることを確認してください：

1. Aspose.GIS for .NET API – [こちら](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
2. C# の基本知識と .NET 開発環境（Visual Studio、VS Code など）。  

## Import Namespaces
まず、C# ファイルに必要な名前空間を追加します：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Create a LineString from WKT
ステップ 1: WKT から LineString を作成する

ここでは、Z 座標を含む WKT 文字列から `LineString` オブジェクトを作成し、**WKT をジオメトリに変換**します：

```csharp
ILineString line = (ILineString)Geometry.FromText("LINESTRING Z (0.1 0.2 0.3, 1 2 1, 12 23 2)");
```

> *プロのコツ:* `FromText` メソッドはジオメトリタイプを自動的に検出するため、適切なインターフェイス（`ILineString`、`IPolygon` など）にキャストできます。

## How to count points in a LineString?
LineString のポイント数をカウントする方法は？

二次的なキーワード **ポイント数のカウント方法** に答えるには、`ILineString` インスタンスの `Count` プロパティを読むだけです：

```csharp
Console.WriteLine(line.Count); // Output: 3
```

出力は、ラインに 3 つの頂点が含まれていることを示し、変換が成功しポイント数が正確であることを確認します。

## Conclusion
結論

これで、Aspose.GIS for .NET を使用して **WKT をジオメトリに変換する方法** と、単一のプロパティ呼び出しでポイント数を取得する方法が分かりました。この基本を活用すれば、デスクトップツールからクラウドサービスまで、あらゆる .NET アプリケーションに GIS データ処理を統合できます。

## FAQ's
### Can I use Aspose.GIS for .NET in my commercial projects?
はい、できます。Aspose.GIS for .NET は開発者ごとにライセンスが付与され、商用プロジェクトで制限なく使用できます。

### Does Aspose.GIS for .NET support other geometric formats besides WKT?
はい、Aspose.GIS for .NET は WKB、GeoJSON、Shapefile などさまざまなジオメトリ形式をサポートしています。

### Is there a free trial available for Aspose.GIS for .NET?
はい、[こちら](https://releases.aspose.com/) から無料トライアルを入手できます。

### Where can I find documentation for Aspose.GIS for .NET?
ドキュメントは[こちら](https://reference.aspose.com/gis/net/) にあります。

### How can I get support for Aspose.GIS for .NET?
サポートは Aspose.GIS フォーラム[こちら](https://forum.aspose.com/c/gis/33) から受けられます。

## Frequently Asked Questions (Additional)

**Q: WKT 文字列に無効な構文が含まれている場合は？**  
A: `Geometry.FromText` は `FormatException` をスローします。try‑catch ブロックで呼び出しをラップし、malformed WKT を適切に処理してください。

**Q: WKT 文字列のコレクションを一括で変換できますか？**  
A: はい – 文字列リストをイテレートし、各項目に対して `Geometry.FromText` を呼び出し、結果を `List<IGeometry>` に格納します。

**Q: 変換時に Z 値は保持されますか？**  
A: もちろんです。例に示すように WKT に Z 座標が含まれている場合、生成されたジオメトリはその値を保持します。

**Q: 操作後にジオメトリを WKT にエクスポートできますか？**  
A: 任意の `IGeometry` インスタンスで `ToText()` メソッドを使用すれば、WKT 表現を取得できます。

---

**最終更新日:** 2025-12-23  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}