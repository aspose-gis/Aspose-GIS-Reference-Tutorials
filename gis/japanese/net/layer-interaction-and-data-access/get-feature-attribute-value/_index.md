---
title: フィーチャー属性値の取得
linktitle: フィーチャー属性値の取得
second_title: Aspose.GIS .NET API
description: シームレスな GIS データ統合のための究極のツールである Aspose.GIS for .NET を探索してください。今すぐ無料トライアルをダウンロードしてください! #Aspose #GIS #.NET
weight: 12
url: /ja/net/layer-interaction-and-data-access/get-feature-attribute-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# フィーチャー属性値の取得

## 導入
Aspose.GIS for .NET の世界へようこそ。これは、.NET 開発者が地理情報システム (GIS) データをシームレスに操作できるようにする強力なライブラリです。経験豊富な開発者であっても、GIS を使い始めたばかりであっても、このチュートリアルでは、Aspose.GIS for .NET を使用してフィーチャ属性値を取得するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- .NET 開発の基本的な理解。
- Visual Studio がマシンにインストールされていること。
-  Aspose.GIS for .NET ライブラリ。[ダウンロードリンク](https://releases.aspose.com/gis/net/).
- GIS の概念と用語に精通していること。
## 名前空間のインポート
プロジェクトを開始するには、必要な名前空間をインポートしていることを確認してください。この手順は、Aspose.GIS for .NET が提供する機能にアクセスするために重要です。コードに次の名前空間を含めます。
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## チュートリアル: フィーチャー属性値の取得
## ステップ 1: プロジェクトをセットアップする
Visual Studio で新しい .NET プロジェクトを作成し、Aspose.GIS ライブラリを参照します。
## ステップ 2: ドキュメント ディレクトリを定義する
ドキュメント ディレクトリへのパスを設定します。これは、シェープファイル (InputShapeFile.shp) がある場所です。
```csharp
string dataDir = "Your Document Directory";
```
## ステップ 3: ベクターレイヤーを開く
Aspose.GIS を使用してベクター レイヤーを開きます。必ずドライバー (この場合は Shapefile ドライバー) を指定してください。
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    //ベクターレイヤーを処理するためのコードはここにあります
}
```
## ステップ 4: フィーチャー属性値を取得する
次に、レイヤー内の各フィーチャをループして属性値を取得します。 Aspose.GIS は、値をフェッチするさまざまな方法を提供します。
### ケース 1: 明示的な型キャスト
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    string nameValue = feature.GetValue<string>("name"); //属性名は大文字と小文字が区別されます
    int ageValue = feature.GetValue<int>("age");
    string dobValue = feature.GetValue<DateTime>("dob").ToString();
    Console.WriteLine("Attribute value for feature #{0} is: {1}, {2}", nameValue, ageValue, dobValue);
}
```
### ケース 2: 動的型キャスト
```csharp
for (int i = 0; i < layer.Count; i++)
{
    Feature feature = layer[i];
    Console.WriteLine("Entry {0} information\n ========================", i);
    var objName = feature.GetValue("name"); //属性名は大文字と小文字が区別されます
    var objAge = feature.GetValue("age");
    var objDob = feature.GetValue("dob");
    Console.WriteLine("Attribute object for feature #{0} is: {1}, {2}", objName, objAge, objDob);
}
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用してフィーチャ属性値を取得する方法を学習しました。このチュートリアルでは、GIS 機能を .NET アプリケーションにシームレスに統合するための基礎的な知識を習得しました。
## よくある質問
### Q: Aspose.GIS は初心者と経験豊富な開発者の両方に適していますか?
A: もちろんです！ Aspose.GIS は、あらゆるスキル レベルの開発者に対応し、GIS データ操作のための直感的な API を提供します。
### Q: Aspose.GIS を商用プロジェクトで使用できますか?
 A: はい、Aspose.GIS は商用製品です。ライセンスの詳細については、[購入ページ](https://purchase.aspose.com/buy).
### Q: 一時ライセンスはテスト目的で利用できますか?
 A: はい、テスト用の一時ライセンスを次のサイトから取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.GIS のコミュニティ サポートはどこで見つけられますか?
 A: に関するディスカッションに参加してください。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)助けを求めたり、他のユーザーとつながったりするため。
### Q: Aspose.GIS の無料試用版はありますか?
 A：確かに！以下から無料試用版をダウンロードして、Aspose.GIS の機能を探索できます。[ここ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
