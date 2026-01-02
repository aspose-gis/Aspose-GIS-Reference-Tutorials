---
date: 2026-01-02
description: Aspose.GIS for .NET を使用して、フィールド名を設定しながらポイント フィーチャを追加し、オブジェクト ID を読み取る方法を学びましょう。開発者向けのステップバイステップ
  ガイドです。
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: ポイントフィーチャを追加し、オブジェクトIDとジオメトリフィールド名を指定する
url: /ja/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ポイント フィーチャを追加し、Object ID とジオメトリ フィールド名を指定する

## Introduction
Aspose.GIS for .NET を使用して地理情報システム (GIS) の領域に踏み込むことは、開発者やエンスージアストにとって多くの可能性を開きます。このチュートリアルでは、**ポイント フィーチャの追加方法** と **フィールド名の設定**、そして **object id の取得** 方法を学び、空間データを完全にコントロールできるようになります。

## Quick Answers
- **このガイドの主な目的は何ですか？** ポイント フィーチャを追加し、Object ID とジオメトリ フィールド名を設定する方法を示すことです。  
- **使用されているライブラリはどれですか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です。製品版ではライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **挿入後に Object ID を取得できますか？** はい – 本チュートリアルではレイヤーから object id を読み取る方法を実演します。

## Prerequisites
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。
- Aspose.GIS for .NET: ライブラリを [here](https://releases.aspose.com/gis/net/) からダウンロードしてインストールします。
- Document Directory: ジオデータベースを保存するためのディレクトリを設定します。
- .NET Environment: 動作する .NET 環境があることを確認します。

## Import Namespaces
作業を開始するには、プロジェクトに必要な名前空間をインポートする必要があります。これらの名前空間は Aspose.GIS for .NET とやり取りするための重要なクラスとメソッドを提供します。

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Step 1: Add point feature and specify Object ID and Geometry Field Names
このステップでは、GIS データの Object ID とジオメトリ フィールド名を設定する方法を学びます。これは効率的なデータ管理に不可欠であり、後で **object id を読み取る** ことができるようにするためです。

### Step 1.1: Set Document Directory
まず、ドキュメント ディレクトリへのパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

### Step 1.2: Create a GeoDatabase and Define Options
Object ID とジオメトリ用に **フィールド名を設定** した GeoDatabase を作成します。

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Step 1.3: Create and Add a Layer
GeoDatabase 内にレイヤーを作成し、ポイント ジオメトリを表すフィーチャを追加します。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Step 1.4: Open and Retrieve Data from the Layer
レイヤーを開き、先ほど追加したフィーチャを取得します。これによりデータセットから **object id を読み取る** 方法が示されます。

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Why set custom field names?
Object ID とジオメトリ フィールド名をカスタマイズすると、既存のデータベースとの統合や、下流アプリケーションが要求する命名規則に従う際に柔軟性が得られます。また、データが自己記述的になるため、保守やコラボレーションが容易になります。

## Common pitfalls and troubleshooting
- **Missing directory** – `dataDir` が実在するフォルダーを指していることを確認してください。そうでない場合、`Dataset.Create` は例外をスローします。  
- **Field name conflicts** – 同名のフィールドがジオデータベースに既に存在すると作成に失敗します。ユニークな名前を選択してください。  
- **Spatial reference mismatch** – 保存するデータに合わせて空間参照系（例: WGS84）を必ず一致させてください。

## Conclusion
おめでとうございます！Aspose.GIS for .NET を使用して **ポイント フィーチャの追加**、**フィールド名の設定**、そして **object id の取得** 方法を習得できました。この基礎により、堅牢な GIS アプリケーションを構築し、自信を持って空間データを管理できるようになります。

## Frequently Asked Questions
### Q: Aspose.GIS for .NET を Web アプリケーションで使用できますか？
A: はい。Aspose.GIS for .NET はデスクトップ アプリケーションだけでなく Web アプリケーションにも適しており、汎用的な地理空間機能を提供します。

### Q: 購入前にトライアル版はありますか？
A: はい。無料トライアルは [here](https://releases.aspose.com/) から利用できます。

### Q: Aspose.GIS for .NET の一時ライセンスはどこで取得できますか？
A: 評価目的の一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

### Q: Aspose.GIS for .NET がサポートする空間参照系は何ですか？
A: Aspose.GIS for .NET はさまざまな空間参照系をサポートしており、異なる地理データセットに柔軟に対応できます。

### Q: Aspose.GIS に関する質問やサポートはどこで受けられますか？
A: サポートやディスカッションは Aspose.GIS フォーラム [here](https://forum.aspose.com/c/gis/33) で行えます。

## Additional Frequently Asked Questions

**Q: レイヤー作成後に Object ID フィールド名を変更できますか？**  
A: できません。フィールド名はレイヤー作成時に決定されるため、変更する場合は新しい `FileGdbOptions` オブジェクトでレイヤーを再作成する必要があります。

**Q: Object ID 以外の属性値を取得するにはどうすればよいですか？**  
A: `feature.GetValue<T>("FieldName")` を使用し、`FieldName` に取得したい属性名を指定します。

**Q: 複数のポイント フィーチャを一括で追加することは可能ですか？**  
A: 可能です。データをループで処理し、各ポイントごとにフィーチャを作成してジオメトリを設定し、同じ `using` ブロック内で `layer.Add(feature)` を呼び出します。

**Q: Aspose.GIS は他のジオメトリタイプもサポートしていますか？**  
A: はい。`LineString`、`Polygon`、`MultiPoint` など、適切なジオメトリオブジェクトを作成すれば扱えます。

**Q: 存在しない Object ID を読み取ろうとした場合はどうなりますか？**  
A: 範囲外のインデックスにアクセスすると（例: `layer[10]` でフィーチャが 1 つしかない場合）`IndexOutOfRangeException` がスローされます。必ず `layer.Count` を確認してからアクセスしてください。

---

**最終更新日:** 2026-01-02  
**テスト環境:** Aspose.GIS for .NET 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}