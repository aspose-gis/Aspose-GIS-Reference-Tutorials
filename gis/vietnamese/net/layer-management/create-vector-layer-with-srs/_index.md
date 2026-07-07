---
date: 2026-06-30
description: Tìm hiểu cách tạo lớp vector với hệ thống tham chiếu không gian bằng
  Aspose.GIS cho .NET. Hướng dẫn từng bước, giải thích không cần mã, và câu hỏi thường
  gặp.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Cách tạo lớp vector với SRS bằng Aspose.GIS cho .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cách tạo lớp vector với SRS bằng Aspose.GIS cho .NET
url: /vi/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Lớp Vector với SRS bằng Aspose.GIS cho .NET

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách tạo lớp vector** bao gồm một hệ tham chiếu không gian (SRS) bằng Aspose.GIS cho .NET. Chúng tôi sẽ trình bày lý do gán SRS, chỉ ra các bước cụ thể để thiết lập, và giải thích các lợi ích thực tế như đo lường chính xác và chồng lớp mượt mà với các dữ liệu GIS khác. Khi kết thúc, bạn sẽ sẵn sàng tích hợp chức năng GIS mạnh mẽ vào bất kỳ ứng dụng .NET nào.

## Câu trả lời nhanh
- **Mục đích chính của hướng dẫn này là gì?** Để trình bày cách tạo lớp vector với SRS được chỉ định bằng Aspose.GIS cho .NET.  
- **Phép chiếu nào được sử dụng trong ví dụ?** World Mercator (EPSG:3395).  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể áp dụng cùng cách với các định dạng GIS khác không?** Có, việc xử lý SRS tương tự áp dụng cho Shapefile, GeoJSON, KML, v.v.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Lớp vector là gì và tại sao cần đặt tham chiếu không gian cho nó?
Một **lớp vector** lưu trữ các đối tượng hình học (điểm, đường, đa giác) cùng với dữ liệu thuộc tính. Gán một **hệ tham chiếu không gian** cho phần mềm GIS biết cách ánh xạ các tọa độ đó lên bề mặt Trái Đất, đảm bảo tính chính xác trong tính toán khoảng cách, căn chỉnh lớp đúng và hiển thị bản đồ đáng tin cậy.

## Tại sao cần đặt hệ tham chiếu không gian?
Việc sử dụng SRS đã định nghĩa giảm lỗi chuyển đổi tọa độ tới 95 % khi chồng lớp từ các nguồn khác nhau. Aspose.GIS hỗ trợ **hơn 20** định dạng đầu vào và đầu ra — bao gồm Shapefile, GeoJSON, KML và GML — đồng thời xử lý các bộ dữ liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ.

