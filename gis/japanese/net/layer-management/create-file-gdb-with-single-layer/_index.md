---
date: 2026-06-30
description: Aspose.GIS for .NET を使用して File Geodatabase にベクトルレイヤーを作成する方法を学びます。空間参照
  WGS84 と file gdb オプションで地理空間データを管理します。
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: 単一レイヤーで File GDB を作成
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: File GDBでベクトルレイヤーを作成 – Aspose.GIS .NET チュートリアル
url: /ja/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# File GDB でベクトルレイヤーを作成する

## はじめに
File Geodatabase（GDB）内に **ベクトルレイヤー** を作成し、ジオスペーシャルデータを効率的に管理したい場合、Aspose.GIS for .NET はクリーンなコードファーストアプローチを提供します。このステップバイステップガイドでは、ラインフィーチャの書き込み、File GDB オプションの設定、空間参照 WGS84 の使用方法を数行の C# で示します。最後まで実行すれば、レイヤー内のフィーチャ数をカウントし、作成した GDB を任意の .NET マッピングまたは解析ワークフローに統合できるようになります。

## クイック回答
- **「ベクトルレイヤーの作成」とは何ですか？** ジオデータベースファイルに新しいベクトルデータセット（ポイント、ライン、ポリゴン）を追加することを意味します。  
- **どのライブラリを使用すべきですか？** Aspose.GIS for .NET は File GDB の作成と編集をフルサポートします。  
- **開発用にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **空間参照を設定できますか？** はい – 一般的な WGS84 データムには `SpatialReferenceSystem.Wgs84` を使用します。  
- **コード行数はどれくらいですか？** GDB の作成、ラインフィーチャの追加、フィーチャ数の取得まで、30 行未満です。

## 「ベクトルレイヤーの作成」操作とは何ですか？
ベクトルレイヤーの作成は、ジオデータベース内に新しいテーブルを定義し、ジオメトリオブジェクト（ポイント、ライン、ポリゴン）とそれらの属性を格納することです。各行がフィーチャを表し、ジオメトリ列に形状が保持されます。Aspose.GIS では、`FileGdbDataSource` 内で `FeatureClass` をインスタンス化し、ジオメトリタイプを指定することで作成します。

## なぜ Aspose.GIS を使ってベクトルレイヤーを作成するのか？
Aspose.GIS は外部依存関係を排除し、**50 以上** の GIS フォーマットをサポートするため、.NET 開発者にとってワンストップソリューションです。  
標準でファイル GDB 圧縮（典型的なベクトルデータで最大 70 % の削減）、空間インデックス、完全な WGS84 ハンドリングを提供します。ライブラリは .NET Framework 4.6+、.NET Core 2.0+、および .NET 5/6 で動作し、追加のネイティブライブラリなしで最新の Windows またはクロスプラットフォーム環境を対象にできます。

## 前提条件
開始する前に、以下を用意してください。

1. **Aspose.GIS for .NET** – [Aspose.GIS for .NET ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロード。  
2. **.NET 開発環境** – Visual Studio、Rider、または `dotnet` CLI。  
3. **フォルダー** – File GDB を作成する場所（ここでは *Your Document Directory* と呼びます）。

## 名前空間のインポート
`using` 文は必要な型をスコープに持ち込みます。  

`Document` 名前空間はコア GIS オブジェクトを提供し、`System.IO` はファイルパスを扱います。

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
`"Your Document Directory"` を、File GDB を配置したい絶対パスに置き換えてください。  
事前にディレクトリを作成しておくことで、新規ユーザーが陥りやすい “File not found” エラーを防げます。

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: 単一レイヤーのファイルジオデータベースを作成する
`FileGdbOptions` は File Geodatabase の圧縮、空間インデックス、その他設定を構成できるクラスです。  
このスニペットは `FileGdbOptions` を使用して **ベクトルレイヤーを作成**し、シンプルなラインフィーチャを書き込み、**空間参照 WGS84** を使用する File GDB に保存します。

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

## ステップ 3: ファイルジオデータベースを開きレイヤー情報を取得する
`FileGdbDataSource` は File Geodatabase の作成とオープンのエントリーポイントです。  
`FeatureClass` はジオデータベース内のベクトルレイヤーを表し、フィーチャへのアクセスを提供します。  
ここではデータセットを開いて **レイヤー内のフィーチャ数をカウント**し、`1` が出力されます。

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## レイヤーが正しく作成されたかどうかを確認するには？
`FileGdbDataSource.Open` でジオデータベースを開き、`FeatureClass` をクエリします。`Count` プロパティがフィーチャ総数を返すため、ラインが永続化されたことを確認できます。この簡易検証ステップは、特に大量インポートを自動化する際に早期に問題を発見するのに役立ちます。

## 一般的な問題と解決策
| 問題 | 原因 | 対策 |
|------|------|------|
| **`File not found`** | `path` 変数が正しくない | `dataDir` が既存フォルダーを指しているか確認し、`path` が `Path.Combine(dataDir, "MyData.gdb")` のようにファイル名と結合されているか確認してください。 |
| **`Unsupported geometry`** | File GDB で許可されていないジオメトリタイプを使用 | 基本レイヤーでは `Point`、`LineString`、`Polygon` のみを使用してください。 |
| **`License not set`** | 本番環境で有効なライセンスが設定されていない | `License license = new License(); license.SetLicense("Aspose.GIS.lic");` でライセンスを登録してください。 |

## よくある質問
### 既存の .NET プロジェクトで Aspose.GIS for .NET を使用できますか？
はい、Aspose.GIS for .NET は既存の .NET プロジェクトにシームレスに統合できます。

### Aspose.GIS for .NET のトライアル版はありますか？
はい、[無料トライアル版](https://releases.aspose.com/) をダウンロードして機能をお試しいただけます。

### Aspose.GIS for .NET の詳細なドキュメントはどこで見つけられますか？
包括的な情報は [ドキュメンテーション](https://reference.aspose.com/gis/net/) を参照してください。

### Aspose.GIS for .NET のサポートはどこで受けられますか？
コミュニティサポートと支援は [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) で提供されています。

### Aspose.GIS for .NET の一時ライセンスは利用可能ですか？
はい、[一時ライセンス](https://purchase.aspose.com/temporary-license/) を取得できます。

---

**最終更新日:** 2026-06-30  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose

## 関連チュートリアル

- [Aspose.GIS を使用したファイルジオデータベース .NET データセットの作成](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [ベクトルレイヤーの作成とレイヤー空間参照系の設定](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Aspose.GIS を使用したファイル GDB データセットからレイヤーを削除する方法](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}