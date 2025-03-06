---
title: 新しいシェープファイルの作成
linktitle: 新しいシェープファイルの作成
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を使用して新しいシェープファイルを作成する方法を学びます。ステップバイステップのガイドに従って、空間データ操作の力を解き放ちましょう。
weight: 12
url: /ja/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新しいシェープファイルの作成

## 導入
.NET を使用した地理情報システム (GIS) 開発を詳しく検討している場合は、Aspose.GIS が頼りになるソリューションです。この強力なライブラリにより、開発者は空間データをシームレスに操作できるようになります。このチュートリアルでは、Aspose.GIS for .NET を使用して新しいシェープファイルを作成するプロセスを説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語の基本的な理解。
- Visual Studio がマシンにインストールされていること。
-  .NET ライブラリ用の Aspose.GIS。ダウンロードできます[ここ](https://releases.aspose.com/gis/net/).
## 名前空間のインポート
まず、Aspose.GIS の機能を利用するために必要な名前空間をインポートします。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: プロジェクトをセットアップする
まず、Visual Studio で新しい C# プロジェクトを作成し、Aspose.GIS ライブラリを含めます。
## ステップ 2: ドキュメント ディレクトリを定義する
```csharp
string dataDir = "Your Document Directory";
```
「Your Document Directory」を、新しいシェープファイルを保存する実際のパスに置き換えます。
## ステップ 3: VectorLayer を作成する
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //機能を追加する前に属性を追加してください
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
このコード セグメントはベクター レイヤーを設定し、フィーチャの属性を定義します。
## ステップ 4: 機能を追加する
### ケース 1: 値を個別に設定する
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
### ケース 2: すべての属性に新しい値を設定する
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用して新しいシェープファイルが正常に作成されました。このチュートリアルでは、プロジェクトの設定、属性の定義、機能の追加の基本について説明しました。さらに詳しく調べる場合は、次を参照してください。[ドキュメンテーション](https://reference.aspose.com/gis/net/)高度な機能を備えています。
## よくある質問
### Q: Aspose.GIS を他のプログラミング言語で使用できますか?
Aspose.GIS は主に .NET をサポートしていますが、Java で利用できるバージョンもあります。
### Q: 無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Q: Aspose.GIS のサポートはどこで見つけられますか?
訪問[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)コミュニティのサポートとディスカッションのために。
### Q: 一時ライセンスを取得するにはどうすればよいですか?
仮免許を取得する[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.GIS for .NET はどこで購入できますか?
図書館を購入できます[ここ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
