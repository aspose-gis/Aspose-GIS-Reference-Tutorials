---
title: Aspose.GIS による座標変換
linktitle: 座標を変換する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して座標を変換する方法を学びます。ステップバイステップのガイド、前提条件、および FAQ が提供されます。
weight: 25
url: /ja/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS による座標変換

## 導入
このチュートリアルでは、.NET 用の強力な Aspose.GIS ライブラリを使用して、地理情報システム (GIS) の世界を詳しく説明します。 Aspose.GIS は、開発者が空間データを簡単に操作できるようにする包括的なツールキットです。経験豊富な開発者でも、初心者でも、このチュートリアルでは、Aspose.GIS を利用して座標を効率的に変換するプロセスを説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. C# の基本知識: 提供されているコード例を理解して実装するには、C# プログラミング言語に精通していることが不可欠です。
  
2.  Aspose.GIS のインストール: .NET 用の Aspose.GIS ライブラリをダウンロードしてインストールしていることを確認してください。からダウンロードできます。[Aspose.GIS Web サイト](https://releases.aspose.com/gis/net/).

## 名前空間のインポート
始める前に、Aspose.GIS の機能にアクセスするために必要な名前空間をインポートしましょう。
```csharp
using System;
using Aspose.Gis;
```

明確に理解できるように、提供された例を複数のステップに分けてみましょう。
## ステップ 1: 変換プロセスを開始する
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
この行は、座標変換プロセスの開始を示すメッセージを表示するだけです。
## ステップ 2: 10 進度に変換する
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
ここでは、座標 (25.5, 45.5) を 10 進度形式に変換します。`AsPointText`を使用したメソッド`PointFormats.DecimalDegrees`パラメータ。結果はコンソールに出力されます。
## ステップ 3: 度 10 進数分に変換する
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
このステップでは、座標を度 10 進分形式に変換し、結果を出力します。
## ステップ 4: 度分秒に変換する
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
同様に、座標を度分秒形式に変換し、出力を表示します。
## ステップ 5: GeoRef に変換する
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
最後に、座標を GeoRef 形式に変換し、結果を出力します。

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用して座標を変換するプロセスについて説明しました。ステップバイステップのガイドに従って Aspose.GIS ライブラリを利用すると、.NET アプリケーション内で空間データを効率的に操作できます。
## よくある質問
### Aspose.GIS は他のプログラミング言語と互換性がありますか?
Aspose.GIS は主に .NET 開発者を対象としていますが、Aspose.GIS for Java を通じて Java との相互運用性を提供します。
### 購入する前に Aspose.GIS を試してみることはできますか?
はい、Aspose.GIS の無料トライアルにアクセスできます。[Webサイト](https://releases.aspose.com/).
### Aspose.GIS のサポートを受けるにはどうすればよいですか?
 Aspose.GIS コミュニティ フォーラムから支援を求めることができます。[ここ](https://forum.aspose.com/c/gis/33).
### Aspose.GIS の一時ライセンスは利用できますか?
はい、一時ライセンスは次のサイトから取得できます。[一時ライセンスのページ](https://purchase.aspose.com/temporary-license/).
### Aspose.GIS はどこで購入できますか?
 Aspose.GIS は、以下から購入できます。[購入ページ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
