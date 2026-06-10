---
date: 2026-06-10
description: Aspose.GIS for .NET と ExtendedPostGis バリアントを使用して、linestring geometry
  を作成し、geometry を WKB に変換する方法を学びます。
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: 翻訳時に WKB Variant を指定
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET で Linestring Geometry と WKB Variant を作成
url: /ja/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET でラインストリングジオメトリと WKB バリアントを作成する

## はじめに
.NET で**create linestring geometry .NET**を作成し、そのジオメトリをバイナリ形式に変換する必要がある場合、Aspose.GIS for .NET は .NET Framework、.NET Core、.NET 5/6+ で動作するクリーンで高性能な API を提供します。このチュートリアルでは、名前空間のインポートから EWKB ファイルの書き込みまで、すべての手順を順に説明しますので、SRID 情報を保持し、GIS データを PostgreSQL/PostGIS や任意のバイナリベースのワークフローに手間なく統合できます。

## クイック回答
- **WKB は何の略ですか？** Well‑Known Binary、ジオメトリオブジェクトのコンパクトなバイナリ表現です。  
- **どの WKB バリアントが SRID を格納しますか？** `ExtendedPostGis` (EWKB) バリアントは SRID をバイナリに直接埋め込みます。  
- **ライセンスは必要ですか？** 本番環境での展開には、一時的または完全な Aspose.GIS ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6+。  
- **実装にどれくらい時間がかかりますか？** 基本的な例では通常 10 分未満です。

## ラインストリングジオメトリとは？
ラインストリングジオメトリは、順序付けられた点のリストを直線セグメントで結んだシンプルな形状です。道路、パイプライン、河川の経路など、空間データベースで線形フィーチャを表すのに最適です。

## なぜ WKB バリアントを指定するのか？
正しい WKB バリアントを使用すると、重要なメタデータ、特に空間参照系識別子 (SRID) がジオメトリと共に保持されます。`ExtendedPostGis` (EWKB) バリアントは SRID をバイナリペイロード内に格納し、PostGIS、Oracle Spatial、または SRID 対応バイナリを期待するシステムとのシームレスな往復を可能にします。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

### Aspose.GIS for .NET のインストール
1. Aspose.GIS をダウンロード: 最新パッケージを取得するには [download link](https://releases.aspose.com/gis/net/) を訪問してください。  
2. NuGet パッケージをプロジェクトに追加します（例: `Install-Package Aspose.GIS`）。  

### C# プログラミングの基礎知識
- C# の構文とプロジェクト構造の基本的な理解。  
- .NET コンソールまたはクラスライブラリ プロジェクトを実行できること。

## 名前空間のインポート
`Aspose.GIS` 名前空間は、ジオメトリ関連クラスすべてへのアクセスを提供します。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

これらの名前空間は、ジオメトリの作成、変換、バイナリシリアライズなど、コア GIS 機能を提供します。

## ラインストリングジオメトリの作成方法は？
ラインストリングを作成するには、座標ペアの順序付けられたリストで `Linestring` オブジェクトをインスタンス化し、必要に応じて SRID を設定し、目的の WKB バリアントにシリアライズします。このプロセスは、ジオメトリの構築、SRID を保持するために `ExtendedPostGis` バリアントの選択、結果のバイト配列をファイルに書き込むという 3 つのステップで構成されます。

### ステップ 1: ジオメトリオブジェクトの作成
`Geometry` クラスは、Aspose.GIS の基底型で、メモリ内の任意の空間オブジェクトを表します。  
`Linestring` は、線形ジオメトリを形成する接続された点の系列を表します。  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
このステップでは、シンプルな道路セグメントをモデル化する座標ペアのコレクションで `Linestring` をインスタンス化します。

### ステップ 2: WKB 表現の生成
`WkbVariant.ExtendedPostGis` は、Aspose.GIS に出力バイナリに SRID を含めるよう指示する列挙値です。  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
ここでは `AsBinary` メソッドを呼び出し、EWKB バリアントを渡します。これにより、完全なバイナリ表現を含む `byte[]` が返されます。

### ステップ 3: ファイルへの書き込み
`File.WriteAllBytes` はバイナリ配列をディスクに書き込みます。  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
生成されたファイル（`EWkbFile.ewkb`）は、`ST_GeomFromEWKB` 関数を使用して PostGIS テーブルに直接インポートできます。

## よくある問題と解決策
| 問題 | 原因 | 解決策 |
|-------|--------|----------|
| **Empty file** | `Path.Combine` が存在しないディレクトリを指しています。 | ターゲットディレクトリが存在することを確認するか、`Directory.CreateDirectory` で作成してください。 |
| **Incorrect SRID** | デフォルトの `WkbVariant.Standard` を使用すると SRID が失われます。 | SRID の保持が必要な場合は常に `WkbVariant.ExtendedPostGis` を使用してください。 |
| **License exception** | 本番環境で有効なライセンスなしで実行しています。 | 本番環境でコードを実行する前に、一時的または完全なライセンスを適用してください。 |

## よくある質問
**Q: EWKB ファイルを PostGIS で使用できますか？**  
A: はい、`ExtendedPostGis` バリアントは SRID を含む EWKB を生成し、PostGIS は `ST_GeomFromEWKB` で直接読み取ります。  

**Q: WKB ファイルをジオメトリオブジェクトに読み戻すことは可能ですか？**  
A: もちろん可能です。`Geometry.FromBinary(byteArray)` を使用して、バイナリ形式からジオメトリを再構築します。  

**Q: ライブラリはポリゴンなど他のジオメトリタイプもサポートしていますか？**  
A: はい、Aspose.GIS はポイント、ラインストリング、ポリゴン、マルチポリゴンなど多数の空間タイプを扱えます。  

**Q: ジオメトリ作成時に別の SRID を指定するには？**  
A: `AsBinary` を呼び出す前にジオメトリオブジェクトの `SRID` プロパティを設定します。例: `linestring.SRID = 4326;`。  

**Q: このコードは .NET Core でも動作しますか？**  
A: はい、同じ API は .NET Framework、.NET Core、.NET 5/6 で変更なしに動作します。

---

**最終更新日:** 2026-06-10  
**テスト環境:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したジオメトリの WKB 形式への変換](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Aspose.GIS を使用した変換時の WKT バリアントの指定](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Aspose.GIS for .NET を使用した MultiLineString ジオメトリの作成](/gis/net/geometry-creation/create-multilinestring-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}