---
date: 2026-01-13
description: Tìm hiểu cách cắt các tính năng lớp với Aspose.GIS cho .NET, bao gồm
  cách cắt raster bằng đa giác, trích xuất kích thước ô raster và lấy phạm vi raster.
  Tải bản dùng thử miễn phí ngay.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Cách cắt các đối tượng lớp bằng Aspose.GIS cho .NET
url: /vi/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Cắt Lớp Đặc Trưng

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách cắt lớp** (crop layer) các đặc trưng bằng Aspose.GIS cho .NET, một phương pháp mạnh mẽ cho phép bạn **cắt raster bằng polygon**, **trích xuất kích thước ô raster**, và **lấy phạm vi raster** để thực hiện phân tích không gian chính xác. Dù bạn đang chuẩn bị dữ liệu cho bản đồ web, cắt bớt ảnh vệ tinh, hay cô lập một khu vực quan tâm, hướng dẫn từng bước này sẽ chỉ cho bạn cách thực hiện công việc một cách hiệu quả.

## Câu trả lời nhanh
- **“Crop layer” có nghĩa là gì?** Nó cắt một lớp raster hoặc vector theo giới hạn của một hình học được cung cấp.  
- **Hình học nào được sử dụng trong ví dụ này?** Một polygon được định nghĩa ở định dạng WKT.  
- **Tôi có thể trích xuất kích thước ô sau khi cắt không?** Có – thuộc tính `CellSize` cung cấp thông tin đó.  
- **Có cần giấy phép để chạy mã không?** Giấy phép tạm thời hoạt động cho mục đích đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “Cách cắt lớp” là gì?
Cắt một lớp có nghĩa là giới hạn bộ dữ liệu trong một khu vực địa lý cụ thể, loại bỏ mọi dữ liệu nằm ngoài hình dạng đã định. Điều này giảm kích thước tệp, tăng tốc xử lý và tập trung phân tích vào khu vực bạn quan tâm.

## Tại sao nên dùng Aspose.GIS để cắt?
- **Xử lý raster hiệu năng cao** – lý tưởng cho các tệp GeoTiff lớn.  
- **API đơn giản** – chỉ một dòng lệnh `Crop` với bất kỳ hình học nào.  
- **Tương thích đầy đủ với .NET** – hoạt động trên ứng dụng desktop, server và cloud.  
- **Xử lý hệ quy chiếu không gian chính xác** – tự động bảo tồn thông tin CRS.

## Yêu cầu trước
Trước khi bắt đầu với các thao tác không gian, hãy đảm bảo bạn đã chuẩn bị đầy đủ các yêu cầu sau:

- Thư viện Aspose.GIS cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.GIS trong dự án .NET của mình. Bạn có thể tải về từ [đây](https://releases.aspose.com/gis/net/).  
- Thư mục tài liệu: Tạo một thư mục để lưu trữ các tài liệu của bạn. Thay thế `"Your Document Directory"` trong mã mẫu bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

Bây giờ, hãy bắt đầu với hướng dẫn chi tiết từng bước.

## Nhập các namespace
Bắt đầu bằng cách nhập các namespace cần thiết để khai thác toàn bộ sức mạnh của Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Bước 1: Mở và Cắt Lớp (crop raster with polygon)
Mở lớp GeoTiff và cắt nó dựa trên một polygon đã định nghĩa. Điều này đảm bảo dữ liệu không gian của bạn được tinh chỉnh theo khu vực quan tâm cụ thể.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Bước 2: Lấy Thông Tin Raster (extract raster cell size & retrieve raster extent)
Sau khi lớp đã được cắt, trích xuất các thông tin quan trọng về dữ liệu raster, chẳng hạn như kích thước ô, hệ quy chiếu không gian và giới hạn.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Bước 3: Hiển Thị Thông Tin
In ra các thông tin đã trích xuất để hiểu tác động của quá trình cắt đối với dữ liệu không gian của bạn.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Lặp lại các bước này khi cần thiết để tinh chỉnh và tùy chỉnh dữ liệu không gian sao cho đáp ứng yêu cầu dự án cụ thể.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Hướng polygon không đúng** | Đảm bảo polygon WKT tuân theo quy tắc tay phải (ngược chiều kim đồng hồ cho vòng ngoài). |
| **Thiếu hệ quy chiếu không gian** | Kiểm tra lớp GeoTiff nguồn có CRS không; nếu không, hãy đặt CRS thủ công trước khi cắt. |
| **Giảm hiệu năng khi raster rất lớn** | Sử dụng `layer.Crop` trên bản sao đã giảm mẫu hoặc xử lý raster theo từng ô (tiles). |

## Câu hỏi thường gặp
### H: Có giấy phép tạm thời cho Aspose.GIS cho .NET không?
Đ: Có, bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### H: Tôi có thể tìm tài liệu đầy đủ cho Aspose.GIS cho .NET ở đâu?
Đ: Tài liệu có sẵn [tại đây](https://reference.aspose.com/gis/net/).

### H: Làm sao để nhận hỗ trợ hoặc kết nối với cộng đồng Aspose.GIS cho .NET?
Đ: Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được hỗ trợ và tham gia cộng đồng.

### H: Tôi có thể tải bản dùng thử miễn phí của Aspose.GIS cho .NET không?
Đ: Có, bạn có thể tải bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### H: Tôi có thể mua Aspose.GIS cho .NET ở đâu?
Đ: Bạn có thể mua thư viện [tại đây](https://purchase.aspose.com/buy).

### H: Có thể cắt nhiều lớp trong một lần chạy không?
Đ: Có — lặp qua từng lớp và áp dụng cùng một lệnh `Crop` với hình học mong muốn.

### H: API có hỗ trợ các định dạng raster khác (ví dụ: JPEG2000) không?
Đ: Aspose.GIS hỗ trợ tất cả các định dạng mà các driver GDAL nền tảng cung cấp, bao gồm JPEG2000, PNG và nhiều định dạng khác.

## Kết luận
Sau khi hoàn thành hướng dẫn này, bạn đã biết **cách cắt lớp** các đặc trưng một cách hiệu quả với Aspose.GIS cho .NET. Bạn có thể dễ dàng **cắt raster bằng polygon**, **trích xuất kích thước ô raster**, và **lấy phạm vi raster** để đáp ứng mọi nhu cầu dự án. Hãy khám phá thêm các API cho việc chuyển đổi hệ quy chiếu, tạo kiểu raster và phân tích vector để khai thác tối đa tiềm năng của quy trình công việc không gian của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

---