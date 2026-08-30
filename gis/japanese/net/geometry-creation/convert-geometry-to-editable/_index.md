---
date: 2026-08-18
description: Aspose.GIS for .NET を使用して、linestring に point を追加し、geometry を editable
  format に簡単に変換する方法を学びましょう。step‑by‑step チュートリアルをご覧ください。
keywords:
- add point to linestring
- add vertex to path
- Aspose.GIS editable geometry
lastmod: 2026-08-18
linktitle: Geometry を Editable に変換
og_description: Aspose.GIS for .NET を使用して、linestring に point を追加し、geometry を editable
  format に変換します。このガイドでは、数分でフルワークフローを示します。
og_image_alt: Screenshot of Aspose.GIS code editing a LineString geometry in a .NET
  console app
og_title: linestring に point を追加 – Aspose.GIS で geometry を editable format に変換
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add point to linestring and convert geometry to an editable
    format effortlessly using Aspose.GIS for .NET. Follow this step‑by‑step tutorial.
  headline: How to add point to linestring and convert geometry to editable format
    with Aspose.GIS
  type: TechArticle
- description: Learn how to add point to linestring and convert geometry to an editable
    format effortlessly using Aspose.GIS for .NET. Follow this step‑by‑step tutorial.
  name: How to add point to linestring and convert geometry to editable format with
    Aspose.GIS
  steps:
  - name: Define a read‑only geometry
    text: First, create a read‑only geometry object that represents a simple line.
      This object cannot be modified directly. **Definition:** A read‑only geometry
      is an immutable object that represents spatial data without allowing modifications.
  - name: Obtain an editable copy
    text: To edit the geometry, obtain an editable version using the `ToEditable()`
      method. This creates a mutable copy while leaving the original untouched. **Definition:**
      The `ToEditable()` method creates a mutable copy of a geometry, enabling changes
      while preserving the original.
  - name: Add point to LineString
    text: Now that you have an editable copy, you can **add point to linestring**.
      The `AddPoint` method appends a new vertex at the specified coordinates. **Definition:**
      The `AddPoint()` method appends a new coordinate to a `LineString` or inserts
      it at a specific index when you provide an index argument.
  - name: Output edited geometry
    text: Print the edited geometry to verify that the new point was added successfully.
  - name: Verify original geometry remains unchanged
    text: It’s good practice to confirm that the original read‑only geometry has not
      been altered.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS integrates smoothly with popular .NET GIS libraries such
      as NetTopologySuite and SharpMap.
    question: Is Aspose.GIS compatible with other .NET libraries?
  - answer: Certainly! You can obtain a free trial from the [releases page](https://releases.aspose.com/)
      to explore its features.
    question: Can I try Aspose.GIS before purchasing?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: How can I get support for Aspose.GIS?
  - answer: Yes, a temporary license can be requested via the [Aspose.GIS purchase
      page](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for evaluation?
  - answer: Absolutely! Use the [purchase page](https://purchase.aspose.com/buy) to
      acquire a license that fits your needs.
    question: Can I purchase Aspose.GIS directly?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- GIS editing
- Aspose.GIS
- .NET geometry manipulation
title: Aspose.GIS を使用して、linestring に point を追加し、geometry を editable format に変換する方法
url: /ja/net/geometry-creation/convert-geometry-to-editable/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS を使用してラインストリングにポイントを追加し、ジオメトリを編集可能な形式に変換する方法

## はじめに
ジオスペーシャル データを扱う際、**add point to linestring** は頻繁に行われる操作です。ルートの修正、パスの拡張、またはジオメトリを動的に構築する場合などに必要です。Aspose.GIS for .NET は、読み取り専用ジオメトリを編集可能なものに変換し、新しい頂点を追加し、元のジオメトリを誤って変更されないように保護するシンプルな API を提供します。このチュートリアルでは、`LineString` にポイントを追加し、編集可能なコピーを取得し、元のジオメトリが変更されていないことを確認する手順を示します。

## クイック回答
- **“add point to linestring” とは何ですか？** 既存の `LineString` ジオメトリに新しい座標を挿入することを指します。  
- **どのライブラリがこれをサポートしていますか？** Aspose.GIS for .NET が `ToEditable()` メソッドと `AddPoint()` 関数を提供します。  
- **この機能にライセンスは必要ですか？** 開発目的であれば無料トライアルで利用可能です。商用環境では商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.6 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **実装にかかる時間は？** 基本的なシナリオであれば 10 分未満です。

## “add point to linestring” とは？
`LineString` は、接続されたポイントの系列で構成されるラインを表すジオメトリタイプです。  
`LineString` にポイントを追加すると、指定した座標に新しい頂点が挿入され、ラインが伸長したり、より詳細なパスが作成されたりします。この操作は、ルート編集、マップ修正、動的ジオメトリ構築などのタスクで不可欠であり、全体のフィーチャを再構築せずに空間データを豊かにできます。

## なぜ Aspose.GIS をこのタスクに使うのか？
Aspose.GIS は、主要な .NET ランタイムすべてで動作し、依存関係がゼロの信頼できるライブラリとして設計されています。元のジオメトリを不変に保ち、誤った変更を防止しながら、`ToEditable()` や `AddPoint()` といったシンプルでチェーン可能なメソッドで編集を容易にします。API は 50 以上の GIS フォーマットをサポートし、ファイル全体をメモリにロードせずに大規模データセットを効率的に処理できます。

- **外部依存なし** – ジオメトリ変換は API 内部で処理されます。  
- **読み取り専用の安全性** – 元のジオメトリは不変のままで、誤った変更を防止します。  
- **シンプルな構文** – `ToEditable()` や `AddPoint()` などのメソッドは C# 開発者にとって直感的です。  
- **クロスプラットフォーム** – Windows、Linux、macOS の .NET ランタイムで動作します。  
- **50 以上の入出力フォーマットに対応** し、ファイル全体をメモリに読み込まずに数百ページ規模のジオメトリも処理できます。

## ラインストリングにポイントを追加する必要があるのはいつですか？
既存のラインに頂点を追加することは、データの精緻化や拡張が必要なときに有用です。誤差の修正、新しいインフラの組み込み、分析用の詳細度向上などに利用できます。一般的なシナリオとしては、工事後の道路ネットワーク更新、GPS トレースの欠落ウェイポイント修正、ユーザーが描いたカスタムパス作成、空間アルゴリズムで必要とされる最小頂点数を満たすデータセットの準備などがあります。

## 前提条件
開始する前に、以下が揃っていることを確認してください。

- **.NET 環境** – [ウェブサイト](https://dotnet.microsoft.com/download) から .NET フレームワークをインストールします。  
- **Aspose.GIS ライブラリ** – [リリースページ](https://releases.aspose.com/gis/net/) から最新パッケージをダウンロードします。  
- **C# の基礎** – C# の構文とコンソール アプリケーションに慣れていることが望ましいです。

### 名前空間のインポート
プロセスを開始するには、C# コードに必要な名前空間をインポートしてください。これにより、Aspose.GIS for .NET が提供する機能にアクセスできます。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

それでは、ジオメトリを編集可能な形式に変換し、`LineString` にポイントを追加する具体的な手順を見ていきましょう。

## Aspose.GIS を使用して LineString にポイントを追加する方法
`ToEditable()` はジオメトリの可変コピーを作成し、変更を可能にします。`AddPoint()` は `LineString` に新しい頂点を挿入します。読み取り専用ジオメトリをロードし、`ToEditable()` で可変コピーを取得し、`AddPoint()` で新しい座標を挿入します。この 4 ステップのワークフローにより、安全に編集し、結果を即座に検証できます。

### 手順 1: 読み取り専用ジオメトリを定義する
まず、シンプルなラインを表す読み取り専用ジオメトリ オブジェクトを作成します。このオブジェクトは直接変更できません。  
**Definition:** 読み取り専用ジオメトリは、空間データを表す不変オブジェクトで、変更を許可しません。

```csharp
ILineString readOnlyLine = (ILineString)Geometry.FromText("LINESTRING (1 1, 2 2)");
```

### 手順 2: 編集可能なコピーを取得する
ジオメトリを編集するには、`ToEditable()` メソッドを使用して編集可能なバージョンを取得します。これにより、元のジオメトリはそのままで可変コピーが作成されます。  
**Definition:** `ToEditable()` メソッドはジオメトリの可変コピーを作成し、元のジオメトリを保持しながら変更を可能にします。

```csharp
LineString editableLine = readOnlyLine.ToEditable();
```

### 手順 3: LineString にポイントを追加する
編集可能なコピーができたら、**add point to linestring** を実行できます。`AddPoint` メソッドは指定した座標に新しい頂点を追加します。  
**Definition:** `AddPoint()` メソッドは `LineString` に新しい座標を追加するか、インデックス引数を指定した場合は特定の位置に挿入します。

```csharp
editableLine.AddPoint(3, 3);
```

### 手順 4: 編集後のジオメトリを出力する
編集されたジオメトリを出力し、新しいポイントが正しく追加されたことを確認します。

```csharp
Console.WriteLine(editableLine.AsText()); // LINESTRING (1 1, 2 2, 3 3)
```

### 手順 5: 元のジオメトリが変更されていないことを確認する
元の読み取り専用ジオメトリが変更されていないことを確認するのがベストプラクティスです。

```csharp
Console.WriteLine(readOnlyLine.AsText()); // LINESTRING (1 1, 2 2)
```

## よくある落とし穴とヒント
- **読み取り専用オブジェクトを直接変更しない** – 常に `ToEditable()` を先に呼び出してください。  
- **座標順序に注意** – (X, Y) の順序で正しく渡すこと。  
- **大規模ジオメトリ** – 非常に長い `LineString` オブジェクトの場合、パフォーマンス向上のためにバッチ編集を検討してください。  
- **スレッド安全性** – 編集可能ジオメトリはスレッドセーフではありません。単一スレッドで編集するか、適切な同期を使用してください。

## FAQ（よくある質問）

**Q: Aspose.GIS は他の .NET ライブラリと互換性がありますか？**  
A: はい、Aspose.GIS は NetTopologySuite や SharpMap などの一般的な .NET GIS ライブラリとスムーズに統合できます。

**Q: 購入前に Aspose.GIS を試すことはできますか？**  
A: もちろんです！[リリースページ](https://releases.aspose.com/) から無料トライアルを取得して機能を確認できます。

**Q: Aspose.GIS のサポートはどこで受けられますか？**  
A: コミュニティ支援と公式サポートは [Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) で提供されています。

**Q: 評価用の一時ライセンスはありますか？**  
A: はい、[Aspose.GIS 購入ページ](https://purchase.aspose.com/temporary-license/) から一時ライセンスをリクエストできます。

**Q: Aspose.GIS を直接購入できますか？**  
A: もちろんです！[購入ページ](https://purchase.aspose.com/buy) からニーズに合ったライセンスを取得してください。

### 追加のクイック FAQ
**Q: `ToEditable()` を呼び出さずに読み取り専用ジオメトリにポイントを追加しようとするとどうなりますか？**  
A: ジオメトリが不変であるため、`InvalidOperationException` がスローされます。

**Q: 終端ではなく特定の位置にポイントを挿入できますか？**  
A: はい、`AddPoint(int index, double x, double y)` のオーバーロードを使用して指定インデックスに挿入できます。

**Q: `ToEditable()` はジオメトリのディープコピーを作成しますか？**  
A: 可変コピーを作成しますが、座標データは共有されます。編集可能コピーへの変更は元のジオメトリに影響しません。

## 結論
Aspose.GIS for .NET を使用して **add point to linestring** を実行し、読み取り専用ジオメトリを編集可能な形式に変換する方法が分かりました。このアプローチにより、元データを安全に保ちつつジオメトリ操作の完全なコントロールが可能です。ルート編集、マップ修正、または動的ジオメトリ更新が必要なシナリオに最適です。複数の `AddPoint` 呼び出しをチェーンしたり、特定インデックスにポイントを挿入したり、他の Aspose.GIS 空間操作と組み合わせてさらに活用してください。

---

**最終更新日:** 2026-08-18  
**テスト環境:** Aspose.GIS 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS for .NET で LineString ジオメトリを作成する方法](/gis/net/geometry-creation/create-linestring-geometry/)
- [Aspose.GIS for .NET でジオメトリ内の頂点数をカウントする方法](/gis/net/geometry-creation/count-points-in-geometry/)
- [Aspose.GIS for .NET でジオメトリ コレクションを作成する方法](/gis/net/geometry-creation/create-geometry-collection/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}