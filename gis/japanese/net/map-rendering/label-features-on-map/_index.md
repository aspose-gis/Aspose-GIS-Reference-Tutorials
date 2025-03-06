---
title: Aspose.GIS for .NET を使用したフィーチャのラベル付けのマスタリング
linktitle: 地図上の地物にラベルを付ける
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を探索し、地図上の地物ラベル付けの技術を習得してください。地理空間の視覚化を簡単に強化します。 #アスポーズ #GIS
weight: 11
url: /ja/net/map-rendering/label-features-on-map/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したフィーチャのラベル付けのマスタリング

## 導入
地理空間データの視覚化の世界では、地図上の地物にラベルを付けることは、情報を効果的に伝える上で重要な役割を果たします。 Aspose.GIS for .NET は、これをシームレスに実現するための強力なツールキットを提供します。このチュートリアルでは、Aspose.GIS を使用して地図上のポイントにラベルを付けるさまざまな方法を検討し、有益なラベルで地図の視覚化を強化します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# と .NET Framework に関する実践的な知識。
-  Aspose.GIS for .NET がインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/gis/net/).
- ポイント データを含む GeoJSON ファイル。お持ちでない場合は、テスト用のサンプル ファイルを使用できます。
## 名前空間のインポート
C# コードでは、Aspose.GIS を操作するために必要な名前空間をインポートしていることを確認してください。
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
次に、各例をステップバイステップのガイド形式で複数のステップに分けて説明します。
##  ポイントのラベル付け

### ステップ 1: ドキュメント ディレクトリへのパスを設定します。
```csharp
string dataDir = "Your Document Directory";
```
### ステップ 2: 単純なマーカー シンボルを含むマップを作成します。
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. ベクターレイヤーを追加し、ラベルを適用します
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    //4. マップを SVG ファイルにレンダリングします。
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## スタイル付きのポイントのラベリング

前の例の手順 1 と 2 に従います。

### ステップ 1: ラベルのスタイルをカスタマイズします。
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
//残りの手順は同じです
```
## 配置されたポイントのラベリング

最初の例のステップ 1 と 2 に従います。
### ステップ 2: ラベルの配置をカスタマイズします。
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
//残りの手順は同じです
```
## フィーチャベースのポイントラベリング

最初の例のステップ 1 と 2 に従います。

### ステップ 1: 機能ベースのラベル付けを実装します。
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        //フィーチャから人口を取得します。
        var population = feature.GetValue<int>("population");
        //フォント サイズは人口に基づいて計算されます。
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        //ラベルの優先順位も人口に基づきます。
        //優先順位が大きいほど、出力イメージにラベルが表示される可能性が高くなります。
        labeling.Priority = population;
    }
};
//残りの手順は同じです
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用してフィーチャにラベルを付けることで、マップの視覚化を強化する方法を学習しました。さまざまなスタイルや配置を試して、データに合わせた魅力的なマップを作成してください。
## よくある質問
### カスタム フォントを使用して地物にラベルを付けることはできますか?
はい、ラベル設定でフォントのスタイルとサイズをカスタマイズできます。
### Aspose.GIS は他の GIS データ形式と互換性がありますか?
Aspose.GIS は、GeoJSON、Shapefile などを含むさまざまな地理空間形式をサポートしています。
### ラベル付けのために大規模なデータセットを処理するにはどうすればよいですか?
Aspose.GIS はパフォーマンスを考慮して最適化されていますが、データ属性に基づいてラベルに優先順位を付けるには、フィーチャベースの構成を使用することを検討してください。
### 利用可能な高度なラベル配置オプションはありますか?
はい、回転、アンカー ポイント、オフセットなどのオプションを使用してラベルの配置を微調整できます。
### バッチプロセスでラベル生成を自動化できますか?
もちろん、Aspose.GIS をバッチ ラベル生成の自動ワークフローに統合できます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
