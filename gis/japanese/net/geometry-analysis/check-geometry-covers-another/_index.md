---
date: 2026-08-03
description: Aspose.GIS for .NET を使用して linestring c# を作成し、linestring にポイントを追加し、covers
  メソッドを使ってライン上のポイントをチェックする方法を学びます。
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: linestring c# の作成 – ジオメトリが別のオブジェクトをカバーするか確認
og_description: Aspose.GIS の covers メソッドを使用して linestring c# を作成し、ライン上のポイントを検証します。.NET
  アプリケーション向けの正確なジオメトリチェック方法を学びます。 (150‑160 chars)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: linestring c# の作成 – ジオメトリが別のオブジェクトをカバーするか確認 (50‑60 chars)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: linestring c# の作成 – ジオメトリが別のオブジェクトをカバーするか確認
url: /ja/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ジオメトリが別のジオメトリをカバーするか確認する

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **linestring の作成方法（C#）** を学び、linestring にポイントを追加し、`Covers` および `CoveredBy` メソッドを使用した信頼性の高い **点が線上にあるかのチェック** を実行します。マッピングツールの構築、空間分析の実施、またはジオメトリ関係の検証が必要な場合でも、これらの操作を習得すれば、アプリケーションに必要な精度を提供できます。

## クイック回答
- **「create linestring c#」は何を意味しますか？** それは `LineString` ジオメトリオブジェクトをインスタンス化し、座標点で構成することを意味します。  
- **どのメソッドが点が線上にあるかをチェックしますか？** `LineString` の `Covers` メソッド、または `Point` の `CoveredBy` メソッドを使用します。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価目的であれば一時ライセンスで動作しますが、本番環境では正式なライセンスが必要です。  
- **これを .NET Core で使用できますか？** はい、Aspose.GIS は .NET Framework と .NET Core の両方をサポートしています。  
- **linestring に何点まで追加できますか？** 厳密な上限はなく、空間分析に必要なだけ多くの点を追加できます。

## create linestring c# とは何ですか？
`LineString` は、直線セグメントで接続された順序付けられた点のリストからなる幾何形状です。C# では、`Aspose.Gis.Geometries` 名前空間の `LineString` クラスをインスタンス化し、`AddPoint` メソッドを使用して **linestring に点を追加** します。このオブジェクトは、ルートマッピングやネットワークトレースなど、あらゆる線形空間分析の基礎となります。

## 点が線上にあるかチェックする際に Aspose.GIS を使用する理由は？
`Covers` は、最初のジオメトリが第二のジオメトリを完全に包含するときに true を返す空間述語メソッドです。  
Aspose.GIS は決定的で高精度な空間述語の実装を提供します。50 以上の GIS 入出力フォーマットをサポートし、データセット全体をメモリに読み込むことなく数百キロメートル規模の線ネットワークを処理できます。また、.NET Framework、.NET Core、.NET 5/6+ 上で動作します。`Covers` メソッドを使用すれば、浮動小数点の丸め誤差を考慮した信頼性の高い点‑オン‑ライン結果が得られ、エンタープライズ向けの厳しいシナリオでも対応可能です。

## 前提条件
Aspose.GIS for .NET の使用を始める前に、以下の前提条件が整っていることを確認してください。

### 1. Visual Studio のインストール
システムに Visual Studio がインストールされていることを確認してください。Aspose.GIS for .NET は Visual Studio とシームレスに統合され、スムーズな開発体験を提供します。

