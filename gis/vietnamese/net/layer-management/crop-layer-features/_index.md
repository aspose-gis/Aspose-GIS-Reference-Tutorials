---
date: 2026-07-05
description: Tìm hiểu cách cắt các đặc trưng lớp với Aspose.GIS for .NET, bao gồm
  cách cắt raster bằng polygon, trích xuất kích thước ô raster và lấy phạm vi raster.
  Tải bản dùng thử miễn phí ngay.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Cách Cắt Đặc Trưng Lớp
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cách Cắt Đặc Trưng Lớp bằng Aspose.GIS for .NET
url: /vi/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Cắt Đặc Điểm Lớp

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **how to crop layer** các đặc điểm bằng cách sử dụng Aspose.GIS cho .NET, một thư viện mạnh mẽ cho phép bạn **crop raster with polygon**, **extract raster cell size**, và **retrieve raster extent** để thực hiện phân tích không gian địa lý chính xác. Cho dù bạn đang chuẩn bị dữ liệu cho bản đồ web, cắt bớt ảnh vệ tinh, hay cô lập một khu vực quan tâm, hướng dẫn từng bước này sẽ chỉ cho bạn cách thực hiện nhanh chóng và đáng tin cậy.

## Trả lời nhanh
- **What does “crop layer” mean?** Nó cắt một lớp raster hoặc vector theo giới hạn của hình học được cung cấp, loại bỏ mọi thứ nằm ngoài.  
- **Which geometry is used in this example?** Một đa giác được định nghĩa ở định dạng WKT (Well‑Known Text).  
- **Can I extract cell size after cropping?** Có – thuộc tính `CellSize` trả về chiều rộng và chiều cao của một ô raster.  
- **Do I need a license to run the code?** Một giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho sử dụng trong môi trường sản xuất.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “how to crop layer” là gì?
**Cropping a layer means restricting the dataset to a specific geographic area, discarding everything outside.** Hoạt động này giảm kích thước tệp, tăng tốc quá trình xử lý tiếp theo và tập trung phân tích vào khu vực bạn quan tâm. Bằng cách giới hạn dữ liệu trong vùng quan tâm, bạn cũng đơn giản hoá các quy trình downstream như tạo kiểu, phân tích và xuất bản, đồng thời bảo tồn hệ thống tham chiếu tọa độ và siêu dữ liệu gốc.

## Tại sao nên sử dụng Aspose.GIS để cắt?
**Aspose.GIS processes raster files up to 2 GB without loading the entire image into memory and supports more than 30 raster formats, including GeoTIFF, JPEG2000, and PNG.** Thư viện cung cấp một lệnh `Crop` một dòng, xử lý CRS tự động và hiệu năng đa luồng cho phép cắt một tệp GeoTIFF 500 MB trong chưa đầy một giây trên máy chủ tiêu chuẩn.

