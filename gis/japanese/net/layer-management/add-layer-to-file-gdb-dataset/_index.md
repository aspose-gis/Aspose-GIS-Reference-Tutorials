---
date: 2026-06-30
description: Aspose.GIS を使用し、空間参照 WGS84 の File GDB データセットにレイヤーを追加する方法を学びます。.NET でレイヤーを追加する手順をステップバイステップでご案内します。
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: File GDB データセットにレイヤーを追加
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS を使用して、空間参照 WGS84 の File GDB データセットにレイヤーを追加する方法
url: /ja/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# レイヤーの追加方法 – 空間参照 wgs84 と Aspose.GIS

## はじめに
Aspose.GIS for .NET を使用して GIS ワークフローを強化する準備はできましたか？このチュートリアルでは、File GDB データセットに **レイヤーの追加方法** を学び、**空間参照 WGS84** 座標系で作業します。データフォルダーの準備から新しく作成したレイヤーの検証まで、各ステップを順に説明するので、地理データを自信を持って効率的に操作できるようになります。

## クイック回答
- **使用されている主な座標系は何ですか？** spatial reference wgs84 (WGS 84)  
- **どのライブラリが API を提供しますか？** Aspose.GIS for .NET  
- **テストにライセンスは必要ですか？** はい – 一時的な Aspose ライセンスが利用可能です。  
- **新しいレイヤーに属性を追加できますか？** はい、任意の数の feature 属性を定義できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## 空間参照 wgs84 とは何ですか？
空間参照 wgs84（World Geodetic System 1984）は、最も広く使用されている地理座標系です。緯度と経度を度で定義し、多くの GIS データセットのデフォルト CRS として機能します。本ガイドで作成するデータセットも含まれます。

## レイヤーを追加するために Aspose.GIS を使用する理由は？
サードパーティのバイナリを使用せずに GIS データをロードし、スキーマ定義を完全に制御できます。Aspose.GIS は **40 以上の空間参照システム** をサポートし、**2 GB** を超えるファイルもデータセット全体をメモリにロードせずに処理でき、Windows、Linux、macOS で動作します。これにより、エンタープライズ向け GIS 自動化のための信頼性の高いクロスプラットフォーム ソリューションとなります。

## 前提条件
- Aspose.GIS for .NET ライブラリ: [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) からライブラリをダウンロードしてインストールしてください。  
- ドキュメント ディレクトリ: GIS ファイルを保存するために、マシン上に専用のフォルダーを作成します。  
- 一時的な Aspose ライセンス（評価用にオプション） – ダウンロードリンクは下記 FAQ を参照してください。

## 名前空間のインポート
C# プロジェクトに必要な `using` ステートメントを追加して、Aspose.GIS クラスにアクセスできるようにします。

*コードブロックは不要です。ファイルの先頭に以下の行を追加してください。*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## ステップ 1: ディレクトリのコピー
**Definition anchor:** File GDB データセットは、フォルダー ベースの ESRI ジオデータベースで、空間データを複数のファイルに保存します。  
まず、元の GDB データセットが入っているフォルダーを複製します。コピーを保持することで、実験中に元データを保護できます。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 2: データセットを開き、作成機能を確認する
`Dataset` は File GDB に保存された GIS レイヤーのコレクションを表します。新しくコピーしたデータセットを開き、レイヤーを新規作成できるか確認します。`CanCreateLayers` プロパティは **True** を返すはずです。**`CanCreateLayers` は、データセットが新しいレイヤーの作成をサポートしているかどうかを示すブール値プロパティです。**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## ステップ 3: 空間参照 wgs84 を使用して新しいレイヤーを作成およびデータを追加
ここでは **data** という名前のレイヤーを作成し、空間参照を **Wgs84** に明示的に設定します。また、**Name** というシンプルな属性を追加し、ポイント フィーチャを 1 つ挿入します。**`CreateLayer` は、指定された名前と空間参照でデータセットに新しいレイヤーを作成します。** **`SpatialReference` はレイヤーで使用される座標系を表します。** **`Feature` はレイヤーに格納される個々の地理オブジェクト（ポイント、ライン、またはポリゴン）です。**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## ステップ 4: 追加したレイヤーを開いて検証する
最後に、作成したレイヤーを開き、その内容を検証します。コンソールにはレイヤーに 1 つのフィーチャが含まれ、**Name** 属性が設定したものと一致することが表示されます。**`Layer.Open` は既存のレイヤーを読み取りまたは編集のために開きます。** これにより、レイヤーが正しく追加され、空間参照が WGS84 であることが確認できます。

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## File GDB データセットにレイヤーを追加する方法は？
データセットをロードし、目的の名前と空間参照で `CreateLayer` を呼び出し、属性スキーマを定義してからフィーチャを挿入します。これらはすべて少数の Aspose.GIS メソッド呼び出しで実行でき、API がファイルロックとスキーマ検証を自動的に処理します。このプロセスにより、新しいレイヤーがデータセットの空間参照に適合し、属性定義がレイヤーのスキーマに保存され、File GDB をサポートする任意の GIS ソフトウェアでデータにアクセスできるようになります。

## 一般的な問題とヒント
- **Incorrect path:** `dataDir` がパス区切り文字（`/` または `\`）で終わっていることを確認し、結合された文字列が有効なファイルパスになるようにします。  
- **License errors:** ライセンス警告が表示された場合、コード実行前に Aspose ポータルから一時ライセンスを適用してください。  
- **CRS mismatch:** 後で別の GIS ツールでレイヤーを開く際、ツールが WGS 84（EPSG:4326）を座標系として認識していることを確認してください。  
- **Large datasets:** データセットが 1 GB を超える場合、`Dataset.OpenReadOnly` の使用を検討してメモリ使用量を削減してください。

## よくある質問
### Q: Aspose.GIS for .NET を他の GIS ライブラリと併用できますか？
A: はい、Aspose.GIS は単独で動作しますが、GDAL や NetTopologySuite などのライブラリと組み合わせて高度な処理が可能です。

### Q: テスト目的の一時ライセンスは利用可能ですか？
A: はい、テストおよび評価用の一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

### Q: Aspose.GIS for .NET がサポートする空間参照システムは何ですか？
A: Aspose.GIS は **40 以上の EPSG コード** をサポートしており、WGS84 (EPSG:4326)、Web Mercator (EPSG:3857)、NAD83 (EPSG:4269) などの一般的なシステムが含まれます。包括的なドキュメントは[こちら](https://reference.aspose.com/gis/net/)で確認してください。

### Q: Aspose.GIS コミュニティに貢献できますか？
A: もちろんです！[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)で議論に参加し、経験を共有してください。

### Q: Aspose.GIS for .NET の詳細なドキュメントはどこで見つけられますか？
A: すべてのクラス、メソッド、ベストプラクティスに関する詳細情報は、包括的なドキュメント[こちら](https://reference.aspose.com/gis/net/)をご覧ください。

---

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.GIS for .NET (latest stable version)  
**作者:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## 関連チュートリアル

- [Aspose.GIS を使用した File Geodatabase .NET データセットの作成](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [File GDB にベクターレイヤーを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [File GDB データセットの作成とレイヤーの許容誤差設定](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}