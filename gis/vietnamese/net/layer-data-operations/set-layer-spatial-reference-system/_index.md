---
date: 2026-06-15
description: Tìm hiểu cách tạo lớp vector và đặt hệ tham chiếu không gian cho lớp
  bằng Aspose.GIS cho .NET. Nắm vững việc định nghĩa tham chiếu không gian, thêm đối
  tượng điểm, và lấy mã EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Đặt Hệ Tham chiếu Không gian cho Lớp
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Tạo Lớp Vector và Đặt Hệ Tham chiếu Không gian cho Lớp
url: /vi/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Lớp Vector và Đặt Hệ Tham chiếu Không gian cho Lớp

## Giới thiệu
Trong bối cảnh rộng lớn của Hệ thống Thông tin Địa lý (GIS), **Aspose.GIS for .NET** nổi bật như một thư viện mạnh mẽ, hiệu suất cao, hỗ trợ hơn **70** định dạng vector và raster và có thể xử lý các tệp lớn hơn **10 GB** mà không cần tải toàn bộ dữ liệu vào bộ nhớ. Trong hướng dẫn này, bạn sẽ **tạo lớp vector**, xác định hệ tham chiếu không gian của nó, **thêm đối tượng điểm**, và lấy mã EPSG — tất cả đều với hướng dẫn rõ ràng, từng bước. Dù bạn đang xây dựng dịch vụ bản đồ, quy trình chuyển đổi dữ liệu, hay động cơ phân tích không gian, việc nắm vững những nền tảng này sẽ giúp hệ tọa độ shapefile của bạn chính xác và quy trình GIS đáng tin cậy.

## Câu trả lời nhanh
- **What does “create vector layer” mean?** Nó tạo một lớp GIS mới (ví dụ, một Shapefile) có thể lưu trữ các hình học như điểm, đường hoặc đa giác.  
- **Mã EPSG nào được sử dụng trong ví dụ?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Có thể thêm đối tượng điểm sau khi tạo lớp không?** Có — sử dụng `ConstructFeature()` và gán một hình học `Point`.  
- **Làm sao để lấy CRS của lớp?** Đọc `layer.SpatialReferenceSystem.EpsgCode` hoặc `.Name`.  
- **Tôi có cần giấy phép cho Aspose.GIS không?** Có bản dùng thử miễn phí; giấy phép cần thiết cho môi trường sản xuất.

## Tạo lớp vector là gì?
Hoạt động **create vector layer** tạo một bộ dữ liệu vector mới (chẳng hạn Shapefile) có thể chứa các đối tượng hình học và dữ liệu thuộc tính. Trong Aspose.GIS, việc này được thực hiện bằng cách khởi tạo một đối tượng `VectorLayer` với driver và hệ tham chiếu không gian.

## Tại sao cần đặt hệ tọa độ (CRS) của lớp một cách chính xác?
Việc đặt hệ tham chiếu tọa độ (CRS) đúng đảm bảo mọi hình học bạn lưu trữ sẽ khớp với các bộ dữ liệu không gian khác. Với Aspose.GIS, bạn có thể xác định CRS bằng mã EPSG tiêu chuẩn, giúp đảm bảo khả năng tương thích với phần mềm GIS trên toàn thế giới. Ví dụ, EPSG 26918 định nghĩa NAD83 / UTM zone 18N, một phép chiếu phổ biến cho dữ liệu ở miền Đông Hoa Kỳ.

