---
date: 2025-12-21
description: Tìm hiểu cách tạo hình học linestring và chuyển đổi hình học sang WKB
  bằng Aspose.GIS cho .NET sử dụng biến thể ExtendedPostGis.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Tạo Hình học Linestring & Biến thể WKB trong Aspose.GIS .NET
url: /vi/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chỉ định biến thể WKB khi chuyển đổi trong Aspose.GIS cho .NET## Giới thiệu
Trong lĩnh vực phát triển Hệ thống Thông tin Địa lý (GIS), Aspose.GIS cho .NET nổi bật như một bộ công cụ mạnh mẽ. Nếu bạn cần **tạo hình học linestring** và sau đó **chuyển đổi hình học sang WKB**, bạn đã đến đúng nơi. Tính đa năng và hiệu quả của nó khiến nó trở thành lựa chọn hàng đầu cho các nhà phát triển muốn tích hợp các chức năng GIS vào ứng dụng .NET một cách liền mạch. Bài viết này là hướng dẫn toàn diện về cách tận dụng Aspose.GIS cho .NET, đặc biệt tập trung vào việc chỉ định các biến thể WKB (Well‑Known Binary) trong quá trình chuyển đổi.

## Câu trả lời nhanh
- **WKB viết tắt của gì?** Well‑Known Binary, một biểu diễn nhị phân gọn gàng của các đối tượng hình học.  
- **Biến thể WKB nào cho phép tôi lưu thông tin SRID?** Biến thể `ExtendedPostGis` (EWKB).  
- **Tôi có cần giấy phép để chạy mã không?** Cần có giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Thời gian thực hiện khoảng bao lâu?** Thông thường dưới 10 phút cho một ví dụ cơ bản.

## Hình học Linestring là gì?
A linestring is a simple geometric shape composed of a sequence of points connected by straight line segments. It’s commonly used to represent roads, rivers, or any linear feature in GIS data.

## Tại sao cần chỉ định biến thể WKB?
Choosing the right WKB variant ensures that important metadata—such as the Spatial Reference System Identifier (SRID)—is preserved when you store or exchange geometry data. The `ExtendedPostGis` variant (EWKB) is particularly useful when working with PostgreSQL/PostGIS or any system that expects SRID information embedded in the binary.

## Yêu cầu trước
Before delving into the specifics of specifying WKB variants in Aspose.GIS for .NET, ensure that you have the following prerequisites in place:

### Cài đặt Aspose.GIS cho .NET
1. Tải về Aspose.GIS: Truy cập [liên kết tải xuống](https://releases.aspose.com/gis/net/) để nhận gói Aspose.GIS cho .NET.  
2. Cài đặt gói: Thực hiện theo hướng dẫn cài đặt trong tài liệu để tích hợp Aspose.GIS vào môi trường .NET của bạn một cách liền mạch.

### Quen thuộc với lập trình C#
1. Kiến thức C# cơ bản: Đảm bảo bạn có hiểu biết nền tảng về cú pháp và các khái niệm của ngôn ngữ lập trình C#.

## Nhập không gian tên
To kickstart your journey with Aspose.GIS for .NET and utilize its functionalities effectively, you need to import the necessary namespaces into your project. Here's a step‑by‑step guide:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

These namespaces provide access to the Aspose.GIS functionalities, allowing you to work with geographic data effortlessly.

## Cách tạo hình học linestring?
Let's dissect the provided example into multiple steps to understand the process of specifying WKB variants on translation thoroughly.

### Bước 1: Tạo đối tượng Geometry
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In this step, we **create a linestring geometry** representing a linear feature with the specified coordinates.

### Bước 2: Tạo biểu diễn WKB
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Here, we **convert the geometry to WKB** using the `ExtendedPostGis` variant, which embeds SRID information.

### Bước 3: Ghi vào tệp
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Finally, we write the generated WKB binary data to a file named `EWkbFile.ewkb` in the directory of your choice.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Lý do | Giải pháp |
|-------|--------|----------|
| **Tệp rỗng** | `Path.Combine` trỏ tới một thư mục không tồn tại. | Đảm bảo thư mục đích tồn tại hoặc tạo nó bằng `Directory.CreateDirectory`. |
| **SRID không đúng** | Sử dụng `WkbVariant.Standard` mặc định sẽ mất SRID. | Luôn sử dụng `WkbVariant.ExtendedPostGis` khi cần bảo toàn SRID. |
| **Ngoại lệ giấy phép** | Chạy mà không có giấy phép hợp lệ trong môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc đầy đủ trước khi thực thi mã trong môi trường sản xuất. |

## Câu hỏi thường gặp
### Aspose.GIS cho .NET có tương thích với tất cả các phiên bản .NET không?
Aspose.GIS for .NET is designed to be compatible with various versions of .NET, ensuring flexibility and accessibility for developers.

### Tôi có thể yêu cầu hỗ trợ hoặc trợ giúp khi sử dụng Aspose.GIS cho .NET không?
Yes, you can seek support and assistance through the dedicated [Aspose.GIS forum](https://forum.aspose.com/c/gis/33), where experts and fellow developers can address your queries.

### Aspose.GIS cho .NET có cung cấp bản dùng thử miễn phí không?
Yes, you can explore the features and capabilities of Aspose.GIS for .NET through a free trial available at [this link](https://releases.aspose.com/).

### Làm sao tôi có thể lấy giấy phép tạm thời cho Aspose.GIS cho .NET?
You can obtain a temporary license by visiting the [temporary license page](https://purchase.aspose.com/temporary-license/) and following the provided instructions.

### Tôi có thể mua giấy phép cho Aspose.GIS cho .NET ở đâu?
You can purchase a license for Aspose.GIS for .NET from the purchase page at [this link](https://purchase.aspose.com/buy).

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng tệp EWKB với PostGIS không?**  
A: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which PostGIS can read directly.

**Q: Có thể đọc lại tệp WKB thành đối tượng geometry không?**  
A: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry.

**Q: Thư viện có hỗ trợ các loại geometry khác như polygon không?**  
A: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons, and more.

**Q: Làm sao chỉ định SRID khác khi tạo geometry?**  
A: Set the SRID on the geometry object before calling `AsBinary`, e.g., `geometry.SRID = 4326;`.

**Q: Đoạn mã này có chạy trên .NET Core không?**  
A: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}