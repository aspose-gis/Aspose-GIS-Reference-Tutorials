---
date: 2026-01-05
description: Aspose.GIS for .NETで属性値を取得し、デフォルトを設定する方法を学びます。このステップバイステップガイドでは、GeoJSONレイヤーの作成とGISフィーチャの構築を示します。
linktitle: How to Get Attribute Value (Default)
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NETで属性値（デフォルト）を取得する方法
url: /ja/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspise.GIS for .NET を使用して属性値（デフォルト）を取得する方法

## はじめに
この包括的なチュートリアルでは、Aspose.GIS for .NET を使用して GIS フィーチャから **属性値を取得する方法** と、属性が存在しない場合のデフォルト値の扱い方を学びます。空間分析エンジンの構築やシンプルなマップビューアの作成など、属性取得とデフォルト処理をマスターすることは、信頼性の高い GIS アプリケーションにとって不可欠です。

## クイック回答
- **主要なメソッドは何ですか？** `Feature.GetValueOrDefault<T>()`  
- **カスタムデフォルトを設定できますか？** はい、デフォルト値を受け取るオーバーロードを使用するか、属性の `DefaultValue` を定義することで設定できます。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **サポートされているジオメトリ形式は？** GeoJSON、Shapefile、GML など、Aspose.GIS ドライバを通じて多数の形式をサポートしています。  
- **.NET Core/.NET 6+ でも動作しますか？** はい、ライブラリはクロスプラットフォームです。

## 前提条件
本題に入る前に、以下が揃っていることを確認してください：

- C# と .NET エコシステムの基本的な知識  
- Aspose.GIS for .NET がインストールされていること。まだの場合は、[here](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
- Visual Studio や Visual Studio Code などのコードエディタ  

## 名前空間のインポート
C# ファイルに必要な `using` 文を追加して、API の型を利用できるようにします：

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

それでは、各例をステップバイステップで見ていきましょう。

## 属性値（デフォルト）を取得する方法
### 手順 1: 環境の設定
テストドキュメントが格納されているフォルダーへのパスを定義します：

```csharp
string dataDir = "Your Document Directory";
```

### 手順 2: GeoJSON レイヤーの作成
**geojson レイヤーを作成**します — ここで、null もしくは未設定になり得る属性を定義します：

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```

### 手順 3: GIS フィーチャの構築
次に **GIS フィーチャを構築**します — これにより、先ほど定義した属性スキーマを遵守した新しいフィーチャ インスタンスが得られます：

```csharp
    Feature feature = layer.ConstructFeature();
```

### 手順 4: 値の取得
最後に、いくつかのシナリオで **フィーチャ属性を取得**し、デフォルトがどのように機能するかを示します：

```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // value == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // value == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // value == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```

## デフォルト値の設定方法
### 手順 1: 別の GeoJSON レイヤーを作成
今回はスキーマ上で **属性のデフォルトを設定**します：

```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```

### 手順 2: GIS フィーチャを再度構築
```csharp
    Feature feature = layer.ConstructFeature();
```

### 手順 3: 値の取得と設定
デフォルトを取得し、実行時に **デフォルトの設定方法** の効果を確認するために変更します：

```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // value == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // value == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // value == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```

## よくある落とし穴とヒント
- **`using` ブロックの閉鎖を忘れないでください。** レイヤーは自動的に破棄され、ファイルハンドルが解放されます。  
- **`CanBeNull` が false の場合、`GetValueOrDefault` は常に値を返します**（格納された値または定義されたデフォルトのいずれか）。  
- **ジェネリックオーバーロード**（`GetValueOrDefault<T>`）を使用して、値型のボクシング/アンボクシングを回避してください。  
- **プロのコツ:** 属性が実際に設定されているか確認したい場合は、`GetValueOrDefault` を呼び出す前に `feature.IsAttributeSet("attribute")` を使用してください。  

## よくある質問
### Aspose.GIS は .NET Core と互換性がありますか？
はい、Aspose.GIS は .NET Core と完全に互換性があり、クロスプラットフォームのサポートを提供します。

### 商用プロジェクトで Aspose.GIS を使用できますか？
もちろんです！ Aspose.GIS には商用ライセンスが付属しており、制限なく商用アプリケーションで使用できます。

### 追加のサポートやリソースはどこで見つけられますか？
コミュニティサポートは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) を、詳細情報は [ドキュメント](https://reference.aspose.com/gis/net/) をご覧ください。

### 無料トライアルは利用できますか？
はい、無料トライアルで Aspose.GIS をお試しいただけます。ダウンロードは [here](https://releases.aspose.com/) から。

### テスト目的の一時ライセンスはどう取得しますか？
一時ライセンスは [here](https://purchase.aspose.com/temporary-license/) から取得してください。

## 追加の FAQ
**Q: 存在しない属性に対して `GetValueOrDefault` を呼び出した場合はどうなりますか？**  
A: メソッドは `ArgumentException` をスローします。必ず属性名を確認するか、まず `feature.HasAttribute("name")` を使用してください。

**Q: レイヤー作成後にデフォルト値を変更できますか？**  
A: はい、`attribute.DefaultValue` を変更し、`layer.UpdateAttribute(attribute)` を呼び出すことで変更を永続化できます。

**Q: Aspose.GIS は属性値の一括更新をサポートしていますか？**  
A: フィーチャ コレクションを反復処理し、各フィーチャで `SetValue` を呼び出すことができます。大規模データセットの場合は、パフォーマンス向上のために `FeatureCursor` API の使用を検討してください。

## 結論
本ガイドでは **属性値の取得方法**、デフォルトの定義と上書き方法、そしてアプリケーションの要件に合わせた **GeoJSON レイヤー** スキーマの作成方法を解説しました。これらのテクニックを活用すれば、欠損データやオプションデータを柔軟に扱える堅牢な GIS ソリューションを構築できます。

---

**最終更新日:** 2026-01-05  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}