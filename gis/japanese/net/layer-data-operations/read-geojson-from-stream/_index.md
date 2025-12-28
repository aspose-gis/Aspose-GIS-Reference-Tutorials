---
date: 2025-12-28
description: Aspose.GIS for .NET を使用してストリームから GeoJSON を読み取る方法を学びましょう。この C# の GeoJSON
  読み取りガイドは、地理空間データを統合するためのステップバイステップの例を提供します。
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してストリームから GeoJSON を読み取る方法
url: /ja/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ストリームから Aspose.GIS for .NET で GeoJSON を読む方法

## はじめに
.NET アプリケーションで **geojson の読み取り方法** をお探しなら、ここが適切な場所です。このチュートリアルでは、GeoJSON 文字列を変換し、メモリストリームから GeoJSON レイヤーを開き、Aspose.GIS を使って GeoJSON のプロパティを抽出する **c# geojson の例** をステップバイステップで解説します。最後まで読めば、地理空間データをのプロジェクトに組み込める再利用可能なパターンが手に入ります。

## クイック回答
- **どのライブラリを使うべきですか？** Aspose.GIS for .NET  
- **GeoJSON をストリームから直接読むことはできますか？** はい – `VectorLayer.Open` と `AbstractPath.FromStream` を使用します。  
用にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **プロパティの抽出ですか？** はい – フィーチャー上で `GetValue<T>(columnName)` を呼び出すだけです。

## 「geojson の読み取り方法」とは？
GeoJSON の読み取りとは、地理的フィーチャ（ポイント、ライン、ポリゴン）を記述した JSON ベースのフォーマットを解析し、アプリケーション内でクエリ、編集、または描画できるオブジェクトとして利用可能にすることです。

## Aspose.GIS で **geojson レイヤーを開く** 理由
Aspose.GIS は低レベルのパース処理を抽象化し、さまざまな GIS フォーマットに対して一貫した API を提供します。ストリームから直接 **geojson レイヤーを開く** ことができ、大容量ファイルも効率的に処理でき、カスタム JSON パーサーを書かずにフィーチャ属性にアクセスできます。

## 前提条件
作業を始める前に以下を用意してください。

1. **C# の基本知識** – .NET の構文と Visual Studio IDE に慣れていること。  
2. **Aspose.GIS のインストール** – ライブラリは [here](https://releases.aspose.com/gis/net/) からダウンロードできます。  
3. **開発環境** – Visual Studio、Visual Studio Code、または JetBrains Rider があれば問題ありません。  

## 名前空間のインポート
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## 手順 1: **GeoJSON 文字列の変換** – **c# geojson の例**
まず、シンプルな `FeatureCollection` を表す JSON 文字列を作成します。これがワークフローの **convert geojson string** 部分です。

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## 手順 2: ストリームから **GeoJSON レイヤーを開く** そして **geojson プロパティを抽出**
次に、文字列を `MemoryStream` に流し込み GIS レイヤーとして開き、属性値の読み取り（**extract geojson properties** 手順）を実演します。

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **プロのコツ:** `VectorLayer.Open` は `Drivers.GeoJson` を指定すると自動的に GeoJSON 形式を検出します。ストリームの代わりにファイルパスを渡すことで直接ファイルを開くことも可能です。

## よくある問題と解決策
| 問題 | 解決策 |
|------|--------|
| **JSON 形式が無効** | GeoJSON 文字列が正しく構成されているか確認し、JSON バリデータで検証してください。 |
| **エンコーディングの問題** | ストリームが UTF-8 (`Encoding.UTF8.GetBytes`) であることを確認してください。 |
| **プロパティが見つからない** | プロパティ名が正しく綴られているか確認（例では `"name"`）。 |
| **ライセンス例外** | テスト用にトライアルライセンスを使用し、本番環境では永続ライセンスを適用してください。 |

## FAQ
### Aspose.GIS は他の GIS フォーマットにも対応していますか？
はい、Aspose.GIS は GeoJSON、Shapefile、KML、GML など多数のフォーマットをサポートしています。

### 購入前に Aspose.GIS を試すことはできますか？
はい、[here](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

### Aspose.GIS のドキュメントはどこにありますか？
ドキュメントは [here](https://reference.aspose.com/gis/net/) にあります。

### Aspose.GIS のサポートはどこで受けられますか？
Aspose フォーラムの [here](https://forum.aspose.com/c/gis/33) でサポートを受けられます。

### Aspose.GIS を使用するために一時ライセンスは必要ですか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論
本ガイドでは、Aspose.GIS for .NET を使用してメモリストリームから **geojson を読む方法** を解説し、**c# read geojson** のワークフローを示し、開いたレイヤーから **extract geojson properties** する手順を紹介しました。これらの手順を活用すれば、任意の .NET アプリケーションに地理空間データ処理をシームレスに統合できます。

---

**最終更新日:** 2025-12-28  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}