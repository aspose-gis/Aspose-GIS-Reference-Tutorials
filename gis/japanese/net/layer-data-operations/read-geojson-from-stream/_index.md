---
date: 2026-04-24
description: Aspose.GIS for .NET を使用してストリームから **geojson の読み取り方法** を学びます。このステップバイステップガイドでは、**geojson
  ストリームの読み込み** 方法、解析、そして C# でプロパティを抽出する方法を示します。
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: ストリームからGeoJSONを読み込む
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してストリームから GeoJSON を読み取る方法
url: /ja/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ストリームからGeoJSONを読む方法（Aspose.GIS for .NET）

## はじめに
もし .NET アプリケーションで **geojson の読み取り方法** を知りたいなら、ここが正しい場所です。このチュートリアルでは、**C# GeoJSON の例** を通じて、GeoJSON 文字列を変換し、**geojson ストリームを** メモリストリームにロードし、GeoJSON レイヤーを開き、Aspose.GIS を使用して GeoJSON プロパティを抽出する方法を示します。最後まで読むと、地理空間データを扱う必要がある任意のプロジェクトに組み込める再利用可能なパターンが手に入ります。

## クイック回答
- **どのライブラリを使用すべきですか？** Aspose.GIS for .NET – すぐに多くの GIS フォーマットを処理します。  
- **ストリームから直接 GeoJSON を読み取れますか？** はい – `VectorLayer.Open` と `AbstractPath.FromStream` を使用します。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、製品版にはフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **プロパティの抽出は簡単ですか？** はい – フィーチャーで `GetValue<T>(columnName)` を呼び出すだけです。

## “how to read geojson” とは何ですか？
GeoJSON を読むことは、地理的なフィーチャー（ポイント、ライン、ポリゴン）を記述する JSON ベースのフォーマットを解析し、それらのフィーチャーをアプリケーション内でクエリ、編集、または描画できるオブジェクトに変換することを意味します。

## Aspose.GIS を使用して **geojson レイヤーを開く** 理由は？
Aspose.GIS は低レベルのパース詳細を抽象化し、多くの GIS フォーマットに対して一貫した API を提供します。ストリームから直接 **geojson レイヤーを開く** ことができ、大きなファイルも効率的に処理でき、カスタム JSON パーサーを書かずにフィーチャー属性にアクセスできます。

## いつ **geojson ストリームをロード** しますか？
- レスポンスボディで GeoJSON を返す Web サービスからデータをインポートする場合。  
- ユーザーがアップロードした GeoJSON ファイルを、まずディスクに書き込まずに処理する場合。  
- オンザフライで生成されたインメモリデータ（例: データベースや別の API から）を扱う場合。  

## 前提条件
1. **C# の基本知識** – .NET の構文と Visual Studio IDE に慣れていることが必要です。  
2. **Aspose.GIS がインストール済み** – ライブラリは [here](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
3. **開発環境** – Visual Studio、Visual Studio Code、または JetBrains Rider が使用できます。  

## 名前空間のインポート
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## ステップ 1: **GeoJSON 文字列の変換** – **C# GeoJSON の例**
まず、シンプルな `FeatureCollection` を表す JSON 文字列を作成します。これがワークフローの **convert geojson string** 部分です。

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## ステップ 2: **GeoJSON ストリームのロード** と **geojson プロパティの抽出**
次に、文字列を `MemoryStream` に渡し、GIS レイヤーとして開き、属性値の読み取り方法を示します（**extract geojson properties** のステップ）。

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **プロのコツ:** `VectorLayer.Open` は `Drivers.GeoJson` を渡すと自動的に GeoJSON フォーマットを検出します。ストリームの代わりにファイルパスを指定すれば、ファイルを直接開くこともできます。

## よくある問題と解決策
| Issue | Solution |
|-------|----------|
| **JSON フォーマットが無効** | GeoJSON 文字列が正しく形成されているか確認し、JSON バリデータを使用してください。 |
| **エンコーディングの問題** | ストリームが UTF-8 (`Encoding.UTF8.GetBytes`) を使用していることを確認してください。 |
| **プロパティが欠落** | プロパティ名が正しく綴られているか確認してください（例では `"name"`）。 |
| **ライセンス例外** | テストにはトライアルライセンスを使用し、製品版には永続ライセンスを適用してください。 |

## よくある質問
### Aspose.GIS は他の GIS フォーマットと互換性がありますか？
はい、Aspose.GIS は GeoJSON、Shapefile、KML、GML など多数のフォーマットをサポートしています。

### 購入前に Aspose.GIS を試せますか？
はい、[here](https://releases.aspose.com/) から Aspose.GIS の無料トライアルをダウンロードできます。

### Aspose.GIS のドキュメントはどこで見つけられますか？
Aspose.GIS のドキュメントは [here](https://reference.aspose.com/gis/net/) にあります。

### Aspose.GIS のサポートはどこで受けられますか？
Aspose.GIS のサポートは Aspose フォーラムの [here](https://forum.aspose.com/c/gis/33) で受けられます。

### Aspose.GIS を使用するのに一時ライセンスは必要ですか？
Aspose.GIS の一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得できます。

## 結論
このガイドでは、Aspose.GIS for .NET を使用してメモリストリームから **geojson の読み取り方法** を解説し、**C# での geojson 読み取り** ワークフローを示し、開いたレイヤーから **geojson プロパティの抽出** 方法を紹介しました。これらの手順により、任意の .NET アプリケーションに地理空間データ処理をシームレスに統合できます。

---

**最終更新日:** 2026-04-24  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}