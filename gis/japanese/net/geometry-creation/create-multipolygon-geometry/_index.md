---
date: 2026-03-29
description: Aspose.GIS for .NET を使用して、マルチポリゴンジオメトリの作成方法とマルチポリゴンへのポリゴン追加方法を学びましょう。無料トライアル付きのステップバイステップガイド。
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GISでマルチポリゴンジオメトリを作成する方法
url: /ja/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用した MultiPolygon ジオメトリの作成方法

## はじめに
.NET 環境で **マルチポリゴンの作成方法** を探しているなら、ここが正しい場所です。Aspose.GIS for .NET は、複雑な地理空間オブジェクトを構築するためのクリーンなオブジェクト指向 API を提供し、このチュートリアルではライブラリのインストールから個々のポリゴンを単一の MultiPolygon に結合するまでのすべての手順を案内します。最後まで読めば、**ポリゴンをマルチポリゴンに追加** することに自信を持てるようになります。

## クイック回答
- **What is a MultiPolygon?** 2 つ以上の Polygon オブジェクトを単一のコレクションにまとめたジオメトリです。  
- **Why use Aspose.GIS?** 多くの GIS フォーマットをサポートし、.NET Framework と .NET Core の両方で動作し、外部のネイティブライブラリを必要としません。  
- **How long does the example take?** タイピングと実行に約 5 分かかります。  
- **Do I need a license?** 開発には無料トライアルで十分ですが、本番環境では商用ライセンスが必要です。  
- **Which .NET versions are supported?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## MultiPolygon ジオメトリとは何ですか？
MultiPolygon は、複数の Polygon オブジェクトを含む複合ジオメトリで、各ポリゴンは内部リング（穴）を持つこともできます。この構造は、離散した土地区画、島、または共通の属性を持つ別々の領域の集合を表現するのに最適です。

## なぜポリゴンを MultiPolygon に追加するのか？
ポリゴンを MultiPolygon に追加すると、複数の独立した形状を単一のエンティティとして扱うことができます。これにより、空間クエリ、レンダリング、データ交換が簡素化され、各ポリゴンを個別に処理する代わりに、1 つのオブジェクトでコレクション全体を保存、転送、操作できます。

## 前提条件
- **Aspose.GIS for .NET** がインストールされていること（以下の手順を参照）。  
- .NET 開発環境（Visual Studio、VS Code、またはお好みの IDE）。  
- C# 構文の基本的な知識。

### Aspose.GIS for .NET のインストール
1. Download Aspose.GIS: Head over to the [download page](https://releases.aspose.com/gis/net/) and select the appropriate version for your development environment.  
2. Install Aspose.GIS: Follow the installation instructions provided in the documentation to install Aspose.GIS for .NET on your machine.

## 名前空間のインポート
.NET プロジェクトで Aspose.GIS を使用し始めるには、必要な名前空間をインポートします：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: LinearRing の作成
まず、各ポリゴンのために **LinearRing** オブジェクトを作成する必要があります。LinearRing は、ポリゴンの外周（必要に応じて内部の穴）を定義する閉じたラインストリングです。

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

## ステップ 2: ポリゴンの作成
次に、各 LinearRing を **Polygon** オブジェクトに変換します。これらのポリゴンは後で MultiPolygon に追加されます。

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## ステップ 3: MultiPolygon の作成
さて、ポリゴンを単一の **MultiPolygon** ジオメトリに結合しましょう。ここが **ポリゴンをマルチポリゴンに追加** する箇所です。

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

おめでとうございます！Aspose.GIS for .NET を使用して、MultiPolygon ジオメトリを正常に作成できました。

## よくある問題と解決策
| 問題 | 原因 | 対策 |
|-------|-------|-----|
| **リングが閉じていない点** | 最初と最後の点が異なる。 | 最初と最後の座標が同一であることを確認してください。Aspose.GIS は自動的にリングを閉じますが、明示的に閉じることで混乱を防げます。 |
| **座標順序が不正 (X, Y と Lon, Lat の混同)** | 経度と緯度が混同されている。 | (X, Y) の順序に従ってください。X = 経度、Y = 緯度です。 |
| **実行時にライブラリが見つからない** | NuGet 参照または DLL が欠如している。 | プロジェクトファイルで Aspose.GIS パッケージが参照されていること、DLL が出力フォルダーにコピーされていることを確認してください。 |

## よくある質問

**Q: Aspose.GIS for .NET は初心者に適していますか？**  
A: もちろんです！Aspose.GIS は包括的なドキュメントとチュートリアルを提供しており、あらゆるスキルレベルの開発者がすぐに始められます。

**Q: 購入前に Aspose.GIS を試すことはできますか？**  
A: はい、[こちら](https://releases.aspose.com/) から無料トライアルをダウンロードして、機能を確認した上で購入をご検討いただけます。

**Q: Aspose.GIS のサポートはどこで受けられますか？**  
A: Aspose.GIS フォーラム [こちら](https://forum.aspose.com/c/gis/33) で質問し、コミュニティから支援を受けることができます。

**Q: Aspose.GIS の一時ライセンスはありますか？**  
A: はい、評価目的で使用できる一時ライセンスを [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.GIS を直接購入できますか？**  
A: はい、ウェブサイトの [こちら](https://purchase.aspose.com/buy) から購入できます。

---

**最終更新日:** 2026-03-29  
**テスト環境:** Aspose.GIS 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}