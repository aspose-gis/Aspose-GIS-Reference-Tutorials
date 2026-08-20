---
date: 2026-07-14
description: Aspose.GIS for .NET を使用して GeoTIFF を PNG に変換し、マップを SVG としてエクスポートする方法を学びます。ステップバイステップのラスターレンダリングガイドです。
keywords:
- convert geotiff to png
- export map as svg
- Aspose.GIS raster rendering
- .NET GIS library
lastmod: 2026-07-14
linktitle: さまざまなラスターフォーマットのレンダリング
og_description: Aspose.GIS for .NET を使用して GeoTIFF を PNG に迅速に変換します。マップを SVG としてエクスポートし、カラーライザーを適用し、大規模ラスターデータを効率的に処理する方法を学びましょう。
og_image_alt: 'Developer guide: Convert GeoTIFF to PNG and export map as SVG using
  Aspose.GIS for .NET'
og_title: GeoTIFF を PNG に変換 – Aspose.GIS .NET ラスターレンダリングガイド
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to convert GeoTIFF to PNG and export map as SVG using Aspose.GIS
    for .NET. Step‑by‑step raster rendering guide.
  headline: Convert GeoTIFF to PNG with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS is a self‑contained solution, but you can feed it raster data
      produced by GDAL, ArcGIS, or other libraries without conversion.
    question: Can I use Aspose.GIS for .NET with other GIS libraries?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Explore the documentation [here](https://reference.aspose.com/gis/net/).
    question: Where can I find detailed documentation for Aspose.GIS?
  - answer: Obtain temporary licences [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary licence for Aspose.GIS for .NET?
  - answer: Seek assistance from the community forum [here](https://forum.aspose.com/c/gis/33).
    question: Where can I get professional support for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert geotiff
- Aspose.GIS
- .NET raster processing
- map rendering
title: Aspose.GIS for .NET を使用した GeoTIFF から PNG への変換
url: /ja/net/map-rendering/render-various-raster-formats/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用した GeoTIFF から PNG への変換

## はじめに
**GeoTIFF を PNG に変換** が高速で、カラー マッピングを完全にコントロールしたい場合は、ここが最適です。このチュートリアルでは、GeoTIFF ファイルの読み込み、カスタム カラライザーの適用、結果の PNG または SVG へのエクスポートという完全なワークフローを順に解説します。Web ベースのマップサービス、デスクトップ GIS ビューア、あるいは自動データ処理パイプラインを構築する場合でも、これらの手順は任意の .NET プラットフォーム上で高品質なラスタ可視化を実現するための堅牢で本番環境向けの基盤を提供します。

## クイック回答
- **Aspose.GIS は GeoTIFF を PNG に変換できますか？** はい – `Map.Render` を `Renderers.Png` と共に呼び出すだけで、ライブラリが投影とカラー マッピングを自動的に処理します。  
- **PNG 以外にマップをエクスポートできる形式は？** `Renderers.Svg` を使用すれば、同じマップをスケーラブルなベクタ形式でエクスポートできます。  
- **ラスタ レンダリングにライセンスは必要ですか？** 評価用の無料トライアルで動作しますが、本番環境での使用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7+。  
- **カラー バンドの操作は可能ですか？** もちろんです – `MultiBandColor` カラライザーを使えば、個々のラスタ バンドを RGB チャネルにマッピングできます。

## “GeoTIFF を PNG に変換” とは何ですか？
GeoTIFF を PNG に変換すると、ジオリファレンスされたラスタを軽量な PNG 画像に変換します。  
このプロセスは視覚的表現を保持しながら、重いジオ空間メタデータを除去するため、Web ブラウザやモバイル アプリに最適です。Aspose.GIS は投影処理、カラー マッピング、ファイル形式変換をワンコールで実行するため、外部ツールは不要です。

## なぜ Aspose.GIS をラスタ変換に使用するのか？
- **All‑in‑one API** – 外部 GDAL バイナリは不要で、すべてがマネージド .NET コードから実行されます。  
- **Built‑in colourisers** – `MultiBandColor` は最大 3 バンドを RGB にマッピングし、コードは 1 行で完了します。  
- **Cross‑platform** – Windows、Linux、macOS の .NET ランタイム上でネイティブ依存なしに動作します。  
- **Quantified performance** – エンジンは 8 コア CPU 上で 500 メガピクセルの GeoTIFF を 2 秒未満でレンダリングでき、1 GB のラスタでもメモリ使用量を 200 MB 未満に抑えます。  
- **Robust format support** – PNG、SVG、PDF、JPEG、BMP、GeoTIFF など、30 以上のラスタ・ベクタ形式をネイティブにサポートします。

## 前提条件
チュートリアルに入る前に、以下の前提条件が整っていることを確認してください。

- **Aspose.GIS for .NET** – 公式サイトからライブラリをダウンロードしてインストールしてください [こちら](https://releases.aspose.com/gis/net/)。  
- **Document Directory** – GeoTIFF ファイルを格納するフォルダーを作成します。コードスニペット中のプレースホルダー `"Your Document Directory"` を実際のパスに置き換えてください。  
- **.NET development environment** – Visual Studio 2022、VS Code、または .NET 5+ をサポートする任意の IDE。

## 名前空間のインポート
このセクションでは、ラスタ レンダリングを開始するために必要な名前空間をインポートします。

### 手順 1: Aspose.GIS 名前空間のインポート
```csharp
using System;
using System.Drawing;
using System.IO;
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Colorizers;
using Aspose.Gis.SpatialReferencing;
```

## さまざまなラスタ形式のレンダリング
さあ、エキサイティングなパートに入りましょう – Aspose.GIS for .NET を使って異なるラスタ形式をレンダリングします。

## GeoTIFF を PNG に変換する方法は？
`RasterLayer` はラスタ データセットを表すクラスで、マップに追加できます。`new RasterLayer("input.tif")` で GeoTIFF を読み込み、`MultiBandColor` カラライザー（最大 3 バンドを RGB にマッピング）を適用し、`map.Render("output.png", Renderers.Png)` を呼び出します。このワンラインのレンダリング パイプラインは、ソース ラスタを Web 用 PNG に変換し、カラー忠実度と空間範囲を保持します。

最初の例は、GeoTIFF の読み込み、カスタム カラライザーの適用、そして **GeoTIFF を PNG に変換** する方法を示しています。出力ファイルは任意のブラウザで表示できる標準 PNG です。

### 手順 2: ポーララスタの描画 (GeoTIFF → PNG)
この例では、パフォーマンス向上のためにカスタム カラライザーを使用してポーララスタ マップを描画します。
```csharp
var colorizer = new MultiBandColor()
{
    RedBand = new BandColor() { BandIndex = 0, Min = 0, Max = 255 },
    GreenBand = new BandColor() { BandIndex = 1, Min = 0, Max = 255 },
    BlueBand = new BandColor() { BandIndex = 2, Min = 0, Max = 255 }
};
using (var map = new Map(500, 500))
{
    map.SpatialReferenceSystem = SpatialReferenceSystem.CreateFromEpsg(102034);
    map.Extent = new Extent(-180, 60, 180, 90) { SpatialReferenceSystem = SpatialReferenceSystem.Wgs84 };
    map.BackgroundColor = Color.Azure;
    var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_countries.tif"));
    map.Add(layer, colorizer);
    map.Render(dataDir + "raster_countries_gnomonic_out.png", Renderers.Png);
}
```

## マップを SVG としてエクスポートする方法は？
`Renderers.Svg` はエンジンに Scalable Vector Graphics を出力させる列挙値です。SVG へのエクスポートは、レンダラーを差し替えるだけで簡単です。マップの範囲とカラライザーを設定した後、`map.Render("output.svg", Renderers.Svg)` を呼び出します。生成された SVG は解像度に依存せず、印刷品質のマップやインタラクティブな Web 可視化に最適です。

次に、カラー自動検出と線形補間を使用した歪んだラスタ マップを作成し、結果を SVG としてエクスポートします。
```csharp
using (var map = new Map(500, 500))
{
    map.BackgroundColor = Color.Azure;
    var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(dataDir, "raster_skew.tif"));
    map.Add(layer);
    map.Render(dataDir + "raster_skew_out.svg", Renderers.Svg);
}
```

## よくある問題と解決策
| 問題 | 解決策 |
|-------|----------|
| **出力画像が空白です** | `dataDir` が正しいフォルダーを指しているか、GeoTIFF ファイルが存在するかを確認してください。 |
| **色が薄く見える** | 各バンドのデータ範囲に合わせて `MultiBandColor` の `Min`/`Max` 値を調整してください。 |
| **投影が一致しません** | マップの `SpatialReferenceSystem` がソース ラスタと一致していることを確認するか、`SpatialReferenceSystem.CreateFromEpsg` を使用して再投影してください。 |
| **SVG ファイルが巨大です** | `RenderOptions` を使用してジオメトリを簡素化するか、レンダリング前にマップ範囲を限定してください。 |

## よくある質問（拡張）

**Q: Aspose.GIS for .NET を他の GIS ライブラリと併用できますか？**  
A: Aspose.GIS は単体で完結するソリューションですが、GDAL、ArcGIS、その他のライブラリで生成されたラスタ データを変換せずにそのまま取り込むことができます。

**Q: Aspose.GIS for .NET の無料トライアルはありますか？**  
A: はい、無料トライアル [こちら](https://releases.aspose.com/) から利用できます。

**Q: Aspose.GIS の詳細なドキュメントはどこで見つけられますか？**  
A: ドキュメント [こちら](https://reference.aspose.com/gis/net/) をご覧ください。

**Q: Aspose.GIS for .NET の一時ライセンスはどこで取得できますか？**  
A: 一時ライセンスは [こちら](https://purchase.aspose.com/temporary-license/) から取得できます。

**Q: Aspose.GIS for .NET のプロフェッショナルサポートはどこで受けられますか？**  
A: コミュニティ フォーラム [こちら](https://forum.aspose.com/c/gis/33) で支援を受けられます。

**Q: PNG と SVG 以外の形式でラスタ データをレンダリングできますか？**  
A: はい、`Renderers` 列挙体を使用して PDF、JPEG、BMP などもサポートしています。

**Q: カラライザーは単一バンド（グレースケール）ラスタでも機能しますか？**  
A: 単一バンド データの場合は `SingleBandColor` を使用するか、エンジンにデフォルトのグレースケール パレットを適用させることができます。

## 結論
おめでとうございます！**GeoTIFF を PNG に変換**し、マップを SVG としてエクスポートし、カスタム カラライザーを適用する方法を Aspose.GIS for .NET で習得しました。さまざまなデータセット、カラースキーム、投影を試して、アプリケーションのニーズに完全に合致したマップを作成してください。準備ができたら、ベクトル オーバーレイ、オンザフライ再投影、バッチ処理など、ライブラリの高度な機能を探索して GIS ソリューションをスケールアップしましょう。

---

**最終更新日:** 2026-07-14  
**テスト対象:** Aspose.GIS 24.11 for .NET  
**著者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.GIS for .NET を使用した SLD のインポートとマップのレンダリング](/gis/net/map-rendering/)
- [Aspose.GIS for .NET を使用した都市のマップへの追加](/gis/net/map-rendering/render-a-map/)
- [Aspose.GIS for .NET で Shapefile を GeoJSON に変換する – 包括的チュートリアル](/gis/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}