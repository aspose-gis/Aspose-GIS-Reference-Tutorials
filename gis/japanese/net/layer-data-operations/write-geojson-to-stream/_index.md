---
date: 2026-10-15
description: Aspose.GIS for .NET を使用して、座標からGeoJSONを作成し、ストリームに書き込む方法を学びます。このチュートリアルでは、ポイントの変換とGeoJSON
  C#コードの生成をステップバイステップで示します。
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: GeoJSONをストリームに書き込む
og_description: Aspose.GIS for .NET を使用して、座標からGeoJSONを作成し、ストリームに書き込む方法を学びます – 大規模データセット向けのステップバイステップガイド。
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: 座標からGeoJSONを作成し、.NETでストリームに書き込む
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: 座標からGeoJSONを作成し、.NETでストリームに書き込む
url: /ja/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 座標からGeoJSONを作成し、ストリームに書き込む

## はじめに
このチュートリアルでは、**座標からGeoJSONを作成する方法**を学び、Aspose.GIS for .NET を使用してストリームに直接書き込む方法を紹介します。環境設定、レイヤー作成、フィーチャーの設定、結果のストリーミングまで順に解説するので、一時ファイルを使用せずに API、クラウド関数、またはファイルレスサービスに地理空間ペイロードを組み込むことができます。

## クイック回答
- **GeoJSONをストリームに書き込むクラスは何ですか？** `VectorLayer` と `GeoJsonDriver` を組み合わせます。  
- **開発にライセンスは必要ですか？** 開発には無料トライアルで十分です。商用環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **ポイントコレクションをGeoJSONに変換できますか？** はい。各ポイントに対して `Feature` を作成し、`Point` ジオメトリを割り当てます。  
- **大規模データセットにストリーミングは適していますか？** はい。`MemoryStream` を使用すれば、ファイル全体をメモリに読み込まずにギガバイト規模のGeoJSONを書き込めます。

## GeoJSONとは何ですか？
GeoJSON は、ポイント、ライン、ポリゴンなどの地理的フィーチャーをエンコードするためのオープンな JSON ベースのフォーマットです。個々の `Feature` オブジェクトをまとめる `FeatureCollection` で構成され、各フィーチャーはジオメトリと属性データを保持します。軽量でウェブに適しているため、GeoJSON はブラウザ、GIS サーバー、モバイルアプリ間で空間データをやり取りする事実上の標準となっています。

## GeoJSON生成にAspose.GISを使用する理由は？
Aspose.GIS は **35 以上の空間ファイル形式** をサポートし、**2 GB** を超えるファイルでもメモリ使用量を **50 MB** 未満に抑えてストリーミングできます。高性能なストリーミングエンジンは GeoJSON を任意の .NET `Stream` に直接書き込み、途中の一時ファイルを不要にし、典型的なクラウドシナリオで I/O レイテンシを最大 **70 %** 削減します。

