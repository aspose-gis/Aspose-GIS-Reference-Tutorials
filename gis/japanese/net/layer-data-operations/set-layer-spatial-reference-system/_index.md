---
date: 2025-12-31
description: Aspose.GIS for .NET を使用してベクターレイヤーを作成し、レイヤーの空間参照系を設定する方法を学びます。空間参照の定義、ポイントフィーチャの追加、EPSG
  コードの取得をマスターしましょう。
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: ベクトルレイヤーの作成とレイヤー空間参照系の設定
url: /ja/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ベクトルレイヤーの作成とレイヤー空間参照系の設定

## はじめに
地理情報システム（GIS）の広大な領域において、**Aspose.GIS for .NET** は開発者向けの堅牢で多用途なツールとして際立っています。このチュートリアルでは **ベクトルレイヤーを作成** し、空間参照を定義し、ポイントフィーチャーを追加し、EPSG コードを取得する方法を、明確なステップバイステップで解説します。経験豊富な GIS エンジニアでも、これから始める方でも、シェープファイルの座標系を正しく設定し、空間データワークフローの信頼性を向上させるテクニックを学べます。

## クイック回答
- **「ベクトルレイヤーを作成」とは何ですか？** 新しい GIS レイヤー（例: Shapefile）を作成し、ポイント、ライン、ポリゴンなどのジオメトリを格納できるようにします。  
- **例で使用されている EPSG コードはどれですか？** EPSG 26918（NAD83 / UTM zone 18N）。  
- **レイヤー作成後にポイントフィーチャーを追加できますか？** はい—`ConstructFeature()` を使用し、`Point` ジオメトリを割り当てます。  
- **レイヤーの CRS を取得するには？** `layer.SpatialReferenceSystem.EpsgCode` または `.Name` を読み取ります。  
- **Aspose.GIS のライセンスは必要ですか？** 無料トライアルは利用可能ですが、本番環境で使用する場合はライセンスが必要です。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください：
- .NET プログラミングの基本的な知識。  
- システムに Visual Studio がインストールされていること。  
- Aspose.GIS for .NET ライブラリ（[こちらからダウンロード](https://releases.aspose.com/gis/net/)）。  
- GIS における空間参照系の基本的な理解。

## 名前空間のインポート
.NET プロジェクトで、Aspose.GIS が提供する機能にアクセスするために必要な名前空間をインポートします。以下のコードスニペットを使用してください：

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## 手順 1: ドキュメントディレクトリの指定
まず、ドキュメントディレクトリへのパスを指定します。ここが空間データファイルの保存場所となります。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: 空間参照の定義とシェープファイル座標系の設定
シェープファイルのパスを定義し、EPSG コード（この例では 26918）を使用して **空間参照を定義** します。この手順でレイヤーの **シェープファイル座標系を設定** します。

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## 手順 3: ベクトルレイヤーの作成
先ほど定義したシェープファイルパス、ドライバタイプ（Shapefile）、および空間参照系を使用して **ベクトルレイヤーを作成** します。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## 手順 4: レイヤーへのポイントフィーチャー追加
新しいフィーチャーを構築し、ジオメトリ（座標 60, 24 の `Point`）を設定して **ポイントフィーチャーを追加** します。その後、フィーチャーをベクトルレイヤーに追加します。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## 手順 5: 空間参照系情報の取得（EPSG コード取得）
ベクトルレイヤーを開き、空間参照系に関する情報（EPSG コードや人間が読める名前）を取得します。これにより **EPSG コードの取得** と **レイヤー CRS の設定** 方法が示されます。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

これらの手順をご自身のユースケースに合わせて繰り返すことで、**ベクトルレイヤーの作成** と Aspose.GIS for .NET を用いた空間参照の管理をマスターできます。

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|------|----------|------|
| **レイヤーが開けない** | ドライバが間違っている、またはファイルパスが破損している | `Drivers.Shapefile` を確認し、`path` が既存の `.shp` ファイルを指しているか確認してください。 |
| **CRS が正しく表示されない** | 誤った EPSG コードを使用している | 権威ある情報源（例: EPSG.io）で EPSG コードを再確認してください。 |
| **フィーチャーが保存されない** | `using` ブロック内で `layer.Add(feature)` を呼び出していない | レイヤーが破棄される前に `Add` メソッドが実行されていることを確認してください。 |

## FAQ
### Aspose.GIS は他の GIS ライブラリと互換性がありますか？
はい、Aspose.GIS は他の GIS ライブラリとうまく統合でき、併用が可能です。

### Aspose.GIS はデスクトップとウェブの両方のアプリケーションで使用できますか？
もちろんです！Aspose.GIS は汎用性が高く、デスクトップアプリケーションでもウェブベースのアプリケーションでも利用できます。

### Aspose.GIS のライセンスオプションはありますか？
はい、ライセンスオプションを確認し、購入は[こちら](https://purchase.aspose.com/buy)から行えます。

### Aspose.GIS の無料トライアルはありますか？
あります！無料トライアル版は[こちら](https://releases.aspose.com/)からダウンロードできます。

### Aspose.GIS に関するサポートはどこで受けられますか？
サポートや質問は[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)をご利用ください。

## 追加の FAQ
**Q: 既存のシェープファイルの CRS を変更するには？**  
A: レイヤーを開き、目的の EPSG コードで新しい `SpatialReferenceSystem` を作成し、`layer.SpatialReferenceSystem` に割り当ててから保存します。

**Q: 同じ手法で他ジオメトリタイプ（例: ポリゴン）を追加できますか？**  
A: はい、`new Point(x, y)` を `new Polygon(...)` や `new LineString(...)` に置き換えるだけです。

**Q: 大規模データセットを効率的に扱う方法は？**  
A: ストリーミング API（`VectorLayer.Create` と `FeatureCollection`）を使用し、レイヤーは速やかに破棄してリソースを解放します。

**Q: Aspose.GIS は座標変換をサポートしていますか？**  
A: はい、`Geometry.Transform(targetSrs)` を使用して異なる空間参照間でジオメトリを再投影できます。

**Q: サポートされている .NET バージョンは？**  
A: .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6/7 がサポートされています。

## 結論
本チュートリアルでは **ベクトルレイヤーの作成**、空間参照の定義、**ポイントフィーチャーの追加**、そして Aspose.GIS for .NET を使用した **EPSG コードの取得** 方法を解説しました。これらの手順を習得すれば、シェープファイルの座標系設定やレイヤー CRS の管理が自信を持って行え、信頼性の高い GIS アプリケーションを構築できます。

---

**最終更新日:** 2025-12-31  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}