---
date: 2026-01-10
description: Aspose.GIS for .NET を使用して、ファイルジオデータベースにベクターレイヤーを作成する方法を学びましょう。空間参照 WGS84
  とファイル GDB オプションで地理空間データを管理します。
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: File GDBでベクターレイヤーを作成 – Aspose.GIS .NET チュートリアル
url: /ja/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# File GDB でベクターレイヤーを作成する

## はじめに
File Geodatabase (GDB) 内に **ベクターレイヤーを作成** し、ジオスペーシャルデータを効率的に管理したい場合、Aspose.GIS for .NET はクリーンなコードファーストアプローチを提供します。このステップバイステップガイドでは、ラインフィーチャを書き込み、File GDB オプションを設定し、空間参照 WGS84 を使用する方法を数行の C# で示します。最後にはレイヤー内のフィーチャ数をカウントし、作成した GDB を任意の .NET マッピングまたは解析ワークフローに統合できるようになります。

## クイック回答
- **「ベクターレイヤーを作成」とは何ですか？** 新しいベクターデータセット（ポイント、ライン、ポリゴン）をジオデータベースファイルに追加することを意味します。  
- **どのライブラリを使用すべきですか？** Aspose.GIS for .NET が File GDB の作成と編集をフルサポートします。  
- **開発にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **空間参照を設定できますか？** はい – 一般的な WGS84 データムには `SpatialReferenceSystem.Wgs84` を使用します。  
- **コード行数はどれくらいですか？** GDB の作成、ラインフィーチャの追加、フィーチャ数の取得まで、30 行未満です。

## 「ベクターレイヤーを作成」操作とは何ですか？
ベクターレイヤーを作成することは、ジオデータベース内に新しいテーブルを定義し、幾何オブジェクト（ポイント、ライン、ポリゴン）とそれらの属性を格納できるようにすることです。この操作は **ジオスペーシャルデータを管理** するすべての GIS ベースアプリケーションの基盤となります。

## なぜ Aspose.GIS を使用してベクターレイヤーを作成するのか？
- **外部依存関係ゼロ** – API は .NET Framework、.NET Core、.NET 5/6 でそのまま動作します。  
- **File GDB のフルサポート** – `FileGdbOptions` で圧縮や空間インデックスなどを制御できます。  
- **組み込みの空間参照処理** – `SpatialReferenceSystem.Wgs84` を渡すだけでグローバル座標系で作業できます。  
- **シンプルな API** – ラインフィーチャを書き込み、レイヤーに追加し、数行のメソッド呼び出しでフィーチャ数を取得できます。

## 前提条件
開始する前に、以下を用意してください。

1. **Aspose.GIS for .NET** – [Aspose.GIS for .NET ダウンロードページ](https://releases.aspose.com/gis/net/) から取得。  
2. **.NET 開発環境** – Visual Studio、Rider、または `dotnet` CLI。  
3. **フォルダー** – File GDB を作成する場所（ここでは *Your Document Directory* と呼びます）。

## 名前空間のインポート
C# ファイルの先頭に必要な `using` 文を追加します。

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

## ステップ 1: ドキュメントディレクトリの設定
```csharp
string dataDir = "Your Document Directory";
```
`"Your Document Directory"` を、File GDB を配置したい絶対パスに置き換えてください。

## ステップ 2: 単一レイヤーのファイルジオデータベースを作成する
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
このスニペットは `FileGdbOptions` を使用して **ベクターレイヤーを作成** し、シンプルなラインフィーチャを書き込み、**空間参照 WGS84** を使用した File GDB に保存します。

## ステップ 3: ファイルジオデータベースを開き、レイヤー情報を取得する
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
ここではデータセットを開いて **フィーチャ数をカウント** し、`1` が出力されます。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **`File not found`** | `path` 変数が間違っている | `dataDir` が既存フォルダーを指しているか確認し、`path` が `Path.Combine(dataDir, "MyData.gdb")` のようにファイル名と結合されているか確認してください。 |
| **`Unsupported geometry`** | File GDB で許可されていないジオメトリタイプを使用している | 基本レイヤーでは `Point`、`LineString`、`Polygon` のみを使用してください。 |
| **`License not set`** | 本番環境で有効なライセンスが設定されていない | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` でライセンスを登録してください。 |

## よくある質問
### 既存の .NET プロジェクトで Aspose.GIS for .NET を使用できますか？
はい、Aspose.GIS for .NET は既存の .NET プロジェクトにシームレスに統合できます。

### Aspose.GIS for .NET のトライアル版はありますか？
はい、[無料トライアル版](https://releases.aspose.com/) をダウンロードして機能をお試しいただけます。

### Aspose.GIS for .NET の詳細なドキュメントはどこにありますか？
包括的な情報は [ドキュメント](https://reference.aspose.com/gis/net/) を参照してください。

### Aspose.GIS for .NET のサポートはどこで受けられますか？
コミュニティサポートや支援は [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でご利用いただけます。

### Aspose.GIS for .NET の一時ライセンスはありますか？
はい、[一時ライセンス](https://purchase.aspose.com/temporary-license/) を取得できます。

---

**最終更新日:** 2026-01-10  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}