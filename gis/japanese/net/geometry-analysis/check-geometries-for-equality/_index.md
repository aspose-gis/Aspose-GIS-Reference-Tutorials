---
title: ジオメトリが等しいかどうかを確認する
linktitle: ジオメトリが等しいかどうかを確認する
second_title: Aspose.GIS .NET API
description: この包括的なチュートリアルでは、Aspose.GIS for .NET を使用して .NET アプリケーション内のジオメトリが等しいかどうかをチェックする方法を学びます。
weight: 10
url: /ja/net/geometry-analysis/check-geometries-for-equality/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ジオメトリが等しいかどうかを確認する

## 導入
Aspose.GIS for .NET は、開発者が .NET アプリケーションで地理空間データを効率的に操作できるようにする強力なライブラリです。マッピング アプリケーション、空間分析ツールを構築している場合でも、地理空間機能を既存のソフトウェアに統合している場合でも、Aspose.GIS はその作業を完了するために必要なツールを提供します。
## 前提条件
Aspose.GIS for .NET の使用に入る前に、次の前提条件が満たされていることを確認してください。
### .NET Frameworkがインストールされている
システムに .NET Framework がインストールされていることを確認してください。 Microsoft Web サイトからダウンロードできます。
### .NET ライブラリ用の Aspose.GIS
 Aspose.GIS for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/gis/net/)。ドキュメントに記載されているインストール手順に従ってください。
### 開発環境
.NET 開発用に、Visual Studio などの好みの開発環境をセットアップします。

## 名前空間のインポート
.NET アプリケーションで、Aspose.GIS 機能を使用するために必要な名前空間をインポートします。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ジオメトリを定義する
まず、比較するジオメトリを定義します。この例には、2 つのジオメトリがあります。`geometry1`そして`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## ステップ 2: ジオメトリが等しいかどうかを確認する
ここで、ジオメトリが空間的に等しいかどうかを、`SpatiallyEquals` Aspose.GIS によって提供されるメソッド。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //真実
```
これで印刷されます`True`それ以来コンソールに`geometry1`そして`geometry2`空間的には等しい。
## ステップ 3: ジオメトリを変更する
次に改造してみます`geometry2`新しい点を追加することによって。
```csharp
geometry2.AddPoint(3, 3);
```
## ステップ 4: 平等性を再確認する
ここで、変更後のジオメトリが等しいかどうかを再確認します。
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); //間違い
```
今回の出力は次のようになります`False`変更が加えられたため、ジオメトリは空間的に等しくなくなったため、`geometry2`.

## 結論
結論として、Aspose.GIS for .NET は、.NET アプリケーションで地理空間データを操作するための強力なツールを提供します。このステップバイステップ ガイドに従うことで、Aspose.GIS メソッドを使用してジオメトリが等しいかどうかを簡単にチェックできます。
## よくある質問
### Aspose.GIS for .NET を他の .NET フレームワークと一緒に使用できますか?
はい、Aspose.GIS for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Aspose.GIS for .NET に利用できる無料トライアルはありますか?
はい、次のサイトから無料試用版をダウンロードできます。[リリースページ](https://releases.aspose.com/).
### Aspose.GIS for .NET のドキュメントはどこで見つけられますか?
詳細なドキュメントは、[Aspose.GIS ドキュメント ページ](https://reference.aspose.com/gis/net/).
### Aspose.GIS for .NET のサポートを受けるにはどうすればよいですか?
Aspose.GIS コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/gis/33).
### Aspose.GIS for .NET の一時ライセンスを購入できますか?
はい、一時ライセンスは次から購入できます。[購入ページ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
