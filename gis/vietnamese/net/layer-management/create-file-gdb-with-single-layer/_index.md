---
date: 2026-01-10
description: Tìm hiểu cách tạo lớp vector trong File Geodatabase bằng Aspose.GIS cho
  .NET. Quản lý dữ liệu không gian với hệ tham chiếu WGS84 và các tùy chọn file gdb.
linktitle: Create File GDB with Single Layer
second_title: Aspose.GIS .NET API
title: Tạo lớp vector trong File GDB – Hướng dẫn Aspose.GIS .NET
url: /vi/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Lớp Vector trong File GDB

## Giới thiệu
Nếu bạn cần **create vector layer** bên trong một File Geodatabase (GDB) và quản lý dữ liệu không gian một cách hiệu quả, Aspose.GIS for .NET cung cấp cho bạn một cách tiếp cận sạch sẽ, code‑first. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách ghi một line feature, cấu hình các tùy chọn file gdb, và làm việc với spatial reference WGS84 — tất cả chỉ trong vài dòng C#. Khi kết thúc, bạn sẽ có thể đếm số đối tượng trong một lớp và tích hợp GDB đã tạo vào bất kỳ quy trình ánh xạ hoặc phân tích nào trên .NET.

## Câu trả lời nhanh
- **What does “create vector layer” mean?** Có nghĩa là thêm một bộ dữ liệu vector mới (điểm, đường, hoặc đa giác) vào một tệp geodatabase.  
- **Which library should I use?** Aspose.GIS for .NET cung cấp hỗ trợ đầy đủ cho việc tạo và chỉnh sửa File GDB.  
- **Do I need a license for development?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép thương mại cho môi trường sản xuất.  
- **Can I set the spatial reference?** Có – sử dụng `SpatialReferenceSystem.Wgs84` cho datum WGS84 phổ biến.  
- **How many lines of code?** Ít hơn 30 dòng để tạo GDB, thêm một line feature, và đọc lại số lượng đối tượng.

## Hoạt động “create vector layer” là gì?
Tạo một lớp vector có nghĩa là định nghĩa một bảng mới trong geodatabase để lưu trữ các đối tượng hình học (điểm, đường, đa giác) cùng với các thuộc tính của chúng. Hoạt động này là nền tảng cho bất kỳ ứng dụng GIS nào cần **manage geospatial data**.

## Tại sao nên dùng Aspose.GIS để tạo lớp vector?
- **Zero external dependencies** – API hoạt động ngay trên .NET Framework, .NET Core và .NET 5/6.  
- **Full support for File GDB** – bạn có thể cấu hình `FileGdbOptions` để kiểm soát nén, lập chỉ mục không gian, và hơn thế nữa.  
- **Built‑in spatial reference handling** – chỉ cần truyền `SpatialReferenceSystem.Wgs84` để làm việc trong hệ tọa độ toàn cầu.  
- **Straightforward API** – API đơn giản – ghi line feature, thêm vào lớp, và lấy số lượng đối tượng chỉ với vài lời gọi phương thức.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Aspose.GIS for .NET** – tải xuống từ [trang tải Aspose.GIS for .NET](https://releases.aspose.com/gis/net/).  
2. **Môi trường phát triển .NET** – Visual Studio, Rider, hoặc `dotnet` CLI.  
3. **Một thư mục** nơi File GDB sẽ được tạo (chúng tôi sẽ gọi là *Your Document Directory*).

## Nhập không gian tên
Thêm các câu lệnh `using` cần thiết ở đầu tệp C# của bạn:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Bước 1: Thiết lập Thư mục Tài liệu của bạn
```csharp
string dataDir = "Your Document Directory";
```
Thay thế `"Your Document Directory"` bằng đường dẫn tuyệt đối nơi bạn muốn File GDB được lưu.

## Bước 2: Tạo File Geodatabase với một Lớp duy nhất
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Đoạn mã này **creates a vector layer** bằng cách sử dụng `FileGdbOptions`, ghi một line feature đơn giản, và lưu nó vào một File GDB sử dụng **spatial reference WGS84**.

## Bước 3: Mở File Geodatabase và Lấy Thông tin Lớp
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```
Ở đây chúng tôi **count features layer** bằng cách mở dataset và in ra số lượng đối tượng – trong trường hợp này, `1`.

## Vấn đề thường gặp và Giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| **`File not found`** | Biến `path` không đúng | Kiểm tra `dataDir` trỏ tới thư mục tồn tại và `path` được kết hợp với tên tệp, ví dụ `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Sử dụng loại hình học không được phép trong File GDB | Chỉ sử dụng `Point`, `LineString`, hoặc `Polygon` cho các lớp cơ bản. |
| **`License not set`** | Chạy mà không có giấy phép hợp lệ trong môi trường sản xuất | Đăng ký giấy phép của bạn bằng `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.GIS for .NET trong các dự án .NET hiện có của mình không?
Có, Aspose.GIS for .NET có thể được tích hợp một cách liền mạch vào các dự án .NET hiện có của bạn.

### Có phiên bản dùng thử cho Aspose.GIS for .NET không?
Có, bạn có thể khám phá các tính năng của Aspose.GIS for .NET bằng cách tải xuống [phiên bản dùng thử miễn phí](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu chi tiết cho Aspose.GIS for .NET ở đâu?
Tham khảo [tài liệu](https://reference.aspose.com/gis/net/) để có thông tin chi tiết về Aspose.GIS for .NET.

### Làm sao tôi có thể nhận hỗ trợ cho Aspose.GIS for .NET?
Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để nhận hỗ trợ và trợ giúp từ cộng đồng.

### Có giấy phép tạm thời cho Aspose.GIS for .NET không?
Có, bạn có thể nhận một [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) cho Aspose.GIS for .NET.

---

**Cập nhật lần cuối:** 2026-01-10  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}