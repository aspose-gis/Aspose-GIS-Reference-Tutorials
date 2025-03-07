---
title: 単一レイヤーのファイル GDB を作成する
linktitle: 単一レイヤーのファイル GDB を作成する
second_title: Aspose.GIS .NET API
description: Aspose.GIS を使用して、.NET での地理空間データ管理の可能性を解き放ちます。ファイル ジオデータベースとレイヤーを作成する方法を段階的に学習します。ダウンロード中！
weight: 11
url: /ja/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 単一レイヤーのファイル GDB を作成する

## 導入
堅牢なファイル ジオデータベースとレイヤーを使用して地理空間アプリケーションを強化する準備はできていますか? Aspose.GIS for .NET 以外に探す必要はありません。このチュートリアルでは、Aspose.GIS for .NET を使用して単一レイヤーのファイル ジオデータベース (GDB) を作成するプロセスを説明します。 .NET アプリケーションで空間データの管理と視覚化の機能を簡単に活用できます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.GIS for .NET: Aspose.GIS ライブラリがインストールされていることを確認してください。からダウンロードできます。[Aspose.GIS for .NET ダウンロード ページ](https://releases.aspose.com/gis/net/).
2. 開発環境: マシン上に動作する .NET 開発環境をセットアップします。
3. ドキュメント ディレクトリ: 地理空間データ ファイルを保存するシステム上のディレクトリを選択または作成します。
## 名前空間のインポート
まず、必要な名前空間を .NET プロジェクトにインポートする必要があります。これらの名前空間は、Aspose.GIS 機能へのアクセスを提供します。コード ファイルの先頭に次の行を追加します。
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
```
「Your Document Directory」を、地理空間データ ファイルを保存するディレクトリへのパスに置き換えます。
## ステップ 2: 単一レイヤーのファイル ジオデータベースを作成する
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
このコード スニペットは、単一レイヤーを持つファイル ジオデータベースを作成し、それにライン フィーチャを追加します。
## ステップ 3: ファイル ジオデータベースを開いてレイヤー情報を取得する
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); //出力: 特徴数: 1
}
```
このステップでは、作成されたファイル ジオデータベースを開き、「layer」という名前のレイヤーを取得し、レイヤー内のフィーチャの数を出力します。
## 結論
おめでとう！ Aspose.GIS for .NET を使用して、単一レイヤーのファイル ジオデータベースが正常に作成されました。アプリケーションでの空間データ管理の膨大な機能を簡単に探索できます。
## よくある質問
### 既存の .NET プロジェクトで Aspose.GIS for .NET を使用できますか?
はい、Aspose.GIS for .NET は既存の .NET プロジェクトにシームレスに統合できます。
### Aspose.GIS for .NET の試用版はありますか?
はい、Aspose.GIS for .NET の機能を調べるには、[無料試用版](https://releases.aspose.com/).
### Aspose.GIS for .NET の詳細なドキュメントはどこで見つけられますか?
を参照してください。[ドキュメンテーション](https://reference.aspose.com/gis/net/) Aspose.GIS for .NET に関する包括的な情報については、「Aspose.GIS for .NET」を参照してください。
### Aspose.GIS for .NET のサポートを受けるにはどうすればよいですか?
訪問[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33)コミュニティのサポートと支援のために。
### Aspose.GIS for .NET の一時ライセンスは利用できますか?
はい、入手できます[仮免許](https://purchase.aspose.com/temporary-license/) Aspose.GIS for .NET の場合。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
