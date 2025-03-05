---
title: Chỉ định Biến thể WKT trên bản dịch bằng Aspose.GIS
linktitle: Chỉ định Biến thể WKT trên bản dịch
second_title: API Aspose.GIS .NET
description: Tìm hiểu cách chỉ định các biến thể WKT trong Aspose.GIS cho .NET để kiểm soát độ chính xác và định dạng biểu diễn dữ liệu không gian một cách hiệu quả.
type: docs
weight: 19
url: /vi/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Giới thiệu
Aspose.GIS for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc với dữ liệu hệ thống thông tin địa lý (GIS) trong các ứng dụng .NET của họ một cách dễ dàng. Một trong những tính năng thiết yếu do Aspose.GIS cung cấp là khả năng chỉ định biến thể Văn bản nổi tiếng (WKT) trong quá trình dịch, cho phép người dùng kiểm soát định dạng và độ chính xác của cách biểu diễn dữ liệu không gian. Trong hướng dẫn này, chúng ta sẽ khám phá cách chỉ định từng bước các biến thể WKT bằng cách sử dụng Aspose.GIS cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Aspose.GIS for .NET: Tải xuống và cài đặt Aspose.GIS cho .NET từ[trang tải xuống](https://releases.aspose.com/gis/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET.
3. Kiến thức cơ bản: Làm quen với ngôn ngữ lập trình C# và .NET framework.

## Nhập không gian tên
Trước khi sử dụng chức năng Aspose.GIS trong mã của bạn, hãy nhập các không gian tên cần thiết:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Bước 1: Tạo đối tượng điểm
 Đầu tiên, tạo một`Point` đối tượng có các giá trị vĩ độ, kinh độ và số đo tùy chọn (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Bước 2: Đặt hệ thống tham chiếu không gian (SRS)
Gán một hệ quy chiếu không gian (SRS) cho đối tượng điểm. Trong ví dụ này, chúng tôi sử dụng hệ thống tham chiếu không gian WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Bước 3: Chỉ định biến thể WKT
 Bây giờ, hãy chỉ định biến thể WKT để dịch. Aspose.GIS hỗ trợ nhiều biến thể WKT khác nhau, bao gồm`Iso`, `SimpleFeatureAccessOutdated` , Và`ExtendedPostGis`. Chọn biến thể phù hợp dựa trên yêu cầu của bạn:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // ĐIỂM M (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // ĐIỂM (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Bước 4: Kiểm soát định dạng số
Bạn có thể kiểm soát định dạng số của tọa độ trong biểu diễn WKT. Aspose.GIS cung cấp các tùy chọn để chỉ định độ chính xác thập phân:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // ĐIỂM M (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // ĐIỂM M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // ĐIỂM M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // ĐIỂM M (23,573 25,342 40,3)
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chỉ định các biến thể WKT khi dịch bằng Aspose.GIS cho .NET. Bằng cách làm theo các bước được nêu ở trên, các nhà phát triển có thể kiểm soát hiệu quả định dạng và độ chính xác của cách biểu diễn dữ liệu không gian trong các ứng dụng .NET của họ, nâng cao tính linh hoạt và khả năng sử dụng của hệ thống thông tin địa lý.
## Câu hỏi thường gặp
### Aspose.GIS có tương thích với tất cả các phiên bản .NET không?
Có, Aspose.GIS hỗ trợ .NET Framework 4.0 trở lên.
### Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?
Có, Aspose.GIS có thể được sử dụng cho cả dự án cá nhân và thương mại.
### Aspose.GIS có cung cấp hỗ trợ cho các định dạng dữ liệu không gian khác không?
Có, Aspose.GIS hỗ trợ nhiều định dạng dữ liệu không gian, bao gồm ESRI Shapefile, GeoJSON và KML.
### Có bản dùng thử miễn phí cho Aspose.GIS không?
 Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.GIS từ[đây](https://releases.aspose.com/).
### Tôi có thể nhận trợ giúp hoặc hỗ trợ cho Aspose.GIS ở đâu?
 Bạn có thể đăng câu hỏi của mình hoặc tìm kiếm sự trợ giúp từ cộng đồng Aspose.GIS tại[diễn đàn](https://forum.aspose.com/c/gis/33).