## Yêu cầu trước
- Kinh nghiệm phát triển .NET (C# hoặc VB.NET).  
- Visual Studio 2022 hoặc mới hơn.  
- Thư viện Aspose.GIS cho .NET – tải xuống **[tại đây](https://releases.aspose.com/gis/net/)**.  
- Kiến thức cơ bản về hệ tham chiếu không gian (CRS/EPSG).

## Nhập không gian tên
Không gian tên `Aspose.Gis` cung cấp các lớp GIS cốt lõi, trong khi `Aspose.Gis.Geometries` cung cấp các kiểu hình học như `Point`.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Làm thế nào để tạo một lớp vector trong Aspose.GIS cho .NET?
VectorLayer đại diện cho một bộ dữ liệu vector như Shapefile và cung cấp các phương thức để tạo, đọc và chỉnh sửa đối tượng.  
SpatialReferenceSystem xác định hệ tham chiếu tọa độ bằng mã EPSG.

Tải thư mục mục tiêu, định nghĩa một `SpatialReferenceSystem` có mã EPSG, và gọi `VectorLayer.Create` với driver Shapefile. Lệnh duy nhất này tạo một tệp `.shp` mới, ghi các tệp `.shx` và `.dbf` kèm theo, và nhúng siêu dữ liệu CRS, sẵn sàng cho việc chèn đối tượng một cách hiệu quả.

### Bước 1: Xác định Thư mục Tài liệu
Bắt đầu bằng cách chỉ định đường dẫn tới thư mục tài liệu của bạn. Đây sẽ là vị trí lưu trữ các tệp dữ liệu không gian.

```csharp
string dataDir = "Your Document Directory";
```

### Bước 2: Xác định Tham chiếu Không gian và Đặt Hệ tọa độ Shapefile
SpatialReferenceSystem đại diện cho CRS của một lớp, được xác định bằng mã EPSG.  

Xác định đường dẫn cho Shapefile, và **định nghĩa tham chiếu không gian** bằng mã EPSG (26918 trong ví dụ này). Bước này **đặt hệ tọa độ shapefile** cho lớp.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Làm thế nào để thêm một đối tượng điểm vào lớp vector?
`Point` là một kiểu hình học đại diện cho một cặp tọa độ X/Y duy nhất.  

Tạo một đối tượng mới, gán một hình học `Point` với các tọa độ X/Y mong muốn, và thêm đối tượng vào `VectorLayer` đang mở. Thao tác này ghi hình học vào tệp `.shp` và bản ghi thuộc tính vào tệp `.dbf` trong một giao dịch duy nhất.

### Bước 3: Tạo Lớp Vector
`ConstructFeature` tạo một đối tượng feature mới có thể chứa dữ liệu hình học và thuộc tính.  

Bây giờ **tạo lớp vector** với đường dẫn Shapefile đã chỉ định, loại driver (Shapefile), và hệ tham chiếu không gian mà bạn vừa định nghĩa.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Bước 4: Thêm Đối tượng Điểm vào Lớp
Tạo một đối tượng feature mới và **thêm đối tượng điểm** bằng cách đặt hình học của nó (một `Point` với tọa độ 60, 24). Sau đó thêm feature vào lớp vector.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Bước 5: Lấy Thông tin Hệ Tham chiếu Không gian (Lấy Mã EPSG)
Mở Lớp Vector và lấy thông tin về hệ tham chiếu không gian, chẳng hạn như mã EPSG và tên có thể đọc được bởi con người. Điều này minh họa cách **lấy mã EPSG** và **đặt CRS cho lớp**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Lớp không mở được** | Driver sai hoặc đường dẫn tệp bị hỏng | Xác minh `Drivers.Shapefile` và đảm bảo `path` trỏ tới một tệp `.shp` tồn tại. |
| **CRS hiển thị không đúng** | Sử dụng mã EPSG sai | Kiểm tra lại mã EPSG với nguồn đáng tin cậy (ví dụ, EPSG.io). |
| **Đối tượng không được lưu** | Không gọi `layer.Add(feature)` trong khối `using` | Đảm bảo phương thức `Add` được thực thi trước khi lớp bị giải phóng. |

## Câu hỏi thường gặp
**Q: Làm sao để thay đổi CRS của một Shapefile hiện có?**  
A: Mở lớp, tạo một `SpatialReferenceSystem` mới với mã EPSG mong muốn, gán nó cho `layer.SpatialReferenceSystem`, sau đó lưu lớp.

**Q: Tôi có thể thêm các loại hình học khác (ví dụ, đa giác) bằng cùng cách tiếp cận không?**  
A: Có — thay thế `new Point(x, y)` bằng `new Polygon(...)` hoặc `new LineString(...)` tùy nhu cầu.

**Q: Có thể làm việc với các bộ dữ liệu lớn một cách hiệu quả không?**  
A: Sử dụng API streaming (`VectorLayer.Create` với `FeatureCollection`) và giải phóng lớp kịp thời để giải phóng tài nguyên.

**Q: Aspose.GIS có hỗ trợ chuyển đổi tọa độ không?**  
A: Có — sử dụng `Geometry.Transform(targetSrs)` để chuyển đổi hình học giữa các hệ tham chiếu không gian khác nhau.

**Q: Các phiên bản .NET nào được hỗ trợ?**  
A: Aspose.GIS hoạt động với .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Cập nhật lần cuối:** 2026-06-15  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Tạo Lớp Vector và Đặt Độ Dung Sai Tuyến tính bằng Aspose.GIS cho .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Tạo Lớp Vector trong File GDB – Hướng dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [tham chiếu không gian wgs84 – Thêm Lớp vào GDB bằng Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}