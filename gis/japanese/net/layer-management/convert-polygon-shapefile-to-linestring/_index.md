---
title: ポリゴン シェープファイルをラインストリングに変換
linktitle: ポリゴン シェープファイルをラインストリングに変換
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET の機能を活用し、ポリゴン シェープファイルをラインストリングに簡単に変換します。今すぐ GIS 開発を強化しましょう!
weight: 18
url: /ja/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ポリゴン シェープファイルをラインストリングに変換

## 導入
.NET で地理情報システム (GIS) を使用している場合、Aspose.GIS はタスクを簡素化できる強力なライブラリです。このチュートリアルでは、Aspose.GIS を使用してポリゴン シェイプファイルをラインストリングに変換するプロセスを説明します。これは、ルート計画やネットワーク解析などのさまざまなアプリケーションでポリゴン データから線形フィーチャを抽出する必要がある場合に特に役立ちます。
## 前提条件
チュートリアルに入る前に、次のものが整っていることを確認してください。
-  Aspose.GIS ライブラリ: Aspose.GIS ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/gis/net/).
- シェープファイル データ: 変換できるポリゴン シェープファイルを用意します。サンプル データがない場合は、サンプル データを見つけるか、独自のデータを作成できます。
- 開発環境: 必要なツールを使用して .NET 開発環境をセットアップします。
## 名前空間のインポート
C# コードで、必要なクラスとメソッドにアクセスするには、Aspose.GIS 名前空間をインポートする必要があります。コード ファイルの先頭に次の名前空間を追加します。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
```
「Your Document Directory」を、シェープファイルが配置されているディレクトリへのパスに置き換えます。
## ステップ 2: ソースシェープファイルを開く
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    //コードの残りの部分はここに配置されます
}
```
このステップでは、読み取り用にソースのポリゴン シェープファイルを開きます。
## ステップ 3: 宛先ラインストリング シェープファイルを作成する
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    //コードの残りの部分はここに配置されます
}
```
ここでは、変換されたデータを書き込むための新しい Linestring Shapefile を作成します。
## ステップ 4: ソース機能を反復処理する
```csharp
foreach (Feature sourceFeature in source)
{
    //コードの残りの部分はここに配置されます
}
```
このループは、ソース ポリゴン シェープファイル内の各フィーチャを反復処理します。
## ステップ 5: ポリゴンをラインストリングに変換し、宛先に書き込む
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
このステップでは、各ポリゴン フィーチャがラインストリングに変換され、結果のラインストリング フィーチャが宛先シェープファイルに書き込まれます。
## 結論
これらの手順に従うと、Aspose.GIS for .NET を使用してポリゴン シェープファイルをラインストリングに簡単に変換できます。このプロセスにより、GIS アプリケーションにおけるデータ分析と視覚化の新たな可能性が開かれます。

## よくある質問
### Aspose.GIS は .NET のすべてのバージョンと互換性がありますか?
はい、Aspose.GIS はさまざまなバージョンの .NET をサポートしており、開発環境との互換性を確保しています。
### Aspose.GIS を商用プロジェクトに使用できますか?
はい、できます。 Aspose.GIS を商用プロジェクトで使用するには、ライセンスの購入を検討してください。[ここ](https://purchase.aspose.com/buy).
### 利用可能な例やドキュメントはありますか?
はい、包括的なドキュメントと例は、[ドキュメントページ](https://reference.aspose.com/gis/net/).
### 試用版はありますか?
はい、次のサイトにアクセスすると、無料トライアルで Aspose.GIS を探索できます。[このリンク](https://releases.aspose.com/).
### どこに助けやサポートを求めればよいですか?
訪問[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)サポートまたはサポート関連の質問については、
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
