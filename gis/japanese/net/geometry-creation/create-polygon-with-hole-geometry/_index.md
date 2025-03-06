---
title: Aspose.GIS を使用して穴ジオメトリを持つポリゴンを作成する
linktitle: 穴ジオメトリを使用してポリゴンを作成する
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して穴ジオメトリを持つポリゴンを作成する方法を学びます。コード例を含むステップバイステップのチュートリアル。
weight: 13
url: /ja/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用して穴ジオメトリを持つポリゴンを作成する

## 導入
このチュートリアルでは、Aspose.GIS for .NET を使用して穴ジオメトリを持つポリゴンを作成するプロセスを説明します。 Aspose.GIS は、開発者が .NET アプリケーションで地理空間データを操作できるようにする強力なライブラリです。 
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Aspose.GIS for .NET ライブラリ: 次からダウンロードできます。[ここ](https://releases.aspose.com/gis/net/).
2. 開発環境: Visual Studio またはその他の .NET IDE がインストールされた開発環境がセットアップされていることを確認します。
## 名前空間のインポート
まず、Aspose.GIS 機能を使用するために必要な名前空間をインポートする必要があります。その方法は次のとおりです。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

次に、Aspose.GIS for .NET を使用して、穴ジオメトリを持つポリゴンの作成に進みましょう。
## ステップ 1: ポリゴン オブジェクトを作成する
```csharp
Polygon polygon = new Polygon();
```
## ステップ 2: 外部リングを定義する
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## ステップ 3: 内部リング (穴) を定義する
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## ステップ 4: 外部リングを割り当て、内部リングをポリゴンに追加する
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用して穴ジオメトリを持つポリゴンを作成する方法を学習しました。この知識は、そのような形状が不可欠なさまざまな地理空間アプリケーションに役立ちます。
## よくある質問
### 1. Aspose.GIS とは何ですか?
Aspose.GIS は、開発者が地理空間データを操作し、さまざまな地理空間ファイル形式を作成、読み取り、操作できるようにする .NET ライブラリです。
### 2. Aspose.GIS を商用プロジェクトに使用できますか?
はい、ライセンスを購入することで、Aspose.GIS を個人プロジェクトと商用プロジェクトの両方に使用できます。訪問[ここ](https://purchase.aspose.com/buy)詳細については。
### 3. Aspose.GIS に利用できる無料トライアルはありますか?
はい、次のサイトから Aspose.GIS の無料トライアルを利用できます。[ここ](https://releases.aspose.com/).
### 4. Aspose.GIS のサポートはどこで見つけられますか?
 Aspose.GIS のサポートは、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33).
### 5. Aspose.GIS の一時ライセンスを取得するにはどうすればよいですか?
 Aspose.GIS の一時ライセンスは、以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
