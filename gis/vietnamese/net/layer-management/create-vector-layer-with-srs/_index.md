---
date: 2026-01-15
description: Khám phá Aspose.GIS cho .NET để tạo lớp vector với hệ thống tham chiếu
  không gian. Tìm hiểu cách thiết lập SRS, tạo lớp và quản lý dữ liệu GIS. Tải ngay!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Tạo lớp vector với SRS
url: /vi/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Vector Layer với SRS

## Giới thiệu
Aspose.GIS for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển **tạo vector layer** và làm việc với dữ liệu hệ thống thông tin địa lý (GIS) một cách liền mạch trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ đi qua cách tạo một vector layer với hệ thống tham chiếu không gian (SRS), lý do tại sao bạn nên đặt spatial reference, và những lợi ích mà nó mang lại cho các dự án thực tế. Khi hoàn thành, bạn sẽ tự tin tích hợp các khả năng GIS vào giải pháp .NET của mình.

## Câu trả lời nhanh
- **Mục đích chính của hướng dẫn này là gì?** Để chỉ cách tạo vector layer với SRS được chỉ định bằng Aspose.GIS for .NET.  
- **Chiếu nào được sử dụng trong ví dụ?** World Mercator (EPSG:3395).  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí đủ cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể áp dụng cùng cách tiếp cận cho các định dạng GIS khác không?** Có, việc xử lý SRS giống nhau áp dụng cho Shapefile, GeoJSON, KML, v.v.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vector layer là gì và tại sao phải đặt spatial reference?
Một **vector layer** lưu trữ các đối tượng hình học (điểm, đường, đa giác) cùng với dữ liệu thuộc tính. Gán **spatial reference** (SRS) cho biết phần mềm GIS cách diễn giải các tọa độ trên bề mặt Trái Đất. Đặt SRS đúng đảm bảo đo lường chính xác, chồng lớp hợp lý với các layer khác, và hiển thị bản đồ đáng tin cậy.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Kiến thức cơ bản về C# và phát triển .NET.  
- Thư viện Aspose.GIS for .NET đã được cài đặt. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/gis/net/)**.  
- Môi trường phát triển (Visual Studio, VS Code, hoặc bất kỳ IDE C# nào).

## Nhập không gian tên
Đảm bảo bạn đã nhập các không gian tên cần thiết ở đầu file C# của mình:

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

## Cách đặt spatial reference (SRS) – Bước 1
Hãy tạo một **projected spatial reference system** sử dụng chiếu World Mercator làm ví dụ. Điều này minh họa **cách đặt srs** cho một layer.

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

## Cách tạo layer – Bước 2
Bây giờ chúng ta sẽ **tạo vector layer** (một Shapefile) và thêm các feature sử dụng SRS mà chúng ta vừa định nghĩa. Phần này trả lời **cách tạo layer** với Aspose.GIS.

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

> **Mẹo chuyên nghiệp:** Luôn kiểm tra rằng `SpatialReferenceSystem` của geometry khớp với SRS của layer trước khi thêm. Các giá trị SRS không khớp sẽ gây ra `GisException`, như đã minh họa ở trên.

## Xác minh Spatial Reference System – Bước 3
Cuối cùng, mở layer và xác nhận rằng SRS đã được áp dụng đúng.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Nếu lời gọi `IsEquivalent` trả về `true`, bạn đã **tạo vector layer** thành công với spatial reference mong muốn.

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| `GisException` khi thêm feature | Geometry sử dụng SRS khác với layer | Đặt `feature.Geometry.SpatialReferenceSystem` thành SRS của layer trước khi thêm |
| Layer hiển thị trống trong phần mềm GIS | Shapefile được tạo mà không có file `.prj` đúng | Đảm bảo đối tượng `projectedSrs` được truyền khi tạo layer |
| Giá trị tọa độ không mong đợi | Tham số chiếu sai (ví dụ: kinh độ trung tâm) | Kiểm tra lại các tham số truyền vào `AddProjectionParameter` |

## Câu hỏi thường gặp
### Aspose.GIS có tương thích với tất cả các định dạng file GIS không?
Aspose.GIS hỗ trợ nhiều định dạng GIS, bao gồm Shapefile, GeoJSON, KML và nhiều hơn nữa. Kiểm tra **[tài liệu](https://reference.aspose.com/gis/net/)** để biết danh sách đầy đủ.

### Tôi có thể sử dụng Aspose.GIS trong ứng dụng web không?
Chắc chắn! Aspose.GIS for .NET rất linh hoạt và có thể được dùng trong ứng dụng web, ứng dụng desktop, và thậm chí cả ứng dụng di động.

### Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể tham gia cộng đồng hữu ích tại **[diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33)** để giải đáp mọi thắc mắc hoặc vấn đề gặp phải.

### Có bản dùng thử miễn phí không?
Có, bạn có thể khám phá các tính năng của Aspose.GIS bằng cách lấy bản dùng thử **[tại đây](https://releases.aspose.com/)**.

### Làm sao để mua giấy phép cho Aspose.GIS?
Để mua giấy phép, hãy truy cập **[trang mua hàng](https://purchase.aspose.com/buy)**.

## Frequently Asked Questions (Additional)

**Q: Điều gì sẽ xảy ra nếu tôi cố gắng thêm một geometry có SRS khác?**  
**A:** Aspose.GIS sẽ ném ra `GisException`. Bạn phải chuyển đổi geometry sang SRS của layer hoặc đảm bảo chúng cùng sử dụng SRS.

**Q: Tôi có thể thay đổi SRS của một layer đã tồn tại không?**  
**A:** Có, bạn có thể tạo một layer mới với SRS mong muốn và sao chép các feature vào, thực hiện chuyển đổi chúng nếu cần.

**Q: Có thể làm việc với tọa độ 3D không?**  
**A:** Aspose.GIS hỗ trợ tọa độ Z; chỉ cần sử dụng các constructor geometry chấp nhận giá trị Z.

**Q: Thư viện có tự động xử lý chuyển đổi datum không?**  
**A:** Khi bạn chuyển đổi geometry bằng `Geometry.Transform`, Aspose.GIS sẽ thực hiện việc dịch datum cần thiết.

**Q: Các phiên bản .NET nào được kiểm thử chính thức?**  
**A:** Thư viện đã được kiểm thử với .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7.

## Kết luận
Bạn đã học cách **tạo vector layer** với hệ thống tham chiếu không gian tùy chỉnh bằng Aspose.GIS for .NET. Bằng việc đặt SRS đúng, xử lý geometry một cách nhất quán và xác minh metadata của layer, bạn có thể xây dựng các ứng dụng GIS mạnh mẽ, tương thích với bất kỳ phần mềm GIS tiêu chuẩn nào.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}