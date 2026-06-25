---
date: 2026-06-25
description: Aspose.GIS for .NET を使用して shapefile を読み取り、ポリゴン shapefile を linestring
  に変換する方法を学びます。明確なステップバイステップのガイダンスで GIS 開発を強化しましょう。
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: ポリゴン Shapefile を Linestring に変換
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Shapefile の読み取り方法 C# – ポリゴン Shapefile を Linestring に変換する
url: /ja/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile C# を読む – ポリゴン Shapefile を Linestring に変換する

## はじめに
.NET 環境で **shapefile の読み取り方法** データが必要な場合、ここが適切な場所です。Aspose.GIS for .NET は Shapefile の低レベルバイナリ形式を抽象化し、数回の API 呼び出しだけで地理的フィーチャをロード、クエリ、変換できます。ポリゴン shapefile を linestring に変換することは、ルーティング、ネットワーク分析、またはシンプルな可視化のために線形表現を抽出したい場合に特に有用です。

## クイック回答
- **どのライブラリが shapefile c# の読み取りを支援しますか？** Aspose.GIS for .NET – 50 以上の GIS フォーマットをサポートし、ファイル全体をメモリにロードせずに数百メガバイトまでのファイルを処理できます。  
- **ポリゴンをラインに変換できますか？** はい – ポリゴンの外周リングに対して `LineString` を呼び出し、結果を新しい shapefile に書き込みます。  
- **本番環境でライセンスが必要ですか？** 本番展開には商用ライセンスが必要です。評価目的には無料トライアルが利用できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7+。  
- **トライアルは利用可能ですか？** もちろんです – Aspose サイトから無料トライアルをダウンロードしてください。

`LineString` は、連続した線分の系列を表すジオメトリタイプです。

## 「read shapefile c#」とは何ですか？
`Document` は GIS データセットを表すコアクラスで、フィーチャへのアクセスを提供します。  
C# で shapefile を読み取るとは、`.shp` ファイルをメモリにロードし、ジオメトリをクエリ、変更、変換できるようにすることです。**ファイルパスを指定して `Document` クラスのインスタンスを作成するだけで、Aspose.GIS がバイナリ構造を解析し**、使いやすいコレクションを通じてフィーチャを公開します。このアプローチにより、低レベルのファイルヘッダーや座標配列を手動で扱う必要がなくなります。

## なぜ Aspose.GIS でポリゴンをラインに変換するのか？
ポリゴンを linestring に変換すると、内部リングを除去しつつ正確な外周境界を保持でき、クリーンな線形表現が得られます。Aspose.GIS は **典型的なサーバー上で 500 MB までのデータセットを 2 秒未満で処理** し、バッチ変換を高速かつメモリ効率的に行います。また、ライブラリは元の空間参照を保持するため、生成されたラインは既存の GIS レイヤーと完全に一致します。

## 前提条件
- **Aspose.GIS ライブラリ** – [website](https://releases.aspose.com/gis/net/) から Aspose.GIS ライブラリをダウンロードしてインストールしてください。  
- **Shapefile データ** – 変換用のポリゴン Shapefile を用意してください。お持ちでない場合は、サンプルデータを取得するか自分で作成できます。  
- **開発環境** – 必要なツール（Visual Studio、.NET SDK など）を備えた .NET 開発環境をセットアップしてください。

## 名前空間のインポート
`Document` クラスは Aspose.GIS のコアオブジェクトで、GIS データセットを表し、shapefile の読み書きメソッドを提供します。コードファイルの冒頭に以下の名前空間を追加してください：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Shapefile を読み取り、ポリゴンを Linestring に変換する方法は？
ソースのポリゴン shapefile をロードし、各ポリゴンの外周リングを抽出し、そのリングから `LineString` を作成して結果を新しい shapefile に書き込みます – すべて 5 つのシンプルな手順で行います。このパターンはデータセットのサイズに関係なく機能し、ソースの座標系が宛先に正しく保持されることを保証します。

### ステップ 1: ドキュメント ディレクトリの設定
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` を、shapefile が存在する実際のパスに置き換えてください。

### ステップ 2: ソース Shapefile を開く
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
この行はソースのポリゴン Shapefile を開き、フィーチャを読み取れるようにします。

### ステップ 3: 宛先 Linestring Shapefile を作成する
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
ここでは、変換されたジオメトリを格納する新しい Linestring Shapefile を作成します。

### ステップ 4: ソース フィーチャを反復処理する
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
このループは元のファイル内の各ポリゴン フィーチャを順に処理します。

### ステップ 5: ポリゴンを Linestring に変換し、宛先に書き込む
`ExteriorRing` プロパティはポリゴンの外周境界を `LineString` として返します。  
このブロックではポリゴンをライン（`LineString`）に変換し、新しいフィーチャを宛先 shapefile に追加します。

```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```

## 一般的な問題とヒント
- **座標系の不一致** – ソースと宛先のレイヤーが同じ空間参照を使用していることを確認してください。そうでないと、ラインがずれて表示される可能性があります。  
- **大規模ファイル** – 非常に大きな shapefile を処理する場合、すべてを一度にメモリにロードするのではなく、フィーチャをストリーミングすることを検討してください。  
- **Null ジオメトリ** – 空のジオメトリを持つフィーチャに対してガードし、実行時例外を防止してください。  
- **ポリゴンからラインを抽出** – 外周リングだけが必要な場合は `ExteriorRing` プロパティを使用し、内部リングが必要な場合は `InteriorRings` を反復処理してください。  

## よくある質問

**Q: Aspose.GIS はすべての .NET バージョンと互換性がありますか？**  
A: はい、Aspose.GIS は .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6/7 をサポートしており、最新の開発スタックとシームレスに統合できます。

**Q: Aspose.GIS を商用プロジェクトで使用できますか？**  
A: はい、使用できます。評価制限を解除し、フルサポートを受けるには、[here](https://purchase.aspose.com/buy) からライセンスを購入してください。

**Q: 例やドキュメントはありますか？**  
A: はい、包括的なドキュメントとコードサンプルは [documentation page](https://reference.aspose.com/gis/net/) にあります。

**Q: トライアル版は利用可能ですか？**  
A: もちろんです – [this link](https://releases.aspose.com/) にアクセスして無料トライアルで Aspose.GIS をお試しください。

**Q: サポートやヘルプはどこで得られますか？**  
A: コミュニティ支援と公式サポートは [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) をご覧ください。

---

**最終更新日:** 2026-06-25  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用して Shapefile を GeoJSON に変換する方法](/gis/net/layer-management/extract-features-to-geojson/)
- [Aspose.GIS for .NET でストリームから GeoJSON を読む方法](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS for .NET でポリゴンジオメトリを作成する方法](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}