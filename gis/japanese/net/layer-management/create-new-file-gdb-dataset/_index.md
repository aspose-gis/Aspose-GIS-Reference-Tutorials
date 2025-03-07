---
title: 新しいファイル GDB データセットの作成
linktitle: 新しいファイル GDB データセットの作成
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET を探索して、GIS データセットを簡単に作成および管理します。シームレスな地理空間開発のために今すぐダウンロードしてください。 #アスポーズ #GIS
weight: 10
url: /ja/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新しいファイル GDB データセットの作成

## 導入
地理空間開発の分野では、Aspose.GIS for .NET は地理情報システム (GIS) データを管理および操作するための強力なツールキットとして際立っています。経験豊富な開発者であっても、GIS を使い始めたばかりであっても、このチュートリアルでは、Aspose.GIS for .NET を使用して新しいファイル ジオデータベース (GDB) データセットを作成するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.GIS for .NET: Aspose.GIS for .NET ライブラリがインストールされていることを確認してください。からダウンロードできます。[Aspose.GIS for .NET ダウンロード ページ](https://releases.aspose.com/gis/net/).
- 開発環境: Visual Studio などの互換性のある IDE を使用して開発環境をセットアップし、.NET プログラミングの基本を理解します。
- ドキュメント ディレクトリ: コード スニペット内の「ドキュメント ディレクトリ」を、GDB データセットを保存する適切なパスに置き換えます。
- C# に精通していること: このチュートリアルは、C# プログラミング言語に精通していることを前提としています。
## 名前空間のインポート
最初の手順では、.NET アプリケーションで Aspose.GIS 機能を利用するために必要な名前空間をインポートします。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## ステップ 1: 新しいファイル GDB データセットを作成する
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); //出力: 0
    //後続の手順に進みます...
}
```
説明: このステップでは、`Dataset.Create`方法。パスとドライバー (FileGdb) を指定して、ファイル ジオデータベースを作成します。コンソール出力には初期レイヤー数が表示されます。この時点ではゼロです。
## ステップ 2: Layer_1 を作成して設定する
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
説明: このステップには、データセット内に「layer_1」という名前のレイヤーを作成することが含まれます。これは、整数型の「value」という名前の属性を定義し、それぞれがポイント ジオメトリを持つ 10 個のフィーチャをレイヤーに設定します。
## ステップ 3: Layer_2 を作成して設定する
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
説明: ここでは、「layer_2」という名前の 2 番目のレイヤーを作成し、ラインストリングジオメトリを持つ 1 つのフィーチャを追加します。
## ステップ 4: 更新されたレイヤー数を確認する
```csharp
Console.WriteLine(dataset.LayersCount); //出力: 2
```
説明: 最後に、2 つのレイヤーを追加した後、更新されたレイヤー数を確認します。この場合、出力は 2 になるはずです。
## 結論
おめでとう！新しい File GDB データセットが正常に作成され、Aspose.GIS for .NET を使用してレイヤーが設定されました。このチュートリアルでは、.NET 環境での地理空間データの操作についての基礎を理解します。
## よくある質問
### Q: Aspose.GIS for .NET を他の GIS ライブラリと一緒に使用できますか?
Aspose.GIS for .NET はスタンドアロン ツールキットです。ただし、他の .NET ライブラリと統合して機能を強化することができます。
### Q: Aspose.GIS サポートのためのコミュニティ フォーラムはありますか?
はい、サポートとディスカッションを見つけることができます。[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33).
### Q: Aspose.GIS の一時ライセンスを取得するにはどうすればよいですか?
訪問[仮免許](https://purchase.aspose.com/temporary-license/)一時ライセンスの取得についてのページ。
### Q: 追加の例やドキュメントはありますか?
を探索してください[Aspose.GIS ドキュメント](https://reference.aspose.com/gis/net/)より多くの例と詳細情報については、こちらをご覧ください。
### Q: Aspose.GIS for .NET はどこで購入できますか?
 Aspose.GIS for .NET は、[購入ページ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
