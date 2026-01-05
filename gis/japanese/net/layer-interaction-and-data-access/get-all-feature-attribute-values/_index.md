---
date: 2026-01-05
description: Aspose.GIS for .NET を使用して C# でシェープファイルの読み取り方法を学び、すべてのフィーチャ属性値を取得し、属性を効率的にダンプする方法を習得しましょう。
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile を C# で読み込む – すべてのフィーチャ属性値を取得
url: /ja/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# すべてのフィーチャ属性値を取得する

## はじめに
Aspose.GIS for .NET を使用した地理空間開発の世界へようこそ！このチュートリアルでは **C# でシェープファイルを読み取る方法** を学び、フィーチャのすべての属性値を取得します。マッピングアプリを構築する場合でも、バッチで空間データを処理する場合でも、属性抽出の習得は不可欠です。さあ、コードを実際に見てみましょう。

## クイック回答
- **このコードは何をしますか？** Shapefile を開き、各フィーチャからすべて、いくつか、またはダンプされた属性値を読み取ります。  
- **必要なライブラリはどれですか？** Aspose.GIS for .NET（.NET Framework と .NET Core に対応）。  
- **ライセンスは必要ですか？** テスト用には一時ライセンスで動作しますが、本番環境ではフルライセンスが必要です。  
- **他のフォーマットも読み取れますか？** はい。同じ API が GeoJSON、KML など多数のフォーマットをサポートしています。  
- **属性をダンプするには？** `feature.GetValuesDump()` を使用して柔軟なオブジェクト配列を取得します。  

## 「C# でシェープファイルを読み取る」とは何ですか？
C# でシェープファイルを読み取るとは、GIS ライブラリで .shp ファイルを開き、ベクトルフィーチャを反復処理し、付随する .dbf ファイルに格納された属性データにアクセスすることを意味します。Aspose.GIS は低レベルのファイル処理を抽象化し、必要な属性値に集中できるようにします。

## 属性を読み取るために Aspose.GIS を使用する理由
- **シンプルな API** – `GetValues` や `GetValuesDump` のような直感的なメソッド。  
- **クロスプラットフォーム** – .NET Core で Windows、Linux、macOS 上で動作します。  
- **豊富なフォーマットサポート** – 追加プラグインなしで Shapefile、GeoJSON、GML などを扱えます。  
- **パフォーマンス最適化** – 大規模データセットの高速反復処理。  

## 前提条件
このエキサイティングな旅に出る前に、以下の前提条件が整っていることを確認してください：

- Aspose.GIS for .NET: ライブラリを [Aspose.GIS for .NET ダウンロードページ](https://releases.aspose.com/gis/net/) からダウンロードしてインストールします。  
- 開発環境: Visual Studio などの .NET 開発環境をセットアップします。  
- シェープファイル: サンプルのシェープファイル（例: "InputShapeFile.shp"）をドキュメントディレクトリに用意します。  

## 名前空間のインポート
C# コードで、Aspose.GIS の機能を利用するために必要な名前空間をインポートします：

```csharp
using System;
using Aspose.Gis;
```

## ステップ 1: ドキュメントディレクトリの設定
"Your Document Directory" をシェープファイルが配置されている実際のパスに置き換えます。

```csharp
string dataDir = "Your Document Directory";
```

## ステップ 2: VectorLayer を開く
このステップでは、Aspose.GIS を使用してシェープファイルを開き、ファイルパスとフォーマット（この場合は Shapefile）を指定します。

```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```

## ステップ 3: すべてのフィーチャ属性値を取得する
このスニペットは、固定サイズの配列にロードすることで、すべてのフィーチャの属性を **読み取る方法** を示しています。

```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```

## ステップ 4: 複数のフィーチャ属性値を取得する
ここでは、フィールドのサブセットだけが必要な場合に、**特定の属性値を読み取る方法** を示します。

```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```

## ステップ 5: 属性値をオブジェクトダンプとして取得する
この最終ステップでは、`GetValuesDump()` を使用して属性を **ダンプする方法** を示します。このメソッドは、検査やシリアライズが可能な柔軟なコレクションを返します。

```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```

## 一般的な問題と解決策
- **配列サイズの不一致** – `GetValues` に渡す配列が期待する属性数と一致していることを確認してください。そうでないと `null` エントリが返ります。  
- **ファイルが見つからない** – `dataDir` が正しいフォルダを指しているか、シェープファイル名が正確に綴られているか確認してください。  
- **ライセンス例外** – ライセンスエラーが表示された場合、API メソッドを呼び出す前に一時またはフルライセンスを適用してください。  

## よくある質問
### Aspose.GIS は .NET Core と互換性がありますか？
はい、Aspose.GIS は .NET Core と完全に互換性があり、クロスプラットフォームアプリケーションを構築できます。

### Aspose.GIS を使用してさまざまな GIS ファイル形式を扱えますか？
もちろんです！Aspose.GIS は Shapefile、GeoJSON など多数のフォーマットをサポートしています。

### Aspose.GIS のサポート用コミュニティフォーラムはありますか？
はい、[サポートフォーラム](https://forum.aspose.com/c/gis/33) で支援を受け、Aspose.GIS コミュニティと交流できます。

### Aspose.GIS の一時ライセンスはどのように取得できますか？
テスト目的の一時ライセンスは[こちら](https://purchase.aspose.com/temporary-license/)から取得できます。

### Aspose.GIS の詳細なドキュメントはどこで見つけられますか？
包括的なドキュメントは[こちら](https://reference.aspose.com/gis/net/)で利用できます。

### 各フィーチャから「Name」属性だけを取得するには？
`GetValues` を使用し、要素数 1 の配列を作成して「Name」フィールドのインデックスを渡すか、`feature["Name"]` を直接呼び出します。

### `GetValues` と `GetValuesDump` の違いは何ですか？
`GetValues` は事前に確保した配列に生の値を埋め込みますが、`GetValuesDump` はスキーマを事前に知らなくても列挙可能なオブジェクト配列を返します。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---