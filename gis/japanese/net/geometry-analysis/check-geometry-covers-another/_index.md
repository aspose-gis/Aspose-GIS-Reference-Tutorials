---
date: 2025-12-06
description: Aspose.GIS for .NET を使用して C# で LineString を作成し、LineString にポイントを追加し、ジオメトリが別のジオメトリをカバーしているかどうかを確認する方法を学びます。
language: ja
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: LineString の作成 C# – ジオメトリが別のジオメトリをカバーしているか確認
url: /net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Check Geometry Covers Another

## Introduction
Aspose.GIS for .NET は、.NET アプリケーション内で地理データを効率的に扱うためのツールを開発者に提供する強力なライブラリです。マッピングアプリ構築、空間データの解析、あるいはソフトウェアへの地理機能の統合など、Aspose.GIS は開発プロセスを簡素化する包括的な機能セットを提供します。本チュートリアルでは **C# で LineString を作成する方法**、ラインにポイントを追加する方法、そして `Covers` と `CoveredBy` メソッドを使用した **点がライン上にあるかのチェック** を学びます。

## Quick Answers
- **“create LineString in C#” とは何ですか？** `LineString` ジオメトリ オブジェクトをインスタンス化し、座標ポイントで構成することを指します。  
- **どのメソッドで点がライン上にあるかを確認しますか？** `LineString` の `Covers` メソッド、または `Point` の `CoveredBy` メソッドを使用します。  
- **サンプル実行にライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境ではフル ライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.GIS は .NET Framework と .NET Core の両方をサポートしています。  
- **LineString に追加できるポイント数に制限はありますか？** 明確な上限はなく、空間解析に必要なだけポイントを追加できます。

## What is **create LineString C#**?
`LineString` は、直線セグメントで結ばれた順序付けられたポイントのリストからなる幾何形状です。C# では `Aspose.Gis.Geometries` 名前空間の `LineString` クラスをインスタンス化し、`AddPoint` メソッドで **LineString にポイントを追加** します。

## Why use Aspose.GIS for a point on line check?
- **Precision** – 浮動小数点計算や空間述語を正確に処理します。  
- **Cross‑platform** – .NET Framework、.NET Core、.NET 5/6+ で動作します。  
- **Rich API** – `Covers`、`CoveredBy`、`Intersects` などの空間関係メソッドをフルセットで提供します。  

## Prerequisites
Aspose.GIS for .NET の使用を開始する前に、以下の前提条件が整っていることを確認してください。

### 1. Install Visual Studio
システムに Visual Studio がインストールされていることを確認してください。Aspose.GIS for .NET は Visual Studio とシームレスに統合され、快適な開発体験を提供します。

### 2. Obtain Aspose.GIS for .NET
Aspose.GIS for .NET ライブラリを [website](https://releases.aspose.com/gis/net/) からダウンロードします。直接ダウンロードするか、NuGet などのパッケージマネージャーを使用してプロジェクトにインストールできます。

### 3. Familiarity with .NET Framework
.NET Framework と C# の基本的な知識は、Aspose.GIS for .NET を効果的に活用するために必須です。

### 4. Access to Documentation and Support
詳細な API 情報は [documentation](https://reference.aspose.com/gis/net/) を参照してください。問題や質問がある場合は、[Aspose.GIS forum](https://forum.aspose.com/c/gis/33) でサポートを受けられます。

### 5. Optional: Temporary License
Aspose.GIS for .NET を試す場合は、[here](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得して機能を評価できます。

## Import Namespaces
Aspose.GIS for .NET をプロジェクトで使用する前に、必要な名前空間をインポートします。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、Aspose.GIS for .NET を使って **あるジオメトリが別のジオメトリをカバーするか** を確認する例を、複数のステップに分けて解説します。

## How to **create LineString C#** – Step‑by‑Step Guide

### Step 1: Create a LineString Object
```csharp
var line = new LineString();
```
ここでは、2 次元空間で連続した線分のシーケンスを表す新しい `LineString` オブジェクトをインスタンス化しています。

### Step 2: **Add Points to LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
`AddPoint` メソッドを使って **LineString にポイントを追加** します。この例では (0, 0) と (1, 1) の 2 点を追加し、単純な対角線セグメントを構成しています。

### Step 3: Create a Point Object
```csharp
var point = new Point(0, 0);
```
2 次元空間の単一点を表す `Point` オブジェクトをインスタンス化します。ここでは座標 (0, 0) の点を作成しています。

### Step 4: Perform a **point on line check** – Does the line cover the point?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
`Covers` メソッドを使用して、ラインが点をカバーしているかを確認します。この場合、点 (0, 0) がライン上に正確に位置しているため `True` が返ります。

### Step 5: Verify the reverse relationship – Is the point covered by the line?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
同様に `CoveredBy` メソッドで点がラインにカバーされているかを確認します。点 (0, 0) がライン上にあるため、こちらも `True` が返ります。

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| `line.Covers(point)` returns `False` even though the point looks on the line | 浮動小数点の精度差により、座標が完全に一致していないことがあります。 | 座標に `Math.Round` を適用するか、`line.Distance(point) < epsilon` のような許容誤差チェックを使用してください。 |
| Missing `using Aspose.Gis.Geometries;` | 名前空間がインポートされていないため、コンパイルエラーが発生します。 | **Import Namespaces** セクションのインポート文があることを確認してください。 |
| License exception at runtime | 本番環境で有効なライセンスがロードされていません。 | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` のように一時またはフル ライセンスをロードしてください。 |

## Frequently Asked Questions

**Q: Can I use Aspose.GIS for .NET in my commercial projects?**  
A: はい、適切なライセンスを取得すれば、商用・非商用を問わず Aspose.GIS for .NET を使用できます。

**Q: Is Aspose.GIS for .NET compatible with .NET Core?**  
A: はい、.NET Framework と .NET Core の両環境で動作します。

**Q: Does Aspose.GIS for .NET support various GIS formats?**  
A: はい、Shapefile、GeoJSON、KML など多数の GIS フォーマットをサポートしています。

**Q: Can I contribute to the development of Aspose.GIS for .NET?**  
A: Aspose.GIS for .NET は Aspose が開発・提供する商用ライブラリのため、外部からのコード貢献は受け付けていません。ただし、フィードバックや改善提案は受け付けています。

**Q: How often are updates released for Aspose.GIS for .NET?**  
A: 新機能、改善、バグ修正を含むアップデートが定期的にリリースされます。最新リリースは [website](https://releases.aspose.com/gis/net/) をご確認ください。

## Conclusion
まとめると、Aspose.GIS for .NET は .NET アプリケーションで地理データを扱うための強力なツールを提供します。上記の手順に従うことで、**C# で LineString を作成し**、**LineString にポイントを追加**、そして **点がライン上にあるかのチェック** を実施し、あるジオメトリが別のジオメトリをカバーしているかを判定できます。この機能はソフトウェアの空間解析機能を強化し、より高度な GIS 操作への道を開きます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose