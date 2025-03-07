---
title: GeoJSON から TopoJSON への変換
linktitle: GeoJSON から TopoJSON への変換
second_title: Aspose.GIS .NET API
description: Aspose.GIS for .NET ライブラリを使用して GeoJSON ファイルを TopoJSON 形式にシームレスに変換する方法を学びます。 GIS データ処理の効率を高めます。
weight: 11
url: /ja/net/geo-data-conversion/convert-geojson-to-topojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON から TopoJSON への変換

## 導入
地理情報システム (GIS) の領域では、データ交換フォーマットは、異なるシステム間のデータ交換と相互運用性を促進する上で重要な役割を果たします。このような一般的な形式としては、GeoJSON と TopoJSON の 2 つがあります。地理データ構造をエンコードするための軽量形式である GeoJSON と、GeoJSON の拡張機能である TopoJSON は、地理データのより効率的な保存と送信のためのトポロジ エンコードを提供します。このチュートリアルでは、Aspose.GIS for .NET ライブラリを使用して GeoJSON を TopoJSON に変換する方法について詳しく説明します。
## 前提条件
変換プロセスに入る前に、次の前提条件が設定されていることを確認してください。
### Aspose.GIS for .NET のインストール
1. Aspose.GIS for .NET ライブラリをダウンロードします。[このリンク](https://releases.aspose.com/gis/net/)Aspose.GIS for .NET ライブラリをダウンロードします。
2. ライブラリをインストールします。ドキュメントに記載されているインストール手順に従います。[ここ](https://reference.aspose.com/gis/net/).

## 必要な名前空間のインポート
必要な名前空間を .NET プロジェクトにインポートしていることを確認してください。
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: GeoJSON ファイルをロードする
まず、TopoJSON に変換する GeoJSON ファイルをロードする必要があります。ファイルパスが手元にあることを確認してください。
## ステップ 2: 出力ファイルのパスを定義する
変換された TopoJSON ファイルを保存するパスを指定します。そのディレクトリへの書き込み権限があることを確認してください。
## ステップ 3: 変換を実行する
を活用してください。`VectorLayer.Convert()`ロードされた GeoJSON ファイルを TopoJSON 形式に変換するメソッド。適切なドライバーパラメータを渡します(`Drivers.GeoJson`入力用と`Drivers.TopoJson`出力用) とファイル パス。
```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSample_out.topojson";
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson);
```

## 結論
GeoJSON から TopoJSON への変換は、GIS データ処理において不可欠なタスクであり、地理データの効率的な保存と送信を可能にします。 Aspose.GIS for .NET ライブラリを使用すると、このプロセスが合理化され、.NET 開発者がアクセスしやすくなります。
## よくある質問
### Aspose.GIS for .NET は、.NET のすべてのバージョンと互換性がありますか?
はい、Aspose.GIS for .NET は、.NET Framework および .NET Core のすべてのバージョンと互換性があります。
### 購入する前に Aspose.GIS for .NET を試すことはできますか?
はい、以下から無料トライアルを利用できます。[このリンク](https://releases.aspose.com/).
### Aspose.GIS for .NET は、GeoJSON と TopoJSON 以外の他の GIS 形式をサポートしていますか?
はい、Aspose.GIS for .NET は、読み取りと書き込みのために幅広い GIS 形式をサポートしています。
### Aspose.GIS for .NET のサポートを受けるにはどうすればよいですか?
 Aspose.GIS コミュニティ フォーラムからサポートを求めることができます。[ここ](https://forum.aspose.com/c/gis/33).
### Aspose.GIS for .NET を商用プロジェクトに使用できますか?
はい、次からライセンスを購入できます。[このリンク](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
