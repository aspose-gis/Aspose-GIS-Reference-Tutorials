---
date: 2025-12-20
description: Tìm hiểu cách tạo đa giác có lỗ bằng Aspose.GIS cho .NET. Hướng dẫn này
  chỉ cho bạn cách tạo lỗ trong đa giác và làm việc với dữ liệu không gian địa lý.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Tạo đa giác có lỗ bằng Aspose.GIS
url: /vi/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Đa Giác Có Lỗ bằng Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ **tạo đa giác có lỗ** bằng Aspose.GIS cho .NET. Cho dù bạn đang xây dựng một ứng dụng bản đồ, thực hiện phân tích không gian, hoặc chuẩn bị dữ liệu cho các dịch vụ GIS, việc biết cách chèn lỗ vào trong một đa giác là rất quan trọng. Chúng tôi sẽ hướng dẫn toàn bộ quy trình từng bước, từ cài đặt môi trường đến tạo đối tượng đa giác cuối cùng.

## Câu trả lời nhanh
- **“create polygon with hole” có nghĩa là gì?** Nó có nghĩa là tạo một đa giác chứa một hoặc nhiều vòng nội (lỗ) bị loại trừ khỏi diện tích.
- **Thư viện nào hỗ trợ điều này?** Aspose.GIS cho .NET cung cấp hỗ trợ đầy đủ cho các vòng ngoại và nội.
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Mất bao lâu để thực hiện?** Thường dưới 10 phút để triển khai và kiểm thử.

## “create polygon with hole” là gì?
Tạo một đa giác có lỗ bao gồm việc xác định một **vòng ngoại** mô tả biên ngoài và một hoặc nhiều **vòng nội** tạo ra các khoảng trống. Các vòng nội thường được gọi là *lỗ* vì chúng đại diện cho các khu vực không thuộc bề mặt của đa giác.

## Tại sao tạo lỗ trong đa giác bằng Aspose.GIS?
- **Mô hình không gian chính xác:** Các đặc tính thực tế như hồ nước bên trong lô đất hoặc sân trong các tòa nhà đòi hỏi có lỗ.
- **Tính tương thích:** Các định dạng như Shapefile, GeoJSON và GML hỗ trợ nguyên bản các vòng nội; Aspose.GIS bảo tồn chúng.
- **Hiệu suất:** Thư viện quản lý tính hợp lệ của hình học, vì vậy bạn không cần viết mã kiểm tra tùy chỉnh.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có các yêu cầu sau:

1. Thư viện Aspose.GIS cho .NET: Bạn có thể tải xuống từ [đây](https://releases.aspose.com/gis/net/).
2. Môi trường phát triển: Đảm bảo bạn đã cài đặt môi trường phát triển với Visual Studio hoặc bất kỳ IDE .NET nào khác.

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
Vòng ngoại xác định biên ngoài của đa giác. Thêm các điểm theo thứ tự đồng hồ để tạo thành một hình dạng đóng.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Bước 3: Định nghĩa Vòng Nội (Lỗ)
Tiếp theo, chúng ta tạo một vòng nội—đây là **lỗ** sẽ bị loại trừ khỏi diện tích của đa giác. Các điểm thường được thêm theo thứ tự ngược chiều kim đồng hồ, nhưng Aspose.GIS tự động xử lý hướng.

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

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Lỗ không hiển thị trong trình xem GIS | Hướng vòng nội bị đảo ngược | Đảm bảo các điểm được thêm theo hướng ngược lại vòng ngoại (ngược chiều kim đồng hồ). |
| Lỗi đa giác không hợp lệ | Các vòng không đóng (điểm đầu ≠ điểm cuối) | Lặp lại điểm đầu làm điểm cuối trong mỗi vòng (như đã minh họa ở trên). |
| Hình học trống không mong muốn | Quên gán `ExteriorRing` trước khi thêm vòng nội | Đặt `polygon.ExteriorRing` trước, sau đó gọi `AddInteriorRing`. |

## Kết luận
Chúc mừng! Bạn đã thành công học cách **tạo đa giác có lỗ** bằng Aspose.GIS cho .NET. Kỹ thuật này là nền tảng cho nhiều trường hợp địa không gian nơi bạn cần biểu diễn các hình dạng phức tạp có khoảng trống bên trong.

## Câu hỏi thường gặp
### 1. Aspose.GIS là gì?
Aspose.GIS là một thư viện .NET cho phép các nhà phát triển làm việc với dữ liệu địa không gian, cho phép họ tạo, đọc và thao tác các định dạng tệp địa không gian khác nhau.

### 2. Tôi có thể sử dụng Aspose.GIS cho dự án thương mại không?
Có, bạn có thể sử dụng Aspose.GIS cho cả dự án cá nhân và thương mại bằng cách mua giấy phép. Tham khảo [đây](https://purchase.aspose.com/buy) để biết thêm chi tiết.

### 3. Có bản dùng thử miễn phí cho Aspose.GIS không?
Có, bạn có thể sử dụng bản dùng thử miễn phí của Aspose.GIS từ [đây](https://releases.aspose.com/).

### 4. Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
Bạn có thể tìm hỗ trợ cho Aspose.GIS trên [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Làm sao để tôi có được giấy phép tạm thời cho Aspose.GIS?
Bạn có thể nhận giấy phép tạm thời cho Aspose.GIS từ [đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-20  
**Kiểm thử với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}