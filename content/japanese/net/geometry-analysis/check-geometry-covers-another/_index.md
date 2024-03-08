---
title: 別のジオメトリ カバーを確認してください
linktitle: 別のジオメトリ カバーを確認してください
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を利用して地理データを効率的に操作し、空間情報を分析し、マッピング機能を .NET アプリケーションに統合する方法を学びます。
type: docs
weight: 15
url: /ja/net/geometry-analysis/check-geometry-covers-another/
---
## 導入
Aspose.GIS for .NET は、.NET アプリケーション内で地理データを効率的に操作するためのツールを開発者に提供する強力なライブラリです。マッピング アプリケーションの構築、空間データの分析、ソフトウェアへの地理的フィーチャの統合のいずれの場合でも、Aspose.GIS は開発プロセスを合理化するための包括的な機能セットを提供します。
## 前提条件
Aspose.GIS for .NET の使用に入る前に、次の前提条件が設定されていることを確認してください。
### 1. Visual Studioをインストールする
システムに Visual Studio がインストールされていることを確認してください。 Aspose.GIS for .NET は Visual Studio とシームレスに統合され、スムーズな開発エクスペリエンスを提供します。
### 2. .NET 用の Aspose.GIS を入手します。
 Aspose.GIS for .NET ライブラリを次の場所からダウンロードします。[Webサイト](https://releases.aspose.com/gis/net/)。ライブラリを直接ダウンロードすることも、NuGet などのパッケージ マネージャーを使用してプロジェクトにインストールすることもできます。
### 3. .NET Framework に関する知識
Aspose.GIS for .NET を効果的に利用するには、.NET Framework と C# プログラミング言語の基本的な知識が不可欠です。
### 4. ドキュメントとサポートへのアクセス
を参照してください。[ドキュメンテーション](https://reference.aspose.com/gis/net/)Aspose.GIS API と機能の詳細については、「Aspose.GIS の API と機能」を参照してください。問題が発生した場合や質問がある場合は、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)援助のために。
### 5. オプション: 一時ライセンス
Aspose.GIS for .NET を検討している場合は、次から一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/)ライブラリの機能を評価します。

## 名前空間のインポート
プロジェクトで Aspose.GIS for .NET を使用する前に、必要な名前空間をインポートする必要があります。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

ここで、Aspose.GIS for .NET を使用して、あるジオメトリが別のジオメトリを覆っているかどうかを確認する方法を理解するために、提供された例を複数のステップに分解してみましょう。
## ステップ 1: LineString オブジェクトを作成する
```csharp
var line = new LineString();
```
ここで、新しいインスタンスを作成します。`LineString`オブジェクト。2 次元空間内の一連の接続された線分を表します。
## ステップ 2: LineString にポイントを追加する
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
にポイントを追加します。`LineString`を使用して`AddPoint`方法。この例では、(0, 0) と (1, 1) の 2 つの点を追加して、線分を形成します。
## ステップ 3: ポイント オブジェクトの作成
```csharp
var point = new Point(0, 0);
```
インスタンス化する`Point` 次元空間内の 1 つの点を表すオブジェクト。ここでは、座標 (0, 0) に点を作成します。
## ステップ 4: 線が点をカバーしているかどうかを確認する
```csharp
Console.WriteLine(line.Covers(point));    //真実
```
使用`Covers`線が点をカバーしているかどうかを確認するメソッド。この場合、返されるのは、`True`点 (0, 0) が直線上にあるからです。
## ステップ 5: 点が線で覆われているかどうかを確認する
```csharp
Console.WriteLine(point.CoveredBy(line)); //真実
```
同様に、`CoveredBy`点が線で覆われているかどうかを確認するメソッド。点(0,0)は直線上にあるので戻ります。`True`.

## 結論
結論として、Aspose.GIS for .NET は、.NET アプリケーションで地理データを操作するための強力なツールを提供します。上記の手順に従うことで、Aspose.GIS の機能を効率的に利用して、あるジオメトリが別のジオメトリを覆っているかどうかを確認し、ソフトウェアの空間解析機能を強化できます。
## よくある質問
### Aspose.GIS for .NET を商用プロジェクトで使用できますか?
はい、適切なライセンスを取得した後、商用プロジェクトと非商用プロジェクトの両方で Aspose.GIS for .NET を使用できます。
### Aspose.GIS for .NET は .NET Core と互換性がありますか?
はい、Aspose.GIS for .NET は .NET Framework 環境と .NET Core 環境の両方と互換性があります。
### Aspose.GIS for .NET はさまざまな GIS 形式をサポートしていますか?
はい、Aspose.GIS for .NET は、Shapefile、GeoJSON、KML などを含む幅広い GIS 形式をサポートしています。
### Aspose.GIS for .NET の開発に貢献できますか?
Aspose.GIS for .NET は、Aspose によって開発された独自のライブラリであるため、外部開発者からの貢献は受け入れられません。ただし、ライブラリを改善するためにフィードバックや提案を提供することはできます。
### Aspose.GIS for .NET の更新プログラムはどのくらいの頻度でリリースされますか?
 Aspose.GIS for .NET の更新は定期的にリリースされ、新機能、拡張機能、バグ修正が導入されています。チェックしてください[Webサイト](https://releases.aspose.com/gis/net/)最新のリリースについては。