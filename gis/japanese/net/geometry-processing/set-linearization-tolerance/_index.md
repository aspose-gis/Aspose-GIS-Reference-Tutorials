---
date: 2025-12-21
description: Aspose.GIS for .NET を使用してベクターレイヤーを作成し、線形化トレランスを設定し、レイヤーにフィーチャーを追加する方法を学びます。このステップバイステップガイドに従って
  GeoJSON ファイルをエクスポートしてください。
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してベクトルレイヤーを作成し、線形化許容誤差を設定する
url: /ja/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクトルレイヤーの作成と線形化許容値の設定

## はじめに
ベクトルレイヤー (**create vector layer**) ファイルを作成し、曲線の精度を制御し、結果を GeoJSON ドキュメントとしてエクスポートする必要がある場合、Aspose.GIS for .NET を使用すれば簡単に実現できます。このチュートリアルでは、GeoJSON オプションの設定方法、線形化許容値の設定方法、そして **add feature to layer** オブジェクトの追加方法を学びます。コードはクリーンで本番環境でも使用できる形に保たれます。

## クイック回答
- **“create vector layer” とは何ですか？** 新しい GIS ベクトルデータセット（例: GeoJSON ファイル）を作成し、ジオメトリと属性を格納できるようにします。  
- **許容値の設定方法は？** `GeoJsonOptions` の `LinearizationTolerance` プロパティを使用します。  
- **GeoJSON ファイルをエクスポートできますか？** はい、`Drivers.GeoJson` ドライバーを使用して `VectorLayer` を作成すれば可能です。  
- **ライセンスは必要ですか？** 有効な Aspose.GIS ライセンスを取得すればすべての機能が使用可能です。評価用の一時ライセンスでも動作します。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以降、.NET Core 3.1 以降、.NET 5/6/7。

## “create vector layer” とは何ですか？
ベクトルレイヤーを作成することは、ポイント、ライン、ポリゴンなどのジオメトリや属性を保持できる新しい GIS コンテナ（例: GeoJSON ファイル）を初期化することを意味します。このレイヤーは、後で構築するジオメトリや付加する属性の格納先となります。

## なぜ GeoJSON オプションを設定するのか？
GeoJSON オプション、特に **線形化許容値** を設定することで、曲線ジオメトリ（例: `CircularString`）が元の曲線にどれだけ近い精度で近似されるかを制御できます。この手順は、後で **GeoJSON ファイルをエクスポート** してウェブマップや空間解析で使用する際に重要です。

## 前提条件
開始する前に以下を用意してください：

1. **Visual Studio** がインストールされていること（最新バージョンで可）。  
2. **Aspose.GIS ライセンス**（または一時評価キー）。  
3. **Aspose.GIS for .NET** ライブラリをダウンロードし、プロジェクトに参照設定していること。  
4. **C#** の基本的な知識があること。

## 名前空間のインポート
まず、必要な名前空間をインポートして、コンパイラが GIS クラスを見つけられるようにします：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップバイステップガイド

### ステップ 1: GeoJSON オプションの設定（許容値の設定方法）
`GeoJsonOptions` オブジェクトを作成し、線形化されたジオメトリが元の曲線にどれだけ近いべきかを Aspose.GIS に指示します。

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### ステップ 2: 出力パスの定義（GeoJSON のエクスポート方法）
生成されたファイルを保存する場所を指定します。プレースホルダーは実際のフォルダーに置き換えてください。

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### ステップ 3: 設定したオプションで **Create Vector Layer**
`VectorLayer.Create` メソッドを使用して実際に **create vector layer** を作成します。`using` ブロックによりリソースの適切な解放が保証されます。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### ステップ 4: ジオメトリの構築（例: CircularString）
ここではサンプルジオメトリとして `CircularString` を構築します。任意の有効な WKT に置き換えても構いません。

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### ステップ 5: **Add Feature to Layer** と保存
最後にフィーチャーを作成し、ジオメトリを割り当ててレイヤーに追加します。これが **add feature to layer** 操作の核心です。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

`using` ブロックが終了すると、レイヤーは `path` で指定したファイルに自動的に書き込まれ、すぐに使用できる GeoJSON ファイルが生成されます。

## よくある問題とヒント
- **パスが正しくない** – ディレクトリが存在し、書き込み権限があることを確認してください。  
- **許容値が低すぎる** – `LinearizationTolerance` を極端に小さく設定すると、ファイルサイズが大幅に増加する可能性があります。精度要件に合わせて調整してください。  
- **ライセンスエラー** – ライセンス警告が表示された場合、Aspose.GIS の呼び出し前にライセンスファイルが正しくロードされているか確認してください。

## FAQ

**Q: Aspose.GIS for .NET は他の .NET フレームワークと互換性がありますか？**  
A: はい、.NET Framework、.NET Core、そして .NET 5/6/7 で動作します。

**Q: 商用プロジェクトで Aspose.GIS を使用できますか？**  
A: もちろんです。商用ライセンスを取得すれば、すべての評価制限が解除されます。

**Q: GeoJSON 以外の GIS フォーマットもサポートしていますか？**  
A: はい、Shapefile、KML、GML など多数のフォーマットに対応しています。

**Q: 試用版はありますか？**  
A: Aspose のウェブサイトから無料トライアルをダウンロードできます。

**Q: サポートはどこで受けられますか？**  
A: Aspose フォーラムまたはリソースセクションにあるサポートリンクをご利用ください。

## 結論
この手順に従うことで、**create vector layer** の作成方法、線形化許容値の設定方法、そして **add feature to layer** による **GeoJSON ファイルのエクスポート** ができるようになりました。さまざまなジオメトリタイプや属性処理を試して、.NET GIS プロジェクトで Aspose.GIS の機能を最大限に活用してください。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-21  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose