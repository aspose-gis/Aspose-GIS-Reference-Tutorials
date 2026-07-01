---
date: 2026-04-03
description: Tìm hiểu cách tạo đa giác có lỗ bằng Aspose.GIS cho .NET. Hướng dẫn này
  cho bạn thấy cách tạo lỗ trong đa giác và làm việc với dữ liệu không gian địa lý.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Tạo đa giác có lỗ
second_title: Aspose.GIS .NET API
title: Tạo đa giác có lỗ bằng Aspose.GIS
url: /vi/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Đa Giác Có Lỗ Sử Dụng Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tạo đa giác có lỗ** bằng cách sử dụng Aspose.GIS cho .NET. Cho dù bạn đang xây dựng một ứng dụng bản đồ, thực hiện phân tích không gian, hoặc chuẩn bị dữ liệu cho các dịch vụ GIS, việc biết cách nhúng một lỗ vào trong đa giác là rất cần thiết. Chúng tôi sẽ hướng dẫn toàn bộ quy trình từng bước, từ thiết lập môi trường đến tạo ra đối tượng đa giác cuối cùng.

## Câu trả lời nhanh
- **What does “create polygon with hole” mean?** Nó có nghĩa là tạo một đa giác chứa một hoặc nhiều vòng nội (lỗ) bị loại trừ khỏi diện tích.  
- **Which library handles this?** Aspose.GIS cho .NET cung cấp hỗ trợ đầy đủ cho các vòng ngoại và nội.  
- **Do I need a license?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does it take?** Thường mất dưới 10 phút để triển khai và kiểm tra.

## Cách thêm lỗ vào đa giác bằng Aspose.GIS
Thêm một lỗ chỉ là việc định nghĩa một **vòng nội** và gắn nó vào đa giác. Thư viện sẽ tự động xử lý hướng và tính hợp lệ, vì vậy bạn có thể tập trung vào các tọa độ đại diện cho khoảng trống cần tạo.

## “Tạo đa giác có lỗ” là gì?
Việc tạo một đa giác có lỗ bao gồm việc định nghĩa một **vòng ngoại** mô tả ranh giới bên ngoài và một hoặc nhiều **vòng nội** để tạo ra các không gian trống. Các vòng nội thường được gọi là *lỗ* vì chúng đại diện cho các khu vực không thuộc bề mặt của đa giác.

## Tại sao tạo lỗ trong đa giác bằng Aspose.GIS?
- **Accurate spatial modeling:** Các đặc điểm thực tế như hồ nước trong các lô đất hoặc sân trong các tòa nhà yêu cầu lỗ.  
- **Interoperability:** Các định dạng như Shapefile, GeoJSON và GML hỗ trợ nguyên bản các vòng nội; Aspose.GIS bảo tồn chúng.  
- **Performance:** Thư viện quản lý tính hợp lệ của hình học, vì vậy bạn không cần viết mã kiểm tra tùy chỉnh.

## Các kịch bản thực tế cho đa giác có lỗ
1. **Lô đất có hồ nội bộ** – hồ được mô hình hóa như một lỗ nên không được tính vào diện tích lô.  
2. **Dấu chân tòa nhà có sân trong** – sân trong được loại trừ khỏi dấu chân tòa nhà.  
3. **Khu bảo tồn bên trong một khu vực bảo tồn lớn hơn** – bạn có thể loại trừ các phần hạn chế mà không cần tạo lớp riêng.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
1. Thư viện Aspose.GIS cho .NET: Bạn có thể tải xuống từ [tại đây](https://releases.aspose.com/gis/net/).  
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển với Visual Studio hoặc bất kỳ IDE .NET nào khác đã được cài đặt.

## Nhập không gian tên
Đầu tiên, bạn cần nhập các không gian tên cần thiết để làm việc với các chức năng của Aspose.GIS. Đây là cách thực hiện:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Bây giờ, chúng ta sẽ tiến hành tạo một đa giác có lỗ bằng Aspose.GIS cho .NET.

## Bước 1: Tạo Đối tượng Polygon
Chúng ta bắt đầu bằng cách khởi tạo một đối tượng `Polygon` rỗng, sau này sẽ chứa cả vòng ngoại và vòng nội.

```csharp
Polygon polygon = new Polygon();
```

## Bước 2: Định nghĩa Vòng Ngoại
Vòng ngoại xác định ranh giới bên ngoài của đa giác. Thêm các điểm theo thứ tự đồng hồ để tạo thành một hình dạng đóng.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Bước 3: Định nghĩa Vòng Nội (Lỗ)
Tiếp theo, chúng ta tạo một vòng nội — đây là **lỗ** sẽ bị loại trừ khỏi diện tích của đa giác. Các điểm thường được thêm theo thứ tự ngược chiều kim đồng hồ, nhưng Aspose.GIS tự động xử lý hướng.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Bước 4: Gán Vòng Ngoại và Thêm Vòng Nội vào Polygon
Cuối cùng, gắn vòng ngoại vào đa giác và sau đó thêm vòng nội (lỗ). Phương thức `AddInteriorRing` có thể được gọi nhiều lần nếu bạn cần nhiều lỗ.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Mẹo và Thực hành tốt nhất
- **Orientation matters for readability** – mặc dù Aspose.GIS tự động sửa hướng, việc giữ vòng ngoại theo chiều kim đồng hồ và vòng nội ngược chiều kim đồng hồ giúp hình học dễ kiểm tra hơn trong các trình xem GIS.  
- **Close each ring** – luôn lặp lại tọa độ đầu tiên làm điểm cuối; điều này đảm bảo một hình dạng đóng hợp lệ.  
- **Validate after creation** – bạn có thể gọi `polygon.IsValid` để đảm bảo hình học tuân thủ tiêu chuẩn OGC trước khi lưu.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| Lỗ không hiển thị trong trình xem GIS | Hướng vòng nội bị đảo ngược | Đảm bảo các điểm được thêm theo hướng ngược lại vòng ngoại (ngược chiều kim đồng hồ). |
| Lỗi đa giác không hợp lệ | Các vòng không đóng (điểm đầu ≠ điểm cuối) | Lặp lại điểm đầu làm điểm cuối trong mỗi vòng (như đã minh họa ở trên). |
| Hình học trống không mong muốn | Quên gán `ExteriorRing` trước khi thêm vòng nội | Đặt `polygon.ExteriorRing` trước, sau đó gọi `AddInteriorRing`. |

## Câu hỏi thường gặp
### 1. Aspose.GIS là gì?
Aspose.GIS là một thư viện .NET cho phép các nhà phát triển làm việc với dữ liệu không gian, cho phép tạo, đọc và thao tác với nhiều định dạng tệp không gian khác nhau.

### 2. Tôi có thể sử dụng Aspose.GIS cho dự án thương mại không?
Có, bạn có thể sử dụng Aspose.GIS cho cả dự án cá nhân và thương mại bằng cách mua giấy phép. Tham khảo [tại đây](https://purchase.aspose.com/buy) để biết thêm chi tiết.

### 3. Có bản dùng thử miễn phí cho Aspose.GIS không?
Có, bạn có thể dùng thử miễn phí Aspose.GIS từ [tại đây](https://releases.aspose.com/).

### 4. Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể tìm hỗ trợ cho Aspose.GIS trên [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.GIS?
Bạn có thể nhận giấy phép tạm thời cho Aspose.GIS từ [tại đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-04-03  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}