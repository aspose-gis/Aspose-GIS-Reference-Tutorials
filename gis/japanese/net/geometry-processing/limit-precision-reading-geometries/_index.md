---
date: 2025-12-20
description: Aspose.GIS for .NET を使用してベクターレイヤーを作成し、ジオメトリを読み込む際に精度を制限する方法を学びます。最適な地理空間データ処理のためのステップバイステップガイド。
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET でベクターレイヤーを作成し、精度を制限する
url: /ja/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクトルレイヤーの作成と精度の制限

## はじめに
ジオスペーシャルデータを扱う際、しばしば **create vector layer** オブジェクトを作成し、読み取り時に保持する数値の詳細度を制御する必要があります。Aspose.GIS for .NET は精度の制限を簡単に行えるようにし、超高精度が不要な場合にパフォーマンスの向上やストレージサイズの削減が可能です。このチュートリアルでは、ベクトルレイヤーの作成方法、シンプルなポイントジオメトリの書き込み、そして正確な精度と切り捨てた精度の両方で読み戻す方法を正確に示します。

## クイック回答
- **「limit precision」とは何ですか？** 座標値を定義された小数点以下の桁数に丸めます。  
- **なぜ最初に vector layer を作成するのですか？** vector layer はポイント、ライン、ポリゴンなどのジオメトリを格納するコンテナです。  
- **利用可能な precision model はどれですか？** `PrecisionModel.Exact`（丸めなし）と `PrecisionModel.Rounding(n)`（*n* 桁に丸め）。  
- **これを試すのにライセンスは必要ですか？** リリースページから無料トライアルが利用可能です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5 以上、.NET Core、.NET 5/6+。

## 前提条件
この手順に入る前に、以下の前提条件が整っていることを確認してください。

1. **Installation** – Aspose.GIS for .NET ライブラリが開発環境にインストールされている必要があります。インストールされていない場合は、[releases page](https://releases.aspose.com/gis/net/) からダウンロードできます。  
2. **Familiarity with .NET** – C# と .NET フレームワークの基本的な知識が必要です。  
3. **Development Environment** – Visual Studio などの .NET 開発環境が必要です。  
4. **Document Directory** – 処理中に生成されるシェープファイルを保存・アクセスできるディレクトリを用意してください。

## 名前空間のインポート
ジオメトリを読み取る際に精度を制限する機能を実装する前に、必要な名前空間をインポートしていることを確認しましょう。

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
最初のステップは、ジオメトリを保持する **create vector layer** を作成することです。このレイヤーはシェープファイルとして保存され、後で異なる精度設定で再度開くことができます。

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
次に、ジオメトリを読み取るためのオプションを定義し、目的の precision model を指定します。まずは正確な精度から始めます。

```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 正確な精度でジオメトリを読み取る
それでは、指定したオプションでベクトルレイヤーを開き、正確な精度でジオメトリを読み取ります。

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 精度の切り捨て
特定の小数点以下桁数に精度を切り捨てたい場合は、precision model をそれに合わせて調整できます。

```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 一般的な問題と解決策
- **Unexpected coordinate values** – レイヤーを開く *前に* `options.XYPrecisionModel` を設定してください。開いた後に変更しても効果がありません。  
- **File not found** – `path` 変数が有効なディレクトリを指しているか、前のステップでシェープファイルが正常に作成されたか確認してください。  
- **Incorrect geometry type** – この例は `Point` を使用しています。他のジオメトリタイプ（例：`LineString`）の場合は、キャストが実際のタイプと一致する必要があります。

## 結論
結論として、ジオメトリを読み取る際の精度管理はジオスペーシャルデータ操作の重要な側面です。Aspose.GIS for .NET はこれを効率的に実現するための強力な機能を提供します。このチュートリアルで示した手順に従うことで、要件に合わせて **create vector layer** オブジェクトをシームレスに作成し、精度を制限でき、アプリケーションでのデータ処理を最適化できます。

## FAQ
### Aspose.GIS for .NET を .NET Core や .NET Standard などの他の .NET フレームワークで使用できますか？
はい、Aspose.GIS for .NET は .NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。  
### Aspose.GIS for .NET のトライアル版は利用可能ですか？
はい、[releases page](https://releases.aspose.com/) から無料トライアル版を取得できます。  
### Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか？
[documentation](https://reference.aspose.com/gis/net/) を参照してください。  
### Aspose.GIS for .NET の一時ライセンスはどのように取得できますか？
[purchase page](https://purchase.aspose.com/temporary-license/) から取得できます。  
### Aspose.GIS for .NET のサポートや支援はどこで受けられますか？
質問や議論、サポートが必要な場合は Aspose.GIS の [forum](https://forum.aspose.com/c/gis/33) をご利用ください。

## よくある質問
**Q: limit precision は元の shapefile に影響しますか？**  
A: いいえ。精度はジオメトリを読み取るときにのみ適用され、元のファイルは変更されません。  

**Q: X と Y の座標で異なる precision model を使用できますか？**  
A: Aspose.GIS は現在、両方の軸に同じ `XYPrecisionModel` を適用しています。  

**Q: カスタムの丸め関数を設定できますか？**  
A: API は組み込みの `PrecisionModel.Rounding(int)` メソッドのみをサポートしています。カスタムロジックが必要な場合は、読み取り後に座標を後処理する必要があります。

---

**最終更新日:** 2025-12-20  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}