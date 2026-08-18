---
date: 2026-08-18
description: Aspose.GIS for .NET を使用して十進法度を DMS に変換します。このステップバイステップの C# ガイドでは、緯度/経度や十進法度を
  DMS に変換する方法などを紹介します。
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: 座標を変換
og_description: Aspose.GIS for .NET で十進法度から DMS への変換が簡単に。緯度‑経度の値を分単位の DMS 形式に変換する方法を学びましょう。
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Aspose.GIS for .NET を使用した十進法度から DMS への変換方法
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Aspose.GIS for .NET を使用した十進法度から DMS への変換方法
url: /ja/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用して十進度を DMS に変換する方法

## はじめに
このチュートリアルでは、.NET 用の強力な Aspose.GIS ライブラリを使用して **十進度を DMS に変換する方法** を学びます。**c# convert lat long** が必要な場合や、レポート用の人間が読みやすい位置文字列を生成したい場合、またはさまざまな座標形式を探索したい場合でも、このガイドは明確な説明と実行可能な C# スニペットとともにすべての手順を案内します。

## クイック回答
- **“convert coordinates to dms” とは何ですか？** 数値の緯度/経度を従来の度‑分‑秒表記に変換します。  
- **どのライブラリが変換を処理しますか？** .NET 用 Aspose.GIS は組み込みのフォーマットサポートを持つ `GeoConvert` クラスを提供します。  
- **試用するのにライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、そして .NET 5/6 以上です。  
- **他のフォーマットでも同じコードを使用できますか？** はい。`PointFormats` 列挙体の値を変更するだけです（例: `DecimalDegrees`、`GeoRef`）。

## 座標を DMS に変換するとは何ですか？
座標を DMS に変換すると、十進度の緯度・経度の値が `25°30'00"N 45°30'00"E` のような形式に書き換えられます。このプロセスでは、各十進度を整数の度、分（1 度の 1/60）、秒（1 分の 1/60）に分割し、適切な半球指標（N、S、E、W）を付加します。この人間が読みやすい形式は、多くのレガシーデータセットや、十進表記に依存せず正確な位置を伝える際に不可欠です。

## 座標変換に Aspose.GIS を使用する理由
Aspose.GIS は **50 以上の入力および出力フォーマット** をサポートし、データセット全体をメモリに読み込むことなく数百ページに及ぶ GIS ファイルを処理できます。API は負の値や半球指標などのエッジケースに対してサブミリメートル単位の精度を提供し、Windows、Linux、macOS の .NET ランタイム上で一貫して動作します。

## 前提条件
1. **C# の基本知識** – 変数、メソッド呼び出し、コンソール出力に慣れていること。  
2. **Aspose.GIS がインストール済み** – 最新パッケージは [Aspose.GIS のウェブサイト](https://releases.aspose.com/gis/net/) からダウンロードしてください。また、[Aspose リリースのウェブサイト](https://releases.aspose.com/) でもメインのリリース情報を確認できます。  

## 名前空間のインポート
まず、GIS 操作に必要な名前空間をインポートします:

名前空間のプレースホルダーは変更せずに残します。

## ステップバイステップガイド

### GeoConvert クラスとは？
`GeoConvert` クラスは、十進度、DMS、GeoRef などの座標フォーマット間の変換を行う静的メソッドを提供します。生の数値または `Point` オブジェクトを受け取るオーバーロードがあり、フォーマット済み文字列または新しい `Point` インスタンスを返します。負の座標や丸めなどのエッジケースを処理することで、出力が標準 GIS 仕様に準拠することを保証し、任意の .NET マッピングアプリケーションへの統合を簡素化します。

### 手順 1: 変換プロセスの開始
デモが開始されたことを示すために、フレンドリーなメッセージを出力します。

```csharp
using System;
using Aspose.Gis;
```

### 手順 2: 十進度に変換
最終目標は DMS ですが、まず元の十進表記を示します。これにより、後でたどる **decimal degrees to dms** のパスもデモします。

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### 手順 3: 度十進分に変換
この形式（`DD°MM.m'`）は、**convert lat long degree minutes** が必要な場合の一般的な中間ステップです。

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### 手順 4: 度分秒 (dms) に変換
これがチュートリアルの核心です — **convert coordinates to dms**。

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### 手順 5: GeoRef に変換
完全性を保つために、リモートセンシングのワークフローで有用な `GeoRef` フォーマットもデモします。

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## よくある問題と解決策
- **半球文字が正しくない** – 北/東は正の値、南/西は負の値を渡すようにしてください。API が自動的に正しいサフィックスを付加します。  
- **予期しない空白出力** – `Aspose.Gis` アセンブリが正しく参照されているか、プロジェクトがサポートされている .NET バージョンを対象としているかを確認してください。  
- **ライセンスが見つからない** – ライセンスファイルをアプリケーションのルートに配置するか、プログラムで `License license = new License(); license.SetLicense("Aspose.GIS.lic");` と設定してください。

## よくある質問

**Q: Aspose.GIS は他のプログラミング言語と互換性がありますか？**  
A: Aspose.GIS は主に .NET 開発者向けですが、Java バージョンも利用可能です。

**Q: 購入前に Aspose.GIS を試すことはできますか？**  
A: はい、[ウェブサイト](https://releases.aspose.com/) から Aspose.GIS の無料トライアルにアクセスできます。

**Q: Aspose.GIS のサポートはどこで受けられますか？**  
A: Aspose.GIS コミュニティフォーラムは [こちら](https://forum.aspose.com/c/gis/33) で利用できます。

**Q: Aspose.GIS の一時ライセンスは利用可能ですか？**  
A: はい、一時ライセンスは [一時ライセンスページ](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.GIS はどこで購入できますか？**  
A: [購入ページ](https://purchase.aspose.com/buy) から購入できます。

## 結論
これらの手順に従うことで、.NET 用 Aspose.GIS を使用して **convert decimal degrees to dms** やその他の一般的な GIS フォーマットへの変換方法が分かります。この機能により、マッピングアプリケーション、レポート、または任意の空間データワークフローに人間が読みやすい位置文字列をシームレスに統合できます。さまざまな緯度/経度の値で試してみたり、`GeoConvert` クラスが提供する他のフォーマットを探索したりしてください。

---

**最終更新日:** 2026-08-18  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## 関連チュートリアル

- [Aspose.GIS for .NET でポイントジオメトリを作成しジオメトリタイプを取得する方法](/gis/net/geometry-analysis/get-geometry-type/)
- [GeoJSON の変換方法 – Aspose.GIS for .NET](/gis/net/geo-data-conversion/)
- [Aspose.GIS を使用した .NET のマルチポイントジオメトリ作成](/gis/net/geometry-creation/create-multipoint-geometry/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}