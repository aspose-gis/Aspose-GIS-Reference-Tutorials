---
date: 2025-12-03
description: Aspose.GIS for .NET の Intersects メソッドを使用して、C# でポリゴンジオメトリを作成し、重なり合うポリゴンを検出する方法を学びましょう。
linktitle: Create Polygon Geometry C#
second_title: Aspose.GIS .NET API
title: C#でポリゴンジオメトリを作成し、Aspose.GIS for .NETで交差をチェックする
url: /ja/net/geometry-analysis/check-geometries-intersection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ポリゴンジオメトリ C# の作成と Aspose.GIS for .NET を使用交差判定

## はじめに
ポリゴンジオメトリを **C# で作成** し、2 つの形状が重なっているかどうかをすばやく判定したい場合、Aspose.GIS for .NET はクリーンで高性能な API を提供します。本ガイドでは、ライブラリのセットアップから `Intersects` メソッドを使用して **ポリゴンの重なりを検出** するまでの全工程を解説します。最後まで読めば、行のコードで任意の .NET アプリケーションにポリゴン交差チェックを組み込めるようになります。

## クイック回答
- **Intersects メソッドは何をするのですか？** 2 つのジオメトリが共通領域を持つと `true` を返します。  
- **ポリゴン関連クラスはどの名前空間にありますか？** `Aspose.Gis.Geometries`。  
- **開発時にライセンスは必要ですか？** テスト用の無料トライアルで動作しますが、製品版では商用ライセンスが必要です。  
- **.NET Core / .NET 6+ でも使用できますか？** はい、Aspose.GIS はすべての最新 .NET ランタイムをサポートしています。  
- **サンプルの実行時間はどれくらいですか？** 標準的な開発マシンで 1 秒未満です。

## “create polygon geometry C#” とは？
C# でポリゴンジオメトリを作成するとは、Aspose.GIS が提供する `Polygon` クラス（または他のジオメトリ型）をインスタンス化し、形状の頂点を表す `Point` オブジェクトの閉じたリングを渡すことを指します。作成したジオメトリは、交差、包含、距離計算などの空間演算に利用できます。

## なぜ Aspose.GIS を使用してポリゴンの重なりを検出するのか？
- **外部依存がゼロ** – 純粋な .NET ライブラリで、ネイティブ GIS のインストールは不要です。  
- **豊富な空間演算** – `Intersects`、`Disjoint`、`Contains` など、すぐに使えるメソッドが揃っています。  
- **高精度** – 共有エッジや頂点といったエッジケースも堅牢に処理します。  
- **クロスプラットフォーム** – Windows、Linux、macOS 上の .NET Core/5/6 で動作します。

## 前提条件
開始する前に、以下を用意してください。

1 **Aspose.GIS for .NET** がインストール済み（以下の手順を参照）。  
2. .NET 開発環境（Visual Studio、VS Code、または Rider）。  
3. .NET Framework 4.6+ または .NET Core 3.1+。

### Aspose.GIS for .NET のインストール
1. ダウンロードページへ移動: [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/) で最新バージョンを取得します。  
2. ツールキットをダウンロード: 開発環境に適合するバージョンを選択し、ツールキットをダウンロードします。  
3. ツールキットをインストール: 提供されているインストール手順に従い、開発マシンに Aspose.GIS for .NET をインストールします。

## 名前空間のインポート
Aspose.GIS for .NET を使用し始めるには、プロジェクトに必要な名前空間をインポートする必要があります。

1. 参照の追加: プロジェクトに Aspose.GIS アセンブリへの参照を追加します。  
2. 名前空間のインポート: コードファイルで以下の名前空間をインポートします。今回のサンプルでは次の名前空間が必要です。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Aspose.GIS を使用して polygon geometry C# を作成する方法は？
環境が整ったので、後で重なりをテストする 2 つのシンプルなポリゴンジオメトリを作成しましょう。

### 手順 1: ジオメトリの定義
このステップでは、2 つの矩形領域を表すポリゴンを作成します。頂点は時計回りに定義し、リングを閉じるために最初の点を最後に再度記述します。

```csharp
var geometry1 = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 3),
    new Point(3, 3),
    new Point(3, 0),
    new Point(0, 0),
}));
var geometry2 = new Polygon(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 4),
    new Point(4, 4),
    new Point(4, 1),
    new Point(1, 1),
}));
```

### 手順 2: Intersects メソッドを使用してポリゴンの重なりを検出する
ジオメトリが定義できたら、`Intersects` メソッドを呼び出します。このメソッドは **Intersects アルゴリズム** を使用して、2 つのポリゴンが同じ空間を共有しているかどうかをチェックします。

```csharp
Console.WriteLine(geometry1.Intersects(geometry2)); // True
Console.WriteLine(geometry2.Intersects(geometry1)); // True
```

### 手順 3: Disjoint ジオメトリの確認（intersect の反対）
2 つの形状が **重ならない** ことを確認したい場合は、`Disjoint` メソッドが逆の結果を返します。

```csharp
// 'Disjoint' is opposite to 'Intersects'
Console.WriteLine(geometry1.Disjoint(geometry2)); // False
```

## よくある問題と解決策
| 問題 | 発生理由 | 対策 |
|------|----------|------|
| **常に `false` を返す** | ポリゴンが閉じていない（最初の点 ≠ 最後の点）。 | 座標配列の末尾に最初の点を再度追加してリングを閉じます。 |
| **エッジが接触している場合に予期しない `true`** | `Intersects` は共有エッジも交差とみなします。 | エッジのみの検出が必要な場合は `Touches` メソッドを使用します。 |
| **多数のポリゴンでパフォーマンス低下** | 各呼び出しで全頂点ペアを比較しているため。 | `GeometryCollection` や空間インデックス（R‑tree）を利用してバッチ処理します（対応している場合）。 |

## よくある質問

**Q: Aspose.GIS for .NET は他の .NET フレームワークでも使用できますか？**  
**A:** はい、Aspose.GIS for .NET は .NET Core や .NET Framework など、さまざまな .NET フレームワークと互換性があります。

**Q: Aspose.GIS for .NET の無料トライアルはありますか？**  
**A:** はい、[こちら](https://releases.aspose.com/) から無料トライアル版を入手。

**Q: Aspose.GIS for .NET のサポートはどこで受けられますか？**  
**A:** [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でコミュニティとやり取りしながらサポートを受けられます。

**Q: Aspose.GIS for .NET の一時ライセンスは取得できますか？**  
**A:** はい、[こちら](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

**Q: Aspose.GIS for .NET の正規ライセンスはどこで購入できますか？**  
**A:** [こちら](https://purchase.aspose.com/buy) で正規ライセンスを購入できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最終更新日:** 2025-12-03  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作成者:** Aspose