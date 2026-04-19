---
date: 2026-01-10
description: Aspose.GIS for .NET を使用して、C# でシェープファイルの読み取り方法とポリゴンシェープファイルをラインストリングに変換する方法を学びましょう。明確なステップバイステップのガイダンスで
  GIS 開発を強化します。
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: C#でシェープファイルを読み取る – ポリゴンシェープファイルをラインストリングに変換
url: /ja/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Shapefile を読む C# – ポリゴン Shapefile を Linestring に変換する

## はじめに
もし .NET で地理情報システム (GIS) を扱っているなら、**read shapefile c#** はデータを操作する前の一般的な最初のステップです。Aspose.GIS はこのプロセスをシンプルにし、数行のコードでポリゴン Shapefile を Linestring に変換できます。この機能は、ルートプランニング、ネットワーク解析、データ可視化など、ポリゴンデータセットから線形フィーチャを抽出する必要がある場合に特に便利です。

## クイック回答
- **どのライブラリが read shapefile c# の読み取りを支援しますか？** Aspose.GIS for .NET  
- **ポリゴンをラインに変換できますか？** はい – ポリゴンの外周リングを使用して `LineString` を使用します。  
- **本番環境でライセンスが必要ですか？** 本番環境で使用するには商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **トライアルは利用可能ですか？** もちろんです – Aspose のサイトから無料トライアルをダウンロードしてください。

## “read shapefile c#” とは何ですか？
C# で shapefile を読むことは、`.shp` ファイルをメモリにロードし、ジオメトリをクエリ、変更、変換できるようにすることを意味します。Aspose.GIS は低レベルの詳細を抽象化したシンプルな API を提供し、GIS ロジックに集中できるようにします。

## なぜ Aspose.GIS でポリゴンをラインに変換するのか？
- **トポロジーを保持** – 変換は各ポリゴンの正確な外周境界を保持します。  
- **パフォーマンス** – ライブラリは大規模データセット向けに最適化されており、バッチ変換が高速です。  
- **柔軟性** – 後で Linestring を別の shapefile、GeoJSON、またはサポートされている任意のフォーマットに書き出すことができます。  

## 前提条件
チュートリアルに入る前に、以下が準備できていることを確認してください。

- **Aspose.GIS ライブラリ** – Aspose.GIS ライブラリを [ウェブサイト](https://releases.aspose.com/gis/net/) からダウンロードしてインストールしてください。  
- **Shapefile データ** – 変換用のポリゴン Shapefile を用意してください。持っていない場合は、サンプルデータを取得するか自分で作成できます。  
- **開発環境** – 必要なツール（Visual Studio、.NET SDK など）を備えた .NET 開発環境を設定してください。  

## 名前空間のインポート
C# コードでは、必要なクラスやメソッドにアクセスするために Aspose.GIS の名前空間をインポートする必要があります。コードファイルの先頭に以下の名前空間を追加してください。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ポリゴンからラインへ shapefile を変換する方法は？
以下は、Aspose.GIS を使用してポリゴンからラインへ shapefile データを **変換する方法** を示すステップバイステップガイドです。

### ステップ 1: ドキュメントディレクトリの設定
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` を shapefile が存在する実際のパスに置き換えてください。

### ステップ 2: ソース Shapefile を開く
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
この行は **ソースのポリゴン Shapefile を開き**、そのフィーチャを読み取れるようにします。

### ステップ 3: 宛先 Linestring Shapefile を作成する
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
ここで **変換されたジオメトリを格納する新しい Linestring Shapefile を作成** します。

### ステップ 4: ソースフィーチャを反復処理する
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
このループは元のファイル内の各ポリゴンフィーチャを順に処理します。

### ステップ 5: ポリゴンを Linestring に変換し、宛先に書き込む
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
このブロックでは **ポリゴンをライン (`LineString`) に変換** し、新しいフィーチャを宛先 shapefile に追加します。

## 一般的な問題とヒント
- **座標系の不一致** – ソースと宛先のレイヤーが同じ空間参照を使用していることを確認してください。そうでないと、ラインがずれて表示される可能性があります。  
- **大きなファイル** – 非常に大きな shapefile を処理する場合、すべてを一度にメモリにロードするのではなく、フィーチャをストリーミングすることを検討してください。  
- **Null ジオメトリ** – 空のジオメトリを持つフィーチャがあるとランタイム例外が発生するため、チェックして回避してください。  

## よくある質問

**Q: Aspose.GIS はすべての .NET バージョンと互換性がありますか？**  
A: はい、Aspose.GIS はさまざまな .NET バージョンをサポートしており、開発環境との互換性が確保されています。

**Q: 商用プロジェクトで Aspose.GIS を使用できますか？**  
A: はい、使用できます。商用プロジェクトで Aspose.GIS を使用するには、ライセンスを [こちら](https://purchase.aspose.com/buy) で購入してください。

**Q: 例やドキュメントはありますか？**  
A: はい、包括的なドキュメントとサンプルは [ドキュメントページ](https://reference.aspose.com/gis/net/) にあります。

**Q: トライアル版は利用可能ですか？**  
A: はい、[このリンク](https://releases.aspose.com/) から無料トライアルで Aspose.GIS をお試しできます。

**Q: サポートやヘルプはどこで得られますか？**  
A: 支援やサポートに関する質問は [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) をご利用ください。

---

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}