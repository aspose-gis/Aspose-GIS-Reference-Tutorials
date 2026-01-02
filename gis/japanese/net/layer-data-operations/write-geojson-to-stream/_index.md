---
date: 2026-01-02
description: Aspose.GIS for .NET を使用して C# で GeoJSON をストリームに書き込む方法を学びましょう。GeoJSON の
  C# サンプルを表示し、ジオスペーシャル アプリを強化します。
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: .NET 用 Aspose.GIS で GeoJSON をストリームに書き込む方法
url: /ja/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON をストリームに書き込む方法

## Introduction
.NET アプリケーションで **GeoJSON の書き込み方法** をメモリストリームやファイルストリームに直接行いたい場合は、ここが適切な場所です。このチュートリアルでは、Aspose.GIS for .NET ライブラリを使用して GeoJSON をストリームに書き込む手順を詳しく解説し、さらに **GeoJSON C# の出力をコンソールに表示** する方法も紹介します。最後まで読めば、任意のジオスペーシャルプロジェクトに組み込める再利用可能なパターンが手に入ります。

## Quick Answers
- **「GeoJSON をストリームに書き込む」とは何ですか？** ベクターレイヤーを GeoJSON 形式にシリアライズし、そのバイト列を `Stream` オブジェクト（例: `MemoryStream`）に送ることを指します。  
- **どのライブラリがこれを処理しますか？** Aspose.GIS for .NET が組み込みの GeoJSON ドライバーを提供します。  
- **開発用にライセンスは必要ですか？** 開発段階では無料トライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **Linux でも実行できますか？** はい – Aspose.GIS はクロスプラットフォームで、Windows、Linux、macOS で動作します。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## What is “how to write geojson” in .NET?
Aspose.GIS を使用すると `VectorLayer` を作成し、フィーチャーを追加した後、`Drivers.GeoJson` ドライバーでレイヤーをシリアライズできます。このドライバーは GeoJSON テキストを任意の `Stream` に直接書き込むため、データの保存先（メモリ、ファイル、ネットワークなど）を完全にコントロールできます。

## Why use Aspose.GIS for this task?
- **Zero‑dependency serialization** – 外部の JSON ライブラリは不要です。  
- **Full GeoJSON spec compliance** – FeatureCollection、プロパティ、座標精度をすべてサポート。  
- **Cross‑platform** – Windows、Linux、macOS で同一の挙動。  
- **Performance‑optimized** – 中間文字列を生成せず、直接ストリームへ書き込みます。

## Prerequisites
1. **Aspose.GIS for .NET** – ダウンロードは [here](https://releases.aspose.com/gis/net/) から。  
2. **Document directory** – 一時ファイルや出力ストリームを保存するフォルダーを決めておきます。

それではコードを見ていきましょう。

## Import Namespaces
まず、Aspose.GIS のクラスと標準 .NET I/O ユーティリティにアクセスできる名前空間をインポートします。

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Step 1: Set up the Document Directory
一時ファイルを格納するフォルダーを定義します。

```csharp
string dataDir = "Your Document Directory";
```

`"Your Document Directory"` を実際のパスに置き換えてください。

## Step 2: Create a Memory Stream
`MemoryStream` を使用すると、GeoJSON をメモリ上に保持でき、API のレスポンスやクライアントへの直接返却に最適です。

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Step 3: Create a Vector Layer with GeoJSON Driver
メモリストリーム内で、GeoJSON ドライバーを使用する `VectorLayer` を作成します。これにより Aspose.GIS がレイヤーを GeoJSON としてシリアライズします。

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Step 4: Define Feature Attributes
最終的な GeoJSON 出力にプロパティとして現れる属性定義を追加します。

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Step 5: Construct and Add Features
サンプルのポイントを 2 つ作成し、属性値を割り当ててレイヤーに追加します。

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Step 6: Display GeoJSON C# Output
レイヤーが完成したら、ストリームのバイト列を UTF‑8 文字列に変換し、コンソールに出力します。これで **GeoJSON C# の出力を表示** する方法が確認できます。

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

端末に有効な GeoJSON FeatureCollection が表示されるはずです。

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Empty output | Stream position is at the end when reading | Call `memoryStream.Position = 0;` before converting to a string. |
| Invalid geometry | Coordinates are outside valid ranges | Verify latitude is between -90 and 90, longitude between -180 and 180. |
| License exception | Running without a valid license in production | Apply a temporary or full license using `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Frequently Asked Questions
### Can I use Aspose.GIS for .NET in both Windows and Linux environments?
Yes, Aspose.GIS for .NET is compatible with both Windows and Linux systems.  

### Is there a free trial available?
Absolutely! You can explore a free trial [here](https://releases.aspose.com/).  

### Where can I find detailed documentation?
Check out the documentation [here](https://reference.aspose.com/gis/net/).  

### How can I get temporary licensing?
Temporary licenses are available [here](https://purchase.aspose.com/temporary-license/).  

### Need assistance or have more questions?
Visit our support forum [here](https://forum.aspose.com/c/gis/33).

## FAQ
**Q: Can I write GeoJSON directly to a file instead of a memory stream?**  
A: Yes—replace `MemoryStream` with `FileStream` and provide a file path. The same driver works.

**Q: How do I control the indentation or formatting of the generated GeoJSON?**  
A: Aspose.GIS writes compact JSON by default. For pretty‑printed output, post‑process the string with `JsonSerializerOptions { WriteIndented = true }`.

**Q: Is it possible to add more complex geometries (e.g., polygons) to the layer?**  
A: Absolutely. Create a `Polygon` or `LineString` object, assign it to `Feature.Geometry`, and add the feature as shown above.

**Q: Will large datasets fit into a `MemoryStream`?**  
A: For very large collections, consider streaming directly to a file or using a `BufferedStream` to avoid high memory consumption.

**Q: Does the GeoJSON driver support CRS (Coordinate Reference System) definitions?**  
A: Yes—set the layer’s `SpatialReferenceSystem` property before adding features if you need a non‑WGS84 CRS.

## Conclusion
You now have a complete, production‑ready pattern for **how to write geojson** to any .NET stream using Aspose.GIS. Whether you need to return GeoJSON from a web it to a file, or simply display it in the console, the steps above cover the entire workflow. Explore the library further to work with other formats like Shapefile, KML, or GML, and keep building richer geospatial applications.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---