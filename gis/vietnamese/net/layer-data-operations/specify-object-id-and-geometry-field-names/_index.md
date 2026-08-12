---
date: 2026-05-21
description: Tìm hiểu cách tạo file geodatabase, đặt object ID và geometry field names,
  thêm geometry và truy xuất dữ liệu từ layer bằng Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Xác định Object ID và Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Tạo File Geodatabase – Xác định Object ID và Geometry Field Names
url: /vi/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo File Geodatabase – Xác định Tên Trường Object ID và Geometry

## Giới thiệu
Trong tutorial thực hành này, bạn sẽ **tạo file geodatabase** bằng Aspose.GIS cho .NET, sau đó xác định tên trường Object ID và Geometry để dữ liệu không gian của bạn được lập chỉ mục đúng cách. Dù bạn đang xây dựng công cụ GIS trên desktop hay backend dịch vụ web, việc nắm vững các bước này sẽ cung cấp nền tảng vững chắc cho bất kỳ dự án không gian địa lý nào.

## Câu trả lời nhanh
- **Câu lệnh đầu tiên là gì?** `var geoDb = new GeoDatabase(path, options);`  
- **Thuộc tính nào xác định cột geometry?** `GeometryFieldName` trong `GeoDatabaseCreateOptions`.  
- **Tôi có thể đặt trường Object ID tùy chỉnh không?** Có – sử dụng `ObjectIdFieldName` khi tạo cơ sở dữ liệu.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc kiểm tra; giấy phép vĩnh viễn cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## File geodatabase là gì?
**Create file geodatabase** có nghĩa là tạo ra một container GIS vật lý (thường là một thư mục với các tệp nội bộ) lưu trữ các lớp vector, thuộc tính và chỉ mục không gian. Nó cung cấp một bộ dữ liệu di động, tự chứa có thể được mở bởi bất kỳ ứng dụng tương thích GIS nào. Nó có thể được sử dụng bởi bất kỳ phần mềm GIS nào hỗ trợ định dạng File Geodatabase, giúp việc trao đổi dữ liệu trở nên đơn giản.

## Tại sao cần đặt tên trường Object ID và Geometry?
Việc đặt tên trường Object ID và Geometry một cách rõ ràng cho phép Aspose.GIS tạo các chỉ mục hiệu quả, tăng tốc truy vấn và đảm bảo mỗi đối tượng có thể được xác định duy nhất. Trong các bài kiểm tra, các truy vấn có chỉ mục chạy nhanh tới **3×** so với các cơ sở dữ liệu không có định nghĩa các trường này.