### 2. Aspose.GIS for .NET の取得
Aspose.GIS for .NET ライブラリを [website](https://releases.aspose.com/gis/net/) からダウンロードしてください。ライブラリを直接ダウンロードするか、NuGet などのパッケージマネージャーを使用してプロジェクトにインストールできます。

### 3. .NET Framework の知識
.NET Framework と C# プログラミング言語の基本的な知識は、Aspose.GIS for .NET を効果的に活用するために必須です。

### 4. ドキュメントとサポートへのアクセス
Aspose.GIS の API と機能に関する詳細情報は、[documentation](https://reference.aspose.com/gis/net/) を参照してください。問題が発生したり質問がある場合は、[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) を利用して支援を受けてください。

### 5. オプション: 一時ライセンス
Aspose.GIS for .NET を試す場合は、[temporary license page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得し、ライブラリの機能を評価できます。

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

それでは、提供された例を複数のステップに分解し、Aspose.GIS for .NET を使用して **あるジオメトリが別のジオメトリをカバーするかどうかを確認する** 方法を理解しましょう。

## linestring の作成方法（C#） – ステップバイステップガイド
プロジェクトをロードし、必要な名前空間をインポートしたら、以下の 5 つの簡潔な手順に従ってください。数行のコードで `LineString` オブジェクト、`Point` オブジェクト、そして線が点をカバーしているか、点が線にカバーされているかを示す 2 つのブールチェックを取得できます。

### ステップ 1: linestring オブジェクトの作成
`LineString` クラスは、2 次元平面上で直線セグメントで接続された点のシーケンスを表します。  
```csharp
var line = new LineString();
```
ここでは、新しい `LineString` オブジェクトをインスタンス化します。これは 2 次元空間で接続された線分のシーケンスを表します。

### ステップ 2: linestring に点を追加
`AddPoint` は座標ペアを `LineString` コレクションの末尾に追加し、挿入順序を保持します。  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
`AddPoint` メソッドを使用して **linestring に点を追加** します。この例では、2 つの点 (0, 0) と (1, 1) を追加し、単純な対角線分を形成します。

### ステップ 3: point オブジェクトの作成
`Point` クラスは、2 次元座標系における単一の位置をモデル化します。  
```csharp
var point = new Point(0, 0);
```
2 次元空間の単一の点を表す `Point` オブジェクトをインスタンス化します。ここでは、座標 (0, 0) の点を作成します。

### ステップ 4: 点が線上にあるかチェック – 線は点をカバーしていますか？
`Covers` は、最初のジオメトリが第二のジオメトリを完全に包含しているかを判定し、第二のジオメトリのすべての点が第一のジオメトリ内部にある場合にのみ true を返します。  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
`Covers` メソッドを使用して線が点をカバーしているか確認します。この場合、点 (0, 0) が線上に正確に位置しているため `True` が返されます。

### ステップ 5: 逆の関係を確認 – 点は線にカバーされていますか？
`CoveredBy` は `Covers` の逆で、呼び出し元ジオメトリが対象ジオメトリの内部に完全に入っている場合に true を返します。  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同様に、`CoveredBy` メソッドを使用して点が線にカバーされているか確認します。点 (0, 0) が線上にあるため、こちらも `True` を返します。

## 一般的な問題と解決策
| 問題 | 発生原因 | 対策 |
|-------|----------------|-----|
| `line.Covers(point)` が `False` を返すが、点は線上に見える | 浮動小数点精度のため、点の座標が完全に一致していません。 | `Math.Round` で座標を丸めるか、`line.Distance(point) < epsilon` のような許容誤差チェックを使用してください。 |
| `using Aspose.Gis.Geometries;` が欠如 | 名前空間がインポートされておらず、コンパイルエラーが発生します。 | インポート文が存在することを確認してください（**名前空間のインポート** セクションを参照）。 |
| 実行時のライセンス例外 | 本番環境で有効なライセンスがロードされていません。 | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` を使用して一時または正式なライセンスをロードしてください。 |

## よくある質問

**Q: 商用プロジェクトで Aspose.GIS for .NET を使用できますか？**  
A: はい、適切なライセンスを取得すれば、商用・非商用を問わず Aspose.GIS for .NET を使用できます。

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: はい、Aspose.GIS for .NET は .NET Framework と .NET Core の両方の環境と互換性があります。

**Q: Aspose.GIS for .NET はさまざまな GIS フォーマットをサポートしていますか？**  
A: はい、Shapefile、GeoJSON、KML など、多種多様な GIS フォーマットをサポートしています。

**Q: Aspose.GIS for .NET の開発に貢献できますか？**  
A: Aspose.GIS for .NET は Aspose が開発した商用ライブラリであり、外部からの貢献は受け付けていません。ただし、フィードバックや提案を通じてライブラリの改善に協力できます。

**Q: Aspose.GIS for .NET のアップデートはどのくらいの頻度でリリースされますか？**  
A: 新機能、改善、バグ修正を含むアップデートが定期的にリリースされます。最新のリリースは [website](https://releases.aspose.com/gis/net/) をご確認ください。

## 結論
上記の手順に従うことで、**linestring の作成（C#）**、**linestring への点の追加**、および `Covers` と `CoveredBy` メソッドを使用した信頼性の高い **点が線上にあるかのチェック** ができるようになりました。この機能により、ソフトウェアの空間分析機能が強化され、ルート検証、ネットワークトポロジーのチェック、近接クエリなど、より高度な GIS 操作への道が開かれます。

---

**最終更新日:** 2026-08-03  
**テスト環境:** Aspose.GIS for .NET (latest release)  
**作者:** Aspose

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用した LineString ジオメトリの作成方法を学ぶ](/gis/net/geometry-creation/create-linestring-geometry/)
- [Aspose.GIS を使用して LineString にポイントを追加し、ジオメトリを編集可能形式に変換する方法](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – ジオメトリが別のジオメトリを含むかチェック](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}