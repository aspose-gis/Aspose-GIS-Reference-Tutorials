---
title: Aspose.GIS を使用してジオメトリ間の距離を計算する
linktitle: ジオメトリ間の距離を計算する
second_title: Aspose.GIS .NET API
description: Aspose.GIS を使用して .NET でジオメトリ間の距離を計算する方法を学びます。コード例を含むステップバイステップのガイド。地理空間アプリケーションを強化します。
weight: 21
url: /ja/net/geometry-analysis/calculate-distance-between-geometries/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用してジオメトリ間の距離を計算する

## 導入
地理空間プログラミングの領域では、異なるジオメトリ間の距離を計算する機能が最も重要です。多角形、線、点のいずれを扱う場合でも、それらの間の距離を知ることは、地図作成から物流計画に至るまで、さまざまなアプリケーションにとって非常に重要です。 Aspose.GIS for .NET は、このような計算を簡単かつ正確に実行するための強力なツールを提供します。
## 前提条件
Aspose.GIS for .NET を使用してジオメトリ間の距離を計算する前に、次の前提条件が満たされていることを確認してください。
### .NET 用の Aspose.GIS をインストールする
開始するには、Aspose.GIS for .NET がシステムにインストールされている必要があります。ライブラリはからダウンロードできます。[Aspose.GIS for .NET リリース ページ](https://releases.aspose.com/gis/net/)ドキュメントに記載されているインストール手順に従ってください。
### .NET 開発に関する知識
このチュートリアルの例に従うには、C# を使用した .NET 開発の基本を理解している必要があります。 .NET 開発が初めての場合は、先に進む前に C# の基本をブラッシュアップすることを検討してください。

## 名前空間のインポート
Aspose.GIS for .NET を使用してジオメトリ間の距離を計算する前に、必要な名前空間を C# プロジェクトにインポートする必要があります。次の手順に従って、必要な名前空間をインポートします。
## C# プロジェクトを開きます
Visual Studio など、好みの統合開発環境 (IDE) で C# プロジェクトに移動します。
## 名前空間参照の追加
距離計算を実行する C# ファイルで、ファイルの先頭に次の名前空間参照を追加します。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Aspose.GIS for .NET を使用してジオメトリ間の距離を計算する方法を理解するために、提供された例を複数のステップに分解してみましょう。
## ステップ 1: ポリゴン ジオメトリの作成
```csharp
var polygon = new Polygon();
```
このステップでは、ポリゴン ジオメトリの新しいインスタンスを作成します。
## ステップ 2: ポリゴンの外部リングを定義する
```csharp
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
});
```
ここでは、多角形の境界を形成する一連の点を指定することによって、多角形の外部リングを定義します。
## ステップ 3: 線ストリング ジオメトリの作成
```csharp
var line = new LineString();
```
このステップでは、ラインストリングジオメトリの新しいインスタンスを初期化します。
## ステップ 4: 線ストリングに点を追加する
```csharp
line.AddPoint(2, 0);
line.AddPoint(1, 3);
```
線ストリングに 2 つの点を追加し、その形状と軌道を定義します。
## ステップ 5: 距離を計算する
```csharp
double distance = polygon.GetDistanceTo(line);
```
このステップでは、多角形と線ストリングの間の距離を計算します。
## ステップ6: 結果を出力する
```csharp
Console.WriteLine(distance.ToString("F")); //0.63
```
最後に、計算されたコンソールまでの距離を小数点以下 2 桁まで表示する形式で出力します。

## 結論
ジオメトリ間の距離の計算は地理空間プログラミングの基本的なタスクであり、Aspose.GIS for .NET は直感的な API を使用してこのプロセスを簡素化します。このチュートリアルで概説されている手順に従うことで、.NET アプリケーション内の多角形、線、点間の距離を簡単に計算できます。
## よくある質問
### Aspose.GIS for .NET はすべての .NET フレームワークと互換性がありますか?
はい、Aspose.GIS for .NET は .NET Framework 4.6 以降と互換性があります。
### Aspose.GIS for .NET を使用して複雑な空間解析を実行できますか?
絶対に！ Aspose.GIS for .NET は、高度な空間分析タスクのための幅広い機能を提供します。
### Aspose.GIS for .NET は 2D ジオメトリと 3D ジオメトリの両方をサポートしていますか?
はい、Aspose.GIS for .NET を使用して 2D ジオメトリと 3D ジオメトリの両方を操作できます。
### Aspose.GIS for .NET を他の GIS ライブラリと統合できますか?
Aspose.GIS for .NET は他の GIS ライブラリとの相互運用性を提供し、追加機能を利用できるようにします。
### Aspose.GIS for .NET ユーザーはテクニカル サポートを利用できますか?
はい、Aspose.GIS for .NET のユーザーは、Aspose を通じてテクニカル サポートにアクセスできます。[フォーラム](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
