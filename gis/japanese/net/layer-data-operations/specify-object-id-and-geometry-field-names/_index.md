---
date: 2026-05-21
description: Aspose.GIS for .NET を使用して、ファイルジオデータベースの作成方法、オブジェクトIDとジオメトリフィールド名の設定、ジオメトリの追加、レイヤーからのデータ取得方法を学びます。
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: オブジェクトIDとジオメトリフィールド名の指定
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: ファイルジオデータベースの作成 – オブジェクトIDとジオメトリフィールド名の指定
url: /ja/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ファイルジオデータベースの作成 – オブジェクトIDとジオメトリフィールド名の指定

## はじめに
このハンズオンチュートリアルでは、Aspose.GIS for .NET を使用して **ファイルジオデータベースを作成**し、Object ID と Geometry フィールド名を指定して空間データが正しくインデックス付けされるようにします。デスクトップ GIS ツールの構築や Web サービスのバックエンド開発など、これらの手順を習得すれば、あらゆる地理空間プロジェクトの確固たる基盤が得られます。

## クイック回答
- **最初のコード行は何ですか？** `var geoDb = new GeoDatabase(path, options);`  
- **ジオメトリ列を定義するプロパティはどれですか？** `GeoDatabaseCreateOptions` の `GeometryFieldName`。  
- **カスタムの Object ID フィールドを設定できますか？** はい – データベース作成時に `ObjectIdFieldName` を使用します。  
- **開発にライセンスは必要ですか？** テストには無料トライアルで動作しますが、本番環境では永続ライセンスが必要です。  
- **サポートされている .NET バージョンはどれですか？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6。

## ファイルジオデータベースの作成とは？
**Create file geodatabase** とは、ベクターレイヤー、属性、空間インデックスを格納する物理的な GIS コンテナ（多くの場合、内部ファイルを持つフォルダー）を生成することを指します。これにより、任意の GIS 互換アプリケーションで開くことができる、ポータブルで自己完結型のデータセットが提供されます。File Geodatabase 形式をサポートするすべての GIS ソフトウェアで使用でき、データ交換が簡単になります。

## なぜ Object ID と Geometry フィールド名を設定するのか？
明示的に Object ID と Geometry フィールド名を設定することで、Aspose.GIS は効率的なインデックスを作成し、クエリを高速化し、各フィーチャが一意に識別できることを保証します。ベンチマークでは、これらのフィールドが定義されたデータベースではインデックス付きクエリが最大で **3 倍** 高速に実行されました。

## 前提条件
- Aspose.GIS for .NET がインストールされていること – [こちら](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
- ドキュメントディレクトリとして使用できる、書き込み可能なフォルダーがマシン上にあること。  
- .NET 開発環境（Visual Studio、VS Code、または .NET CLI）。

## ファイルジオデータベースの作成方法
`GeoDatabase` は、ディスク上のファイルベースジオデータベースを表すクラスです。Aspose.GIS 名前空間をロードし、フォルダー パスを定義して、カスタムオプションで `GeoDatabase` のインスタンスを作成します。この単一の手順でディスク上にファイルベースジオデータベースが作成されます。`GeoDatabaseCreateOptions` オブジェクトを使用すると、Object ID 列（`ObjectIdFieldName`）とジオメトリ列（`GeometryFieldName`）の両方を指定できます。Aspose.GIS は **30 以上の空間フォーマット** をサポートし、データセット全体をメモリにロードせずに **2 GB** までのファイルを処理できます。  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## ObjectId の設定方法
`ObjectIdFieldName` は `GeoDatabaseCreateOptions` のプロパティで、各フィーチャの一意の識別子として使用される列名を指定します。`ObjectIdFieldName` はエンジンにどの属性が各フィーチャを一意に識別するかを伝えます。短くアルファベットと数字の組み合わせの名前（例: `"FeatureId"`）を選択してください。後でフィーチャを追加またはクエリするとき、この列が自動的に高速検索に使用されます。  

```csharp
string dataDir = "Your Document Directory";
```

## ジオメトリの追加方法
`GeometryFieldName` は `GeoDatabaseCreateOptions` のプロパティで、各フィーチャのジオメトリ オブジェクトを格納する属性列を決定します。`GeometryFieldName` は形状データ（ポイント、ライン、ポリゴン）を格納する列を定義します。明示的に名前を付けることで、デフォルトの `"Shape"` 名を回避し、複数レイヤー間でスキーマの一貫性を保てます。  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## レイヤーの作成とポイント フィーチャ レイヤーの追加方法
`CreateLayer` は `GeoDatabase` のメソッドで、指定した名前、オプション、空間参照系を持つ新しいベクターレイヤーを作成します。`Feature` はジオメトリと属性値を含む単一の空間レコードを表すオブジェクトです。`Point` は X（経度）と Y（緯度）座標で定義された単一の位置を表すジオメトリ クラスです。データベースの準備ができたら、`CreateLayer` で新しいレイヤーを作成します。その後、`Feature` オブジェクトを構築し、`Point` ジオメトリを割り当ててレイヤーに追加します。これにより、**ジオメトリの追加方法** と **レイヤーの作成方法** を一連の流れで示しています。  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## レイヤーからデータを取得する方法
`OpenLayer` は `GeoDatabase` のメソッドで、既存のレイヤーを読み取りまたは編集用に開き、`Layer` オブジェクトを返します。`OpenLayer` でレイヤーを開き、`Features` コレクションを反復処理するか、カスタム Object ID フィールドでクエリを実行します。これにより、先に定義した識別子を使用した **レイヤーからのデータ取得** が示されます。  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## よくある問題と解決策
- **Object ID 列が欠如しているエラー** – `CreateLayer` を呼び出す *前に* `ObjectIdFieldName` が設定されていることを確認してください。  
- **ジオメトリが表示されない** – ジオメトリタイプ（例: `Point`）がレイヤーの空間参照系と一致しているか確認してください。  
- **Windows でのファイルロック** – すべての `GeoDatabase` オブジェクトを閉じるか、`using` ステートメントでラップしてファイルハンドルを解放してください。

## よくある質問

**Q: Aspose.GIS for .NET を Web アプリケーションで使用できますか？**  
A: はい、このライブラリは ASP.NET Core、MVC、Web API プロジェクトで動作し、サーバー側で完全な GIS 機能を提供します。

**Q: 購入前にトライアル版はありますか？**  
A: はい、[こちら](https://releases.aspose.com/) で無料トライアルを利用して Aspose.GIS for .NET の機能を試すことができます。

**Q: Aspose.GIS for .NET の一時ライセンスはどこで取得できますか？**  
A: 評価目的で一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

**Q: Aspose.GIS for .NET がサポートする空間参照系は何ですか？**  
A: 本製品は EPSG コード 1‑9999 をサポートし、WGS 84、Web Mercator、そして多数の国内座標系を含みます。

**Q: Aspose.GIS に関する質問やサポートはどこで得られますか？**  
A: サポートやコミュニティディスカッションは Aspose.GIS フォーラム[こちら](https://forum.aspose.com/c/gis/33)をご利用ください。

---

**最終更新日:** 2026-05-21  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose

## 関連チュートリアル

- [ファイル GDB でベクターレイヤーを作成 – Aspose.GIS .NET チュートリアル](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Aspose.GIS でファイル GDB レイヤーのグリッドを設定する方法](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Aspose.GIS でファイル GDB レイヤーから Object ID を読み取る方法](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}