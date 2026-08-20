---
date: 2026-06-30
description: Aspose.GIS for .NET を使用して shapefile の作成方法を学びます。このステップバイステップガイドでは、vector
  layer の定義、date attribute の追加、spatial data の効率的な管理方法を示します。
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: 新しい Shapefile を作成
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET を使用した Shapefile の作成方法
url: /ja/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新しいシェープファイルの作成

## はじめに
.NETで地理情報システム（GIS）開発に取り組んでいる場合、Aspose.GISはプログラムで**how to create shapefile**するための最適なソリューションです。このライブラリはベクターレイヤー、属性スキーマ、ファイル形式の準拠を完全にコントロールできるため、データパイプラインを自動化したり、数分でテストデータセットを生成したりできます。

## クイック回答
- **このチュートリアルで学べることは何ですか？** 新しいシェープファイルの作成方法、ベクターレイヤーの定義、属性（日時フィールドを含む）の追加方法を学びます。  
- **必要なライブラリはどれですか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 学習には無料トライアルで十分です。商用利用には商用ライセンスが必要です。  
- **どのIDEを使用すべきですか？** Visual Studio（最新バージョン）。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で約10〜15分です。

## Aspose.GIS for .NETでシェープファイルを作成する方法
Aspose.GISライブラリをロードし、出力フォルダーを設定し、`VectorLayer`を作成し、属性を定義してフィーチャーを追加します—この一連の作業はC#で30行未満で記述できます。ライブラリはジオメトリの作成、属性の型付け、ファイル書き込みを自動的に処理するため、低レベルのシェープファイル仕様を自分で管理する必要はありません。

## 前提条件
Before we jump into the tutorial, make sure you have the following prerequisites in place:
- C#プログラミング言語の基本的な理解。  
- マシンにVisual Studioがインストールされていること。  
- Aspose.GIS for .NETライブラリ。ダウンロードは[here](https://releases.aspose.com/gis/net/)から。

## 名前空間のインポート
Start by importing the necessary namespaces to leverage the functionality of Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順 1: プロジェクトの設定
Visual Studioで新しいC#プロジェクトを作成し、Aspose.GISライブラリを追加します。

## 手順 2: ドキュメントディレクトリの定義
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory* を、新しいシェープファイルを保存したい実際のパスに置き換えてください。

## 手順 3: VectorLayer の作成
`VectorLayer` クラスは、ジオメトリと属性データを格納する単一のシェープファイルレイヤーを表します。  
この手順ではベクターレイヤーを定義し、3つの属性を宣言します：テキストフィールド（`name`）、整数フィールド（`age`）、日時フィールド（`dob`）。日時属性の追加は **temporal GIS shapefile** 分析にとって重要です。

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## 手順 4: フィーチャーの追加
### ケース 1: 個別に値を設定
`SetValues` メソッドは、定義された順序で属性値をフィーチャーに割り当てます。  
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
ここでは2つのポイントを作成し、各属性を個別に設定し、レイヤーにフィーチャーを追加しています。

### ケース 2: すべての属性に新しい値を設定
あるいは、`SetValues` にオブジェクト配列を使用して、すべての属性値を一度に提供することもできます。  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
この方法では、オブジェクト配列を使って一度の呼び出しで全属性値を設定します—属性が多数ある場合に便利です。

## なぜこれが重要なのか？
プログラムでシェープファイルを作成すると、データパイプラインの自動化、テストデータセットの生成、またはGIS出力をウェブサービスに直接組み込むことが可能になります。Aspose.GISは **30+ vector and raster formats** をサポートし、ファイル全体をメモリに読み込むことなく数百ページにわたるシェープファイルを書き込めるため、速度とスケーラビリティの両方を提供します。

## よくある落とし穴とヒント
- **パス区切り文字:** 文字列結合の代わりに `Path.Combine` を使用して、クロスプラットフォーム互換性を確保してください。  
- **属性の順序:** `SetValues` の値の順序は、属性を追加した順序と一致する必要があります。  
- **日付の取り扱い:** GISデータをタイムゾーン間で共有する場合は、常に `DateTimeKind.Utc` を使用してください。

## 結論
おめでとうございます！Aspose.GIS for .NETを使用して新しいシェープファイルを正常に作成できました。このチュートリアルでは、プロジェクトの設定、ベクターレイヤーの定義、フィーチャーの追加（日時属性を含む）の基本をカバーしました。さらに詳しく学ぶ際は、[documentation](https://reference.aspose.com/gis/net/) を参照して高度な機能や機能性をご確認ください。

## よくある質問
**Q: Aspose.GISを他のプログラミング言語で使用できますか？**  
A: Aspose.GISは主に .NET をサポートしていますが、Java 用のバージョンも提供されています。  

**Q: 無料トライアルは利用可能ですか？**  
A: はい、無料トライアルは[here](https://releases.aspose.com/)から利用できます。  

**Q: Aspose.GIS のサポートはどこで得られますか？**  
A: コミュニティサポートやディスカッションは[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)をご覧ください。  

**Q: 一時ライセンスはどのように取得できますか？**  
A: 一時ライセンスは[here](https://purchase.aspose.com/temporary-license/)から取得できます。  

**Q: Aspose.GIS for .NET をどこで購入できますか？**  
A: ライブラリは[here](https://purchase.aspose.com/buy)から購入できます。  

---

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [レイヤー属性の取得 – Aspose.GIS for .NETでレイヤー属性情報を取得](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [ベクターレイヤーの作成とレイヤー空間参照系の設定](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [File GDBでベクターレイヤーを作成 – Aspose.GIS .NETチュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}