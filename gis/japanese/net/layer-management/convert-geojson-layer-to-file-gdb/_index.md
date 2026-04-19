---
date: 2026-01-10
description: Aspose.GIS for .NET を使用して GeoJSON を File GDB に変換する方法を学びましょう。このステップバイステップガイドでは、地理空間データの変換と
  Aspose GIS の変換について解説します。
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して GeoJSON を File GDB に変換する方法
url: /ja/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用して GeoJSON を File GDB に変換する方法

## はじめに
GIS ワークフローを強化するために **GeoJSON を File Geodatabase (File GDB) に変換** する方法をお探しなら、ここが適切な場所です。このチュートリアルでは Aspose.GIS for .NET を使った全プロセスを順に解説し、このライブラリが地理空間データ変換の最適な選択肢である理由と、GeoJSON レイヤーからファイルジオデータベースを迅速に作成する方法を示します。

## クイック回答
- **このチュートリアルの内容は？** Aspose.GIS for .NET を使用して GeoJSON レイヤーを File GDB に変換すること。  
- **対象の主要キーワードは？** *how to convert geojson*。  
- **ライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **実装にかかる時間は？** 基本的な変換で約 10‑15 分です。

## GeoJSON と File GDB とは？
GeoJSON はさまざまな地理データ構造をエンコードするための軽量テキストベース形式です。File Geodatabase (File GDB) はフォルダー単位の高性能フォーマットで、多くのデスクトップ GIS アプリケーションで使用されています。これらを相互に変換することで、プロジェクトで両方のフォーマットの長所を活用できます。

## なぜ Aspose.GIS を地理空間データ変換に使用するのか？
Aspose.GIS はフォーマット処理の複雑さを抽象化した統一 API を提供します。**geojson to file gdb** の組み込みサポートにより、以下が可能です：

- サードパーティのパーサーなしで C# で GeoJSON を読み取る。  
- プログラムからファイルジオデータベースを作成する。  
- 属性データと空間参照情報を自動的に保持する。  

## 前提条件
開始する前に、以下を確認してください：

- .NET プログラミングの実務知識があること。  
- Aspose.GIS for .NET がインストールされていること。未インストールの場合は、[here](https://releases.aspose.com/gis/net/) からダウンロードし、インストール手順に従ってください。

## 名前空間のインポート
必要な名前空間をスコープに持ち込む最初のステップです。

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

## ステップ 1: GeoJSON レイヤーの設定
変換したい属性とフィーチャーを含む一時的な GeoJSON ファイルを作成します。この例ではシンプルなポイントフィーチャーを 2 つ追加しています。

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## ステップ 2: テストデータセットのコピー
元のテストデータをそのままにしておくため、既存の File GDB データセットを複製します。これにより、変換用のクリーンな環境が確保されます。

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## ステップ 3: GeoJSON を File GDB に変換
GeoJSON レイヤーを開き、コピーした File GDB 内に新しいレイヤーを作成し、属性をコピーして各フィーチャーを転送します。これが **aspose gis conversion** プロセスの核心です。

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## 一般的な問題と解決策
- **空間参照が欠如している:** ソースの GeoJSON に CRS 定義が含まれていることを確認するか、File GDB レイヤー作成時に `SpatialReferenceSystem.Wgs84` を明示的に設定してください。  
- **属性型の不一致:** GeoJSON の属性データ型はターゲットスキーマと一致している必要があります。そうでない場合、Aspose.GIS は例外をスローします。  
- **ファイルアクセスエラー:** 宛先フォルダーに書き込み権限があること、また GDB ファイルが他のプロセスによってロックされていないことを確認してください。  

## よくある質問
### Aspose.GIS は最新の .NET フレームワークと互換性がありますか？
はい、Aspose.GIS は最新の .NET フレームワーク バージョンと互換性があります。

### Aspose.GIS で他の地理空間フォーマットも変換できますか？
もちろんです！Aspose.GIS は多種多様な地理空間フォーマットをサポートしており、柔軟なデータ操作が可能です。

### Aspose.GIS のトライアル版はありますか？
はい、[here](https://releases.aspose.com/) からトライアル版をダウンロードして Aspose.GIS の機能をお試しいただけます。

### Aspose.GIS に関する質問のサポートはどこで受けられますか？
専用サポートは Aspose.GIS の [forum](https://forum.aspose.com/c/gis/33) へお越しください。

### Aspose.GIS の一時ライセンスは取得できますか？
はい、[here](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

---

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}