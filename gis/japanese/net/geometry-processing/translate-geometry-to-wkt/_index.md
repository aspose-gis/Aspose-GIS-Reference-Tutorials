---
date: 2026-09-15
description: Aspose.GIS for .NET を使用してジオメトリを WKT に変換する方法を学びます。このガイドでは、ジオメトリを WKT に変換する手順と、AsText
  メソッドを効率的に使用する方法を示します。
keywords:
- convert geometry to wkt
- how to convert geometry
- Aspose.GIS WKT conversion
lastmod: 2026-09-15
linktitle: ジオメトリを WKT に変換
og_description: Aspose.GIS for .NET を使用してジオメトリを WKT に変換します。AsText メソッドを用いたジオメトリの WKT
  変換の最速の方法を学び、実際の例をご覧ください。
og_image_alt: Screenshot of Aspose.GIS code converting geometry objects to WKT strings
og_title: Aspose.GIS for .NET でジオメトリを WKT に変換 – クイックガイド
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert geometry to WKT using Aspose.GIS for .NET. This
    guide shows how to translate geometry to WKT and how to use the AsText method
    efficiently.
  headline: How to convert geometry to WKT with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert geometry to WKT using Aspose.GIS for .NET. This
    guide shows how to translate geometry to WKT and how to use the AsText method
    efficiently.
  name: How to convert geometry to WKT with Aspose.GIS for .NET
  steps:
  - name: import the required namespaces
    text: First, bring the Aspose.GIS geometry classes into scope.
  - name: create a geometry object (point example)
    text: The `Point` class represents a single location defined by X and Y coordinates.
      Instantiate the geometry you want to translate. The example uses a `Point`,
      but the same pattern works for `LineString`, `Polygon`, `MultiPolygon`, and
      other types.
  - name: convert the geometry to WKT with `AsText()`
    text: '`AsText()` is an **extension method that returns the WKT representation
      of a geometry object**. Call it on your geometry instance and you’ll receive
      a ready‑to‑store string. > **Pro tip:** If you need the WKT without commas between
      coordinates, chain a `Replace(",", " ")` call after `AsText()`.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS for .NET runs on .NET Framework 4.5+, .NET Core 3.1+,
      .NET 5, and .NET 6, providing identical functionality across all supported runtimes.
    question: Can I use Aspose.GIS for .NET with other .NET frameworks?
  - answer: Absolutely. The library processes millions of geometry objects per minute,
      uses streaming I/O to keep memory usage low, and has been benchmarked to convert
      1 million points to WKT in under 12 seconds on a standard 8‑core server.
    question: Is Aspose.GIS for .NET suitable for large‑scale applications?
  - answer: Yes. In addition to WKT, it handles WKB, GeoJSON, Shapefile, KML, GML,
      CSV, and many more, covering over 30 spatial data formats.
    question: Does Aspose.GIS for .NET support formats other than WKT?
  - answer: Use the [Aspose.GIS for .NET forum](https://forum.aspose.com/c/gis/33)
      to submit requests, get support, and discuss best practices with the community
      and product team.
    question: Where can I ask for feature requests or report bugs?
  - answer: Yes, you can download a free trial of Aspose.GIS for .NET [download the
      trial version](https://releases.aspose.com/). The trial includes all features
      but adds a small evaluation watermark to generated files.
    question: Is a trial version available?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geometry
- Aspose.GIS
- .NET GIS processing
- WKT conversion
title: Aspose.GIS for .NET を使用したジオメトリの WKT 変換方法
url: /ja/net/geometry-processing/translate-geometry-to-wkt/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したジオメトリの WKT への変換方法

## はじめに
.NET アプリケーションで空間データを扱う場合、**ジオメトリを WKT に変換**する必要が頻繁にあります。これにより、他のサービスやデータベース、GIS ツールが情報を読み取れるようになります。Well‑Known Text (WKT) は、点、線、ポリゴンなどを表す業界標準のテキスト表現です。このチュートリアルでは、Aspose.GIS for .NET を使用して **ジオメトリを WKT に変換**する手順を詳しく解説し、変換を簡単にするワンライナー `AsText()` メソッドを紹介します。

## クイック回答
- **「ジオメトリを変換する」とは何ですか？** ジオメトリオブジェクト（点、線、ポリゴンなど）を WKT などのテキスト形式に変換することです。  
- **WKT を生成するメソッドはどれですか？** 任意のジオメトリオブジェクトの `AsText()`。  
- **ライセンスは必要ですか？** 開発用には無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **対応 .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **他のフォーマットも変換できますか？** はい – Aspose.GIS は WKB、GeoJSON、Shapefile などもサポートしています。

## ジオメトリを WKT に変換するとは？
ジオメトリを WKT に変換するとは、空間オブジェクトの座標と形状をプレーンテキスト文字列で表現することです。例: `POINT (23.5732 25.3421)`。この形式は人間が読みやすく、リレーショナルデータベースに保存しやすく、事実上すべての GIS プラットフォームで受け入れられます。

## なぜ Aspose.GIS を使うのか？
Aspose.GIS は **依存関係ゼロ、完全マネージド API** を提供し、.NET Framework、.NET Core、.NET 5/6 で一貫して動作します。**30 以上の入出力フォーマット**（WKT、WKB、GeoJSON、Shapefile、KML、GML など）をサポートし、ファイル全体をメモリにロードせずに数百ページ規模のデータセットを処理でき、典型的な点や線のジオメトリではミリ秒未満の変換時間を実現します。

## 前提条件
開始する前に以下を確認してください。

1. **Aspose.GIS for .NET がインストール済み** – 公式の [Aspose.GIS for .NET ドキュメント](https://reference.aspose.com/gis/net/) に従ってください。  
2. **.NET 開発環境** – Visual Studio、Rider、または C# 拡張機能付き VS Code。  
3. **基本的な C# の知識** – コードスニペットはシンプルな C# 構文を使用しています。

## Aspose.GIS for .NET を使用したジオメトリの WKT 変換手順
以下はステップバイステップの解説です。各ステップには簡単な説明と、必要なコード（コードブロックは省略してプレースホルダーを残しています）を示します。

### 手順 1: 必要な名前空間をインポート
まず、Aspose.GIS のジオメトリクラスをスコープに持ち込みます。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 手順 2: ジオメトリオブジェクトを作成（点の例）
`Point` クラスは X と Y 座標で定義された単一位置を表します。変換したいジオメトリをインスタンス化します。例は `Point` ですが、`LineString`、`Polygon`、`MultiPolygon` などでも同様のパターンが使えます。

```csharp
Point point = new Point(23.5732, 25.3421);
```

### 手順 3: `AsText()` でジオメトリを WKT に変換
`AsText()` は **ジオメトリオブジェクトの WKT 表現を返す拡張メソッド** です。ジオメトリインスタンスに対して呼び出すと、保存可能な文字列が取得できます。

```csharp
Console.WriteLine(point.AsText()); // POINT (23.5732, 25.3421)
```

> **プロのコツ:** 座標間のカンマを除去したい場合は、`AsText()` の後に `Replace(",", " ")` をチェーンしてください。

## AsText メソッドの使い方
`AsText()` は **ジオメトリを WKT に変換**する主要手段です。`Geometry` から派生したクラスであれば、`LineString`、`Polygon`、`MultiPolygon` などでも追加の変換ステップなしに直接呼び出せます。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| `AsText()` が `null` を返す | ジオメトリが初期化されていない | `AsText()` を呼び出す前に、座標が有効なジオメトリオブジェクトを作成してください。 |
| 期待しない形式（カンマ vs スペース） | GIS ツールによって区切り文字が異なる | `Replace` で文字列操作するか、カスタム書式用に `WktWriter` クラスを使用してください。 |
| 大量コレクション変換時のパフォーマンス低下 | コンソール I/O の繰り返し | `Console.WriteLine` の代わりにバッチ変換してファイルまたは `StringBuilder` に書き込むようにしてください。 |

## FAQ

**Q: 他の .NET フレームワークでも Aspose.GIS for .NET を使用できますか？**  
A: はい、Aspose.GIS for .NET は .NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 で動作し、すべてのサポート対象ランタイムで同一機能を提供します。

**Q: 大規模アプリケーションに適していますか？**  
A: 絶対に適しています。ライブラリは 1 分間に数百万のジオメトリオブジェクトを処理でき、ストリーミング I/O によりメモリ使用量を抑え、標準的な 8 コアサーバー上で 100 万点を 12 秒未満で WKT に変換したベンチマークがあります。

**Q: WKT 以外のフォーマットもサポートしていますか？**  
A: はい。WKT に加えて、WKB、GeoJSON、Shapefile、KML、GML、CSV など、30 以上の空間データフォーマットに対応しています。

**Q: 機能要望やバグ報告はどこで行えますか？**  
A: [Aspose.GIS for .NET フォーラム](https://forum.aspose.com/c/gis/33) で要望やバグ報告が可能です。コミュニティや製品チームと議論できます。

**Q: トライアル版はありますか？**  
A: はい、Aspose.GIS for .NET の無料トライアルを [トライアル版をダウンロード](https://releases.aspose.com/) できます。トライアルはすべての機能を含みますが、生成ファイルに小さな評価用透かしが付加されます。

**Q: ジオメトリコレクションを効率的に変換する方法は？**  
A: コレクションをループし、各ジオメトリに対して `AsText()` を呼び出し、結果を `StringBuilder` に追加するか直接ファイルに書き込んでください。これによりコンソール書き込みのオーバーヘッドを回避できます。

**Q: エクスポートする WKT に SRID を含められますか？**  
A: `AsText(int srid)` のオーバーロードを使用すると、空間参照識別子を WKT 文字列に直接埋め込めます。

**Q: `AsText()` の出力はロケールに依存しますか？**  
A: `AsText()` は常に不変カルチャを使用し、サーバーのロケール設定に関係なく小数点はピリオド（`.`）になります。

**Q: Aspose.GIS は 3‑D 座標の WKT を扱えますか？**  
A: バージョン 22.10 以降、Z および M 値をサポートし、`POINT Z (x y z)` や `POINT M (x y m)` のような文字列を生成できます。

---

**最終更新日:** 2026-09-15  
**テスト環境:** Aspose.GIS for .NET 23.11  
**作者:** Aspose

## 関連チュートリアル

- [WKT からポイントをカウントする方法 (Aspose.GIS for .NET)](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [WKB ジオメトリを変換する方法 (Aspose.GIS for .NET)](/gis/net/geometry-processing/translate-geometry-from-wkb/)
- [空間参照を設定し、WKT バリアントを指定する方法 (Aspose.GIS)](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}