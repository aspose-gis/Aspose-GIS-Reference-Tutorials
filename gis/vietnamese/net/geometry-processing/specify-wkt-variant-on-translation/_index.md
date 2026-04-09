---
date: 2026-04-09
description: Tìm hiểu cách gán tham chiếu không gian và đặt độ chính xác thập phân
  khi tạo điểm C# với Aspose.GIS cho .NET trong các ứng dụng .NET của bạn.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Chỉ định biến thể WKT khi dịch
second_title: Aspose.GIS .NET API
title: Gán Tham chiếu Không gian & Đặt Biến thể WKT bằng Aspose.GIS
url: /vi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gán Tham chiếu Không gian & Đặt Biến thể WKT bằng Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **gán tham chiếu không gian** cho một hình học và kiểm soát định dạng đầu ra WKT chính xác bằng Aspose.GIS cho .NET. Cho dù bạn cần **tạo đối tượng point C#** cho việc bản đồ, phân tích, hoặc trao đổi dữ liệu, khả năng chọn biến thể WKT phù hợp và độ chính xác số học sẽ làm cho dữ liệu không gian của bạn có thể tương tác và dễ đọc. Hãy cùng đi qua quy trình từng bước.

## Câu trả lời nhanh
- **Gán tham chiếu không gian có nghĩa là gì?** Nó gắn một hình học với một hệ tọa độ cụ thể như WGS‑84.  
- **Các biến thể WKT nào được hỗ trợ?** Iso, SimpleFeatureAccessOutdated, và ExtendedPostGis.  
- **Làm thế nào để kiểm soát độ chính xác thập phân?** Sử dụng các tùy chọn `NumericFormat` như `General`, `RoundTrip`, hoặc `Flat`.  
- **Tôi có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào tương thích?** .NET Framework 4.0+ và .NET Core/5/6+.

## “Gán tham chiếu không gian” là gì?
Gán một tham chiếu không gian (hoặc hệ thống tham chiếu không gian, SRS) cho phần mềm GIS biết cách diễn giải các giá trị tọa độ của một hình học. Nếu không có SRS, các số vĩ độ‑kinh độ của một điểm sẽ không có ý nghĩa thực tế.

## Tại sao phải kiểm soát biến thể WKT và định dạng số học?
Các công cụ GIS khác nhau yêu cầu các cú pháp WKT hơi khác nhau. Việc chọn biến thể phù hợp đảm bảo trao đổi dữ liệu liền mạch, trong khi việc đặt độ chính xác thập phân ngăn ngừa lỗi làm tròn hoặc các số quá dài gây lộn xộn trong log và file.

## Yêu cầu trước
1. Aspose.GIS cho .NET – tải xuống từ [download page](https://releases.aspose.com/gis/net/).  
2. Môi trường phát triển .NET (Visual Studio, VS Code, hoặc Rider).  
3. Kiến thức cơ bản về C# và .NET framework.

## Nhập không gian tên
Trước khi sử dụng bất kỳ lớp Aspose.GIS nào, nhập các không gian tên cần thiết:

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

## Bước 1: Tạo Đối tượng Point (tạo point C#)
Chúng ta bắt đầu bằng việc tạo một `Point` với vĩ độ, kinh độ và một giá trị đo (M) tùy chọn:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Bước 2: Gán Hệ thống Tham chiếu Không gian (SRS)
Bây giờ chúng ta **gán tham chiếu không gian** cho điểm. Ở đây chúng ta sử dụng hệ thống WGS‑84 được hỗ trợ rộng rãi (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Bước 3: Chỉ định Biến thể WKT Mong muốn
Chọn biến thể WKT phù hợp với ứng dụng downstream của bạn:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Bước 4: Đặt Độ chính xác Thập phân cho Đầu ra WKT
Kiểm soát số chữ số xuất hiện trong chuỗi cuối cùng bằng `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Những Cạm bẫy Thông thường & Mẹo
- **Cạm bẫy:** Quên đặt SRS trước khi gọi `AsText` có thể dẫn đến thiếu thông tin SRID.  
- **Mẹo:** Sử dụng `NumericFormat.RoundTrip` khi bạn cần chuyển đổi tọa độ không mất mát.  
- **Mẹo:** Biến thể `Iso` là phổ biến nhất; chỉ chọn `ExtendedPostGis` khi bạn cần nhúng SRID.

## Kết luận
Bạn đã biết cách **gán tham chiếu không gian**, chọn biến thể WKT phù hợp, và **đặt độ chính xác thập phân** khi **tạo point C#** với Aspose.GIS. Những điều chỉnh này cung cấp cho bạn sự linh hoạt để đáp ứng các yêu cầu chính xác của bất kỳ quy trình GIS nào, từ trực quan đơn giản đến phân tích không gian độ chính xác cao.

## Câu hỏi thường gặp

**Hỏi:** Aspose.GIS có tương thích với mọi phiên bản .NET không?  
**Đáp:** Có, Aspose.GIS hỗ trợ .NET Framework 4.0 trở lên, cũng như .NET Core/5/6.

**Hỏi:** Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?  
**Đáp:** Chắc chắn. Cần giấy phép thương mại cho việc sử dụng trong sản xuất, nhưng có bản dùng thử miễn phí để đánh giá.

**Hỏi:** Aspose.GIS có hỗ trợ các định dạng dữ liệu không gian khác không?  
**Đáp:** Có, nó hoạt động với ESRI Shapefile, GeoJSON, KML, và nhiều định dạng khác.

**Hỏi:** Tôi có thể tải bản dùng thử miễn phí ở đâu?  
**Đáp:** Bạn có thể tải phiên bản dùng thử miễn phí của Aspose.GIS từ [here](https://releases.aspose.com/).

**Hỏi:** Làm sao tôi có thể nhận được trợ giúp nếu gặp vấn đề?  
**Đáp:** Đăng câu hỏi của bạn trên [forum](https://forum.aspose.com/c/gis/33) cộng đồng Aspose.GIS, nơi cả nhân viên Aspose và các thành viên cộng đồng có thể hỗ trợ.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}