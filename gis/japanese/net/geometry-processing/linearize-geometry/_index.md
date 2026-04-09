---
date: 2026-04-09
description: Aspose.GIS for .NET を使用して曲線を直線に変換（ジオメトリの線形化）する方法を学び、.NET アプリで効率的な地理空間処理と分析を実現します。
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: ジオメトリを線形化する
second_title: Aspose.GIS .NET API
title: .NET 用 Aspose.GIS で曲線を直線に変換する方法
url: /ja/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# カーブをラインに変換 (ジオメトリの線形化) Aspose.GIS for .NET を使用して

## はじめに
マッピング、空間分析、またはデータ交換タスクのために **カーブをラインに変換** する必要がある場合、Aspose.GIS for .NET はクリーンでプログラム的な方法を提供します。このチュートリアルでは、曲線や複合形状を含む複雑なジオメトリを取得し、任意の GIS システムで動作するシンプルな線形表現に変換する完全な実例を順を追って解説します。

## クイック回答
- **「カーブをラインに変換」とは何ですか？** 曲線ジオメトリを直線セグメントに変換します。  
- **なぜ Aspose.GIS を選ぶのですか？** ライブラリは数十種類の GIS フォーマットをサポートし、外部ツールなしでジオメトリ変換を処理します。  
- **事前に何が必要ですか？** .NET Framework または .NET Core、Visual Studio（または任意の C# IDE）、そして Aspose.GIS NuGet パッケージ。  
- **サンプルの実行時間はどれくらいですか？** ライブラリをインストールすれば 5 分未満で完了します。  
- **他のフォーマットにエクスポートできますか？** もちろんです—KML ドライバを Shapefile、GeoJSON などに置き換えるだけです。

## カーブをラインに変換するとはどういう意味ですか？
カーブをラインに変換（**ジオメトリの線形化**）は、曲線や複合形状を一連の直線セグメント、すなわち「線形ジオメトリ」に分解することです。この単純化により描画が高速化され、古い GIS サービスとの互換性が向上し、空間アルゴリズムの複雑さが軽減されます。

## カーブをラインに変換する理由
- **パフォーマンス:** 線形ジオメトリは描画およびクエリがはるかに高速です。  
- **互換性:** 多くの GIS プラットフォーム（特にレガシーサービス）は線形フィーチャのみを受け付けます。  
- **単純化:** サムネイル、クイックプレビュー、または線形入力を必要とするアルゴリズムへのデータ供給に最適です。

## 前提条件
コードに入る前に、以下を用意してください。

1. **Aspose.GIS for .NET** – [Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/) からダウンロード。  
2. **.NET Framework**（または .NET Core）を開発マシンにインストール。  
3. **Visual Studio**（または任意の C# 対応 IDE）でサンプルを作成・実行。

## 名前空間のインポート
Aspose.GIS の機能を使用するには、必要な名前空間をインポートします。

### 手順 1: Core Aspose.GIS 名前空間
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### 手順 2: ターゲットフォーマット用ドライバ
この例では結果を KML ファイルに書き出します:
```csharp
using Aspose.GIS.Kml;
```

## カーブをラインに変換するステップバイステップガイド
以下はコードの各行を詳細に解説し、**カーブをラインに変換**する方法と各ステップの重要性を説明します。

### 手順 1: 出力パスの定義
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` を KML ファイルを保存したいフォルダーに置き換えてください。`Path.Combine` を使用するとクロスプラットフォームでの互換性が向上します。

### 手順 2: 出力ファイル用レイヤーの作成
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*レイヤー* は地理的フィーチャのコンテナです。ここでは線形化されたジオメトリを保持する新しい KML レイヤーを作成します。

### 手順 3: 新しいフィーチャの構築
```csharp
var feature = layer.ConstructFeature();
```
*フィーチャ* は単一の地理オブジェクト（ポイント、ライン、ポリゴンなど）を表します。このフィーチャに線形ジオメトリを割り当てます。

### 手順 4: 元の複雑ジオメトリの定義
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Well‑Known Text (WKT) 文字列からジオメトリを作成します。この例には `LineString`、`CompoundCurve`、`CircularString` が含まれており、**カーブをラインに変換**を実演するのに最適です。

### 手順 5: カーブをラインに変換
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` メソッドはすべての曲線を直線セグメントに変換し、元のジオメトリの *線形* バージョンを生成します。

### 手順 6: 線形ジオメトリをフィーチャに割り当て
```csharp
feature.Geometry = linear;
```
これでフィーチャは簡略化された線形ジオメトリを保持します。

### 手順 7: フィーチャをレイヤーに追加
```csharp
layer.Add(feature);
```
最後にフィーチャを KML レイヤーに追加します。`using` ブロックが終了すると、線形ジオメトリが出力ファイルに書き込まれます。

## よくある落とし穴とプロのコツ
- **パス区切り文字:** Windows と Linux の違いによる問題を回避するため、`Path.Combine` を使用してください。  
- **非常に大きなジオメトリ:** 複雑な形状を線形化すると数千の頂点が生成される可能性があります。線形化後に `Simplify()` を呼び出してポイント数を削減することを検討してください。  
- **ドライバ選択:** 別の出力フォーマットが必要な場合は、`Drivers.Kml` を `Drivers.Shapefile`、`Drivers.GeoJson` などに置き換え、ファイル拡張子も同様に変更します。  
- **Z 値の保持:** `ToLinearGeometry()` は 3‑D (Z) 座標を保持するため、標高データが失われません。

## よくある質問 (FAQ)

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: はい、Aspose.GIS は .NET Core でも動作し、クロスプラットフォームアプリケーションを実現します。

**Q: Aspose.GIS for .NET を使用してさまざまな GIS ファイル形式を扱えますか？**  
A: もちろんです！ライブラリは KML、Shapefile、GeoJSON など多数のフォーマットをサポートしています。

**Q: Aspose.GIS は空間操作や分析機能を提供していますか？**  
A: はい、バッファリングから空間結合まで、幅広い空間機能を提供します。

**Q: 無料トライアルはありますか？**  
A: はい、[Aspose のウェブサイト](https://releases.aspose.com/)から無料トライアルをダウンロードできます。

**Q: 問題が発生した場合、どこでサポートを受けられますか？**  
A: コミュニティとスタッフのサポートが受けられる [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)をご利用ください。

### 追加の一般的な質問

**Q: 3D (Z) 座標を含むジオメトリも線形化できますか？**  
A: はい、`ToLinearGeometry()` は 2D と 3D の両方のジオメトリで動作し、Z 値は保持されます。

**Q: 線形化はファイルサイズにどのような影響を与えますか？**  
A: 曲線を多数の短い線分に変換するとファイルサイズが増加する可能性があります。サイズが問題になる場合は、線形化後に `Simplify()` を使用してください。

**Q: カーブをラインに変換する際にセグメント長を制御できますか？**  
A: デフォルトでは内部トレランスが使用されます。カスタム分割が必要な場合は、`ToLinearGeometry()` を呼び出す前に曲線を手動でテッセレーションしてください。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して **カーブをラインに変換**（ジオメトリの線形化）する方法を、環境設定から KML ファイルへの線形化結果の書き出しまで網羅しました。これで、マッピングアプリケーションやデータ処理パイプライン、または簡略化ジオメトリを必要とするあらゆる GIS 関連プロジェクトにこのワークフローを組み込むことができます。

---

**最終更新日:** 2026-04-09  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}