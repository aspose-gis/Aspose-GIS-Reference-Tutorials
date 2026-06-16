---
date: 2026-02-15
description: Aspose.GIS for .NET を使用してベクターレイヤーを作成し、円形ストリングジオメトリを追加する方法を学びましょう – GIS
  アプリケーションを迅速に構築する手段です。
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NETでベクターレイヤーと円形文字列を作成する
url: /ja/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

 final answer with only translated content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクターレイヤーと円形文字列ジオメトリの作成

## はじめに
.NET プラットフォーム上で GIS アプリケーションを構築する場合、最初のステップは通常、空間フィーチャーを格納する **ベクターレイヤー** オブジェクトを作成することです。Aspose.GIS for .NET はこのプロセスをシンプルにし、円形文字列などの高度なジオメトリでレイヤーを拡張できるようにします。このチュートリアルでは、**ベクターレイヤーの作成**、**円形文字列ジオメトリの追加**、そして結果を Shapefile として保存する方法を、クリーンで本番環境向けの C# コードを使って学びます。

## クイック回答
- **“ベクターレイヤーの作成” とは何ですか？** 空間フィーチャー（ポイント、ライン、ポリゴンなど）を保持できる新しいコンテナ（レイヤー）を作成します。  
- **円形文字列を表すクラスはどれですか？** `Aspose.Gis.Geometries` の `CircularString`。  
- **レイヤーを Shapefile として保存できますか？** はい – レイヤー作成時に `Drivers.Shapefile` を使用します。  
- **開発にライセンスは必要ですか？** 評価用の一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## “ベクターレイヤーの作成” とは？
ベクターレイヤーは、単一のデータソースに格納されたベクターフィーチャー（ポイント、ライン、ポリゴン）を論理的にグループ化したものです。Aspose.GIS では `VectorLayer.Create` を呼び出し、対象のファイルパスと使用するドライバー（例: Shapefile）を指定してレイヤーをインスタンス化します。レイヤーが作成されれば、フィーチャーの追加、ジオメトリの割り当て、空間操作を実行できます。

## なぜ円形文字列を追加するのか？
円形文字列は **線形ジオメトリ** の一種で、点のシーケンスを用いて弧を近似します。多数の小さなラインセグメントを使用せずに、曲線道路や川の曲がりなど、滑らかな曲線が必要なフィーチャーを表現するのに便利です。

## 前提条件
- **.NET Framework または .NET Core** がマシンにインストールされていること。  
- **Aspose.GIS for .NET** ライブラリ – 公式サイト **[here](https://releases.aspose.com/gis/net/)** からダウンロードしてください。  
- **Visual Studio** や **JetBrains Rider** などの IDE。  
- **C#** プログラミングの基本的な知識。

## 名前空間のインポート
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 手順ガイド

### 手順 1: 出力ファイルパスの定義
Set the location where the Shapefile will be written.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"` をシステム上の実際のフォルダー パスに置き換えてください。

### 手順 2: **ベクターレイヤーの作成**
Open a `VectorLayer` using the `Create` method. This is the core of the **create vector layer** operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 手順 3: 新しいフィーチャーの構築
A feature represents a single spatial record inside the layer.

```csharp
    var feature = layer.ConstructFeature();
```

### 手順 4: 円形文字列ジオメトリの構築
Add the points that define the curved shape. The sequence of points creates an arc that starts and ends at the same location, forming a closed circular string.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 手順 5: ジオメトリを割り当て、フィーチャーをレイヤーに追加
Link the geometry to the feature and store it in the layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` ブロックが終了すると、レイヤーは自動的にディスク上の Shapefile にフラッシュされます。

## よくある問題と解決策

| 問題 | 解決策 |
|-------|----------|
| **ファイルパスが無効** | ディレクトリが存在し、書き込み権限があることを確認してください。 |
| **CircularString が直線として表示される** | ポイントが正しい順序で追加されているか確認してください。閉じた形状の場合、最初と最後のポイントは同一である必要があります。 |
| **ライセンス例外** | 開発時に一時ライセンスを適用するか、本番使用のためにフルライセンスを購入してください。 |

## よくある質問

### Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？
はい、Aspose.GIS for .NET は .NET Framework 4.5 から最新の .NET 8 リリースまで、幅広い .NET バージョンで動作するよう設計されています。

### Aspose.GIS for .NET を他の GIS ライブラリと統合できますか？
もちろんです！他のライブラリでデータを読み取り、Aspose.GIS で操作し、再度書き戻すことが、柔軟な API により可能です。

### Aspose.GIS for .NET は空間データの可視化をサポートしていますか？
はい、ライブラリにはレンダリングユーティリティが含まれており、ジオメトリのマップやビジュアル表現を生成できます。

### Aspose.GIS for .NET に関するサポートを求められるコミュニティフォーラムはありますか？
はい、質問や経験を共有できる Aspose.GIS フォーラムは **[here](https://forum.aspose.com/c/gis/33)** にあります。

### Aspose.GIS for .NET の評価用に一時ライセンスを取得できますか？
もちろんです！評価用の一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から取得できます。

### 同じレイヤーにより複雑なジオメトリ（例: MultiLineString）を追加するには？
適切なジオメトリオブジェクト（例: `MultiLineString`）を作成し、個々の `LineString` オブジェクトで構成し、`feature.Geometry` に割り当てて、円形文字列と同様にフィーチャーを追加します。

## FAQ（クイックリファレンス）

**Q:** プログラムで **ベクターレイヤーの作成** を行うにはどうすればよいですか？  
**A:** `using` ブロック内で `VectorLayer.Create(path, Drivers.Shapefile)`（または別のドライバー）を呼び出します。

**Q:** 円形文字列にポイントを追加するメソッドは何ですか？  
**A:** 各座標に対して `circularString.AddPoint(x, y)` を使用します。

**Q:** 同じレイヤーに複数のジオメトリを保存できますか？  
**A:** はい、各ジオメトリごとに新しいフィーチャーを作成し、`layer.Add(feature)` で追加します。

**Q:** Shapefile が作成されない場合はどうすればよいですか？  
**A:** 出力ディレクトリが存在し、書き込み権限があり、ドライバー（`Drivers.Shapefile`）が正しく参照されていることを確認してください。

**Q:** 評価ビルドにライセンスは必要ですか？  
**A:** 開発・テストには一時ライセンスで十分ですが、本番環境ではフルライセンスが必要です。

## 結論
これらの手順に従うことで、Aspose.GIS for .NET を使用して **ベクターレイヤー** オブジェクトを作成し、**円形文字列** ジオメトリで拡張する方法が分かります。この基盤により、交通ネットワークのマッピング、環境データの可視化、カスタム空間分析ツールの開発など、よりリッチな GIS ソリューションを構築できます。

---

**最終更新日:** 2026-02-15  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}