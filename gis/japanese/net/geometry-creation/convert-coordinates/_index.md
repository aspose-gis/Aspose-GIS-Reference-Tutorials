---
date: 2025-12-11
description: Aspose.GIS for .NET を使用して座標を DMS に変換する方法を学びましょう。C# のサンプル、C# での緯度・経度変換、ステップバイステップのガイドが含まれています。
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用して座標を DMS に変換する
url: /ja/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した座標の DMS 変換

## はじめに
このチュートリアルでは、強力な Aspose.GIS ライブラリ for .NET を使用して **座標を DMS**（度・分・秒）に変換する方法を学びます。マッピングアプリケーション向けに緯度・経度を変換したり、人が読みやすい位置文字列を生成したり、さまざまな座標形式を試したりしたい場合でも、本ガイドは明確な解説とすぐに実行できる C# コードとともに、すべての手順を丁寧に案内します。

## クイック回答
- **「座標を DMS に変換する」とは何ですか？** 数値の緯度/経度を従来の度・分・秒表記に変換します。  
- **変換を行うライブラリはどれですか？** Aspose.GIS for .NET が `GeoConvert` クラスと組み込みのフォーマットサポートを提供します。  
- **試用するのにライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、そして .NET 5/6 以上です。  
- **他のフォーマットでも同じコードを使えますか？** はい。`PointFormats` 列挙体の値を変更するだけです（例: `DecimalDegrees`, `GeoRef`）。

## 座標の DMS 変換とは何ですか？
座標を DMS に変換すると、十進法の緯度・経度を `25°30'00"N 45°30'00"E` のような形式に書き換えます。この表記は地図製作、航海、GIS データのやり取りで広く使用されています。

## なぜ座標変換に Aspose.GIS を使用するのか？
- **オールインワン API** – 外部ライブラリや複雑な計算は不要です。Aspose.GIS が内部でパースとフォーマットを処理します。  
- **高精度** – 負の値や半球指示子などのエッジケースを正確に処理します。  
- **クロスプラットフォーム** – Windows、Linux、macOS の .NET ランタイム上で同様に動作します。  
- **拡張性** – DMS、十進法度、度‑小数分、GeoRef 形式間を簡単に切り替えられます。

## 前提条件
開始する前に、以下が揃っていることを確認してください：

1. **C# の基本知識** – 変数、メソッド呼び出し、コンソール出力に慣れていること。  
2. **Aspose.GIS がインストール済み** – 最新パッケージを [Aspose.GIS website](https://releases.aspose.com/gis/net/) からダウンロードしてください。

## 名前空間のインポート
まず、GIS 操作に必要な名前空間をインポートします：

```csharp
using System;
using Aspose.Gis;
```

## ステップバイステップ ガイド

### ステップ 1: 変換プロセスの開始
デモが開始されたことを示すために、フレンドリーなメッセージを出力します。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### ステップ 2: 十進法度への変換
最終目標は DMS ですが、まず元の十進法表現を示します。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### ステップ 3: 度小数分への変換
この形式（`DD°MM.m'`）は、*緯度経度の度分を変換*する際の一般的な中間ステップです。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### ステップ 4: 度分秒 (DMS) への変換
これが本チュートリアルの核心です — **座標を DMS に変換**します。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### ステップ 5: GeoRef への変換
完全性を保つために、リモートセンシングのワークフローで役立つ `GeoRef` 形式も示します。

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## よくある問題と解決策
- **半球文字が間違っている** – 北/東は正の値、南/西は負の値で渡すようにしてください。API が自動で正しいサフィックスを付加します。  
- **予期せぬ空出力** – `Aspose.Gis` アセンブリが正しく参照されているか、プロジェクトがサポート対象の .NET バージョンを対象にしているか確認してください。  
- **ライセンスが見つからない** – ライセンスファイルをアプリケーションのルートに配置するか、`License license = new License(); license.SetLicense("Aspose.GIS.lic");` のようにプログラムで設定してください。

## よくある質問

**Q: Aspose.GIS は他のプログラミング言語と互換性がありますか？**  
A: Aspose.GIS は主に .NET 開発者向けですが、Java バージョンも提供されています。

**Q: 購入前に Aspose.GIS を試すことはできますか？**  
A: はい、[website](https://releases.aspose.com/) から Aspose.GIS の無料トライアルにアクセスできます。

**Q: Aspose.GIS のサポートはどこで受けられますか？**  
A: Aspose.GIS コミュニティフォーラム [here](https://forum.aspose.com/c/gis/33) で支援を受けられます。

**Q: Aspose.GIS の一時ライセンスは利用できますか？**  
A: はい、[temporary license page](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.GIS はどこで購入できますか？**  
A: [purchase page](https://purchase.aspose.com/buy) から購入できます。

## 結論
これらの手順に従うことで、Aspose.GIS for .NET を使用して **座標を DMS** やその他の一般的な GIS 形式に変換する方法が分かります。この機能により、マッピングアプリケーション、レポート、または任意の空間データワークフローに人が読みやすい位置文字列をシームレスに組み込むことができます。さまざまな緯度・経度の値で試してみたり、`GeoConvert` クラスが提供する他の形式を探索したりしてください。

---

**最終更新日:** 2025-12-11  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}