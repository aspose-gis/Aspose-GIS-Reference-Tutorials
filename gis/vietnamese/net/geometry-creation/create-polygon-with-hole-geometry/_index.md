---
date: 2026-09-05
description: Tìm hiểu cách tạo một vòng trong của đa giác (polygon interior ring)
  có lỗ bằng Aspose.GIS cho .NET. Hướng dẫn này chỉ cho bạn cách thêm lỗ vào đa giác
  và làm việc với dữ liệu.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Tạo Polygon Với Hole Geometry
og_description: Tìm hiểu cách tạo một vòng trong của đa giác (polygon interior ring)
  có lỗ bằng Aspose.GIS cho .NET. Hướng dẫn này chỉ cho bạn cách thêm lỗ vào đa giác
  và làm việc với dữ liệu.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Tạo một vòng trong của đa giác (polygon interior ring) có lỗ bằng Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Tạo một vòng trong của đa giác (polygon interior ring) có lỗ bằng Aspose.GIS
url: /vi/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo một vòng trong của đa giác có lỗ bằng Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **create a polygon interior ring** có chứa một lỗ bằng Aspose.GIS cho .NET. Dù bạn đang xây dựng một ứng dụng bản đồ, thực hiện phân tích không gian, hay chuẩn bị dữ liệu cho các dịch vụ GIS, việc nhúng một lỗ vào trong đa giác là một kỹ năng cốt lõi. Chúng tôi sẽ hướng dẫn toàn bộ quy trình — từ thiết lập môi trường phát triển đến tạo ra một đối tượng đa giác hợp lệ có thể lưu dưới bất kỳ định dạng không gian địa lý nào được hỗ trợ.

## Câu trả lời nhanh
- **What does “create polygon with hole” mean?** Nó có nghĩa là tạo một đa giác chứa một hoặc nhiều vòng trong (lỗ) bị loại trừ khỏi diện tích.  
- **Which library handles this?** Aspose.GIS for .NET cung cấp hỗ trợ đầy đủ cho các vòng ngoài và vòng trong.  
- **Do I need a license?** Một bản dùng thử miễn phí hoạt động cho việc phát triển; cần có giấy phép thương mại cho môi trường sản xuất.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** Thông thường dưới 10 phút để triển khai và kiểm thử.

## Cách thêm lỗ vào đa giác bằng Aspose.GIS
Tải môi trường GIS của bạn, xác định một vòng ngoài, sau đó gắn một hoặc nhiều vòng trong. Aspose.GIS tự động định hướng các vòng và xác thực hình học, vì vậy bạn có thể tập trung vào các tọa độ đại diện cho khoảng trống cần thiết.

## Vòng trong của đa giác là gì?
Một **polygon interior ring** là một ranh giới bên trong giảm diện tích khỏi hình dạng bên ngoài của đa giác.  
Bạn tạo nó bằng cách xác định một chuỗi các điểm đóng mà Aspose.GIS coi là một lỗ, lỗ này sẽ bị loại trừ khi tính diện tích hoặc hiển thị hình dạng.

## Tại sao tạo vòng trong của đa giác bằng Aspose.GIS?
Aspose.GIS xác thực và chỉnh sửa hướng của các vòng trong dưới 5 ms cho các đa giác thường có 200 điểm, loại bỏ nhu cầu viết mã xác thực tùy chỉnh. Nó cũng hỗ trợ **30+ geospatial file formats** (Shapefile, GeoJSON, GML, KML, v.v.) và có thể xử lý các đa giác lên tới 10.000 điểm mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại cho bạn cả tốc độ và khả năng mở rộng.

## Các kịch bản thực tế cho đa giác có lỗ
1. **Land parcel with an internal lake** – hồ được mô hình hoá như một lỗ nên không được tính vào diện tích lô đất.  
2. **Building footprints with courtyards** – sân trong được loại trừ khỏi diện tích nền của tòa nhà.  
3. **Protected zones inside a larger conservation area** – bạn có thể loại trừ các khu vực bị hạn chế mà không cần tạo các lớp riêng.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có các yêu cầu sau:
1. Thư viện Aspose.GIS cho .NET: Bạn có thể tải xuống từ **Aspose.GIS for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển với Visual Studio hoặc bất kỳ IDE .NET nào khác đã được cài đặt.

