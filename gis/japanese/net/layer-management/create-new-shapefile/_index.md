---
date: 2026-01-13
description: Aspose.GIS for .NET を使用して新しいシェープファイルを作成する方法を学びましょう。このステップバイステップガイドでは、ベクターレイヤーの定義、日付属性の追加、空間データの管理方法を示します。
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: 新しいシェープファイルを作成
url: /ja/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新しいシェープファイルの作成

## はじめに
.NET で地理情報システム（GIS）開発に取り組むなら、Aspose.GIS が最適なソリューションです。この強力なライブラリは開発者が空間データをシームレスに扱えるようにし、本チュートリアルでは Aspose.GIS for .NET を使用して **新しいシェープファイルを作成**する方法をご案内します。ベクターレイヤーの定義や日付属性の追加が、堅牢な GIS プロジェクトにとって重要なステップである理由も解説します。

## クイック回答
- **このチュートリアルで学べることは？** 新しいシェープファイルの作成、ベクターレイヤーの定義、属性（日時フィールドを含む）の追加方法。  
- **必要なライブラリは？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 学習目的なら無料トライアルで可。商用利用には商用ライセンスが必要です。  
- **使用する IDE は？** Visual Studio（最新バージョンで可）。  
- **実装にかかる時間は？** 基本的な例で約 10‑15 分。

## 前提条件
チュートリアルに入る前に、以下の前提条件を満たしていることを確認してください。
- C# プログラミング言語の基本的な理解。  
- マシンに Visual Studio がインストールされていること。  
- Aspose.GIS for .NET ライブラリ。ダウンロードは [こちら](https://releases.aspose.com/gis/net/)。

## 名前空間のインポート
Aspose.GIS の機能を利用するために、必要な名前空間をインポートします。

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順 1: プロジェクトのセットアップ
Visual Studio で新しい C# プロジェクトを作成し、Aspose.GIS ライブラリを追加します。

## 手順 2: ドキュメントディレクトリの定義
```csharp
string dataDir = "Your Document Directory";
```
*Your Document Directory* を、作成したシェープファイルを保存したい実際のパスに置き換えてください。

## 手順 3: VectorLayer の作成
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
このコードは **ベクターレイヤーを定義**し、3 つの属性（テキスト フィールド `name`、整数フィールド `age`、日時フィールド `dob`）を宣言します。日時属性の追加は、時間的な GIS 分析にとって重要です。

## 手順 4: フィーチャの追加
### ケース 1: 個別に値を設定
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
ここでは 2 つのポイントを作成し、各属性を別々に設定してレイヤーに追加しています。

### ケース 2: すべての属性に対して新しい値を一括設定
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
この方法では、オブジェクト配列を使ってすべての属性値を一度に設定します。属性が多数ある場合に便利です。

## なぜ重要か
プログラムからシェープファイルを作成できれば、データパイプラインの自動化、テストデータセットの生成、あるいは GIS 出力を直接ウェブサービスに統合することが可能になります。Aspose.GIS で **シェープファイルの作成方法** をマスターすれば、フィーチャジオメトリ、属性スキーマ、ファイル形式の準拠性を完全にコントロールできます。

## よくある落とし穴とヒント
- **パス区切り文字:** 文字列結合ではなく `Path.Combine` を使用して、クロスプラットフォーム互換性を確保してください。  
- **属性の順序:** `SetValues` に渡す値の順序は、属性を追加した順序と一致させる必要があります。  
- **日付の取り扱い:** GIS データをタイムゾーン間で共有する場合は、常に `DateTimeKind.Utc` を使用してください。

## 結論
おめでとうございます！Aspose.GIS for .NET を使用して新しいシェープファイルの作成に成功しました。このチュートリアルでは、プロジェクトのセットアップ、ベクターレイヤーの定義、フィーチャの追加（日時属性を含む）という基本的な流れを解説しました。さらに詳しい機能や高度な使い方については、[ドキュメント](https://reference.aspose.com/gis/net/)をご参照ください。

## FAQ（よくある質問）
### Q: 他のプログラミング言語でも Aspose.GIS を使用できますか？
Aspose.GIS は主に .NET 向けですが、Java 用のバージョンも提供されています。  

### Q: 無料トライアルはありますか？
はい、無料トライアルは [こちら](https://releases.aspose.com/) から入手できます。  

### Q: Aspose.GIS のサポートはどこで受けられますか？
コミュニティサポートやディスカッションは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) で行われています。  

### Q: 一時ライセンスはどう取得できますか？
一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。  

### Q: Aspose.GIS for .NET を購入するには？
ライブラリの購入は [こちら](https://purchase.aspose.com/buy) から可能です。

---

**最終更新日:** 2026-01-13  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}