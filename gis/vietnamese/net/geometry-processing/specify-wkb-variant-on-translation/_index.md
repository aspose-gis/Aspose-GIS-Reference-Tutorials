---
date: 2026-06-10
description: Tìm hiểu cách tạo hình học linestring trong .NET và chuyển đổi hình học
  sang WKB bằng Aspose.GIS cho .NET với biến thể ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Chỉ định biến thể WKB khi dịch
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Tạo hình học Linestring & biến thể WKB trong Aspose.GIS cho .NET
url: /vi/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Hình học Linestring & Biến thể WKB trong Aspose.GIS cho .NET

## Giới thiệu
Nếu bạn cần **tạo hình học linestring .NET** và sau đó chuyển đổi hình học đó thành dạng nhị phân, Aspose.GIS cho .NET cung cấp cho bạn một API sạch sẽ, hiệu suất cao hoạt động trên .NET Framework, .NET Core và .NET 5/6+. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn từng bước — từ việc nhập không gian tên đến ghi tệp EWKB — để bạn có thể bảo tồn thông tin SRID và tích hợp dữ liệu GIS vào PostgreSQL/PostGIS hoặc bất kỳ quy trình làm việc dựa trên nhị phân nào mà không gặp rắc rối.

## Câu trả lời nhanh
- **WKB viết tắt của gì?** Well‑Known Binary, một biểu diễn nhị phân gọn gàng của các đối tượng hình học.  
- **Biến thể WKB nào lưu SRID?** Biến thể `ExtendedPostGis` (EWKB) nhúng SRID trực tiếp vào dữ liệu nhị phân.  
- **Tôi có cần giấy phép không?** Cần một giấy phép Aspose.GIS tạm thời hoặc đầy đủ cho các triển khai sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Thời gian thực hiện khoảng bao lâu?** Thường dưới 10 phút cho một ví dụ cơ bản.

## Hình học Linestring là gì?
Một hình học linestring là một hình dạng đơn giản được tạo thành từ danh sách các điểm có thứ tự, được nối bằng các đoạn thẳng. Nó là cách biểu diễn tiêu chuẩn cho các đối tượng tuyến tính như đường phố, đường ống, hoặc lộ trình sông trong các cơ sở dữ liệu không gian.

## Tại sao phải chỉ định một biến thể WKB?
Sử dụng đúng biến thể WKB đảm bảo rằng siêu dữ liệu quan trọng — đặc biệt là Spatial Reference System Identifier (SRID) — đi kèm với hình học của bạn. Biến thể `ExtendedPostGis` (EWKB) lưu SRID trong payload nhị phân, cho phép chuyển đổi liền mạch với PostGIS, Oracle Spatial, hoặc bất kỳ hệ thống nào yêu cầu nhị phân có thông tin SRID.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:

### Cài đặt Aspose.GIS cho .NET
1. Tải xuống Aspose.GIS: Truy cập [download link](https://releases.aspose.com/gis/net/) để lấy gói mới nhất.  
2. Thêm gói NuGet vào dự án của bạn (ví dụ, `Install-Package Aspose.GIS`).  

### Quen thuộc với lập trình C#
- Hiểu biết cơ bản về cú pháp C# và cấu trúc dự án.  
- Khả năng chạy một dự án console .NET hoặc thư viện lớp.

## Nhập không gian tên
`Aspose.GIS` namespace cung cấp cho bạn quyền truy cập vào tất cả các lớp liên quan đến hình học.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Các không gian tên này cung cấp chức năng GIS cốt lõi, bao gồm tạo hình học, chuyển đổi và tuần tự hoá nhị phân.

## Cách tạo hình học linestring?
Để tạo một linestring, khởi tạo một đối tượng `Linestring` với danh sách các cặp tọa độ có thứ tự, đặt SRID nếu cần, và sau đó tuần tự hoá nó thành biến thể WKB mong muốn. Quá trình bao gồm ba bước: xây dựng hình học, chọn biến thể `ExtendedPostGis` để giữ SRID, và ghi mảng byte kết quả vào tệp.

### Bước 1: Tạo đối tượng Geometry
Lớp `Geometry` là kiểu cơ sở của Aspose.GIS đại diện cho bất kỳ đối tượng không gian nào trong bộ nhớ.  
Linestring đại diện cho một chuỗi các điểm kết nối tạo thành một hình học tuyến tính.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
Trong bước này, chúng tôi khởi tạo một `Linestring` với một tập hợp các cặp tọa độ mô phỏng một đoạn đường đơn giản.

### Bước 2: Tạo biểu diễn WKB
`WkbVariant.ExtendedPostGis` là giá trị enum cho Aspose.GIS biết bao gồm SRID trong dữ liệu nhị phân đầu ra.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Ở đây chúng tôi gọi phương thức `AsBinary`, truyền vào biến thể EWKB, phương thức trả về một `byte[]` chứa toàn bộ biểu diễn nhị phân.

### Bước 3: Ghi vào tệp
`File.WriteAllBytes` ghi mảng nhị phân vào đĩa.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Tệp kết quả (`EWkbFile.ewkb`) có thể được nhập trực tiếp vào bảng PostGIS bằng hàm `ST_GeomFromEWKB`.

## Các vấn đề thường gặp và giải pháp
| Issue | Reason | Solution |
|-------|--------|----------|
| **Tệp rỗng** | `Path.Combine` trỏ tới một thư mục không tồn tại. | Đảm bảo thư mục đích tồn tại hoặc tạo nó bằng `Directory.CreateDirectory`. |
| **SRID không đúng** | Sử dụng `WkbVariant.Standard` mặc định sẽ loại bỏ SRID. | Luôn sử dụng `WkbVariant.ExtendedPostGis` khi cần bảo tồn SRID. |
| **Ngoại lệ giấy phép** | Chạy mà không có giấy phép hợp lệ trong môi trường sản xuất. | Áp dụng giấy phép tạm thời hoặc đầy đủ trước khi thực thi mã trong môi trường sản xuất. |

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng tệp EWKB với PostGIS không?**  
**A:** Có, biến thể `ExtendedPostGis` tạo ra EWKB bao gồm SRID, mà PostGIS đọc trực tiếp bằng `ST_GeomFromEWKB`.  

**Q: Có thể đọc lại tệp WKB thành đối tượng hình học không?**  
**A:** Chắc chắn. Sử dụng `Geometry.FromBinary(byteArray)` để tái tạo hình học từ dạng nhị phân của nó.  

**Q: Thư viện có hỗ trợ các loại hình học khác như polygon không?**  
**A:** Có, Aspose.GIS hỗ trợ điểm, linestring, polygon, multipolygon và nhiều loại không gian khác.  

**Q: Làm thế nào để chỉ định SRID khác khi tạo hình học?**  
**A:** Đặt thuộc tính `SRID` trên đối tượng hình học trước khi gọi `AsBinary`, ví dụ, `linestring.SRID = 4326;`.  

**Q: Đoạn mã này có hoạt động trên .NET Core không?**  
**A:** Có, cùng một API hoạt động trên .NET Framework, .NET Core và .NET 5/6 mà không cần sửa đổi.

---

**Cập nhật lần cuối:** 2026-06-10  
**Kiểm tra với:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Chuyển đổi hình học sang định dạng WKB với Aspose.GIS cho .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Chỉ định biến thể WKT khi chuyển đổi bằng Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Tạo hình học MultiLineString bằng Aspose.GIS cho .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}