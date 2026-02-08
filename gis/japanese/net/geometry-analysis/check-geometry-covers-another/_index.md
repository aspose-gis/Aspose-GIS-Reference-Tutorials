---
date: 2026-02-08
description: Aspose.GIS for .NET を使用して C# でラインストリングを作成し、ラインストリングにポイントを追加し、covers メソッドを使って点がライン上にあるかどうかをチェックする方法を学びましょう。
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString を作成する C# – ジオメトリが別のジオメトリを包含しているか確認
url: /ja/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ジオメトリが別のジオメトリをカバーするか確認

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **C# で LineString を作成** し、LineString にポイントを追加し、`Covers` および `CoveredBy` メソッドを使った信頼性の高い **点が線上にあるかのチェック** を行う方法を学びます。マッピングツールの構築、空間分析の実施、またはジオメトリ間の関係を検証する必要がある場合、これらの操作をマスターすればアプリケーションに必要な精度を提供できます。

## クイック回答
- **「create linestring c#」は何を意味しますか？** `LineString` ジオメトリオブジェクトをインスタンス化し、座標ポイントで構成することを指します。  
- **どのメソッドで点が線上にあるかをチェックしますか？** `LineString` の `Covers` メソッド、または `Point` の `CoveredBy` メソッドを使用します。  
- **サンプル実行にライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境では正式ライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.GIS は .NET Framework と .NET Core の両方をサポートしています。  
- **LineString に追加できるポイント数に上限はありますか？** ハードリミットはなく、空間分析に必要なだけポイントを追加できます。

## **create linestring c#** とは？
`LineString` は、直線セグメントで結ばれた順序付けられたポイントのリストからなる幾何形状です。C# では `Aspose.Gis.Geometries` 名前空間の `LineString` クラスをインスタンス化し、`AddPoint` メソッドで **linestring にポイントを追加** します。

## なぜ Aspose.GIS を点が線上にあるかのチェックに使うのか？
- **精度** – 浮動小数点計算と空間述語を正確に処理し、**精密な点が線上にあるか** の結果を提供します。  
- **クロスプラットフォーム** – .NET Framework、.NET Core、.NET 5/6+ で動作します。  
- **豊富な API** – `Covers`、`CoveredBy`、`Intersects` など、空間関係メソッドをフルセットで提供します。  

## 前提条件
Aspose.GIS for .NET の使用を始める前に、以下の前提条件が整っていることを確認してください。

### 1. Visual Studio のインストール
システムに Visual Studio がインストールされていることを確認してください。Aspose.GIS for .NET は Visual Studio とシームレスに統合され、快適な開発体験を提供します。

### 2. Aspose.GIS for .NET の取得
[ウェブサイト](https://releases.aspose.com/gis/net/) から Aspose.GIS for .NET ライブラリをダウンロードします。直接ダウンロードするか、NuGet などのパッケージマネージャーを使ってプロジェクトにインストールできます。

### 3. .NET Framework の基礎知識
.NET Framework と C# の基本的な知識が、Aspose.GIS for .NET を効果的に活用するために必要です。

### 4. ドキュメントとサポートへのアクセス
[Aspose.GIS API リファレンス](https://reference.aspose.com/gis/net/) を参照して、機能や使用方法の詳細を確認してください。問題が発生したり質問がある場合は、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でサポートを受けられます。

### 5. 任意: 一時ライセンス
Aspose.GIS for .NET を試す場合は、[こちら](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得して機能を評価できます。

## 名前空間のインポート
プロジェクトで Aspose.GIS for .NET を使用する前に、必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、Aspose.GIS for .NET を使って **ジオメトリが別のジオメトリをカバーするか** を確認する例を、複数のステップに分けて解説します。

## C# で linestring を作成する手順 – ステップバイステップガイド

### ステップ 1: LineString オブジェクトの作成
```csharp
var line = new LineString();
```
ここでは、2 次元空間で連続した線分のシーケンスを表す新しい `LineString` オブジェクトをインスタンス化しています。

### ステップ 2: **LineString にポイントを追加**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
`AddPoint` メソッドを使って **linestring にポイントを追加** します。この例では、(0, 0) と (1, 1) の 2 点を追加し、単純な対角線分を構成しています。

### ステップ 3: Point オブジェクトの作成
```csharp
var point = new Point(0, 0);
```
2 次元空間の単一ポイントを表す `Point` オブジェクトをインスタンス化します。ここでは座標 (0, 0) のポイントを作成しています。

### ステップ 4: **点が線上にあるかのチェック** – 線がポイントをカバーしているか？
```csharp
Console.WriteLine(line.Covers(point));    // True
```
`Covers` メソッドを使用して、線がポイントをカバーしているかを確認します。この場合、ポイント (0, 0) が線上に正確に位置しているため `True` が返ります。

### ステップ 5: 逆方向の関係を確認 – ポイントは線にカバーされているか？
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同様に `CoveredBy` メソッドを使用して、ポイントが線にカバーされているかをチェックします。ポイント (0, 0) が線上にあるため、こちらも `True` が返ります。

## よくある問題と解決策
| 問題 | 発生理由 | 解決策 |
|------|----------|--------|
| `line.Covers(point)` が `False` を返すが、ポイントは線上に見える | 浮動小数点精度の違いにより座標が完全に一致していない | 座標に `Math.Round` を適用するか、`line.Distance(point) < epsilon` のような許容誤差チェックを使用する |
| `using Aspose.Gis.Geometries;` が抜けている | 名前空間がインポートされておらず、コンパイルエラーになる | **名前空間のインポート** セクションの記述を確認し、インポート文を追加する |
| 実行時にライセンス例外が発生 | 本番環境で有効なライセンスがロードされていない | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` で一時または正式ライセンスをロードする |

## FAQ

**Q: Aspose.GIS for .NET を商用プロジェクトで使用できますか？**  
A: はい、適切なライセンスを取得すれば、商用・非商用を問わず使用できます。

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: はい、.NET Framework と .NET Core の両方で動作します。

**Q: Aspose.GIS for .NET はさまざまな GIS フォーマットをサポートしていますか？**  
A: はい、Shapefile、GeoJSON、KML など多数の GIS フォーマットに対応しています。

**Q: Aspose.GIS for .NET の開発に貢献できますか？**  
A: Aspose.GIS for .NET は Aspose が開発するプロプライエタリライブラリのため、外部からのコード貢献は受け付けていません。ただし、フィードバックや改善提案は受け付けています。

**Q: Aspose.GIS for .NET のアップデートはどのくらいの頻度で行われますか？**  
A: 新機能、改善、バグ修正を含むアップデートが定期的にリリースされます。最新リリースは [ウェブサイト](https://releases.aspose.com/gis/net/) をご確認ください。

## 結論
上記の手順に従うことで、**C# で linestring を作成**し、**linestring にポイントを追加**し、`Covers` と `CoveredBy` メソッドを使った信頼性の高い **点が線上にあるかのチェック** ができるようになりました。この機能はソフトウェアの空間分析機能を強化し、より高度な GIS 操作への道を開きます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2026-02-08  
**テスト環境:** Aspose.GIS for .NET (最新リリース)  
**作者:** Aspose