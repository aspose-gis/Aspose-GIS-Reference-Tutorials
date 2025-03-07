---
title: Aspose.GIS を使用してジオメトリ内のジオメトリを数える
linktitle: ジオメトリ内のジオメトリを数える
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して、ジオメトリ内のジオメトリをカウントする方法を学習します。開発者向けのコード例を含むステップバイステップのチュートリアル。
weight: 23
url: /ja/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用してジオメトリ内のジオメトリを数える

## 導入
Aspose.GIS for .NET は、.NET アプリケーションに地理空間機能を組み込もうとしている開発者にとって強力なツールです。地図作成ソフトウェア、位置ベースのサービス、空間分析ツールのいずれを構築している場合でも、Aspose.GIS はニーズを満たす包括的な機能セットを提供します。このチュートリアルでは、Aspose.GIS for .NET を使用してジオメトリ内のジオメトリをカウントする方法を検討します。
## 前提条件
このチュートリアルに入る前に、次の前提条件を満たしていることを確認してください。
1. Visual Studio: Visual Studio がシステムにインストールされていることを確認してください。
2. Aspose.GIS for .NET: Aspose.GIS for .NET を次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/gis/net/).
3. C# の基本知識: C# プログラミング言語の基本を理解します。

## 名前空間のインポート
コーディングを開始する前に、Aspose.GIS 機能にアクセスするために必要な名前空間をインポートする必要があります。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 2: ポイント ジオメトリの作成
```csharp
Point point = new Point(40.7128, -74.006);
```
ここでは、`Point`緯度 40.7128、経度 -74.006 のジオメトリ。
## ステップ 3: ラインストリング ジオメトリを作成する
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
このステップでは、`LineString`ジオメトリを作成し、それに 2 つの点を追加します。
## ステップ 4: ジオメトリ コレクションを作成する
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
次に、`GeometryCollection`そして、以前に作成した点と線のジオメトリをそれに追加します。
## ステップ 5: ジオメトリを数える
```csharp
int geometriesCount = geometryCollection.Count;
```
このステップでは、オブジェクト内のジオメトリの数をカウントします。`GeometryCollection`.
## ステップ 6: カウントを表示する
```csharp
Console.WriteLine(geometriesCount); // 2
```
最後に、ジオメトリの数を出力します。この場合は次のようになります。`2`.

## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用してジオメトリ内のジオメトリをカウントする方法を学習しました。これらの手順に従うことで、地理空間機能を .NET アプリケーションに簡単に組み込むことができます。
## よくある質問
### Aspose.GIS for .NET はデスクトップ アプリケーションと Web アプリケーションの両方に適していますか?
はい、Aspose.GIS for .NET はデスクトップ アプリケーションと Web アプリケーションの両方でシームレスに使用できます。
### Aspose.GIS for .NET を使用して空間クエリを実行できますか?
もちろん、Aspose.GIS for .NET は、ジオメトリに対して空間クエリを実行するための強力なサポートを提供します。
### Aspose.GIS for .NET はさまざまな GIS ファイル形式をサポートしていますか?
はい、Aspose.GIS for .NET は、SHP、KML、GeoJSON などの幅広い GIS ファイル形式をサポートしています。
### Aspose.GIS for .NET に利用できる無料トライアルはありますか?
はい、次のサイトから無料試用版をダウンロードできます。[Webサイト](https://releases.aspose.com/).
### Aspose.GIS for .NET のサポートはどこで見つけられますか?
サポートは次のサイトで見つけることができます。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
