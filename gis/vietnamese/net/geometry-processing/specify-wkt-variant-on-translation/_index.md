---
date: 2025-12-23
description: Tìm hiểu cách chuyển đổi hình học sang WKT với các tùy chọn đa dạng,
  thiết lập định dạng số và điều chỉnh độ chính xác thập phân bằng Aspose.GIS cho
  .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Chuyển đổi Hình học sang các tùy chọn biến thể WKT bằng Aspose.GIS
url: /vi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển Đổi Hình Học Sang Các Tùy Chọn Biến Thể WKT bằng Aspose.GIS

## Giới thiệu
Trong các ứng dụng .NET hiện đại, **chuyển đổi hình học sang WKT** là một bước phổ biến khi bạn cần trao đổi dữ liệu không gian với các hệ thống khác hoặc lưu trữ nó ở định dạng dựa trên văn bản. Aspose.GIS cho .NET thực hiện việc chuyển đổi này một cách dễ dàng đồng thời cho phép bạn kiểm soát toàn bộ biến thể WKT, định dạng số và độ chính xác thập phân. Trong hướng dẫn này, bạn sẽ học cách chuyển đổi hình học sang WKT, chọn biến thể phù hợp, và tinh chỉnh đầu ra để đáp ứng yêu cầu chính xác của dự án.

## Câu trả lời nhanh
- **Chuyển đổi hình học sang WKT có nghĩa là gì?** Nó chuyển đổi các đối tượng hình học (điểm, đường, đa giác) thành định dạng Văn Bản Được Biết Đến (Well‑Known Text).  
- **Các biến thể WKT nào được hỗ trợ?** `Iso`, `SimpleFeatureAccessOutdated`, và `ExtendedPostGis`.  
- **Làm thế nào để kiểm soát độ chính xác thập phân?** Sử dụng các tùy chọn `NumericFormat` như `General`, `RoundTrip`, hoặc `Flat`.  
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại cho việc sử dụng không phải thử nghiệm.  
- **Các phiên bản .NET nào tương thích?** .NET Framework 4.0+ và .NET 5/6/7.

## Chuyển Đổi Hình Học Sang WKT là gì?
Việc chuyển đổi hình học sang WKT tạo ra một chuỗi có thể đọc được bởi con người mô tả các đối tượng không gian. Định dạng này được chấp nhận rộng rãi bởi các công cụ GIS, cơ sở dữ liệu và dịch vụ web, làm cho nó trở thành lựa chọn lý tưởng cho việc trao đổi dữ liệu.

