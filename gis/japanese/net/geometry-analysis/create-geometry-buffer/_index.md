---
title: ジオメトリバッファの作成
linktitle: ジオメトリバッファの作成
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して地理空間プログラミングの力を解き放ちます。空間分析、データの視覚化などを簡単に実行します。
type: docs
weight: 22
url: /ja/net/geometry-analysis/create-geometry-buffer/
---
## 導入
地理空間プログラミングの分野では、Aspose.GIS for .NET は強力なツールとして際立っています。堅牢な機能と直感的なインターフェイスにより、開発者は地理データを効率的に処理し、空間分析を実行し、見事なビジュアライゼーションを作成できます。この包括的なチュートリアルでは、Aspose.GIS for .NET の重要な側面を掘り下げ、主要な機能を分析し、初心者と経験豊富な開発者に同様に段階的なガイダンスを提供します。
## 前提条件
Aspose.GIS for .NET の使用を開始する前に、必要な前提条件が整っていることを確認することが重要です。
### Aspose.GIS for .NET のインストール
1.  Aspose.GIS for .NET ライブラリをダウンロードします。[ダウンロードリンク](https://releases.aspose.com/gis/net/)最新バージョンの Aspose.GIS for .NET ライブラリを入手します。
2. Visual Studio との統合: ダウンロードしたら、プロジェクトに参照としてライブラリを追加して、ライブラリを Visual Studio 環境に統合します。
3. ライセンスの取得: から有効なライセンスを取得します。[安置する](https://purchase.aspose.com/buy)Aspose.GIS for .NET ライブラリの可能性を最大限に引き出します。あるいは、[仮免許](https://purchase.aspose.com/temporary-license/)テスト目的のため。

## 名前空間のインポート
Aspose.GIS for .NET の機能の利用を開始するには、必要な名前空間をプロジェクトにインポートすることが重要です。これにより、地理空間操作に不可欠なクラスとメソッドにアクセスできるようになります。
## ステップ 1: Aspose.GIS 名前空間のインポート
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ここで、提供された例を複数のステップに分けて、途中の各ステップを説明してみましょう。
## ステップ 1: ジオメトリ バッファを作成する
```csharp
//LineString ジオメトリを定義する
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(3, 3);
```
このステップでは、LineString ジオメトリ オブジェクトを作成し、2 つの点を追加して (0,0) から (3,3) までのラインを定義します。
## ステップ 2: LineString のバッファを生成する
```csharp
//正の距離を持つ LineString のバッファを生成します
var lineBuffer = line.GetBuffer(distance: 1);
```
ここでは、入力ジオメトリから指定された距離内のすべての点を含む、指定された正の距離を持つ LineString の周囲にバッファーを作成します。
## ステップ 3: 空間的包含を確認する
```csharp
//バッファ内のポイントの空間的包含をチェックする
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(1, 2)));     //真実
Console.WriteLine(lineBuffer.SpatiallyContains(new Point(3.1, 3.1))); //真実
```
生成されたバッファー内に特定の点が存在するかどうかをチェックして、空間的包含をテストし、包含を示すブール値を返します。
## ステップ 4: ポリゴン ジオメトリを定義する
```csharp
//ポリゴン ジオメトリを定義する
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
});
```
ここでは、一連の点で定義された外部リングを持つポリゴン ジオメトリ オブジェクトを作成します。
## ステップ 5: ポリゴンのバッファを生成する
```csharp
//負の距離を持つポリゴンのバッファを生成します
var polygonBuffer = (IPolygon)polygon.GetBuffer(distance: -1);
```
指定された負の距離でポリゴンの周囲にバッファを作成し、ジオメトリを内側に「縮小」させます。
## ステップ 6: バッファ外部リング ポイントにアクセスする
```csharp
//バッファポリゴンの外部リングのアクセスポイント
var ring = polygonBuffer.ExteriorRing;
for (int i = 0; i < ring.Count; ++i)
{
    Console.WriteLine("[{0}] = ({1} {2})", i, ring[i].X, ring[i].Y);
}
```
最後に、バッファリングされたポリゴンの外部リングを構成するポイントを取得して反復処理し、その座標を表示します。

## 結論
結論として、Aspose.GIS for .NET は開発者に地理空間プログラミングのための包括的なツールキットを提供し、地理データの操作、分析、視覚化を簡単に可能にします。このチュートリアルに従うことで、重要な機能についての洞察が得られ、Aspose.GIS for .NET をプロジェクトに効果的に統合して利用する方法を学びました。
## よくある質問
### Aspose.GIS for .NET は他の .NET フレームワークと互換性がありますか?
はい、Aspose.GIS for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Aspose.GIS for .NET を使用して空間分析を実行できますか?
絶対に！ Aspose.GIS for .NET は、バッファリング、交差、距離計算などの空間分析のための堅牢な機能を提供します。
### 処理できる地理データセットのサイズに制限はありますか?
Aspose.GIS for .NET は、大規模な地理データセットを効率的に処理できるように設計されており、大量のデータでもパフォーマンスを保証する最適化されたアルゴリズムを備えています。
### Aspose.GIS for .NET はさまざまな空間参照系をサポートしていますか?
はい、Aspose.GIS for .NET はさまざまな空間参照システムをサポートしているため、開発者はさまざまなソースからの地理データをシームレスに操作できます。
### Aspose.GIS for .NET のテクニカル サポートは利用できますか?
はい、次の Aspose.GIS コミュニティ フォーラムから技術サポートや支援を求めることができます。[https://forum.aspose.com/c/gis/33](https://forum.aspose.com/c/gis/33).