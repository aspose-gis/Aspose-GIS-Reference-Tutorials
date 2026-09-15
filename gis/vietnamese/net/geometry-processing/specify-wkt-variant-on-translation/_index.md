---
date: 2026-09-15
description: Tìm hiểu cách gán coordinate system, đặt WKT variant và kiểm soát decimal
  precision khi tạo point geometry trong C# với Aspose.GIS cho .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Chỉ định WKT Variant khi Dịch
og_description: Tìm hiểu cách gán coordinate system, đặt WKT variant và kiểm soát
  decimal precision khi tạo point geometry trong C# với Aspose.GIS cho .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Gán coordinate system, đặt WKT variant bằng Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Gán coordinate system, đặt WKT variant bằng Aspose.GIS
url: /vi/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gán hệ tọa độ, đặt biến thể WKT bằng Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **gán hệ tọa độ**, chọn biến thể WKT phù hợp, và kiểm soát độ chính xác thập phân khi **tạo hình học điểm** trong C# với Aspose.GIS cho .NET. Cho dù bạn đang xây dựng dịch vụ bản đồ, thực hiện phân tích không gian, hoặc trao đổi dữ liệu giữa các nền tảng GIS, các cài đặt này đảm bảo đầu ra của bạn vừa tương thích vừa dễ đọc. Hãy cùng đi qua quy trình từng bước.

## Câu trả lời nhanh
- **Gán hệ tọa độ** có nghĩa là gì?** Nó gắn một hình học với một hệ tham chiếu tọa độ cụ thể như WGS‑84.  
- **Các biến thể WKT nào được hỗ trợ?** Iso, SimpleFeatureAccessOutdated, và ExtendedPostGis.  
- **Làm sao tôi có thể kiểm soát độ chính xác thập phân?** Sử dụng enum `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Tôi có cần giấy phép cho Aspose.GIS không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho việc sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào tương thích?** .NET Framework 4.0+ và .NET Core/5/6+.

## “Gán hệ tọa độ” là gì?
Gán một tham chiếu không gian (hoặc hệ tham chiếu không gian, SRS) cho phần mềm GIS biết cách diễn giải các giá trị tọa độ của một hình học, liên kết các số với một hệ tọa độ thực tế như WGS‑84. Nếu không có SRS, các số vĩ độ‑kinh độ của một điểm sẽ không có ý nghĩa thực tế.

## Tại sao cần kiểm soát biến thể WKT và định dạng số?
Hơn 30 công cụ GIS yêu cầu các cú pháp WKT cụ thể, vì vậy việc chọn đúng biến thể giúp tránh lỗi nhập khẩu. Đặt định dạng số giảm tiếng ồn làm tròn và giữ đầu ra ngắn gọn, điều này đặc biệt quan trọng khi các log hoặc tệp được phân tích tự động.

## Yêu cầu trước
1. Aspose.GIS for .NET – tải về từ [download page](https://releases.aspose.com/gis/net/).  
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

## Cách gán hệ tọa độ cho một điểm?
Tải một thể hiện `Point`, sau đó gắn hệ tham chiếu không gian (SRS) bằng lớp `SpatialReference`. Mô hình hai bước này đảm bảo hình học mang siêu dữ liệu hệ tọa độ khi xuất, cho phép các công cụ hạ nguồn diễn giải tọa độ đúng. Lớp `Point` đại diện cho một vị trí duy nhất được xác định bởi tọa độ X (kinh độ) và Y (vĩ độ).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Bước 2: gán hệ tham chiếu không gian (SRS)
Bây giờ chúng ta **gán tham chiếu không gian** cho điểm. `SpatialReference` đại diện cho một hệ tham chiếu tọa độ được xác định bằng SRID. Ở đây chúng ta sử dụng hệ WGS‑84 phổ biến (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Bước 3: chỉ định biến thể WKT mong muốn
Chọn biến thể WKT phù hợp với ứng dụng hạ nguồn của bạn:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Cách đặt độ chính xác thập phân cho đầu ra WKT?
Kiểm soát số chữ số xuất hiện trong chuỗi cuối cùng bằng enum `NumericFormat`, định nghĩa các quy tắc định dạng như `General`, `RoundTrip`, hoặc `Flat`. Chọn `RoundTrip` giữ nguyên độ chính xác tọa độ cho các kịch bản vòng lặp, trong khi `General` cung cấp biểu diễn ngắn gọn phù hợp cho hầu hết các tác vụ trực quan hoá. Enum `NumericFormat` kiểm soát cách các số tọa độ được định dạng trong đầu ra WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Các lỗi thường gặp & mẹo
- **Cạm bẫy:** Quên đặt SRS trước khi gọi `AsText` có thể dẫn đến thiếu thông tin SRID.  
- **Mẹo:** Sử dụng `NumericFormat.RoundTrip` khi bạn cần chuyển đổi tọa độ không mất mát.  
- **Mẹo:** Biến thể `Iso` là phổ biến nhất; chỉ chọn `ExtendedPostGis` khi bạn cần nhúng SRID.

## Kết luận
Bạn đã biết cách **gán hệ tọa độ**, chọn biến thể WKT phù hợp, và **đặt độ chính xác thập phân** khi **tạo hình học điểm** với Aspose.GIS. Những điều chỉnh này cung cấp cho bạn sự linh hoạt để đáp ứng các yêu cầu chính xác của bất kỳ quy trình GIS nào, từ trực quan hoá đơn giản đến phân tích không gian độ chính xác cao.

## Câu hỏi thường gặp

**Q:** Có Aspose.GIS tương thích với mọi phiên bản .NET không?  
**A:** Có, Aspose.GIS hỗ trợ .NET Framework 4.0 trở lên, cũng như .NET Core/5/6.

**Q:** Tôi có thể sử dụng Aspose.GIS cho dự án thương mại không?  
**A:** Chắc chắn. Cần giấy phép thương mại cho việc sử dụng trong môi trường sản xuất, nhưng có bản dùng thử miễn phí để đánh giá.

**Q:** Aspose.GIS có hỗ trợ các định dạng dữ liệu không gian khác không?  
**A:** Có, nó hỗ trợ hơn 30 định dạng, bao gồm ESRI Shapefile, GeoJSON, KML, CSV và nhiều hơn nữa.

**Q:** Tôi có thể tải bản dùng thử miễn phí ở đâu?  
**A:** Bạn có thể tải bản dùng thử miễn phí của Aspose.GIS từ [Aspose.GIS free trial download page](https://releases.aspose.com/).

**Q:** Làm sao tôi có thể nhận được hỗ trợ nếu gặp vấn đề?  
**A:** Đăng câu hỏi của bạn trên [forum](https://forum.aspose.com/c/gis/33) cộng đồng Aspose.GIS, nơi cả nhân viên Aspose và các thành viên cộng đồng có thể hỗ trợ.

---

**Last Updated:** 2026-09-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Các hướng dẫn liên quan

- [Tạo lớp Vector và đặt Hệ tham chiếu không gian của nó](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Cách chuyển đổi Geometry sang WKT với Aspose.GIS cho .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Cách giới hạn độ chính xác khi ghi Geometry với Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}