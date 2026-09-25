---
date: 2026-09-25
description: Aspose.GIS for .NET を使ってマルチラインストリングジオメトリを素早く作成する方法を学びます。この C# チュートリアルでは、複雑なラインジオメトリのステップバイステップ作成方法を示します。
keywords:
- create multilinestring geometry
- how to create multilinestring
- multilinestring example c#
lastmod: 2026-09-25
linktitle: MultiLineString ジオメトリを作成する
og_description: Aspose.GIS for .NET で数分で MultiLineString ジオメトリを作成します。この C# チュートリアルに従って、マッピングや分析用の複雑なラインジオメトリを構築しましょう。
og_image_alt: Code example showing creation of MultiLineString geometry with Aspose.GIS
  in C#
og_title: Aspose.GIS for .NET を使用して MultiLineString ジオメトリを作成する
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to quickly create multilinestring geometry with Aspose.GIS
    for .NET. This multilinestring tutorial C# shows step‑by‑step creation of complex
    line geometries.
  headline: Create MultiLineString geometry using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can call `multiLineString.Save("output.geojson", new GeoJsonOptions());`
      after adding the necessary using directives.
    question: Can I export the MultiLineString to GeoJSON?
  - answer: Use `multiLineString.SpatialReference = new SpatialReference(4326);` to
      assign WGS 84 (EPSG:4326).
    question: How do I set a spatial reference (SRID) for the MultiLineString?
  - answer: Absolutely. Use `FeatureReader` to iterate over features and cast the
      geometry to `MultiLineString`.
    question: Is it possible to read a MultiLineString from a Shapefile?
  - answer: Duplicate points are allowed but may affect length calculations and rendering;
      consider cleaning the data if duplicates are unintended.
    question: What happens if I add duplicate points to a LineString?
  - answer: Yes, you can add a Z value with `AddPoint(x, y, z);` and the geometry
      will be stored as 3‑dimensional.
    question: Does Aspose.GIS support 3D coordinates for MultiLineString?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create multilinestring
- Aspose.GIS
- .NET GIS development
title: Aspose.GIS for .NET を使用して MultiLineString ジオメトリを作成する
url: /ja/net/geometry-creation/create-multilinestring-geometry/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET を使用したマルチラインストリングジオメトリの作成

## はじめに
このチュートリアルでは、Aspose.GIS for .NET を使用して **マルチラインストリングジオメトリ** を作成します。道路、河川、ユーティリティネットワークなどの線状フィーチャのコレクションを表現する必要がある場合に一般的に求められる要件です。マッピングアプリケーションの構築、空間分析の実施、または複雑なラインデータのエクスポートを行う際に、本ガイドはステップバイステップで手順を案内します。

Aspose.GIS for .NET は、開発者が .NET アプリケーション内で地理空間データをシームレスに扱える強力なライブラリです。デスクトップとサーバーサイドのシナリオの両方をサポートし、.NET Framework、.NET Core、.NET 5/6/7 にまたがる一貫した API を提供します。

## クイック回答
- **「マルチラインストリングジオメトリを作成する」とは何ですか？** これは、複数の `LineString` コンポーネントを含む単一のジオメトリオブジェクトを構築することを意味します。  
- **使用されているライブラリはどれですか？** Aspose.GIS for .NET。  
- **ライセンスは必要ですか？** はい、商用利用には商用ライセンスが必要です。無料トライアルも利用可能です。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7。  
- **実装にどれくらい時間がかかりますか？** この基本例では、通常 10 分未満で完了します。

## MultiLineString ジオメトリとは？
**MultiLineString** は、2 つ以上の `LineString` オブジェクトを単一の空間エンティティとしてまとめたコレクションです。  
河川ネットワークや道路セグメントの集合など、複数の関連する線を 1 つのフィーチャとして扱いながら、各線が独自の座標列を保持する必要がある場合に作成します。このクラスは `Aspose.GIS.Geometry` 名前空間にあり、Shapefile、GeoJSON、KML などの形式にシリアライズできます。

## MultiLineString を作成するために Aspose.GIS for .NET を使用する理由
Aspose.GIS を使用すれば、数回のフルエントな呼び出しだけで MultiLineString を構築でき、低レベルのジオメトリバッファを管理する必要がなくなります。**最大 500 MB のベクトルデータをメモリ効率の高いストリーミングモードで処理**し、**50 以上の入出力フォーマットに対応**、外部のネイティブ依存関係なしで **すべての主要な .NET ランタイム上で動作**します。この速度、フォーマットの広さ、クロスプラットフォームの安定性の組み合わせにより、エンタープライズ GIS プロジェクトの第一選択肢となります。

## 前提条件
コードに取り掛かる前に、以下が揃っていることを確認してください。

### .NET 開発環境
1. Visual Studio 2022（または .NET 6+ をサポートする任意の IDE）をインストール。  
2. NuGet パッケージを使用できる .NET 6 コンソールプロジェクトを用意。

