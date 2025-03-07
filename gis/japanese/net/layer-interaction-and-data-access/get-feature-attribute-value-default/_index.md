---
title: フィーチャー属性値の取得 (デフォルト)
linktitle: フィーチャー属性値の取得 (デフォルト)
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET のパワーを解放してください!このステップバイステップのガイドを使用すると、フィーチャ属性値を簡単に取得して操作できます。今すぐ試用版をダウンロードしてください!
weight: 14
url: /ja/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# フィーチャー属性値の取得 (デフォルト)

## 導入
Aspose.GIS for .NET の世界へようこそ!この包括的なガイドでは、Aspose.GIS の強力な機能を使用してフィーチャ属性値を取得する複雑な仕組みについて詳しく説明します。経験豊富な開発者であっても、初心者であっても、このチュートリアルではステップバイステップのウォークスルーを提供し、この優れたツールの可能性を最大限に活用できるようにします。
## 前提条件
このコーディングの冒険に着手する前に、次の前提条件が満たされていることを確認してください。
- C# および .NET Framework に関する実践的な知識。
-  Aspose.GIS for .NET がインストールされています。そうでない場合は、からダウンロードしてください[ここ](https://releases.aspose.com/gis/net/).
- Visual Studio などのコード エディターでシームレスに操作できます。
## 名前空間のインポート
C# プロジェクトに、必要な名前空間を必ず含めてください。
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
ここで、それぞれの例を一連のわかりやすい手順に分けて見てみましょう。
## フィーチャー属性値の取得 (デフォルト)
### ステップ 1: 環境をセットアップする
まず、ドキュメント ディレクトリへのパスを定義します。
```csharp
string dataDir = "Your Document Directory";
```
### ステップ 2: GeoJson レイヤーを作成する
GeoJson レイヤーを作成し、デフォルト値を使用して属性を定義します。
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### ステップ 3: フィーチャを構築する
定義された属性を使用してフィーチャを構築します。
```csharp
    Feature feature = layer.ConstructFeature();
```
### ステップ 4: 値を取得する
さまざまなシナリオで属性値を取得します。
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); //値 == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); //値 == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); //値 == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## デフォルト値の設定
### ステップ 1: 別の GeoJson レイヤーを作成する
別の GeoJson レイヤーと double 属性を使用してプロセスを繰り返します。
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### ステップ 2: フィーチャーを構築する (再度)
```csharp
    Feature feature = layer.ConstructFeature();
```
### ステップ 3: 値の取得と設定
属性値を取得および設定し、デフォルトを示します。
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); //値 == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); //値 == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); //値 == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
おめでとう！フィーチャ属性値の取得と操作において、Aspose.GIS for .NET の機能をうまく活用することができました。
## 結論
このチュートリアルでは、Aspose.GIS for .NET を使用してフィーチャ属性値を取得する微妙な違いを検討しました。 Aspose.GIS は、直感的な API と堅牢な機能により、.NET 環境での GIS 開発の可能性の世界を開きます。
## よくある質問
### Aspose.GIS は .NET Core と互換性がありますか?
はい、Aspose.GIS は .NET Core と完全に互換性があり、クロスプラットフォーム サポートを提供します。
### Aspose.GIS を商用プロジェクトに使用できますか?
絶対に！ Aspose.GIS には商用ライセンスが付属しており、商用アプリケーションで制限なく使用できます。
### 追加のサポートやリソースはどこで入手できますか?
訪問[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)コミュニティのサポートを求めて、[ドキュメンテーション](https://reference.aspose.com/gis/net/)詳細な情報については。
### 無料トライアルはありますか?
はい、無料トライアルで Aspose.GIS を探索できます。ダウンロードしてください[ここ](https://releases.aspose.com/).
### テスト目的で一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスについては、次のサイトをご覧ください。[ここ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
