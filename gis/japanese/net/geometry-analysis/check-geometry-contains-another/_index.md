---
title: ジオメトリに別のものが含まれていることを確認してください
linktitle: ジオメトリに別のものが含まれていることを確認してください
second_title: Aspose.GIS .NET API
description: .NET アプリケーションでのシームレスな地理空間データ統合のための堅牢なライブラリである Aspose.GIS for .NET を探索してください。
weight: 14
url: /ja/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ジオメトリに別のものが含まれていることを確認してください

## 導入
Aspose.GIS for .NET は、開発者が .NET アプリケーション内で地理空間データをシームレスに操作できるようにする強力なライブラリです。マッピング アプリケーションの構築、地理空間分析の実行、ソフトウェアへの位置ベースの機能の統合のいずれの場合でも、Aspose.GIS は直感的な API と堅牢な機能を提供することでプロセスを簡素化します。
## 前提条件
Aspose.GIS for .NET の使用に入る前に、次の前提条件を満たしていることを確認してください。
### 1..NET開発環境のセットアップ
マシン上に動作する .NET 開発環境がセットアップされていることを確認してください。これには、.NET SDK のインストールと適切な構成が含まれます。
### 2. Aspose.GIS のインストール
リリース ページからライブラリをダウンロードして、Aspose.GIS for .NET をインストールします。[ここ](https://releases.aspose.com/gis/net/) 。ドキュメントに記載されているインストール手順に従ってください[ここ](https://reference.aspose.com/gis/net/)Aspose.GIS をプロジェクトに統合します。
### 3. C# の基本的な理解
Aspose.GIS for .NET は主に C# で使用されるため、C# プログラミング言語に慣れてください。

## 名前空間のインポート
C# プロジェクトで、Aspose.GIS 機能を利用するために必要な名前空間をインポートします。
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: ジオメトリ オブジェクトを定義する
まず、Aspose.GIS クラスを使用してジオメトリ オブジェクトを定義します。
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## ステップ 2: 空間的包含を確認する
次に、あるジオメトリに別のジオメトリが含まれているかどうかを確認します。
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); //間違い
```
## ステップ 3: 別のジオメトリを定義する
別のジオメトリ オブジェクトを定義します。
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## ステップ 4: 空間的包含を再確認する
新しく定義されたジオメトリが最初のジオメトリ内に含まれているかどうかを確認します。
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); //真実
```
## ステップ 5: 同等の機能
だとわかる`a.SpatiallyContains(b)`と同等です`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); //真実
```

## 結論
結論として、Aspose.GIS for .NET は、.NET アプリケーションで地理空間データを処理するための強力なツールを提供します。このガイドに従い、提供されている例を利用すると、空間包含チェックを効率的に実行し、プロジェクト内で他の地理空間機能を活用できます。
## よくある質問
### Q1: Aspose.GIS は .NET Core と互換性がありますか?
A: はい、Aspose.GIS は .NET Core を完全にサポートしているため、さまざまなプラットフォーム間で地理空間アプリケーションを開発できます。
### Q2: Aspose.GIS を使用して地理空間分析を実行できますか?
A: 確かに、Aspose.GIS は、空間クエリ、距離計算、ジオメトリ操作など、地理空間分析のためのさまざまな機能を提供します。
### Q3: Aspose.GIS の更新はどのくらいの頻度でリリースされますか?
A: Aspose.GIS は、パフォーマンスの向上、新機能の追加、報告された問題への対処を目的としたアップデートを定期的にリリースします。リリース ページにアクセスすると、最新情報を入手できます。
### Q4: Aspose.GIS ユーザー向けのコミュニティ フォーラムはありますか?
A: はい、Aspose.GIS コミュニティ フォーラムに参加できます。[ここ](https://forum.aspose.com/c/gis/33)他のユーザーとつながり、質問し、経験を共有します。
### Q5: 購入する前に Aspose.GIS を試すことはできますか?
 A: 確かに、以下から無料トライアルをダウンロードすると、Aspose.GIS を探索できます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
