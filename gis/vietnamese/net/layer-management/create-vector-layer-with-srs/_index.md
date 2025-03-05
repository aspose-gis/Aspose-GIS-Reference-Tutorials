---
title: Tạo lớp Vector với SRS
linktitle: Tạo lớp Vector với SRS
second_title: API Aspose.GIS .NET
description: Khám phá Aspose.GIS cho .NET - chìa khóa để bạn tích hợp GIS liền mạch. Tạo các lớp vectơ dễ dàng với các hệ quy chiếu không gian được chỉ định. Tải ngay!
type: docs
weight: 13
url: /vi/net/layer-management/create-vector-layer-with-srs/
---
## Giới thiệu
Aspose.GIS for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với dữ liệu hệ thống thông tin địa lý (GIS) trong các ứng dụng .NET. Trong hướng dẫn này, chúng ta sẽ tập trung vào việc tạo một lớp vectơ bằng hệ quy chiếu không gian (SRS). Đến cuối hướng dẫn này, bạn sẽ có thể dễ dàng tích hợp các khả năng của GIS vào các dự án .NET của mình.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về phát triển C# và .NET.
-  Đã cài đặt thư viện Aspose.GIS cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/gis/net/).
- Một môi trường phát triển được thiết lập và sẵn sàng.
## Nhập không gian tên
Đảm bảo bạn đã nhập các không gian tên cần thiết ở đầu tệp C#:
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
## Bước 1: Thiết lập hệ thống tham chiếu không gian dự kiến
Hãy tạo một hệ thống tham chiếu không gian dự kiến (SRS) bằng cách sử dụng phép chiếu World Mercator làm ví dụ. Thực hiện theo các bước sau:
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
## Bước 2: Tạo lớp Vector và thêm tính năng
Bây giờ, hãy tạo một tệp hình dạng và thêm các tính năng với SRS được chỉ định:
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
        layer.Add(feature); // Điều này sẽ đưa ra một ngoại lệ vì hình học có SRS khác
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Bước 3: Xác minh hệ quy chiếu không gian
Cuối cùng, hãy mở lớp và xác minh hệ quy chiếu không gian của nó:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Thế giới Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Nên trả về true
}
```
Bằng cách làm theo các bước này, bạn đã tạo thành công lớp vectơ với hệ thống tham chiếu không gian được chỉ định bằng Aspose.GIS cho .NET.
## Phần kết luận
Việc tích hợp chức năng GIS vào các ứng dụng .NET của bạn chưa bao giờ dễ dàng hơn thế nhờ Aspose.GIS. Với khả năng dễ dàng tạo các lớp vectơ và quản lý hệ thống tham chiếu không gian, bạn có thể nâng cao các dự án của mình bằng khả năng không gian địa lý mạnh mẽ.
## Câu hỏi thường gặp
### Aspose.GIS có tương thích với tất cả các định dạng tệp GIS không?
 Aspose.GIS hỗ trợ nhiều định dạng GIS khác nhau, bao gồm Shapefile, GeoJSON, KML, v.v. Kiểm tra[tài liệu](https://reference.aspose.com/gis/net/) để có danh sách đầy đủ.
### Tôi có thể sử dụng Aspose.GIS trong ứng dụng web không?
Tuyệt đối! Aspose.GIS for .NET rất linh hoạt và có thể được sử dụng trong các ứng dụng web, ứng dụng máy tính để bàn và thậm chí cả ứng dụng di động.
### Tôi có thể nhận hỗ trợ cho Aspose.GIS ở đâu?
 Bạn có thể tìm thấy một cộng đồng hữu ích tại[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) cho bất kỳ truy vấn hoặc vấn đề nào bạn có thể gặp phải.
### Có bản dùng thử miễn phí không?
 Có, bạn có thể khám phá các tính năng của Aspose.GIS bằng cách dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể mua giấy phép cho Aspose.GIS?
 Để mua giấy phép, hãy truy cập[trang mua hàng](https://purchase.aspose.com/buy).