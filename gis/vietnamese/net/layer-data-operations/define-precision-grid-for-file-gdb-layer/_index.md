---
date: 2025-12-28
description: Tìm hiểu cách đặt lưới cho lớp File GDB bằng Aspose.GIS cho .NET, bao
  gồm việc thêm đối tượng vào lớp và xác thực phạm vi tọa độ.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Cách thiết lập lưới cho lớp File GDB trong Aspose.GIS
url: /vi/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Lưới cho Lớp File GDB trong Aspose.GIS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách đặt mạng** cho một lớp Cơ sở dữ liệu địa lý tệp (GDB) bằng Aspose.GIS cho .NET. Đặt mạng chính xác giúp bạn **xác thực phạm vi thảo luận**, giải lỗi ngoài phạm vi, và đảm bảo dữ liệu **họm đối tượng vào lớp** luôn chính xác và đáng tin cậy. Chúng tôi sẽ hướng dẫn từng bước, giải thích tại sao các cài đặt quan trọng và chỉ cho bạn cách xử lý các vấn đề thường gặp.

## Trả lời nhanh
- **“set Grid” có nghĩa là gì?** Nó xác định độ chính xác chính xác và phạm vi hợp lệ cho một lớp GIS.
- **Tại sao lại sử dụng độ chính xác của mạng?** Nó bảo vệ dữ liệu của bạn khỏi các chế độ họp không hợp lệ và cải thiện hiệu quả lưu trữ.
- **Thư viện nào cung cấp tính năng này?** Aspose.GIS cho .NET.
- **Tôi có cần giấy phép không?** Có bản thử; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Có thể sử dụng .NET Core không?** Có, Aspose.GIS hỗ trợ .NET Framework và .NET Core.

## Lưới chính xác là gì và tại sao lại thiết lập nó?
Độ chính xác của lưới là một tập hợp các tham số (gốc, tỉ lệ, v.v.) cho phép công cụ GIS biết cách làm tròn và lưu trữ giá trị tự do. Bằng cách định nghĩa mạng, bạn **xác thực phạm vi thảo luận** tự động, và bất kỳ cố gắng nào chèn một điểm ngoài mạng sẽ gây ra ngoại lệ—giúp bạn **xử lý các trường hợp hợp ngoài phạm vi** ngay từ giai đoạn phát triển phát triển.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt các mục sau:

1. **Visual Studio** – bất kỳ phiên bản mới nào (Cộng đồng, Chuyên nghiệp hoặc Doanh nghiệp).
2. **Aspose.GIS cho .NET** – tải về từ [trang web](https://releases.aspose.com/gis/net/).
3. **Cơ sở kiến ​​trúc về C#** – bạn nên làm quen với công việc tạo dự án console .NET.

## Nhập không gian tên
Đầu tiên, hãy nhập các không gian tên cần thiết để làm việc với Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Cách đặt lưới trong lớp GDB tệp
Đây là hướng dẫn chi tiết từng bước cho thấy cách cấu hình mạng, tạo lớp và toàn **các đối tượng vào lớp**.

### Bước 1: Tạo bộ dữ liệu
Chúng tôi bắt đầu bằng cách tạo một tập dữ liệu mới Cơ sở dữ liệu địa lý. Đây là nơi sẽ được lưu.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Bước 2: Xác định các tùy chọn lưới chính xác
Ở đây chúng ta chỉ định các tham số lưới. Điều chỉnh gốc và tỉ lệ sao cho phù hợp với hệ tọa độ của dự án.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Cờ `EnsureValidCoordinatesRange = true` thông báo cho Aspose.GIS **xác thực phạm vi tọa độ** cho mỗi đối tượng bạn thêm.*

### Bước 3: Tạo lớp với lưới
Bây giờ chúng ta tạo một lớp mới trong dataset, áp dụng các tùy chọn lưới vừa định nghĩa. Chúng ta sẽ sử dụng hệ tham chiếu không gian WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Bước 4: Thêm đối tượng vào lớp
Chúng ta tạo hai đối tượng điểm. Điểm đầu tiên nằm trong lưới, trong khi điểm thứ hai cố ý nằm ngoài để minh họa **cách xử lý lỗi ngoài phạm vi**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Bước 5: Xử lý ngoại lệ khi thêm các đối tượng nằm ngoài phạm vi
Việc cố gắng thêm đối tượng thứ hai sẽ gây ra ngoại lệ vì tọa độ X (`-410`) nằm ngoài lưới đã định nghĩa. Chúng ta bắt ngoại lệ và in ra thông báo rõ ràng.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Bước 6: Dọn dẹp
Lệnh `sử dụng` tự động đóng và giải nén tập dữ liệu và lớp, đảm bảo mọi tài nguyên được giải phóng.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách giải quyết |
|-------|--------------------------|-------|
| **Ngoại lệ: “Giá trị X … nằm ngoài phạm vi hợp lệ.”** | Cuộc trò chuyện nằm ngoài độ chính xác của mạng. | Điều chỉnh `XOrigin`, `YOrigin`, hoặc `XYScale` để bao phủ dữ liệu của bạn hoặc đảm bảo dữ liệu đầu vào nằm trong phạm vi đã xác định. |
| ** Đối tượng không hiển thị trong trình xem GIS** | Lớp không được lưu hoặc hệ thống tham chiếu không chính xác. | Kiểm tra `SpatialReferenceSystem.Wgs84` so khớp với CRS của trình xem và `Dataset.Create` đã thành công. |
| **Giá trị M bị bỏ qua** | `MScale` được cài đặt thành 0 hoặc quá thấp. | Đặt `MScale` hợp lý (ví dụ `1e4`) để lưu số đo giá trị. |

## Câu hỏi thường gặp

**H: Tôi có thể sử dụng Aspose.GIS cho .NET với các tệp GIS định dạng khác không?**
Đ: Có, Shapefile hỗ trợ Aspose.GIS, GeoJSON, KML và nhiều định dạng khác.

**H: Aspose.GIS cho .NET có tương thích với .NET Core không?**
Đ: Hoàn toàn có. Thư viện hoạt động với .NET Framework, .NET Core và .NET 5/6+.

**H: Tôi có thể thực hiện các phép toán không gian như bộ đệm hay giao lộ không?**
Đ: Có, API cung cấp các phương thức cho bộ đệm, giao nhau và tính toán khoảng cách.

**H: Aspose.GIS không có khả năng chuyển đổi chế độ?**
Đ: Có, bạn có thể chuyển đổi hình học giữa các tham chiếu khác nhau bằng cách sử dụng hợp nhất công cụ chiếu lại.

**H: Có phiên bản đang được thử nghiệm không?**
Đ: Có, bạn có thể tải xuống bản dùng thử miễn phí từ [trang web](https://releases.aspose.com/gis/net/).

---

**Cập nhật lần cuối:** 2025-12-28
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET
**Tác giả:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}