## 前提条件
1. **Aspose.GIS for .NET** がインストールされていること。**Aspose.GIS for .NET** パッケージは [here](https://releases.aspose.com/gis/net/) からダウンロードできます。  
2. 必要に応じて一時ファイルを配置できる、プロジェクト内の書き込み可能なフォルダーがあること。  
3. .NET 5+ または .NET Core 3.1+ ランタイムがインストールされていること。  

それでは、実装に進みましょう。

## 座標からGeoJSONを作成し、ストリームに書き込む方法は？
`VectorLayer` は、さまざまな形式で保存できるインメモリのベクターデータセットを表します。  
`GeoJsonDriver` は、GeoJSON ファイルの読み書きを可能にするドライバーです。  

`GeoJsonDriver` で `VectorLayer` をロードし、`Point` ジオメトリを含む `Feature` オブジェクトを追加し、`layer.Save(stream, new GeoJsonSaveOptions())` を呼び出します。この一度の呼び出しで、全フィーチャーコレクションが標準準拠の GeoJSON ドキュメントにシリアライズされ、指定された `MemoryStream` に格納されます。属性マッピングと座標変換は自動的に処理されるため、手動で文字列を組み立てることなく、すぐに使用できる JSON ペイロードが得られます。

### 定義アンカー
**VectorLayer** は、メモリ内で可変なベクターデータセットを表す Aspose.GIS のコアオブジェクトです。  
**GeoJsonDriver** は、GeoJSON ファイルの読み書きを担当するドライバーです。  

## 名前空間のインポート
まず最初に、コードで Aspose.GIS の機能にアクセスするために必要な名前空間をインクルードしてください。
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## ステップ 1: ドキュメントディレクトリの設定
Aspose.GIS が必要に応じて補助ファイルを保存できるフォルダー パスを作成します。  
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory" を実際のドキュメントディレクトリのパスに置き換えてください。

## ステップ 2: メモリストリームの作成
`MemoryStream` は、HTTP で直接送信したりクラウドストレージに保存したりできるインメモリ バッファを提供します。  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## ステップ 3: GeoJSON ドライバーでベクターレイヤーを作成
`VectorLayer` クラスは、GeoJSON を含むさまざまな形式で保存できるベクターデータセットを表します。  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## ステップ 4: フィーチャー属性の定義
フィーチャーの属性スキーマを定義します（例: ID、Name）。  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## ステップ 5: フィーチャーの構築と追加
`Feature` オブジェクトを作成し、ポイントジオメトリを割り当て、属性値を設定し、レイヤーに追加します。  
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

## ステップ 6: GeoJSON 出力の表示
保存後、ストリーム位置をリセットし、検証または送信のために JSON 文字列を読み取ります。  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

おめでとうございます！Aspose.GIS for .NET を使用して、座標からGeoJSONを作成し、ストリームに書き込むことに成功しました。

## 一般的な問題と解決策
- **出力ストリームが空:** 読み取る前にストリーム位置をリセット（`stream.Position = 0`）してください。  
- **座標順序が正しくない:** GeoJSON は経度‑緯度の順序を期待します。ポイントの値を確認してください。  
- **大規模データセット:** `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` を使用してフィーチャーをインクリメンタルにストリーミングし、メモリ使用量を低く抑えます。

## よくある質問

**Q: Aspose.GIS for .NET を Windows と Linux の両方の環境で使用できますか？**  
A: はい、Aspose.GIS for .NET は Windows、Linux、macOS 上でフル .NET Core サポートと共に動作します。

**Q: 無料トライアルは利用可能ですか？**  
A: もちろんです！**無料トライアルダウンロードページ** を [here](https://releases.aspose.com/) でご確認いただけます。

**Q: 詳細なドキュメントはどこで見つけられますか？**  
A: **Aspose.GIS .NET ドキュメント** を [here](https://reference.aspose.com/gis/net/) でご覧ください。

**Q: 一時ライセンスはどのように取得できますか？**  
A: **一時ライセンスページ** で取得可能です。 [here](https://purchase.aspose.com/temporary-license/)

**Q: サポートが必要、または質問がありますか？**  
A: **GIS サポートフォーラム** をご利用ください。 [here](https://forum.aspose.com/c/gis/33)

**Q: 緯度/経度ポイントのコレクションから GeoJSON を生成できますか？**  
A: はい。各ポイントに対して `Feature` を作成し、`Point` ジオメトリを割り当て、`VectorLayer` に追加します。

**Q: Aspose.GIS は圧縮された GeoJSON（gzip）を書き込むことをサポートしていますか？**  
A: 保存前に `MemoryStream` を `GZipStream` でラップすれば、圧縮ペイロードを生成できます。

**Q: Aspose.GIS が扱える GeoJSON ファイルの最大サイズはどれくらいですか？**  
A: ライブラリは 2 GB を超えるファイルもストリーミングでき、データがインクリメンタルに書き込まれるためメモリ使用量は低く抑えられます。

---

**最終更新日:** 2026-10-15  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

## 関連チュートリアル

- [Aspose.GIS for .NET を使用したストリームからの GeoJSON の読み取り方法](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Aspose.GIS を使用した GeoJSON から TopoJSON への変換方法](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Aspose.GIS for .NET を使用した Shapefile から GeoJSON への変換方法](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}