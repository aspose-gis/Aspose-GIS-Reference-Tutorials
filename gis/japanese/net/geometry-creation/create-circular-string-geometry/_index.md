---
date: 2025-12-12
description: Aspose.GIS for .NET を使用してベクトルレイヤーを作成し、円形ストリングジオメトリを追加する方法を学びましょう — GIS
  アプリケーションを迅速に構築する手段です。
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NETでベクターレイヤーと円形ストリングを作成する
url: /ja/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したベクトルレイヤーと円形文字列ジオメトリの作成

## はじめに
.NET プラットフォーム上で GIS アプリケーションを構築する場合、最初のステップは **ベクトルレイヤーを作成** して空間フィーチャを格納することが多いです。Aspose.GIS for .NET はこのプロセスをシンプルにし、円形文字列などの高度なジオメトリでレイヤーを拡張できます。本チュートリアルでは、ベクトルレイヤーの作成方法、円形文字列ジオメトリの追加方法、そして結果を Shapefile として保存する手順を、クリーンで本番向けの C# コードとともに学びます。

## クイック回答
- **“create vector layer” は何を意味しますか？** 新しいコンテナ（レイヤー）を作成し、ポイント、ライン、ポリゴンなどの空間フィーチャを保持できるようにします。  
- **円形文字列を表すクラスはどれですか？** `Aspose.Gis.Geometries` の `CircularString`。  
- **レイヤーを Shapefile として保存できますか？** はい – レイヤー作成時に `Drivers.Shapefile` を使用します。  
- **開発にライセンスは必要ですか？** 評価用に一時ライセンスが使用可能ですが、本番環境ではフルライセンスが必要です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  

## “create vector layer” とは何ですか？
ベクトルレイヤーは、単一のデータソースに格納されたベクトルフィーチャ（ポイント、ライン、ポリゴン）を論理的にグループ化したものです。Aspose.GIS では `VectorLayer.Create` を呼び出し、対象ファイルパスと目的のドライバー（例: Shapefile）を指定してレイヤーをインスタンス化します。レイヤーが作成されれば、フィーチャの追加、ジオメトリの割り当て、空間操作が可能になります。

## なぜ円形文字列を追加するのか？
円形文字列は **線形ジオメトリ** の一種で、点のシーケンスを使って円弧を近似します。曲線道路や河川の曲がり角など、滑らかな曲線が必要なフィーチャを多数の小さなラインセグメントに分割せずに表現できるため便利です。

## 前提条件
- **.NET Framework または .NET Core** がマシンにインストールされていること。  
- **Aspose.GIS for .NET** ライブラリ – 公式サイト **[here](https://releases.aspose.com/gis/net/)** からダウンロードしてください。  
- **Visual Studio** や **JetBrains Rider** などの IDE。  
- **C#** プログラミングの基本的な知識。  

## 名前空間のインポート
C# ファイルに必要な名前空間を追加します:

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
Shapefile が書き込まれる場所を設定します。

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"` をシステム上の実際のフォルダー パスに置き換えてください。

### 手順 2: **Create vector layer**
`Create` メソッドを使用して `VectorLayer` を開きます。これが **create vector layer** 操作の核心です。

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 手順 3: 新しいフィーチャの作成
フィーチャはレイヤー内の単一の空間レコードを表します。

```csharp
    var feature = layer.ConstructFeature();
```

### 手順 4: 円形文字列ジオメトリの構築
曲線形状を定義する点を追加します。点のシーケンスは、開始点と終了点が同じ位置になるようにして閉じた円形文字列を形成します。

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 手順 5: ジオメトリを割り当て、フィーチャをレイヤーに追加
ジオメトリをフィーチャにリンクし、レイヤーに保存します。

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` ブロックが終了すると、レイヤーは自動的にディスク上の Shapefile にフラッシュされます。

## よくある問題と解決策
| 問題 | 解決策 |
|------|--------|
| **ファイルパスが無効** | ディレクトリが存在し、書き込み権限があることを確認してください。 |
| **CircularString が直線として表示される** | ポイントが正しい順序で追加されているか確認してください。閉じた形状の場合、最初と最後のポイントは同一である必要があります。 |
| **ライセンス例外** | 開発中は一時ライセンスを適用し、本番使用時はフルライセンスを購入してください。 |

## よくある質問

### Aspose.GIS for .NET はすべての .NET Framework バージョンと互換性がありますか？
はい、Aspose.GIS for .NET は .NET Framework 4.5 から最新の .NET 8 リリースまで、幅広い .NET バージョンで動作するよう設計されています。

### Aspose.GIS for .NET を他の GIS ライブラリと統合できますか？
もちろんです！他のライブラリでデータを読み取り、Aspose.GIS で操作し、再び書き出すことが可能です。柔軟な API がそれを支えます。

### Aspose.GIS for .NET は空間データの可視化をサポートしていますか？
はい、ライブラリにはレンダリングユーティリティが含まれており、マップやジオメトリの視覚的表現を生成できます。

### Aspose.GIS for .NET に関するサポートを求められるコミュニティフォーラムはありますか？
はい、Aspose.GIS フォーラム **[here](https://forum.aspose.com/c/gis/33)** で質問や経験の共有ができます。

### Aspose.GIS for .NET の評価用に一時ライセンスを取得できますか？
もちろんです！評価用の一時ライセンスは **[here](https://purchase.aspose.com/temporary-license/)** から入手可能です。

### 同じレイヤーにより複雑なジオメトリ（例: MultiLineString）を追加するには？
適切なジオメトリオブジェクト（例: `MultiLineString`）を作成し、個々の `LineString` オブジェクトで構成します。`feature.Geometry` に割り当て、円形文字列と同様にフィーチャをレイヤーに追加してください。

## 結論
本手順に従うことで、**ベクトルレイヤーを作成**し、円形文字オメトリで拡張する方法が習得できました。この基盤を活用すれば、交通ネットワークのマッピング、環境データの可視化、カスタム空間分析ツールの開発など、よりリッチな GIS ソリューションを構築できます。

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}