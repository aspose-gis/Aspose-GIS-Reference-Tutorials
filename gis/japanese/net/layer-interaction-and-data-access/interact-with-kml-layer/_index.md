---
date: 2026-01-07
description: Aspose.GIS for .NET を使用して KML ファイルの書き込み方法、KML の作成方法、ブール属性の追加方法、そしてアプリケーションでのラインストリングの作成方法を学びましょう。
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: .NET 用 Aspose.GIS で KML ファイルを書き込む方法
url: /ja/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した KML ファイルの書き込み方法

## はじめに
データ駆動型の現代において、**KML ファイルを書き込む**ことができれば、地理情報をプラットフォーム間で共有したり、マップ上にルートを可視化したり、位置データを Web やモバイルアプリに統合したりすることが可能になります。Aspose.GIS for .NET はこのプロセスをシンプルにし、ファイル形式の細部に煩わされることなくロジックに集中できるようにします。本チュートリアルでは、KML レイヤーの作成、属性（ブール属性を含む）の追加、ラインストリングジオメトリの構築を、分かりやすいステップバイステップのコードで解説します。

## クイック回答
- **「KML ファイルを書き込む」とは何ですか？**  
  ポイント、ライン、ポリゴンなどの地理的特徴を記述した KML（Keyhole Markup Language）ドキュメントを生成することです。  
- **.NET 向けの最なライブラリはどれですか？**  
  Aspose.GIS for .NET は、KML ファイルの作成・編集に適したフルエント API を提供します。  
- **開発時にライセンスは必要ですか？**  
  評価用の無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **カスタム属性は追加できますか？**  
  はい、文字列、整数、ブール、倍精度実数の属性を各フィーチャーに追加できます。  
- **ジオメトリの作成はサポートされていますか？**  
  もちろんです。ポイント、ラインストリング、ポリゴンなどを作成できます。

## 前提条件
この手順を始める前に、以下の環境が整っていることを確認してください。
- Aspose.GIS for .NET: [Aspose.GIS for .NET ダウンロードページ](https://releases.aspose.com/gis/net/) からライブラリを取得し、インストールしてください。  
- 開発環境: Visual Studio など、Aspose.GIS を .NET プロジェクトにシームレスに統合できる開発環境を用意してください。

## 名前空間のインポート
KML レイヤーを操作する前に、プロジェクトに必要な名前空間をインクルードします。この手順により、地理空間データ操作に必要なクラスやメソッドが利用可能になります。

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## 手順 1: ドキュメントディレクトリの設定
KML ファイルを保存するドキュメントディレクトリへのパスを定義します。

```csharp
string dataDir = "Your Document Directory";
```

## 手順 2: KML レイヤーの作成
Aspose.GIS を使用して KML レイヤーを初期化し、KML ファイルの保存先パスを指定します。

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## 手順 3: 属性の定義（ブール属性の追加）
文字列、整数、**ブール**、倍精度実数といったさまざまなデータ型を表す属性を KML レイヤーに追加します。ここで各フィーチャーに「ブール属性」を追加します。

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## 手順 4: フィーチャーの構築と属性設定（ラインストリングの作成）
地理空間エンティティを表すフィーチャーを構築し、定義した属性に値を設定します。ここでは **ラインストリング** ジオメトリを作成し、シンプルなパスを示します。

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## 手順 5: もう一つのフィーチャーを追加
別の属性値と null ジオメトリを持つ第二のフィーチャーを追加する手順を繰り返します。

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## KML ファイルの書き込み – すべてをまとめる
上記の手順に従うことで、カスタム属性（ブールフラグを含む）とラインストリングジオメトリを持つ完全な KML ファイルが作成できます。生成された `Kml_File_out.kml` は Google Earth、ArcGIS、または KML をサポートする任意の GIS ビューアで開くことができます。

## 一般的な問題とトラブルシューティング
- **ファイルパスエラー** – `dataDir` の末尾が OS に適したパス区切り文字（`\` または `/`）で終わっていることを確認してください。  
- **ライセンスがない** – トライアルは評価用に機能しますが、KML ファイルの無制限書き込みにはライセンス版が必要です。  
- **ジオメトリが null** – `Geometry.Null` の設定は空間データがないフィーチャー用に意図的に行われています。常にジオメトリが必要な場合は省略してください。

## よくある質問
### Aspose.GIS は他の GIS フォーマットと互換性がありますか？
はい、Aspose.GIS はシェープファイル、GeoJSON、KML などさまざまな GIS フォーマットをサポートしています。

### Aspose.GIS で作成した地理空間データを可視化できますか？
もちろんです。Aspose.GIS はマッピングライブラリとシームレスに統合でき、作成したデータを簡単に可視化できます。

### Aspose.GIS のトライアル版はありますか？
はい、[無料トライアル版](https://releases.aspose.com/) をダウンロードして機能をお試しいただけます。

### Aspose.GIS のサポートはどこで受けられますか？
[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) でコミュニティサポートを受けるか、[こちら](https://purchase.aspose.com/buy) からプレミアムサポートオプションをご確認ください。

### Aspose.GIS の一時ライセンスは取得できますか？
はい、[こちら](https://purchase.aspose.com/temporary-license/) から時ライセンスをご取得いただけます。

## 追加のよくある質問

**Q: カスタムスタイリング付きの **KML** ファイルはどう作成しますか？**  
A: `Aspose.Gis.Formats.Kml.Styles` 名前空間を使用して、アイコン、ラインカラー、ラベルスタイルなどを定義し、フィーチャーを追加する前に設定します。

**Q: 大容量の KML ファイルを書き込む際の効率的な方法はありますか？**  
A: フィーチャーをバッチで書き込み、定期的にレイヤーをフラッシュすることでメモリ使用量を抑えられます。

**Q: Aspose.GIS は .NET Core および .NET 6+ に対応していますか？**  
A: はい、.NET Core、.NET 5、.NET 6 すべてに完全対応しています。

---

**最終更新日:** 2026-01-07  
**テスト環境:** Aspose.GIS 24.10 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}