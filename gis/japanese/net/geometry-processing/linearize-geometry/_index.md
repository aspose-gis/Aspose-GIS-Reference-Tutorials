---
date: 2026-04-06
description: Aspose.GIS for .NET を使用して曲線を直線に変換し、ジオメトリを線形化する方法を学び、.NET アプリケーションで高速な地理空間処理と分析を実現します。
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: ジオメトリを線形化する
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して曲線を直線に変換する
url: /ja/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した曲線から直線への変換

## はじめに
マッピング、空間分析、またはデータ交換タスクのために **曲線を直線に変換** が必要な場合、Aspose.GIS for .NET はクリーンでプログラム的な方法を提供します。このチュートリアルでは、曲線や複合形状を含む複雑なジオメトリを取得し、任意の GIS システムで機能するシンプルな線形表現に変換する、完全な実例を順に解説します。

## クイック回答
- **ジオメトリの線形化とは何ですか？** 曲線や複雑な形状を直線セグメントに変換します。  
- **なぜ Aspose.GIS を使用するのですか？** 数十種類の GIS フォーマットをサポートし、外部ツールなしでジオメトリ変換を処理します。  
- **前提条件は？** .NET Framework または .NET Core、Visual Studio、そして Aspose.GIS ライブラリ。  
- **サンプルの実行時間はどれくらいですか？** ライブラリをインストールすれば、実行は5分未満です。  
- **他のフォーマットに保存できますか？** はい—KML ドライバーを Shapefile、GeoJSON などに置き換えるだけです。

## ジオメトリの線形化とは何ですか？
ジオメトリの線形化とは、曲線や複合形状を一連の直線セグメント（「線形ジオメトリ」）に分解することです。これにより、レンダリング、分析、そして線とポイントのみを理解できるツールとの相互運用性が簡素化されます。

## なぜ曲線を直線に変換するのか？
- **パフォーマンス:** 線形ジオメトリはレンダリングやクエリが高速です。  
- **互換性:** 多くの GIS プラットフォーム（例：古いマップサービス）は線形フィーチャのみ受け付けます。  
- **単純化:** サムネイル作成やクイックプレビュー、線形入力を必要とするアルゴリズムへのデータ供給に便利です。

## 前提条件
コードに取り掛かる前に、以下が揃っていることを確認してください：

1. **Aspose.GIS for .NET** – [Aspose.GIS website](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
2. 開発マシンに **.NET Framework**（または .NET Core）がインストールされていること。  
3. サンプルの作成と実行のために **Visual Studio**（または C# 対応の任意の IDE）が必要です。

## 名前空間のインポート
Aspose.GIS の機能を使用するには、必要な名前空間をインポートします。

### ステップ 1: Aspose.GIS コア名前空間のインポート
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### ステップ 2: 対象フォーマット用ドライバーのインポート
この例では結果を KML ファイルに書き込みます:
```csharp
using Aspose.GIS.Kml;
```

## 曲線を直線に変換する方法 – ステップバイステップガイド
以下にコードの各行を詳細に解説し、**曲線を直線に変換** の方法と各ステップの重要性を説明します。

### ステップ 1: 出力パスの定義
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
`"Your Document Directory"` を、KML ファイルを保存したいフォルダーに置き換えてください。

### ステップ 2: 出力ファイル用レイヤーの作成
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*レイヤー* は地理的フィーチャのコンテナです。ここでは、線形化されたジオメトリを保持する新しい KML レイヤーを作成します。

### ステップ 3: 新しいフィーチャの構築
```csharp
var feature = layer.ConstructFeature();
```
*フィーチャ* は単一の地理オブジェクト（ポイント、ライン、ポリゴンなど）を表します。このフィーチャに線形ジオメトリを添付します。

### ステップ 4: 元の複合ジオメトリの定義
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Well‑Known Text（WKT）文字列からジオメトリを作成します。この例は `LineString`、`CompoundCurve`、`CircularString` を含み、曲線を直線に変換するデモに最適です。

### ステップ 5: ジオメトリの線形化
```csharp
var linear = geometry.ToLinearGeometry();
```
`ToLinearGeometry()` メソッドはすべての曲線を直線セグメントに変換し、元のジオメトリの *線形* バージョンを生成します。

### ステップ 6: 線形ジオメトリをフィーチャに割り当てる
```csharp
feature.Geometry = linear;
```
これでフィーチャは簡略化された線形ジオメトリを保持します。

### ステップ 7: フィーチャをレイヤーに追加
```csharp
layer.Add(feature);
```
最後に、フィーチャを KML レイヤーに追加します。`using` ブロックが終了すると、線形ジオメトリが出力ファイルに書き込まれます。

## 一般的な落とし穴とヒント
- **パス区切り文字:** クロスプラットフォームのパス構築には `Path.Combine` を使用してください。  
- **大規模ジオメトリ:** 非常に複雑な形状を線形化すると多数の頂点が生成される可能性があります。ポイント数を減らす必要がある場合は、線形化後に `Simplify()` の使用を検討してください。  
- **ドライバーの選択:** 別の出力フォーマットが必要な場合は、`Drivers.Kml` を `Drivers.Shapefile`、`Drivers.GeoJson` などに置き換え、ファイル拡張子もそれに合わせて調整してください。

## よくある質問（改訂版）

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: はい、Aspose.GIS for .NET は .NET Core で動作し、クロスプラットフォームアプリケーションの構築が可能です。

**Q: Aspose.GIS for .NET を使用して、さまざまな GIS ファイルフォーマットを扱えますか？**  
A: もちろんです！Aspose.GIS は KML、Shapefile、GeoJSON など多数のフォーマットをサポートしています。

**Q: Aspose.GIS は空間操作や分析をサポートしていますか？**  
A: はい、幅広い空間操作と分析機能を提供し、複雑な地理空間タスクに対応します。

**Q: Aspose.GIS for .NET の無料トライアルはありますか？**  
A: はい、[Aspose のウェブサイト](https://releases.aspose.com/)から無料トライアルをダウンロードできます。

**Q: Aspose.GIS のヘルプやサポートはどこで得られますか？**  
A: コミュニティや Aspose のサポートスタッフから支援を受けるには、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)をご覧ください。

**追加の Q&A**

**Q: 3D（Z）座標を含むジオメトリを線形化できますか？**  
A: `ToLinearGeometry()` は 2D と 3D の両ジオメトリで動作し、Z 値は結果の線分に保持されます。

**Q: 線形化は出力ファイルのサイズにどのように影響しますか？**  
A: 曲線を多数の短い線分に変換するとファイルサイズが増加する可能性があります。サイズが問題の場合は、線形化後に `Simplify()` を使用してください。

**Q: 線形化時にセグメントの長さを制御できますか？**  
A: デフォルトの方法は内部トレランスを使用します。カスタムのセグメンテーションが必要な場合は、`ToLinearGeometry()` を呼び出す前に曲線を手動でテッセレーションできます。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用した **曲線を直線に変換** の方法を、環境設定から線形化結果を KML ファイルに書き込むまでカバーしました。これで、マッピングアプリケーション、データ処理パイプライン、または簡略化されたジオメトリが必要なあらゆる GIS 関連プロジェクトにこのワークフローを統合できます。

---

**最終更新日:** 2026-04-06  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}