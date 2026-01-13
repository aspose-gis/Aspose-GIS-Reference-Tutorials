---
date: 2026-01-13
description: Aspose.GIS を使用して、空間参照 WGS84 をサポートした File GDB データセットにレイヤーを追加する方法を学びましょう。.NET
  で GDB にレイヤーを追加する手順をステップバイステップでご案内します。
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: 空間参照 WGS84 – Aspose.GIS を使用して GDB にレイヤーを追加
url: /ja/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Aspose.GIS を使用して GDB にレイヤーを追加

## Introduction
Aspose.GIS for .NET で GIS ワークフローを強化する準備はできましたか？このチュートリアルでは、**spatial reference wgs84** 座標系を使用しながら、**File GDB データセットにレイヤーを追加する方法** を学びます。データフォルダーの準備から新しく作成したレイヤーの検証まで、各ステップを順に解説するので、地理データの操作を自信を持って始められます。

## Quick Answers
- **使用される主座標系は何ですか？** spatial reference wgs84 (WGS 84)  
- **API を提供しているライブラリはどれですか？** Aspose.GIS for .NET  
- **テストにライセンスは必要ですか？** はい – 一時的な Aspose ライセンスが利用可能です。  
- **新しいレイヤーに属性を追加できますか？** もちろん、任意の数のフィーチャ属性を定義できます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6。

## What is spatial reference wgs84?
spatial reference wgs84（World Geodetic System 1984）は、最も広く使用されている地理座標系です。緯度と経度を度で定義し、多くの GIS データセットのデフォルト CRS として機能します。本ガイドで作成するデータセットもこの座標系を使用します。

## Why use Aspose.GIS to add a layer?
- **外部依存がない:** 純粋な .NET コードだけで動作します。  
- **スキーマを完全に制御:** カスタム属性やジオメトリタイプを自由に定義可能。  
- **クロスプラットフォーム:** Windows、Linux、macOS のランタイムで動作します。  
- **堅牢なライセンス:** 一時ライセンスで迅速に評価でき、導入前に確認できます。

## Prerequisites
開始する前に、以下を用意してください。

- Aspose.GIS for .NET ライブラリ: [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) からダウンロードしてインストールします。  
- ドキュメントディレクトリ: GIS ファイルを保存するための専用フォルダーを作成します。

## Import Namespaces
Aspose.GIS クラスにアクセスできるよう、C# プロジェクトに必要な `using` 文を追加します。

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

## Step 1: Copy Directory
元の GDB データセットが入っているフォルダーを複製します。コピーを作成しておくことで、実験中に元データを保護できます。

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
コピーしたデータセットを開き、新しいレイヤーを作成できるか確認します。`CanCreateLayers` プロパティは **True** を返すはずです。

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
ここで **data** という名前のレイヤーを作成し、spatial reference を **Wgs84** に明示的に設定します。また、**Name** というシンプルな属性を追加し、1 つのポイントフィーチャを挿入します。

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

## Step 4: Open and Validate the Added Layer
最後に、作成したレイヤーを開いて内容を検証します。コンソールにはレイヤーに 1 件のフィーチャが含まれ、**Name** 属性が設定した値と一致していることが表示されます。

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **パスが正しくない:** `dataDir` の末尾にパス区切り文字（`/` または `\`）が付いていることを確認し、文字列結合で有効なファイルパスが生成されるようにします。  
- **ライセンスエラー:** ライセンス警告が表示された場合は、コード実行前に Aspose ポータルから一時ライセンスを適用してください。  
- **CRS の不一致:** 後で別の GIS ツールでレイヤーを開く際は、ツールが WGS 84（EPSG:4326）を座標系として認識しているか確認してください。

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS for .NET は単独で動作するよう設計されていますが、機能拡張のために他のライブラリと統合することも可能です。  

### Q: Is a temporary license available for testing purposes?
はい、テストおよび評価用の一時ライセンスを [here](https://purchase.aspose.com/temporary-license/) から取得できます。  

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS for .NET は多数の spatial reference system をサポートしており、地理データの取り扱いに柔軟性を提供します。  

### Q: Can I contribute to the Aspose.GIS community?
もちろんです！[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) でディスカッションに参加し、経験を共有してください。  

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
詳細な情報は、[here](https://reference.aspose.com/gis/net/) にある包括的なドキュメントをご覧ください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose