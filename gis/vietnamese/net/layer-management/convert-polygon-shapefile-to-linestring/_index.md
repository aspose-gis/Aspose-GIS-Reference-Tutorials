---
title: Chuyển đổi Shapefile đa giác thành Linestring
linktitle: Chuyển đổi Shapefile đa giác thành Linestring
second_title: API Aspose.GIS .NET
description: Khám phá sức mạnh của Aspose.GIS cho .NET và dễ dàng chuyển đổi Tệp hình dạng đa giác thành Linestrings. Thúc đẩy sự phát triển GIS của bạn ngay hôm nay!
type: docs
weight: 18
url: /vi/net/layer-management/convert-polygon-shapefile-to-linestring/
---
## Giới thiệu
Nếu bạn đang làm việc với hệ thống thông tin địa lý (GIS) trong .NET, Aspose.GIS là một thư viện mạnh mẽ có thể đơn giản hóa công việc của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi Tệp hình đa giác thành Chuỗi đường bằng Aspose.GIS. Điều này có thể đặc biệt hữu ích khi bạn cần trích xuất các đặc điểm tuyến tính từ dữ liệu đa giác cho các ứng dụng khác nhau như lập kế hoạch tuyến đường hoặc phân tích mạng.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:
-  Thư viện Aspose.GIS: Tải xuống và cài đặt thư viện Aspose.GIS từ[trang mạng](https://releases.aspose.com/gis/net/).
- Dữ liệu Shapefile: Chuẩn bị sẵn một Shapefile đa giác để chuyển đổi. Nếu chưa có, bạn có thể tìm dữ liệu mẫu hoặc tạo dữ liệu của riêng mình.
- Môi trường phát triển: Thiết lập môi trường phát triển .NET của bạn với các công cụ cần thiết.
## Nhập không gian tên
Trong mã C#, bạn cần nhập vùng tên Aspose.GIS để truy cập các lớp và phương thức được yêu cầu. Thêm các không gian tên sau vào đầu tệp mã của bạn:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Bước 1: Đặt thư mục tài liệu
```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục chứa Shapefile của bạn.
## Bước 2: Mở Shapefile nguồn
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Phần còn lại của mã sẽ ở đây
}
```
Bước này mở tệp hình dạng đa giác nguồn để đọc.
## Bước 3: Tạo Shapefile chuỗi dòng đích
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Phần còn lại của mã sẽ ở đây
}
```
Ở đây, chúng tôi tạo một Shapestring Shapefile mới để ghi dữ liệu đã chuyển đổi.
## Bước 4: Lặp lại các tính năng nguồn
```csharp
foreach (Feature sourceFeature in source)
{
    // Phần còn lại của mã sẽ ở đây
}
```
Vòng lặp này lặp qua từng tính năng trong Tệp hình đa giác nguồn.
## Bước 5: Chuyển đổi đa giác thành chuỗi dòng và ghi vào đích
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Trong bước này, mỗi tính năng Đa giác được chuyển đổi thành Chuỗi đường và tính năng Chuỗi đường kết quả được ghi vào Shapefile đích.
## Phần kết luận
Bằng cách làm theo các bước này, bạn có thể dễ dàng chuyển đổi Tệp hình đa giác thành Chuỗi đường bằng cách sử dụng Aspose.GIS cho .NET. Quá trình này mở ra những khả năng mới cho việc phân tích và trực quan hóa dữ liệu trong các ứng dụng GIS.

## Câu hỏi thường gặp
### Aspose.GIS có tương thích với tất cả các phiên bản .NET không?
Có, Aspose.GIS hỗ trợ nhiều phiên bản .NET khác nhau, đảm bảo khả năng tương thích với môi trường phát triển của bạn.
### Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?
 Vâng, bạn có thể. Để sử dụng Aspose.GIS trong các dự án thương mại, hãy cân nhắc việc mua giấy phép[đây](https://purchase.aspose.com/buy).
### Có bất kỳ ví dụ hoặc tài liệu nào có sẵn không?
 Có, bạn có thể tìm thấy tài liệu và ví dụ đầy đủ về[trang tài liệu](https://reference.aspose.com/gis/net/).
### Có sẵn phiên bản dùng thử không?
 Có, bạn có thể khám phá Aspose.GIS với bản dùng thử miễn phí bằng cách truy cập[liên kết này](https://releases.aspose.com/).
### Tôi có thể tìm kiếm sự giúp đỡ hoặc hỗ trợ ở đâu?
 Tham quan[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) cho bất kỳ trợ giúp hoặc truy vấn liên quan đến hỗ trợ.