## Yêu cầu trước
Trước khi đi sâu vào các thao tác không gian địa lý, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Thư viện Aspose.GIS cho .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.GIS trong dự án .NET của mình. Bạn có thể tải xuống từ [here](https://releases.aspose.com/gis/net/).  
- Thư mục tài liệu: Thiết lập một thư mục để lưu trữ tài liệu của bạn. Thay thế `"Your Document Directory"` trong mã mẫu bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

Bây giờ, chúng ta hãy bắt đầu hướng dẫn từng bước.

## Nhập không gian tên
Không gian tên `Aspose.Gis` chứa tất cả các kiểu cốt lõi cho việc xử lý raster và vector. Nhập nó để truy cập các lớp `Layer`, `Geometry` và các lớp liên quan.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Làm thế nào để cắt một lớp bằng đa giác?
`Crop` là một phương thức của lớp `Layer` dùng để trích xuất một phần raster được định nghĩa bởi một hình học.  
Tải raster nguồn, định nghĩa một hình đa giác, và gọi phương thức `Crop` – toàn bộ thao tác được thực hiện trong một dòng mã. Phương thức trả về một raster mới chỉ chứa các pixel bên trong đa giác, tự động bảo tồn hệ tham chiếu không gian gốc.

## Bước 1: Mở và Cắt Lớp (crop raster with polygon)
`Layer` đại diện cho một tập dữ liệu raster có thể được mở, truy vấn và chỉnh sửa.  
Lớp `Layer` đại diện cho một tập dữ liệu raster có thể được mở, truy vấn và chỉnh sửa. Mở một tệp GeoTIFF và cắt nó bằng một đa giác sẽ cô lập khu vực quan tâm chỉ trong vài câu lệnh.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Bước 2: Lấy Thông Tin Raster (extract raster cell size & retrieve raster extent)
`CellSize` cung cấp chiều rộng và chiều cao của mỗi ô raster theo đơn vị tọa độ.  
`Extent` trả về hộp bao địa lý của raster.  
Thuộc tính `CellSize` cung cấp chiều rộng và chiều cao của mỗi ô raster theo đơn vị tọa độ, trong khi thuộc tính `Extent` trả về hộp bao địa lý của raster đã được cắt. Cả hai thông tin này đều quan trọng cho các phép tính downstream như đo diện tích hoặc chuyển đổi hệ tọa độ.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Bước 3: Hiển thị Thông tin
In ra thông tin đã trích xuất để hiểu tác động của quá trình cắt đối với dữ liệu không gian địa lý của bạn.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Lặp lại các bước này khi cần để tinh chỉnh và tùy chỉnh dữ liệu không gian địa lý của bạn đáp ứng các yêu cầu dự án cụ thể.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Định hướng đa giác không đúng** | Đảm bảo đa giác WKT tuân theo quy tắc tay phải (ngược chiều kim đồng hồ cho các vòng ngoài). |
| **Thiếu tham chiếu không gian** | Kiểm tra xem GeoTiff nguồn có chứa CRS không; nếu không, hãy đặt thủ công trước khi cắt. |
| **Hiệu năng chậm trên raster lớn** | Sử dụng `layer.Crop` trên bản sao giảm mẫu hoặc xử lý raster theo các ô (tiles). |

## Câu hỏi thường gặp
**Q: Có giấy phép tạm thời cho Aspose.GIS cho .NET không?**  
A: Có, bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm tài liệu đầy đủ cho Aspose.GIS cho .NET ở đâu?**  
A: Tài liệu có sẵn [here](https://reference.aspose.com/gis/net/).

**Q: Làm sao để tôi nhận hỗ trợ hoặc kết nối với cộng đồng cho Aspose.GIS cho .NET?**  
A: Truy cập [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) để được hỗ trợ và tham gia cộng đồng.

**Q: Tôi có thể tải bản dùng thử miễn phí của Aspose.GIS cho .NET không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí [here](https://releases.aspose.com/).

**Q: Tôi có thể mua Aspose.GIS cho .NET ở đâu?**  
A: Bạn có thể mua thư viện [here](https://purchase.aspose.com/buy).

**Q: Tôi có thể cắt nhiều lớp trong một lần chạy không?**  
A: Có—lặp qua mỗi lớp và áp dụng cùng một lệnh `Crop` với hình học mong muốn.

**Q: API có hỗ trợ các định dạng raster khác (ví dụ: JPEG2000) không?**  
A: Aspose.GIS hỗ trợ tất cả các định dạng do các driver GDAL nền tảng cung cấp, bao gồm JPEG2000, PNG và nhiều hơn nữa.

## Kết luận
Bằng cách làm theo hướng dẫn này, bạn giờ đã biết **how to crop layer** các đặc điểm một cách hiệu quả với Aspose.GIS cho .NET. Bạn có thể dễ dàng **crop raster with polygon**, **extract raster cell size**, và **retrieve raster extent** để đáp ứng nhu cầu của bất kỳ dự án nào. Khám phá các API khác cho việc chuyển hệ tọa độ, tạo kiểu raster và phân tích vector để khai thác tối đa tiềm năng của quy trình không gian địa lý của bạn.

---

**Cập nhật lần cuối:** 2026-07-05  
**Đã kiểm tra với:** Aspose.GIS 24.10 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách tạo hình đa giác với Aspose.GIS cho .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Lấy thuộc tính lớp – Truy xuất thông tin thuộc tính lớp với Aspose.GIS cho .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Tạo hình đa giác C# và kiểm tra giao nhau với Aspose.GIS cho .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}