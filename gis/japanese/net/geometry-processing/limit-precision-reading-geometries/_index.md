---
date: 2026-04-03
description: Aspose.GIS for .NET を使用してベクトルレイヤーを作成し、ジオメトリを読み込む際に精度を制限する方法を学びましょう。最適な地理空間データ処理のためのステップバイステップガイド。
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: 精度制限ジオメトリの読み取り
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用してベクターレイヤーを作成し、精度を制限する
url: /ja/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクトルレイヤーの作成と精度の制限

## はじめに
地理空間データを扱う際、**ベクトルレイヤー**オブジェクトを作成し、座標の小数点以下何桁まで必要かを決定する必要があります。精度を制限することで、処理速度が向上するだけでなく、**シェープファイルのサイズを削減**でき、保存や転送が効率的になります。このチュートリアルでは、ベクトルレイヤーの作成、シンプルなポイントジオメトリの書き込み、そして正確な精度モデルと丸め精度モデルの両方を使用して読み戻す手順を説明します。最後まで読むと、アプリケーションの精度要件に合った**精度モデルの設定**オプションが理解できるようになります。

## クイック回答
- **「精度の制限」とは何ですか？** 座標値を定義された小数点以下の桁数に丸めます。  
- **なぜ最初にベクトルレイヤーを作成するのですか？** ベクトルレイヤーは、ポイント、ライン、ポリゴンなどのジオメトリを格納するコンテナです。  
- **利用可能な精度モデルはどれですか？** `PrecisionModel.Exact`（丸めなし）と `PrecisionModel.Rounding(n)`（*n* 桁に丸め）。  
- **これを試すのにライセンスは必要ですか？** リリースページから無料トライアルが利用可能です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.5 以降、.NET Core、.NET 5/6+。

## なぜ精度を制限し、どのように役立つのか
- **パフォーマンス向上** – 桁数が減ることで、解析およびシリアライズするデータが少なくなります。  
- **ファイルサイズ縮小** – 座標を丸めることで、特に大規模データセットの場合、シェープファイルを顕著に小さくできます。  
- **十分な精度** – 多くの GIS 分析ではサブミリメートル単位の精度は不要で、2〜3 桁に丸めれば十分なことが多いです。

## 前提条件
この手順に入る前に、以下の前提条件が整っていることを確認してください。
1. **インストール** – Aspose.GIS for .NET ライブラリが開発環境にインストールされている必要があります。未インストールの場合は、[releases page](https://releases.aspose.com/gis/net/) からダウンロードできます。
2. **.NET の知識** – C# と .NET フレームワークの基本的な知識が、提供されたコード例を理解し実装するために必要です。
3. **開発環境** – Visual Studio などの動作する .NET 開発環境が必要です。
4. **ドキュメントディレクトリ** – プロセス中に生成されるシェープファイルを保存・アクセスできるディレクトリを用意してください。

## 名前空間のインポート
ジオメトリを読み取る際に精度を制限する機能を実装する前に、必要な名前空間をインポートしていることを確認しましょう:
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
最初のステップは、ジオメトリを保持する **ベクトルレイヤー** を作成することです。このレイヤーはシェープファイルとして保存され、後で異なる精度設定で再度開くことができます。
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
次に、ジオメトリを読み取るためのオプションを定義し、希望する精度モデルを指定します。まずは正確な精度から始めます:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 正確な精度でジオメトリを読み取る
それでは、指定したオプションでベクトルレイヤーを開き、正確な精度でジオメトリを読み取ります:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 精度の切り捨て
特定の小数点以下桁数に精度を切り捨てたい場合は、精度モデルをそれに合わせて調整できます:
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
`Exact` と `Rounding` の使い分けが気になるかもしれません。以下は一般的な2つのシナリオです。

| シナリオ | 推奨モデル | 理由 |
|----------|-------------------|--------|
| 高精度の科学分析 | `PrecisionModel.Exact` | 座標の詳細が失われない |
| ウェブマッピングタイルやモバイルアプリ | `PrecisionModel.Rounding(2)` | ファイルサイズを削減し、レンダリングを高速化 |

適切なモデルを選択することは、**精度モデルの設定** における意思決定プロセスの一部であり、精度とパフォーマンスのバランスを取ります。

## よくある問題と解決策
- **予期しない座標値** – `options.XYPrecisionModel` をレイヤーを開く *前に* 設定してください。開いた後に変更しても効果がありません。  
- **ファイルが見つかりません** – `path` 変数が有効なディレクトリを指していること、そして前のステップでシェープファイルが正常に作成されたことを確認してください。  
- **ジオメトリタイプが不正** – サンプルは `Point` を使用しています。他のジオメトリタイプ（例：`LineString`）の場合は、キャストが実際のタイプと一致している必要があります。  

## シェープファイルサイズ削減のヒント
- `PrecisionModel.Rounding` を使用し、精度要件を満たす最小限の小数点以下桁数に設定します。  
- レイヤーを書き込む前に不要な属性フィールドを削除します。  
- 転送が必要な場合は、標準的な ZIP ユーティリティを使用して生成された `.shp`、`.shx`、`.dbf` ファイルを圧縮します。

## 結論
結論として、ジオメトリを読み取る際の精度管理は、地理空間データ操作において重要な要素です。Aspose.GIS for .NET はこれを効率的に実現するための強力な機能を提供します。上記の手順に従うことで、シームレスに **ベクトルレイヤー** オブジェクトを **作成** し、**精度モデルを設定**、必要に応じて **シェープファイルサイズを削減** でき、アプリケーションでの最適なデータ処理が保証されます。

## FAQ
### Aspose.GIS for .NET を .NET Core や .NET Standard などの他の .NET フレームワークで使用できますか？
はい、Aspose.GIS for .NET は .NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。

### Aspose.GIS for .NET のトライアル版はありますか？
はい、[releases page](https://releases.aspose.com/) から無料トライアル版を入手できます。

### Aspose.GIS for .NET の包括的なドキュメントはどこで見つけられますか？
詳細情報やサンプルは、[documentation](https://reference.aspose.com/gis/net/) を参照してください。

### Aspose.GIS for .NET の一時ライセンスはどのように取得できますか？
Aspose.GIS の一時ライセンスは、[purchase page](https://purchase.aspose.com/temporary-license/) から取得できます。

### Aspose.GIS for .NET のサポートや支援はどこで受けられますか？
質問やディスカッション、サポートが必要な場合は、Aspose.GIS の[forum](https://forum.aspose.com/c/gis/33) をご利用ください。

## よくある質問
**Q: 精度を制限すると元のシェープファイルに影響しますか？**  
A: いいえ。精度はジオメトリを読み取る際にのみ適用され、元のファイルは変更されません。

**Q: X と Y 座標で異なる精度モデルを使用できますか？**  
A: 現在、Aspose.GIS は両軸に同じ `XYPrecisionModel` を適用しています。

**Q: カスタムの丸め関数を設定できますか？**  
A: API は組み込みの `PrecisionModel.Rounding(int)` メソッドのみをサポートしています。カスタムロジックが必要な場合は、読み取り後に座標を後処理する必要があります。

**最終更新日:** 2026-04-03  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}