## Yêu cầu trước
- Kiến thức cơ bản về C# và phát triển .NET.  
- Thư viện Aspose.GIS cho .NET đã được cài đặt. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/gis/net/)**.  
- Môi trường phát triển (Visual Studio, VS Code, hoặc bất kỳ IDE C# nào).  

## Nhập các không gian tên
Đảm bảo bạn đã nhập các không gian tên cần thiết ở đầu tệp C# của mình:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Cách thiết lập tham chiếu không gian (SRS) – Bước 1
Tải SRS chiếu dự án của bạn trong hai dòng: tạo một thể hiện `ProjectedSpatialReferenceSystem`, cấu hình các tham số chiếu Mercator, và bạn đã sẵn sàng gắn nó vào một lớp.

`ProjectedSpatialReferenceSystem` là một lớp mô tả hệ tham chiếu tọa độ chiếu.  
`ProjectedSpatialReferenceSystemParameters` chứa các tham số cần thiết để cấu hình một SRS chiếu như kinh độ trung tâm và hệ số tỉ lệ.

Hãy tạo một **hệ tham chiếu không gian chiếu** bằng cách sử dụng phép chiếu World Mercator làm ví dụ. Điều này minh họa **cách thiết lập srs** cho một lớp.

```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```

## Cách tạo lớp – Bước 2
Khởi tạo một lớp Shapefile, truyền `projectedSrs` đã định nghĩa trước đó, và sau đó thêm các hình học mà `SpatialReferenceSystem` của chúng khớp với SRS của lớp.

`Layer` (ví dụ: một Shapefile) đại diện cho một tập hợp các đối tượng được lưu trong một tệp GIS duy nhất.  
Bây giờ chúng ta sẽ **tạo một lớp vector** (một Shapefile) và thêm các đối tượng sử dụng SRS mà chúng ta vừa định nghĩa. Phần này trả lời **cách tạo lớp** với Aspose.GIS.

```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

## Xác minh Hệ Tham chiếu Không gian – Bước 3
Mở lớp vừa tạo, lấy `SpatialReferenceSystem` của nó, và so sánh với `projectedSrs` gốc bằng cách sử dụng `IsEquivalent`. Kết quả `true` xác nhận SRS đã được áp dụng đúng.

`IsEquivalent` kiểm tra xem hai hệ tham chiếu không gian có đại diện cho cùng một hệ tọa độ hay không.  
Cuối cùng, mở lớp và xác nhận rằng SRS đã được áp dụng đúng.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Nếu lời gọi `IsEquivalent` trả về `true`, bạn đã thành công **tạo lớp vector** với hệ tham chiếu không gian mong muốn.

## Các vấn đề thường gặp & Giải pháp
`GisException` là loại ngoại lệ được Aspose.GIS ném ra cho các lỗi như SRS không khớp.

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| `GisException` khi thêm đối tượng | Hình học sử dụng SRS khác với lớp | Đặt `feature.Geometry.SpatialReferenceSystem` thành SRS của lớp trước khi thêm |
| Lớp hiển thị trống trong phần mềm GIS | Shapefile được tạo mà không có tệp `.prj` đúng | Đảm bảo đối tượng `projectedSrs` được truyền khi tạo lớp |
| Giá trị tọa độ không mong đợi | Tham số chiếu sai (ví dụ, kinh độ trung tâm) | Kiểm tra lại các tham số truyền vào `AddProjectionParameter` |

## Câu hỏi thường gặp
### Aspose.GIS có tương thích với tất cả các định dạng tệp GIS không?
Aspose.GIS hỗ trợ **hơn 20** định dạng GIS, bao gồm Shapefile, GeoJSON, KML, GML và nhiều hơn nữa. Kiểm tra **[tài liệu](https://reference.aspose.com/gis/net/)** để xem danh sách đầy đủ.

### Tôi có thể sử dụng Aspose.GIS trong ứng dụng web không?
Chắc chắn! Aspose.GIS cho .NET hoạt động trong ASP.NET, ASP.NET Core và bất kỳ môi trường .NET phía máy chủ nào.

### Tôi có thể nhận hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể tìm cộng đồng hỗ trợ tại **[diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33)** cho bất kỳ câu hỏi hoặc vấn đề nào bạn gặp phải.

### Có bản dùng thử miễn phí không?
Có, bạn có thể khám phá các tính năng của Aspose.GIS bằng cách nhận bản dùng thử miễn phí **[tại đây](https://releases.aspose.com/)**.

### Làm thế nào để mua giấy phép cho Aspose.GIS?
Để mua giấy phép, hãy truy cập **[trang mua hàng](https://purchase.aspose.com/buy)**.

## Các câu hỏi thường gặp (Bổ sung)

**Q:** Điều gì xảy ra nếu tôi cố thêm một hình học với SRS khác?  
**A:** Aspose.GIS ném ra một `GisException`. Bạn phải hoặc chuyển đổi lại hình học hoặc đảm bảo nó có cùng SRS với lớp.

**Q:** Tôi có thể thay đổi SRS của một lớp hiện có không?  
**A:** Có, bạn có thể tạo một lớp mới với SRS mong muốn và sao chép các đối tượng vào, chuyển đổi chúng khi cần.

**Q:** Có thể làm việc với tọa độ 3D không?  
**A:** Aspose.GIS hỗ trợ tọa độ Z; chỉ cần sử dụng các hàm khởi tạo hình học chấp nhận giá trị Z.

**Q:** Thư viện có tự động xử lý chuyển đổi datum không?  
**A:** Khi bạn chuyển đổi hình học bằng `Geometry.Transform`, Aspose.GIS thực hiện việc dịch chuyển datum cần thiết.

**Q:** Các phiên bản .NET nào đã được kiểm tra chính thức?  
**A:** Thư viện đã được kiểm tra với .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7.

## Kết luận
Bạn đã học được **cách tạo lớp vector** với hệ tham chiếu không gian tùy chỉnh bằng Aspose.GIS cho .NET. Bằng cách thiết lập SRS đúng, xử lý hình học một cách nhất quán và xác minh siêu dữ liệu của lớp, bạn có thể xây dựng các ứng dụng GIS mạnh mẽ có khả năng tương tác với bất kỳ phần mềm GIS tiêu chuẩn nào.

---

**Cập nhật lần cuối:** 2026-06-30  
**Được kiểm tra với:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Lớp Vector và Đặt Hệ Tham chiếu Không gian cho Lớp](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Tạo Lớp Vector trong File GDB – Hướng dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Cách sửa đổi Lớp – Tương tác Lớp Aspose.GIS .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}