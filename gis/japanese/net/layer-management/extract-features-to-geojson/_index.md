---
date: 2026-01-13
description: Aspose.GIS for .NET を使用して shapefile を geojson に変換する方法を学びます。このガイドでは、レイヤー間で属性をコピーする方法や、C#
  で geojson ファイルを生成する方法も取り上げています。
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して Shapefile を GeoJSON に変換する方法
url: /ja/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した Shapefile の GeoJSON への変換

## はじめに
この包括的なステップバイステップチュートリアルでは、強力な Aspose.GIS ライブラリ for .NET を使用して **Shapefile を GeoJSON に変換する方法** を学びます。マッピング Web サービスの構築、モバイル GIS アプリ向けのデータ準備、または単にフォーマット間でデータをやり取りしたい場合でも、本ガイドでは具体的な手順、各ステップの重要性、そして一般的な落とし穴の回避方法を詳しく解説します。

## クイック回答
- **このチュートリアルでカバーする内容は？** Shapefile を GeoJSON ファイルに変換し、レイヤー間で属性をコピーし、C# で出力を生成します。  
- **必要なライブラリは？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 本番環境では一時ライセンスまたはフルライセンスが必要です。評価目的であれば無料トライアルで動作します。  
- **実装にかかる時間は？** 基本的な変換で約 10〜15 分です。  
- **.NET Core/.NET 6 でも実行できますか？** はい。コードはすべてのサポート対象 .NET バージョンで動作します。

## 前提条件
作業を始める前に以下を用意してください。

- Aspose.GIS for .NET: ライブラリがインストールされていることを確認してください。未インストールの場合は、[Aspose.GIS for .NET ページ](https://releases.aspose.com/gis/net/)からダウンロードできます。  
- Shapefile データ: 入力用の Shapefile を用意してください。サンプルデータが必要な場合は、[Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/)にあります。  
- .NET 環境: 提供されたコードを実行できる .NET 環境をセットアップしてください。  
- ドキュメントディレクトリ: コードスニペット内で使用するドキュメントディレクトリへのパスを定義します。

これで準備が整いました。さっそく Shapefile を GeoJSON に変換しましょう！

## 「Shapefile を GeoJSON に変換する」とは？
Shapefile を GeoJSON に変換するとは、従来の ESRI Shapefile 形式からベクターフィーチャを読み取り、モダンで Web フレンドリーな GeoJSON ドキュメントとして書き出すことです。GeoJSON は JavaScript のマッピングライブラリ（Leaflet、Mapbox GL）や各種 API で広く利用されており、GIS 開発において頻繁に行われるタスクです。

## なぜ Aspose.GIS を使うのか？
Aspose.GIS はファイルフォーマットの低レベルな詳細を抽象化し、属性テーブルのコピーを簡単に行えるだけでなく、.NET Framework、.NET Core、.NET 5/6 で共通に利用できるクリーンなオブジェクト指向 API を提供します。これにより、バイナリファイルの解析に時間を取られることなく、ビジネスロジックに集中できます。

## 名前空間のインポート
まず、コードで必要な名前空間をインクルードします。

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

これらの名前空間は Aspose.GIS の機能を使用するために必須です。

## Shapefile を GeoJSON に変換する手順
以下に、明確なステップに分割したフルワークフローを示します。各ステップには簡単な説明と、プロジェクトにコピーすべき正確なコードブロックが含まれています。

### 手順 1: 入力 Shapefile を開く
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
`VectorLayer.Open` メソッドで入力 Shapefile を開きます。これにより `Feature` オブジェクトの列挙可能コレクションが取得できます。

### 手順 2: 出力 GeoJSON を作成
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
`VectorLayer.Create` メソッドを使用し、`Drivers.GeoJson` ドライバーを指定して出力ファイルを作成します。

### 手順 3: レイヤー間で属性をコピー
```csharp
outputLayer.CopyAttributes(inputLayer);
```
この 1 行で、ソース Shapefile から新しい GeoJSON レイヤーへ属性スキーマ（フィールド名・型）をコピーします。*copy attributes between layers* が示す通りの処理です。

### 手順 4: フィーチャを処理
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Shapefile の各フィーチャを走査し、出力前に任意のカスタムロジックを適用できるようにします。

### 手順 5: 日付でフィーチャをフィルタリング
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
この例では、`dob`（生年月日）フィールドが欠損しているか、1982 年 1 月 1 日以前のレコードをスキップします。必要に応じてフィルタ条件を調整してください。

### 手順 6: 新しいフィーチャを構築 (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
ここで GeoJSON レイヤー用の新しい `Feature` を作成し、ジオメトリと属性値をコピーして出力に追加します。これは *c# generate geojson file* の核心部分です。

おめでとうございます！ **Shapefile を GeoJSON に変換** でき、属性をレイヤー間でコピーする方法も習得しました。

## よくある問題と解決策
| 問題 | 発生原因 | 対策 |
|------|----------|------|
| 出力ファイルが空です | `CopyAttributes` が出力レイヤーが閉じた後に呼び出された | `outputLayer` の `using` ブロックがすべてのフィーチャが追加されるまで開いたままになるようにしてください。 |
| 日付フィルタで全レコードが除外される | フィールド名が間違っている、または予期しない日付形式 | 属性名（`dob`）を確認し、日付が文字列として保存されている場合は `GetValue<string>` を使用してください。 |
| ライセンス例外 | 本番環境で有効な Aspose.GIS ライセンスなしで実行している | Aspose のドキュメントに記載されているように、一時ライセンスまたはフルライセンスを適用してください。 |

## FAQ
**Q: さらに詳しいドキュメントはどこで見られますか？**  
A: 詳細情報は [Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/) をご覧ください。

**Q: 一時ライセンスはどこで取得できますか？**  
A: [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: サポートはどこで受けられますか？**  
A: コミュニティサポートやディスカッションは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) で行われています。

**Q: 無料トライアルはありますか？**  
A: はい、[こちら](https://releases.aspose.com/) から無料トライアルをダウンロードできます。

**Q: Aspose.GIS for .NET の購入先は？**  
A: 製品は [こちら](https://purchase.aspose.com/buy) から購入できます。

## 結論
本チュートリアルでは、Aspose.GIS for .NET を使用して **Shapefile を GeoJSON に変換** する一連の手順を解説し、レイヤー間で属性をコピーする方法と *c# generate geojson file* の実装例を示しました。さまざまなフィルタや大規模データ、追加のジオメトリ変換を試して、ライブラリの機能を最大限に活用してください。

---

**最終更新日:** 2026-01-13  
**テスト環境:** Aspose.GIS for .NET（最新安定版）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}