## Tại sao nên sử dụng Aspose.GIS cho việc chuyển đổi này?
- **Kiểm soát độ chính xác** – Chọn số chữ số thập phân được xuất ra.  
- **Linh hoạt về biến thể** – Phù hợp với ngôn ngữ WKT chính xác mà hệ thống hạ nguồn của bạn yêu cầu.  
- **Không phụ thuộc bên ngoài** – Thư viện .NET thuần, không có binary gốc.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Aspose.GIS cho .NET** – Tải xuống và cài đặt từ [trang tải xuống](https://releases.aspose.com/gis/net/).  
2. **Môi trường phát triển** – Bất kỳ phiên bản Visual Studio hoặc VS Code nào mới với .NET SDK.  
3. **Kiến thức C# cơ bản** – Quen thuộc với các lớp, đối tượng và .NET framework.

## Nhập các không gian tên
Đầu tiên, đưa các không gian tên cần thiết vào phạm vi:

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

## Bước 1: Tạo Đối Tượng Point
Tạo một `Point` mà sau này bạn sẽ **chuyển đổi hình học sang WKT**. Điểm này bao gồm vĩ độ, kinh độ và một giá trị đo (M) tùy chọn:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Bước 2: Đặt Hệ Tham Chiếu Không Gian (SRS)
Gán một hệ tham chiếu không gian để đầu ra WKT biết hệ tọa độ nào cần tham chiếu. Ở đây chúng ta sử dụng hệ thống WGS84 phổ biến:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Bước 3: Chỉ định Biến Thể WKT
Chọn biến thể WKT phù hợp khi bạn **chuyển đổi hình học sang WKT**. Mỗi biến thể sẽ định dạng đầu ra hơi khác nhau:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Bước 4: Kiểm Soát Định Dạng Số (Đặt Định Dạng Số & Điều Chỉnh Độ Chính Xác Thập Phân)
Tinh chỉnh cách biểu diễn số của các tọa độ. Lớp `NumericFormat` cho phép bạn **đặt định dạng số** và **điều chỉnh độ chính xác thập phân** phù hợp với nhu cầu của mình:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Vấn Đề Thường Gặp & Mẹo
- **Thiếu giá trị M** – Nếu bạn không cần đo, bỏ qua thuộc tính `M`; biến thể ISO sẽ tự động loại bỏ nó.  
- **Độ chính xác không mong muốn** – Kiểm tra lại rằng bạn đang sử dụng `NumericFormat` đúng; `General` giữ nguyên độ chính xác double đầy đủ, trong khi `Flat` làm tròn tới số chữ số thập phân đã chỉ định.  
- **SRID không hiển thị** – Chỉ biến thể `ExtendedPostGis` mới thêm tiền tố `SRID=` vào đầu ra. Chọn biến thể này khi hệ thống đích của bạn yêu cầu SRID.

## Kết luận
Bằng cách thực hiện các bước trên, bạn đã biết cách **chuyển đổi hình học sang WKT**, chọn biến thể phù hợp và kiểm soát chính xác đầu ra số. Điều này mang lại cho bạn sự linh hoạt để tích hợp Aspose.GIS với bất kỳ quy trình GIS, cơ sở dữ liệu hoặc dịch vụ web nào tiêu thụ WKT.

## Câu hỏi thường gặp
### Aspose.GIS có tương thích với mọi phiên bản .NET không?
Có, Aspose.GIS hỗ trợ .NET Framework 4.0 trở lên.  

### Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?
Có, Aspose.GIS có thể được sử dụng cho cả dự án cá nhân và thương mại.  

### Aspose.GIS có hỗ trợ các định dạng dữ liệu không gian khác không?
Có, Aspose.GIS hỗ trợ nhiều định dạng dữ liệu không gian, bao gồm ESRI Shapefile, GeoJSON và KML.  

### Có bản dùng thử miễn phí cho Aspose.GIS không?
Có, bạn có thể tải xuống phiên bản dùng thử miễn phí của Aspose.GIS từ [đây](https://releases.aspose.com/).  

### Tôi có thể nhận trợ giúp hoặc hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể đăng câu hỏi hoặc tìm kiếm hỗ trợ từ cộng đồng Aspose.GIS tại [diễn đàn](https://forum.aspose.com/c/gis/33).

## Các Câu Hỏi Thường Gặp
**H: Làm thế nào để xuất một bộ sưu tập Geometry thành một chuỗi WKT duy nhất?**  
Đ: Duyệt qua mỗi geometry trong bộ sưu tập và nối các kết quả `AsText` của chúng, tùy chọn tách bằng dấu phẩy hoặc xuống dòng.

**H: Tôi có thể thay đổi SRID mà không thay đổi tọa độ không?**  
Đ: Có, đặt thuộc tính `SpatialReferenceSystem` thành SRID mong muốn; các giá trị tọa độ vẫn giữ nguyên.

**H: Điều gì sẽ xảy ra nếu tôi sử dụng một biến thể WKT không được hỗ trợ?**  
Đ: Aspose.GIS sẽ ném ra một `ArgumentException`. Luôn kiểm tra biến thể so với các giá trị enum `WktVariant`.

---

**Cập nhật lần cuối:** 2025-12-23  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}