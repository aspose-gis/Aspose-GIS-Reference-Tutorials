---
date: 2025-12-21
description: Aspose.GIS for .NET の ExtendedPostGis バリアントを使用して、ラインストリングジオメトリの作成方法とジオメトリを
  WKB に変換する方法を学びましょう。
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Aspose.GIS .NETでラインストリングジオメトリとWKBバリアントを作成する
url: /ja/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET の変換時に WKB バリアントを指定する

## はじめに
Geographic Information Systems (GIS) 開発の領域において、Aspose.GIS for .NET は強力なツールセットとして際立っています。**ラインストリングジオメトリを作成**し、**ジオメトリを WKB に変換**したい場合、ここが適切な場所です。その汎用性と効率性により、.NET アプリケーションに GIS 機能をシームレスに統合しようとする開発者にとって選択肢となっています。本稿は Aspose.GIS for .NET を活用するための包括的ガイドであり、特に変換プロセス中に WKB（Well‑Known Binary）バリアントを指定する方法に焦点を当てています。

## クイック回答
- **WKB は何の略ですか？** Well‑Known Binary、ジオメトリオブジェクトのコンパクトなバイナリ表現です。  
- **どの WKB バリアントが SRID 情報の保存を可能にしますか？** `ExtendedPostGis`（EWKB）バリアントです。  
- **コードを実行するのにライセンスが必要ですか？** 本番環境で使用するには一時ライセンスまたはフルライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上です。  
- **実装にどれくらい時間がかかりますか？** 基本的な例で通常 10 分未満です。

## ラインストリングジオメトリとは？
ラインストリングは、直線セグメントで接続された点のシーケンスで構成されるシンプルなジオメトリ形状です。道路、河川、または GIS データ内の任意の線形フィーチャを表すために一般的に使用されます。

## なぜ WKB バリアントを指定するのか？
適切な WKB バリアントを選択することで、空間参照系識別子（SRID）などの重要なメタデータがジオメトリデータの保存や交換時に保持されます。`ExtendedPostGis` バリアント（EWKB）は、PostgreSQL/PostGIS や SRID 情報がバイナリに埋め込まれることを期待するシステムで特に有用です。

## 前提条件
Aspose.GIS for .NET で WKB バリアントを指定する具体的な手順に入る前に、以下の前提条件が整っていることを確認してください。

### Aspose.GIS for .NET のインストール
1. Aspose.GIS をダウンロード: [download link](https://releases.aspose.com/gis/net/) にアクセスして Aspose.GIS for .NET パッケージを取得します。  
2. パッケージをインストール: ドキュメントに記載されたインストール手順に従い、Aspose.GIS を .NET 環境にシームレスに統合します。

### C# プログラミングの知識
1. 基本的な C# の知識: C# の構文と概念の基礎的な理解があることを確認してください。

## 名前空間のインポート
Aspose.GIS for .NET の利用を開始し、機能を効果的に活用するには、プロジェクトに必要な名前空間をインポートする必要があります。以下にステップバイステップのガイドを示します：

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

これらの名前空間により Aspose.GIS の機能にアクセスでき、地理データを容易に扱うことができます。

## ラインストリングジオメトリの作成方法？
提供された例を複数のステップに分解し、変換時に WKB バリアントを指定するプロセスを徹底的に理解しましょう。

### ステップ 1: ジオメトリオブジェクトの作成
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
このステップでは、指定された座標で線形フィーチャを表す **ラインストリングジオメトリを作成** します。

### ステップ 2: WKB 表現の生成
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
ここでは、SRID 情報を埋め込む `ExtendedPostGis` バリアントを使用して **ジオメトリを WKB に変換** します。

### ステップ 3: ファイルへの書き込み
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
最後に、生成された WKB バイナリデータを任意のディレクトリにある `EWkbFile.ewkb` という名前のファイルに書き込みます。

## 一般的な問題と解決策
| 問題 | 原因 | 解決策 |
|-------|--------|----------|
| **空ファイル** | `Path.Combine` が存在しないディレクトリを指しています。 | 対象ディレクトリが存在することを確認するか、`Directory.CreateDirectory` で作成してください。 |
| **SRID が不正** | デフォルトの `WkbVariant.Standard` を使用すると SRID が失われます。 | SRID の保持が必要な場合は常に `WkbVariant.ExtendedPostGis` を使用してください。 |
| **ライセンス例外** | 本番環境で有効なライセンスなしで実行しています。 | 本番環境でコードを実行する前に、一時またはフルライセンスを適用してください。 |

## FAQ

### Aspose.GIS for .NET はすべての .NET バージョンと互換性がありますか？
Aspose.GIS for .NET はさまざまな .NET バージョンと互換性があるよう設計されており、開発者に柔軟性と利便性を提供します。

### Aspose.GIS for .NET の使用中にサポートや支援を依頼できますか？
はい、専門家や他の開発者が質問に答えてくれる専用の [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でサポートや支援を求めることができます。

### Aspose.GIS for .NET は無料トライアルを提供していますか？
はい、[このリンク](https://releases.aspose.com/) で提供されている無料トライアルを通じて Aspose.GIS for .NET の機能と性能を体験できます。

### Aspose.GIS for .NET の一時ライセンスはどう取得できますか？
[一時ライセンスページ](https://purchase.aspose.com/temporary-license/) にアクセスし、指示に従うことで一時ライセンスを取得できます。

### Aspose.GIS for .NET のライセンスはどこで購入できますか？
[このリンク](https://purchase.aspose.com/buy) の購入ページから Aspose.GIS for .NET のライセンスを購入できます。

## よくある質問
**Q: EWKB ファイルを PostGIS で使用できますか？**  
A: はい、`ExtendedPostGis` バリアントは SRID を含む EWKB を生成し、PostGIS が直接読み取れます。

**Q: WKB ファイルをジオメトリオブジェクトに読み戻すことは可能ですか？**  
A: もちろんです。`Geometry.FromBinary(byteArray)` を使用してジオメトリを再構築します。

**Q: ライブラリはポリゴンなど他のジオメトリタイプもサポートしていますか？**  
A: はい、Aspose.GIS はポイント、ラインストリング、ポリゴン、マルチポリゴンなどを扱えます。

**Q: ジオメトリ作成時に別の SRID を指定するにはどうすればよいですか？**  
A: `AsBinary` を呼び出す前にジオメトリオブジェクトの SRID を設定します。例: `geometry.SRID = 4326;`

**Q: このコードは .NET Core でも動作しますか？**  
A: はい、同じ API は .NET Framework、.NET Core、.NET 5/6 で動作します。

---

**最終更新日:** 2025-12-21  
**テスト環境:** Aspose.GIS for .NET 23.9 (執筆時点での最新)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}