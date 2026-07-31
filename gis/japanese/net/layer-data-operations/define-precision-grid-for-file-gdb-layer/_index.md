---
date: 2026-04-24
description: Aspose.GIS for .NET を使用してファイルジオデータベースを作成し、File GDB レイヤーに精度グリッドを設定する方法を学びます。レイヤーへのフィーチャ追加や座標範囲の検証も含みます。
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: ファイルGDBレイヤーの精度グリッドを定義する
second_title: Aspose.GIS .NET API
title: ファイルジオデータベースの作成とGDBレイヤーのグリッド設定（Aspose.GIS）
url: /ja/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS で File GDB レイヤーのグリッドを設定する方法

## はじめに
このチュートリアルでは、**ファイルジオデータベース** オブジェクトを作成し、Aspose.GIS for .NET を使用して File Geodatabase (GDB) レイヤーの **グリッドを設定** する方法を学びます。精度グリッドを定義することで、**座標範囲の検証** が可能になり、範囲外エラーを防止し、**レイヤーにフィーチャを追加** する操作が正確にデータを保存できるよう保証します。すべての手順を順に説明し、各設定の重要性を解説し、**範囲外** のシナリオを優雅に **処理する** 方法を示します。

## クイック回答
- **「グリッドを設定する」とは何ですか？** GIS レイヤーの座標精度と有効範囲を定義します。  
- **なぜ精度グリッドを使用するのですか？** データを無効な座標から保護し、ストレージ効率を向上させます。  
- **この機能を提供するライブラリはどれですか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** 試用版が利用可能です。商用利用には商用ライセンスが必要です。  
- **.NET Core でも使用できますか？** はい、Aspose.GIS は .NET Framework と .NET Core をサポートしています。

## 精度グリッドとは何か、なぜ設定するのか
精度グリッドは、GIS エンジンに座標値をどのように丸めて保存するかを指示するパラメータ（原点、スケールなど）の集合です。グリッドを設定することで、**座標範囲を自動的に検証** でき、グリッド外に点を挿入しようとすると例外が発生します—これにより、開発初期段階で **範囲外** のシナリオを **処理** しやすくなります。

## なぜ精度グリッド付きのファイルジオデータベースを作成するのか
ファイルジオデータベースを作成すると、ベクターデータ用のポータブルで高性能なコンテナが得られます。作成時に精度グリッドを追加することで、以下が保証されます：
- **一貫したデータ品質** – すべてのフィーチャが同じ数値精度を遵守します。  
- **高速インデックス作成** – エンジンが座標をより効率的に保存できます。  
- **早期エラー検出** – 範囲外の座標がデータセットを破損させる前に検出されます。

## 前提条件
開始する前に、以下がインストールされていることを確認してください：

1. **Visual Studio** – 任意の最新バージョン（Community、Professional、Enterprise のいずれか）。  
2. **Aspose.GIS for .NET** – [ウェブサイト](https://releases.aspose.com/gis/net/) からダウンロードしてください。  
3. **基本的な C# の知識** – .NET コンソールプロジェクトの作成に慣れている必要があります。

## 一般的な使用例
- **フィールドデータ収集** – GPS デバイスが意図した範囲外の座標を若干生成する可能性がある場合。  
- **データ移行** – 異なる座標精度を使用していたレガシーシステムからの移行。  
- **自動化 ETL パイプライン** – GIS データベースにデータをロードする前に空間整合性を強制する必要がある場合。

## 名前空間のインポート
まず、Aspose.GIS の操作に必要な名前空間をインポートします：

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## File GDB レイヤーで座標グリッドを構成する方法
以下は、グリッドを構成し、レイヤーを作成し、**レイヤーにフィーチャを安全に追加** する方法をステップバイステップで示したガイドです。

### ステップ 1: データセットの作成
まず、新しい File Geodatabase データセットを作成します。ここにレイヤーが格納されます。

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### ステップ 2: 精度グリッドオプションの定義
ここでグリッドパラメータを指定します。プロジェクトの座標系に合わせて原点とスケールを調整してください。

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*`EnsureValidCoordinatesRange = true` フラグは、追加するすべてのフィーチャに対して Aspose.GIS が **座標範囲を検証** するよう指示します。*

### ステップ 3: グリッド付きレイヤーの作成
次に、先ほど定義したグリッドオプションを適用して、データセット内に新しいレイヤーを作成します。WGS84 空間参照系を使用します。

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### ステップ 4: レイヤーにフィーチャを追加
2 つのポイントフィーチャを構築します。最初のポイントはグリッド内にあり、2 番目は意図的に外側に配置して、**範囲外エラーの処理方法** を示します。

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### ステップ 5: 範囲外フィーチャ追加時の例外処理
2 番目のフィーチャを追加しようとすると、X 座標 (`-410`) が定義されたグリッド外であるため例外が発生します。例外を捕捉し、明確なメッセージを出力します。

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### ステップ 6: クリーンアップ
`using` ステートメントはデータセットとレイヤーを自動的に閉じて破棄し、すべてのリソースが解放されることを保証します。

## 一般的な問題と解決策
| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| **例外: “X 値 … が有効範囲外です。”** | 座標が精度グリッドの外にあるため。 | `XOrigin`、`YOrigin`、または `XYScale` を調整してデータを包含するか、入力データが定義された範囲内にあることを確認してください。 |
| **フィーチャが GIS ビューアに表示されない** | レイヤーが保存されていない、または空間参照が間違っている。 | `SpatialReferenceSystem.Wgs84` がビューアの CRS と一致しているか、`Dataset.Create` が成功したかを確認してください。 |
| **M 値が無視される** | `MScale` が 0 または低すぎる。 | 測定値を保存するために、適切な `MScale`（例: `1e4`）を設定してください。 |

## トラブルシューティングのヒント
- **大量データをロードする前にグリッド範囲を再確認**してください。`XOrigin` の小さなタイプミスでも多くの行が拒否される可能性があります。  
- **例外メッセージをログに記録**（try‑catch ブロックの例のように）してファイルに保存すると、自動インポート処理時に範囲外データのパターンを把握しやすくなります。  
- **`EnsureValidCoordinatesRange = false` は信頼できるデータソースの場合のみ使用**してください。無効にすると検証がスキップされ、ジオメトリが破損する可能性があります。

## よくある質問

**Q: Aspose.GIS for .NET を他の GIS ファイル形式と併用できますか？**  
A: はい、Aspose.GIS は Shapefile、GeoJSON、KML など多数の形式をサポートしています。

**Q: Aspose.GIS for .NET は .NET Core と互換性がありますか？**  
A: もちろんです。このライブラリは .NET Framework、.NET Core、そして .NET 5/6 以降でも動作します。

**Q: バッファリングやインターセクションなどの空間操作は実行できますか？**  
A: はい、API にはバッファリング、インターセクション、距離計算のメソッドが含まれています。

**Q: Aspose.GIS は座標変換機能を提供していますか？**  
A: はい、組み込みの再投影ツールを使用して、異なる空間参照系間でジオメトリを変換できます。

**Q: 試用版はありますか？**  
A: はい、[ウェブサイト](https://releases.aspose.com/gis/net/) から無料の試用版をダウンロードできます。

---

**最終更新日:** 2026-04-24  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}