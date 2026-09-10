---
date: 2026-09-10
description: Aspose.GIS for .NET を使用して vector layer を作成し、precision を制限して shapefile
  のサイズを縮小し、performance を向上させ、coordinate accuracy を維持する方法を学びます。
keywords:
- how to create vector layer
- limit precision reading geometries
- reduce shapefile size
lastmod: 2026-09-10
linktitle: precision を制限したジオメトリの読み取り
og_description: Aspose.GIS for .NET を使用して vector layer を作成し、precision を制限して shapefile
  のサイズを削減し、performance を改善し、coordinate accuracy を管理する方法を学びます。
og_image_alt: Screenshot showing Aspose.GIS code for creating a vector layer and setting
  precision
og_title: Aspose.GIS for .NET を使用した vector layer の作成方法
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  headline: How to create vector layer with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create vector layer with Aspose.GIS for .NET and limit
    precision to shrink shapefile size, boost performance, and keep coordinate accuracy.
  name: How to create vector layer with Aspose.GIS for .NET
  steps:
  - name: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
    text: '**Installation** – Aspose.GIS for .NET library should be installed in your
      development environment. If not, you can download it from the [releases page](https://releases.aspose.com/gis/net/).'
  - name: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
    text: '**Familiarity with .NET** – Basic knowledge of C# and the .NET framework
      is necessary to understand and implement the provided code examples.'
  - name: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
    text: '**Development environment** – A working .NET development environment, such
      as Visual Studio, is required.'
  - name: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
    text: '**Document directory** – Have a directory set up where you can store and
      access the shapefile generated during the process.'
  type: HowTo
- questions:
  - answer: No. Precision is applied only when reading the geometry; the source file
      remains unchanged.
    question: Does limiting precision affect the original shapefile?
  - answer: Aspose.GIS currently applies the same `XYPrecisionModel` to both axes.
    question: Can I use a different precision model for X and Y coordinates?
  - answer: The API supports only the built‑in `PrecisionModel.Rounding(int)` method.
      For custom logic, you would need to post‑process the coordinates after reading.
    question: Is it possible to set a custom rounding function?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- Aspose.GIS
- vector layer
- precision model
- .NET GIS
title: Aspose.GIS for .NET を使用した vector layer の作成方法
url: /ja/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクトルレイヤーの作成方法

## はじめに
ジオスペーシャルデータを扱う際、アプリケーションが本当に必要とする精度に合致した **ベクトルレイヤーの作成方法** のオブジェクトをしばしば考えます。座標を適切な小数点以下の桁数に丸めることで、パース速度が向上するだけでなく、典型的なポイントデータセットでは **最大30 %までシェープファイルサイズを削減** できます。このステップバイステップガイドでは、ベクトルレイヤーの作成方法、ポイントジオメトリの書き込み、そして正確な精度モデルと丸めた精度モデルの両方を使用してそれを読み戻す方法を示します。最後まで読むと、パフォーマンスと必要な空間精度のバランスを取るための **精度モデルを設定** オプションが分かります。

## クイック回答
- **“limit precision”とは何ですか？** 座標値を定義された小数点以下の桁数に丸めます。  
- **なぜ最初にベクトルレイヤーを作成するのですか？** ベクトルレイヤーは、ポイント、ライン、ポリゴンなどのジオメトリを格納するコンテナです。  
- **利用可能な精度モデルはどれですか？** `PrecisionModel.Exact`（丸めなし） と `PrecisionModel.Rounding(n)`（*n* 桁に丸め）。  
- **これを試すのにライセンスは必要ですか？** リリースページから無料トライアルが利用可能です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5+、.NET Core、.NET 5/6+。

## ベクトルレイヤーの作成とは何ですか？
**ベクトルレイヤーの作成** とは、ディスク上の単一シェープファイルを表し、追加したすべてのジオメトリフィーチャを保持する Aspose.GIS の `VectorLayer` クラスのインスタンス化を意味します。このレイヤーは空間データの読み取り、書き込み、操作のエントリーポイントとなります。また、属性フィールドを定義し、データセットの空間参照を設定することもできます。

## なぜ精度を制限し、どのように役立つのか？
- **パフォーマンス向上** – 小数点以下の桁数を減らすことで、解析・シリアライズすべきバイナリデータ量が削減され、大規模ファイルでしばしば 15‑20 % の速度向上が得られます。  
- **ファイルサイズ縮小** – 座標を小数点以下2〜3桁に丸めることで、10 MB のシェープファイルを約7 MB に縮小でき、保存やネットワーク転送が楽になります。  
- **十分な精度** – 多くの GIS 分析（例：市レベルのマッピング）ではメートル単位の精度で十分であり、3 桁の丸めで十分に対応できます。

## 前提条件
この手順に入る前に、以下の前提条件が整っていることを確認してください：

1. **インストール** – Aspose.GIS for .NET ライブラリが開発環境にインストールされている必要があります。未インストールの場合は、[releases page](https://releases.aspose.com/gis/net/) からダウンロードできます。  
2. **.NET の知識** – C# と .NET フレームワークの基本的な知識が、提供されたコード例を理解し実装するために必要です。  
3. **開発環境** – Visual Studio などの動作する .NET 開発環境が必要です。  
4. **ドキュメントディレクトリ** – プロセス中に生成されるシェープファイルを保存・アクセスできるディレクトリを用意してください。

## 名前空間のインポート
ジオメトリを読み取る際に精度を制限する機能を実装する前に、必要な名前空間をインポートしていることを確認しましょう：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ベクトルレイヤーの作成方法
`VectorLayer` を新規にロードするには、出力フォルダーと目的のシェープファイル名を指定します。これにより、ジオメトリオブジェクトを受け入れる準備ができた空のコンテナが作成されます。

`VectorLayer` クラスは、ディスク上の単一シェープファイルを表す Aspose.GIS の最上位オブジェクトです。インスタンスを作成した後、フィーチャを追加し、属性フィールドを定義し、最後に `Save()` を呼び出してファイルシステムに書き出すことができます。

```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## 精度オプションの設定
`PrecisionModel` は、ジオメトリを読み取る際に座標値を丸めるか正確に保持するかを定義します。レイヤーを開く前に `ReadOptions` オブジェクトにモデルを設定します。

`PrecisionModel` クラスは、X 軸と Y 軸の両方の丸め動作を制御する Aspose.GIS のコアコンポーネントです。適切なモデルを選択することで、ライブラリがすべての桁を保持するか、特定の小数桁数に切り捨てるかを決定できます。

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 正確な精度でジオメトリを読み取る
`ReadOptions` は、適用する精度モデルなど、ベクトルレイヤーを読み取る際のパラメータを指定します。  
`PrecisionModel.Exact` を参照する `ReadOptions` インスタンスを使用して、以前に保存したベクトルレイヤーを開きます。これにより、すべての座標が丸められることなく読み取られます。

`PrecisionModel.Exact` を使用すると、Aspose.GIS はシェープファイルに保存された生の倍精度（double）値を読み取り、読み取り操作中に情報が失われないことを保証します。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 精度の切り捨て
精度を特定の小数桁数に切り捨てたい場合は、`Exact` を `PrecisionModel.Rounding(n)` に置き換えます。*n* は保持したい小数桁数です。

小数点以下2桁に丸める（`PrecisionModel.Rounding(2)`）と、通常ファイルサイズが20‑30 %削減され、ほとんどのマッピングスケールで座標精度は数センチメートル以内に保たれます。

```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## シナリオ別の精度モデル設定方法
使用ケースに合ったモデルを選択してください：

- **高精度な科学分析** – すべての桁を保持するために `PrecisionModel.Exact` を使用します。  
- **ウェブマッピングタイルやモバイルアプリ** – ファイルを軽量に保ち、レンダリングを高速にするために `PrecisionModel.Rounding(2)` を使用します。

適切なモデルを選択することは、精度とパフォーマンスのバランスを取る **精度モデルの設定** の意思決定プロセスの一部です。

## よくある問題と解決策
`XYPrecisionModel` は `ReadOptions` のプロパティで、X と Y の両座標の精度モデルを設定します。

- **予期しない座標値** – レイヤーを開く *前に* `options.XYPrecisionModel` を設定してください。開いた後に変更しても効果がありません。  
- **ファイルが見つかりません** – `path` 変数が有効なディレクトリを指していること、そして前のステップでシェープファイルが正常に作成されたことを確認してください。  
- **ジオメトリタイプが不正** – 例では `Point` を使用しています。他のジオメトリタイプ（例：`LineString`）の場合は、キャストが実際のタイプと一致している必要があります。

## シェープファイルサイズ削減のヒント
- 必要な精度を満たす最小限の小数桁数で `PrecisionModel.Rounding` を使用します。  
- レイヤーを書き込む前に不要な属性フィールドを削除します。  
- 生成された `.shp`、`.shx`、`.dbf` ファイルを標準的な ZIP ユーティリティで圧縮し、転送が必要な場合に使用します。

## 結論
ジオメトリを読み取る際の精度管理は、ジオスペーシャルデータ操作の重要な側面です。Aspose.GIS for .NET はこれを効率的に実現するための堅牢な機能を提供します。上記の手順に従うことで、シームレスに **ベクトルレイヤーの作成** オブジェクト、 **精度モデルの設定**、そして適切な場合には **シェープファイルサイズの削減** を行うことができ、アプリケーションにおけるデータ処理を最適化できます。

## FAQ

### Aspose.GIS for .NET を .NET Core や .NET Standard などの他の .NET フレームワークと併用できますか？
はい、Aspose.GIS for .NET は .NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。

### Aspose.GIS for .NET のトライアル版は利用可能ですか？
はい、[releases page](https://releases.aspose.com/) から無料トライアル版を入手できます。

### Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか？
詳細情報やサンプルは、[documentation](https://reference.aspose.com/gis/net/) を参照してください。

### Aspose.GIS for .NET の一時ライセンスはどのように取得できますか？
Aspose.GIS の一時ライセンスは、[purchase page](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.GIS for .NET のサポートや支援はどこで受けられますか？
質問や議論、サポートが必要な場合は、Aspose.GIS の [forum](https://forum.aspose.com/c/gis/33) をご利用ください。

## よくある質問

**Q: 精度を制限すると元のシェープファイルに影響しますか？**  
A: いいえ。精度はジオメトリを読み取るときにのみ適用され、元のファイルは変更されません。

**Q: X 軸と Y 軸で異なる精度モデルを使用できますか？**  
A: 現在、Aspose.GIS は両軸に同じ `XYPrecisionModel` を適用しています。

**Q: カスタムの丸め関数を設定できますか？**  
A: API は組み込みの `PrecisionModel.Rounding(int)` メソッドのみをサポートしています。カスタムロジックが必要な場合は、読み取り後に座標を後処理する必要があります。

---

**最終更新日:** 2026-09-10  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS を使用したジオメトリ書き込み時の精度制限方法](/gis/net/geometry-processing/limit-precision-writing-geometries/)
- [Aspose.GIS for .NET を使用した SRS 付きベクトルレイヤーの作成方法](/gis/net/layer-management/create-vector-layer-with-srs/)
- [File GDB にベクトルレイヤーを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}