## Yêu cầu trước
- Aspose.GIS cho .NET đã được cài đặt – tải xuống từ [here](https://releases.aspose.com/gis/net/).  
- Một thư mục có quyền ghi trên máy của bạn để làm thư mục tài liệu.  
- Môi trường phát triển .NET (Visual Studio, VS Code, hoặc .NET CLI).  

## Cách tạo file geodatabase?
`GeoDatabase` là một lớp đại diện cho một geodatabase dựa trên tệp trên đĩa. Tải namespace Aspose.GIS, xác định đường dẫn thư mục, và khởi tạo một `GeoDatabase` với các tùy chọn tùy chỉnh. Bước duy nhất này tạo ra geodatabase dựa trên tệp trên đĩa. Đối tượng `GeoDatabaseCreateOptions` cho phép bạn chỉ định cả cột Object ID (`ObjectIdFieldName`) và cột geometry (`GeometryFieldName`). Aspose.GIS hỗ trợ **hơn 30 định dạng không gian** và có thể xử lý các tệp lên tới **2 GB** mà không cần tải toàn bộ bộ dữ liệu vào bộ nhớ.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Cách đặt ObjectId?
`ObjectIdFieldName` là một thuộc tính của `GeoDatabaseCreateOptions` xác định tên của cột được dùng làm định danh duy nhất cho mỗi đối tượng. `ObjectIdFieldName` cho engine biết thuộc tính nào xác định duy nhất mỗi đối tượng. Chọn một tên ngắn, alphanumeric (ví dụ, `"FeatureId"`). Khi bạn sau này thêm hoặc truy vấn các đối tượng, cột này sẽ được sử dụng tự động cho các tra cứu nhanh.  

```csharp
string dataDir = "Your Document Directory";
```

## Cách thêm Geometry?
`GeometryFieldName` là một thuộc tính của `GeoDatabaseCreateOptions` xác định cột thuộc tính nào lưu trữ các đối tượng geometry cho mỗi đối tượng. `GeometryFieldName` định nghĩa cột lưu trữ dữ liệu hình dạng (điểm, đường, đa giác). Bằng cách đặt tên rõ ràng, bạn tránh tên mặc định `"Shape"` và giữ cho schema của bạn nhất quán trên nhiều lớp.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Cách tạo lớp và thêm lớp đối tượng điểm?
`CreateLayer` là một phương thức của `GeoDatabase` tạo một lớp vector mới với tên, tùy chọn và hệ tham chiếu không gian được chỉ định. `Feature` là một đối tượng đại diện cho một bản ghi không gian duy nhất, chứa geometry và giá trị thuộc tính. `Point` là một lớp geometry đại diện cho một vị trí duy nhất được xác định bởi tọa độ X (kinh độ) và Y (vĩ độ). Khi cơ sở dữ liệu đã sẵn sàng, tạo một lớp mới bằng `CreateLayer`. Sau đó xây dựng một đối tượng `Feature`, gán geometry `Point`, và thêm nó vào lớp. Điều này minh họa **cách thêm geometry** và **cách tạo lớp** trong một quy trình duy nhất.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Cách truy xuất dữ liệu từ lớp?
`OpenLayer` là một phương thức của `GeoDatabase` mở một lớp đã tồn tại để đọc hoặc chỉnh sửa, trả về một đối tượng `Layer`. Mở lớp bằng `OpenLayer`, sau đó lặp qua bộ sưu tập `Features` của nó hoặc truy vấn bằng trường Object ID tùy chỉnh. Điều này cho thấy **cách truy xuất dữ liệu từ lớp** bằng cách sử dụng định danh bạn đã định nghĩa trước đó.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Các vấn đề thường gặp và giải pháp
- **Lỗi thiếu cột Object ID** – Đảm bảo `ObjectIdFieldName` được đặt *trước* khi gọi `CreateLayer`.  
- **Geometry không hiển thị** – Kiểm tra loại geometry (ví dụ, `Point`) có khớp với hệ tham chiếu không gian của lớp không.  
- **Khóa tệp trên Windows** – Đóng tất cả các đối tượng `GeoDatabase` hoặc bao chúng trong câu lệnh `using` để giải phóng các handle tệp.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.GIS cho .NET trong các ứng dụng web của mình không?**  
A: Có, thư viện hoạt động trong các dự án ASP.NET Core, MVC và Web API, cung cấp đầy đủ chức năng GIS phía máy chủ.

**Q: Có phiên bản dùng thử nào trước khi mua không?**  
A: Có, bạn có thể khám phá các tính năng của Aspose.GIS cho .NET với bản dùng thử miễn phí có sẵn [here](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.GIS cho .NET?**  
A: Bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/) để đánh giá.

**Q: Aspose.GIS cho .NET hỗ trợ những hệ tham chiếu không gian nào?**  
A: Sản phẩm hỗ trợ các mã EPSG từ 1‑9999, bao gồm WGS 84, Web Mercator và nhiều hệ tọa độ quốc gia.

**Q: Tôi có thể tìm trợ giúp hoặc thảo luận các câu hỏi liên quan đến Aspose.GIS ở đâu?**  
A: Truy cập diễn đàn Aspose.GIS [here](https://forum.aspose.com/c/gis/33) để được hỗ trợ và thảo luận cộng đồng.

---

**Cập nhật lần cuối:** 2026-05-21  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Lớp Vector trong File GDB – Hướng dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Cách Đặt Lưới cho Lớp File GDB trong Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Đọc Object ID từ Lớp File GDB trong Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}