---
date: 2026-02-13
description: Aspose.GIS for .NET を使用して座標を DMS に変換する方法を学びましょう。このステップバイステップの C# ガイドでは、C#
  で緯度・経度や十進度数を DMS に変換する方法などを紹介します。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して座標を DMS に変換する方法
url: /ja/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した座標の DMS 変換方法

## Introduction
このチュートリアルでは、.NET 用の強力な Aspose.GIS ライブラリを使用して **座標を DMS（度・分・秒）に変換する方法** を学びます。**c# convert lat long** が必要な場合や、人が読みやすい位置文字列を生成したい場合、あるいはさまざまな座標形式を試したい場合でも、本ガイドは明確な説明とすぐに実行できる C# コードでステップバイステップで案内します。

## Quick Answers
- **「座標を DMS に変換する」とは何ですか？** 数値の緯度/経度を従来の度・分・秒表記に変換することです。  
- **どのライブラリが変換を担当しますか？** Aspose.GIS for .NET が `GeoConvert` クラスと組み込みのフォーマットサポートを提供します。  
- **試用にライセンスは必要ですか？** 無料トライアルがあります。商用利用には商用ライセンスが必要です。  
- **対応している .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、および .NET 5/6+ をサポートしています。  
- **他の形式にも同じコードを使えますか？** はい—`PointFormats` 列挙体の値を変更するだけで（例：`DecimalDegrees`、`GeoRef`）利用できます。  

## How to Convert Coordinates to DMS
コードに入る前に、なぜ DMS が依然として価値があるのかを整理しましょう。測量士、パイロット、そして多くの GIS データ提供者は、DMS が人間にとって分かりやすく、従来の地図と整合性があるために使用しています。Aspose.GIS を使えば手動で計算する必要がなくなり、アプリケーションロジックに集中できます。

## What is coordinate conversion to DMS?
座標を DMS に変換すると、10進数の緯度・経度を `25°30'00"N 45°30'00"E` のような形式に書き換えます。この表記は測量、航海、GIS データ交換で広く利用されています。

## Why use Aspose.GIS for coordinate conversion?
- **All‑in‑one API** – 外部ライブラリや複雑な計算は不要で、Aspose.GIS が内部でパースとフォーマットを処理します。  
- **High accuracy** – 負の値や半球記号などのエッジケースも正確に処理します。  
- **Cross‑platform** – Windows、Linux、macOS の .NET ランタイムで同じように動作します。  
- **Extensible** – DMS、十進度、度・小数分、GeoRef 形式などに簡単に切り替えられます。

## Prerequisites
開始する前に以下を確認してください。

1. **Basic knowledge of C#** – 変数、メソッド呼び出し、コンソール出力に慣れていること。  
2. **Aspose.GIS installed** – 最新パッケージを [Aspose.GIS website](https://releases.aspose.com/gis/net/) からダウンロードしてください。  

## Import Namespaces
GIS 操作に必要な名前空間をインポートします。

```csharp
using System;
using Aspose.Gis;
```

## Step‑by‑step guide

### Step 1: Start the conversion process
デモが開始したことを示すメッセージを出力します。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Step 2: Convert to Decimal Degrees  
最終目標は DMS ですが、まず元の十進表記を表示します。これにより後で実行する **decimal degrees to dms** の流れが分かります。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Step 3: Convert to Degree Decimal Minutes  
この形式（`DD°MM.m'`）は、*convert lat long degree minutes* が必要なときの一般的な中間ステップです。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Step 4: Convert to Degree Minutes Seconds (DMS)  
本チュートリアルの核心です—**convert coordinates to DMS**。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Step 5: Convert to GeoRef  
補足として、リモートセンシングのワークフローで役立つ `GeoRef` 形式も示します。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Common Issues and Solutions
- **Incorrect hemisphere letters** – 北/東は正の値、南/西は負の値を渡すようにしてください。API が自動で正しいサフィックスを付加します。  
- **Unexpected blank output** – `Aspose.Gis` アセンブリが正しく参照されているか、プロジェクトがサポート対象の .NET バージョンをターゲットにしているか確認してください。  
- **License not found** – ライセンスファイルをアプリケーションのルートに配置するか、`License license = new License(); license.SetLicense("Aspose.GIS.lic");` でプログラムから設定してください。

## Frequently Asked Questions

**Q: Is Aspose.GIS compatible with other programming languages?**  
A: Aspose.GIS は主に .NET 開発者向けですが、Java バージョンも提供されています。

**Q: Can I try Aspose.GIS before purchasing?**  
A: はい、[website](https://releases.aspose.com/) から無料トライアルにアクセスできます。

**Q: How can I get support for Aspose.GIS?**  
A: Aspose.GIS コミュニティフォーラムは [here](https://forum.aspose.com/c/gis/33) で利用できます。

**Q: Are temporary licenses available for Aspose.GIS?**  
A: はい、[temporary license page](https://purchase.aspose.com/temporary-license/) から取得可能です。

**Q: Where can I purchase Aspose.GIS?**  
A: [purchase page](https://purchase.aspose.com/buy) で購入できます。

## Conclusion
これらの手順に従うことで、Aspose.GIS for .NET を使って **座標を DMS** や他の一般的な GIS 形式に変換する方法が習得できました。この機能を利用すれば、マッピングアプリケーション、レポート、または任意の空間データワークフローに人が読みやすい位置文字列をシームレスに組み込めます。さまざまな緯度/経度の値で実験し、`GeoConvert` クラスが提供する他の形式もぜひ試してみてください。

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}