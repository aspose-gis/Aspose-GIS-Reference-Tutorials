---
date: 2026-05-21
description: Aspose.GIS for .NET を使用して GeoJSON をストリームに書き込む方法を学びます。この GeoJSON チュートリアル（.NET）では、ポイントのステップバイステップ変換と
  GeoJSON C# コードの生成方法を示します。
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: GeoJSON をストリームに書き込む
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用した GeoJSON のストリームへの書き込み方法
url: /ja/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON をストリームに書き込む

## はじめに
このチュートリアルでは、Aspose.GIS を使用した .NET アプリケーションで **GeoJSON をストリームに書き込む方法** を学びます。環境設定から有効な GeoJSON ドキュメントの出力まで、各ステップを順に解説するので、ジオスペーシャル データをサービスにシームレスに統合できます。

## クイック回答
- **GeoJSON 出力の主要クラスは何ですか？** `VectorLayer` と `GeoJsonDriver` を使用します。  
- **開発にライセンスは必要ですか？** 開発には無料トライアルが使用できます。商用環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **ポイントコレクションを GeoJSON に変換できますか？** はい – `Feature` クラスを使用し、ポイントジオメトリを定義します。  
- **大規模データセットでストリーミングはサポートされていますか？** はい；`MemoryStream` を使用すれば中間ファイルなしで書き込めます。

## GeoJSON とは
GeoJSON は、JSON を使用してさまざまな地理データ構造をエンコードするためのオープン標準フォーマットです。FeatureCollection、Feature、ジオメトリタイプ（Point、LineString、Polygon）などのオブジェクトを定義します。この軽量で Web フレンドリーな表現により、複数のプラットフォームやプログラミング言語間で空間データの容易な交換と可視化が可能になります。

## GeoJSON 生成に Aspose.GIS を使用する理由
Aspose.GIS は 30 以上の空間ファイル形式をサポートし、ドキュメント全体をメモリに読み込むことなく 2 GB を超えるファイルを処理できます。高性能なストリーミングエンジンにより GeoJSON をストリームに直接書き込むことで I/O オーバーヘッドを削減します。これにより、エンタープライズ規模のジオスペーシャル ワークロード、クラウドサービス、リアルタイム アプリケーションに最適です。

## 前提条件
チュートリアルに入る前に、以下の前提条件が満たされていることを確認してください：
1. Aspose.GIS for .NET ライブラリ: Aspose.GIS for .NET ライブラリがインストールされていることを確認してください。ダウンロードは [here](https://releases.aspose.com/gis/net/) から行えます。  
2. ドキュメントディレクトリ: プロジェクト内にドキュメントディレクトリを設定し、そのパスをメモしておいてください。  

それでは、チュートリアルを始めましょう！

## GeoJSON をストリームに書き込むには？
VectorLayer は、GeoJSON を含むさまざまな形式で保存できるベクターデータセットを表します。  
GeoJsonDriver は、Aspose.GIS が GeoJSON ファイルの読み書きに使用するドライバです。  
`layer.Save` は、指定された保存オプションを使用してレイヤーの内容を提供されたストリームに書き込みます。  

`GeoJsonDriver` で `VectorLayer` をロードし、ポイントジオメトリを含むフィーチャーを追加してから、`layer.Save(stream, new GeoJsonSaveOptions())` を呼び出します。これにより、数行のコードで完全な標準準拠の GeoJSON ドキュメントが提供された `MemoryStream` に直接書き込まれます。このメソッドはフィーチャーコレクションをシリアライズし、属性データとジオメトリ変換を自動的に処理するため、手動で文字列を操作することなく、すぐに使用できる JSON ペイロードが取得できます。

## 名前空間のインポート
まず最初に、コードで Aspose.GIS の機能にアクセスするために必要な名前空間をインクルードしてください：
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 手順 1: ドキュメントディレクトリの設定
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory" を実際のドキュメントディレクトリのパスに置き換えてください。

## 手順 2: Memory Stream の作成
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## 手順 3: GeoJSON ドライバで Vector Layer を作成
`VectorLayer` クラスは、GeoJSON を含むさまざまな形式で保存できるベクターデータセットを表します。  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## 手順 4: フィーチャ属性の定義
フィーチャの属性スキーマを定義します（例: ID、Name）。  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## 手順 5: フィーチャの構築と追加
`Feature` オブジェクトを作成し、ポイントジオメトリを割り当て、属性値を設定してレイヤーに追加します。  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## 手順 6: GeoJSON 出力の表示
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

おめでとうございます！Aspose.GIS for .NET を使用して、GeoJSON をストリームに正常に書き込むことができました。

## よくある問題と解決策
- **出力ストリームが空**: 読み取る前にストリーム位置をリセット (`stream.Position = 0`) してください。  
- **座標順序が正しくない**: GeoJSON は経度‑緯度の順序を期待します。ポイントの値を確認してください。  
- **大規模データセット**: `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` を使用してフィーチャーをインクリメンタルにストリーミングしてください。

## よくある質問
### Aspose.GIS for .NET を Windows と Linux の両方の環境で使用できますか？
はい、Aspose.GIS for .NET は Windows と Linux の両方のシステムで互換性があります。  

### 無料トライアルは利用可能ですか？
もちろんです！無料トライアルは [here](https://releases.aspose.com/) からお試しいただけます。  

### 詳細なドキュメントはどこで見つけられますか？
ドキュメントは [here](https://reference.aspose.com/gis/net/) でご確認ください。  

### 一時ライセンスはどのように取得できますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) で入手可能です。  

### サポートが必要ですか、または他に質問がありますか？
サポートフォーラムは [here](https://forum.aspose.com/c/gis/33) へご訪問ください。  

**Q: 緯度/経度のポイントコレクションから GeoJSON を生成できますか？**  
A: はい – 各ポイントに対して `Feature` を作成し、`Point` ジオメトリを割り当て、`VectorLayer` に追加してください。  

**Q: Aspose.GIS は圧縮された GeoJSON（gzip）の書き込みをサポートしていますか？**  
A: 保存する前に `MemoryStream` を `GZipStream` でラップすることで、圧縮されたペイロードを生成できます。  

**Q: Aspose.GIS が扱える GeoJSON ファイルの最大サイズはどれくらいですか？**  
A: このライブラリは 2 GB を超えるファイルもストリーミングでき、データがインクリメンタルに書き込まれるためメモリ使用量は低く抑えられます。  

---

**最終更新:** 2026-05-21  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したストリームからの GeoJSON の読み取り方法](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS を使用した GeoJSON から TopoJSON への変換方法](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS for .NET を使用した Shapefile から GeoJSON への変換方法](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}