---
title: GIS マスタリー - Aspose.GIS for .NET を使用して GDB にレイヤーを追加する
linktitle: ファイル GDB データセットにレイヤーを追加
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET で GIS の力を解き放ちましょう!このステップバイステップのチュートリアルで、ファイル GDB データセットにレイヤーを追加する方法を学習します。 #地理データ #Aspose #GIS
weight: 16
url: /ja/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GIS マスタリー - Aspose.GIS for .NET を使用して GDB にレイヤーを追加する

## 導入
Aspose.GIS for .NET を使用して GIS 機能を強化する準備はできていますか?このステップバイステップ ガイドでは、ファイル ジオデータベース (GDB) データセットにレイヤーを追加するプロセスについて説明します。 Aspose.GIS for .NET は、地理情報を操作するための強力な機能を提供しており、このチュートリアルを使用すると、追加のレイヤーをデータセットにシームレスに統合できるようになります。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.GIS for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.GIS for .NET ドキュメント](https://reference.aspose.com/gis/net/).
- ドキュメント ディレクトリ: GIS 関連ファイルを保存および管理するために、マシン上に専用のドキュメント ディレクトリを作成します。
## 名前空間のインポート
.NET プロジェクトでは、Aspose.GIS 機能にアクセスするために必要な名前空間をインポートしてください。次のコード スニペットを使用します。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: ディレクトリをコピーする
続行する前に、GDB データセットを含むディレクトリを複製します。このステップにより、元のデータセットがそのまま残ることが保証されます。提供されたコード スニペットを使用します。
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## ステップ 2: データセットを開いて作成機能を確認する
複製したデータセットを開いて、レイヤーを作成できるかどうかを確認します。これは、次の存在によって確認されます。`True`コンソール出力で。
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); //真実
```
## ステップ 3: 新しいレイヤーを作成して設定する
データセット内に新しいレイヤーを作成し、その空間参照系、属性、サンプル フィーチャを定義します。このコード スニペットはプロセスを示しています。
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## ステップ 4: 追加されたレイヤーを開いて検証する
作成したばかりのレイヤーを開いて、そのコンテンツを検証します。次のコードを使用して、カウントを確認し、属性値を取得します。
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); //1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // 「名前_1」
}
```
## 結論
おめでとう！ Aspose.GIS for .NET を使用してファイル GDB データセットにレイヤーを追加する方法を学習しました。これらの新たなスキルを使用すると、GIS プロジェクト内の地理データを効率的に操作できます。
## よくある質問
### Q: Aspose.GIS for .NET を他の GIS ライブラリと一緒に使用できますか?
Aspose.GIS for .NET は独立して動作するように設計されていますが、他のライブラリと統合して機能を強化することができます。
### Q: 一時ライセンスはテスト目的で利用できますか?
はい、次から一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/)テストと評価用。
### Q: Aspose.GIS for .NET はどのような空間参照系をサポートしていますか?
Aspose.GIS for .NET は幅広い空間参照系をサポートし、地理データの処理に柔軟性をもたらします。
### Q: Aspose.GIS コミュニティに貢献できますか?
絶対に！ディスカッションに参加して、あなたの経験を共有してください[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33).
### Q: Aspose.GIS for .NET の詳細なドキュメントはどこで見つけられますか?
包括的なドキュメントを調べる[ここ](https://reference.aspose.com/gis/net/)Aspose.GIS for .NET の詳細については、「Aspose.GIS for .NET」を参照してください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