## Nhập không gian tên
Không gian tên `Aspose.Gis` chứa tất cả các kiểu hình học bạn sẽ cần, bao gồm `Polygon`, `LinearRing`, và các phương thức trợ giúp để xác thực.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Bây giờ, hãy tiếp tục tạo một hình đa giác có lỗ bằng Aspose.GIS cho .NET.

## Bước 1: tạo đối tượng đa giác
`Polygon` là kiểu hình học của Aspose.GIS đại diện cho một đa giác phẳng có thể có các vòng trong tùy chọn. Chúng ta bắt đầu bằng cách khởi tạo một đối tượng `Polygon` rỗng sẽ sau này chứa cả vòng ngoài và vòng trong.

```csharp
Polygon polygon = new Polygon();
```

## Bước 2: xác định vòng ngoài
`LinearRing` là lớp được sử dụng cho cả ranh giới ngoài và trong. Vòng ngoài xác định ranh giới bên ngoài của đa giác. Thêm các điểm theo thứ tự đồng hồ để tạo thành một hình dạng đóng.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Bước 3: xác định vòng trong (lỗ)
`LinearRing` cũng đại diện cho các vòng trong. Vòng trong là **hole** sẽ bị loại trừ khỏi diện tích của đa giác. Các điểm thường được thêm theo thứ tự ngược chiều kim đồng hồ, nhưng Aspose.GIS tự động xử lý hướng.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Bước 4: gán vòng ngoài và thêm vòng trong vào đa giác
Phương thức `AddInteriorRing` gắn một hoặc nhiều vòng trong vào một `Polygon`. Gọi nó sau khi thiết lập thuộc tính `ExteriorRing`; bạn có thể lặp lại lời gọi để thêm nhiều lỗ.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Mẹo và thực tiễn tốt nhất
- **Orientation matters for readability** – trong khi Aspose.GIS tự động chỉnh sửa hướng, việc giữ vòng ngoài theo chiều kim đồng hồ và vòng trong ngược chiều kim đồng hồ giúp hình học dễ kiểm tra hơn trong các trình xem GIS.  
- **Close each ring** – luôn lặp lại tọa độ đầu tiên làm điểm cuối cùng; điều này đảm bảo một hình dạng đóng hợp lệ.  
- **Validate after creation** – bạn có thể gọi `polygon.IsValid` để đảm bảo hình học tuân thủ tiêu chuẩn OGC trước khi lưu.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Lỗ không hiển thị trong trình xem GIS | Hướng vòng trong bị đảo ngược | Đảm bảo các điểm được thêm theo hướng ngược lại so với vòng ngoài (ngược chiều kim đồng hồ). |
| Lỗi đa giác không hợp lệ | Các vòng không đóng (điểm đầu ≠ điểm cuối) | Lặp lại điểm đầu làm điểm cuối trong mỗi vòng (như đã minh họa ở trên). |
| Hình học bất ngờ rỗng | Quên gán `ExteriorRing` trước khi thêm các vòng trong | Đặt `polygon.ExteriorRing` trước, sau đó gọi `AddInteriorRing`. |

## Câu hỏi thường gặp
### 1. Aspose.GIS là gì?
Aspose.GIS là một thư viện .NET cho phép các nhà phát triển làm việc với dữ liệu không gian địa lý, cho phép họ tạo, đọc và thao tác với các định dạng tệp không gian địa lý khác nhau.

### 2. Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?
Có, bạn có thể sử dụng Aspose.GIS cho cả dự án cá nhân và thương mại bằng cách mua giấy phép. Tham khảo **Aspose.GIS purchase page**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) để biết thêm chi tiết.

### 3. Có bản dùng thử miễn phí cho Aspose.GIS không?
Có, bạn có thể sử dụng bản dùng thử miễn phí của Aspose.GIS từ **Aspose.GIS free trial download page**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể tìm hỗ trợ cho Aspose.GIS trên [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.GIS?
Bạn có thể nhận giấy phép tạm thời cho Aspose.GIS từ **Aspose.GIS temporary license page**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Cập nhật lần cuối:** 2026-09-05  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo hình đa giác với Aspose.GIS cho .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Học cách tạo hình MultiPolygon với Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Chuyển đổi đa giác thành đường với Aspose.GIS cho .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}