### Aspose.GIS for .NET
1. [purchase.aspose.com](https://purchase.aspose.com/buy) から Aspose.GIS for .NET のライセンスを取得。  
2. [releases.aspose.com](https://releases.aspose.com/gis/net/) からライブラリをダウンロード。  
3. NuGet でパッケージを追加（`Install-Package Aspose.GIS`）または DLL を手動で参照。

## 名前空間のインポート
以下の名前空間をインポートすると、コア GIS 機能にアクセスできます。

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
この名前空間は Aspose.GIS のコア機能へのアクセスを提供し、さまざまな種類の空間データを扱うことができます。

それでは、提供されたサンプルを複数のステップに分解してみましょう。

## マルチラインストリングジオメトリの作成方法
2 つの `LineString` オブジェクトをインスタンス化し、ポイントを追加してから `MultiLineString` に結合します。全体の操作は 3 回のメソッド呼び出しだけで完了します：ラインオブジェクトの作成、座標の追加、そしてラインをコレクションに追加することです。各 `LineString` は順序付けされたポイントリストで定義された単一のラインジオメトリを表し、`MultiLineString` は複数のラインを 1 つのジオメトリとして表す `LineString` オブジェクトのコレクションです。

### 手順 1: LineString オブジェクトの作成
```csharp
LineString firstLine = new LineString();
firstLine.AddPoint(7.5, -3.5);
firstLine.AddPoint(-9.6, 12.6);
LineString secondLine = new LineString();
secondLine.AddPoint(8.5, -2.6);
secondLine.AddPoint(-8.6, 1.5);
```
この手順では、個別のラインを表す 2 つの `LineString` オブジェクトを作成します。各 `LineString` にポイントを追加してジオメトリを定義します。

### 手順 2: MultiLineString オブジェクトの作成
```csharp
MultiLineString multiLineString = new MultiLineString();
multiLineString.Add(firstLine);
multiLineString.Add(secondLine);
```
ここでは、`MultiLineString` オブジェクトをインスタンス化し、先に作成した `LineString` オブジェクトを追加します。これにより、単一のエンティティとしてまとめられたラインのコレクションが生成されます。

## よくある問題とヒント
- **座標順序:** Aspose.GIS は座標を **(X, Y)** の順序（経度、緯度）で期待します。順序が混在するとジオメトリが逆転する可能性があります。  
- **空のジオメトリ:** 空の `LineString` を追加しようとすると例外がスローされます。各ラインが少なくとも 2 点を含んでいることを必ず確認してください。  
- **投影の取り扱い:** データが特定の CRS を使用している場合、エクスポート前にジオメトリに空間参照を設定してください。

## 結論
Aspose.GIS for .NET は、複雑なラインジオメトリの構築と操作のための簡潔で高性能な API を提供します。上記の手順に従うことで、**マルチラインストリングジオメトリ** を迅速に作成し、サポートされている任意の GIS フォーマットへエクスポートできます。

## FAQ

### Aspose.GIS for .NET はすべての .NET フレームワークと互換性がありますか？
はい、Aspose.GIS for .NET はさまざまなバージョンの .NET フレームワークと互換性があり、開発者に柔軟性を提供します。

### 購入前に Aspose.GIS for .NET を試すことはできますか？
もちろんです！[releases.aspose.com](https://releases.aspose.com/) から無料トライアル版をダウンロードして、機能と性能を体験できます。

### Aspose.GIS for .NET のサポートはどのように受けられますか？
サポートや支援が必要な場合は、[Aspose.GIS フォーラム](https://forum.aspose.com/c/gis/33) にアクセスしてください。ここで質問したり、他のユーザーや専門家と交流できます。

### テスト目的で一時ライセンスは必要ですか？
トライアル版はテストに利用できますが、追加機能が必要だったり、フル機能を評価したい場合は、[purchase.aspose.com](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Aspose.GIS for .NET はデスクトップとウェブの両方のアプリケーションに適していますか？
はい、Aspose.GIS for .NET はデスクトップ、ウェブ、サーバーサイドシナリオなど、さまざまなアプリケーションで使用でき、異なる開発環境において汎用性を提供します。

## よくある質問
**Q: MultiLineString を GeoJSON にエクスポートできますか？**  
A: はい、必要な using ディレクティブを追加した後、`multiLineString.Save("output.geojson", new GeoJsonOptions());` を呼び出すことでエクスポートできます。

**Q: MultiLineString の空間参照（SRID）を設定するには？**  
A: `multiLineString.SpatialReference = new SpatialReference(4326);` を使用して、WGS 84（EPSG:4326）を割り当てます。

**Q: Shapefile から MultiLineString を読み取ることは可能ですか？**  
A: 可能です。`FeatureReader` を使用してフィーチャを反復処理し、ジオメトリを `MultiLineString` にキャストします。

**Q: LineString に重複ポイントを追加した場合はどうなりますか？**  
A: 重複ポイントは許容されますが、長さ計算や描画に影響を与える可能性があります。意図しない重複がある場合はデータをクリーンアップすることを検討してください。

**Q: Aspose.GIS は MultiLineString の 3D 座標をサポートしていますか？**  
A: はい、`AddPoint(x, y, z);` で Z 値を追加すれば、ジオメトリは 3 次元として保存されます。

**最終更新日:** 2026-09-25  
**テスト環境:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.GIS を使用した MultiPolygon ジオメトリの作成方法を学ぶ](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [.NET 用 Aspose.GIS でポリゴンジオメトリを作成する方法](/gis/net/geometry-creation/create-polygon-geometry/)
- [WKT をジオメトリに変換: Aspose.GIS .NET で MultiCurve](/gis/net/geometry-creation/create-multicurve-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}