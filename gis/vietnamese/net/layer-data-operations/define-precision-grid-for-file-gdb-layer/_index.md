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

## Introduction
Trong hướng dẫn này, bạn sẽ học **cách đặt lưới** cho một lớp File Geodatabase (GDB) bằng Aspose.GIS cho .NET. Đặt lưới độ chính xác giúp bạn **xác thực phạm vi tọa độ**, ngăn ngừa lỗi ngoài phạm vi, và đảm bảo dữ liệu **thêm đối tượng vào lớp** luôn chính xác và đáng tin cậy. Chúng tôi sẽ hướng dẫn từng bước, giải thích tại sao các cài đặt quan trọng, và chỉ cho bạn cách xử lý các vấn đề thường gặp.

## Quick Answers
- **“set grid” có nghĩa là gì?** Nó xác định độ chính xác tọa độ và phạm vi hợp lệ cho một lớp GIS.  
- **Tại sao lại sử dụng lưới độ chính xác?** Nó bảo vệ dữ liệu của bạn khỏi các tọa độ không hợp lệ và cải thiện hiệu quả lưu trữ.  
- **Thư viện nào cung cấp tính năng này?** Aspose.GIS cho .NET.  
- **Tôi có cần giấy phép không?** Có bản dùng thử; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể dùng với .NET Core không?** Có, Aspose.GIS hỗ trợ .NET Framework và .NET Core.

## What is a Precision Grid and Why Set It?
Lưới độ chính xác là một tập hợp các tham số (gốc, tỉ lệ, v.v.) cho phép engine GIS biết cách làm tròn và lưu trữ giá trị tọa độ. Bằng cách định nghĩa lưới, bạn **xác thực phạm vi tọa độ** tự động, và bất kỳ cố gắng chèn một điểm ngoài lưới sẽ gây ra ngoại lệ—giúp bạn **xử lý các trường hợp ngoài phạm vi** ngay từ giai đoạn phát triển.

## Prerequisites
Trước khi bắt đầu, hãy chắc chắn bạn đã cài đặt các mục sau:

1. **Visual Studio** – bất kỳ phiên bản mới nào (Community, Professional, hoặc Enterprise).  
2. **Aspose.GIS cho .NET** – tải về từ [website](https://releases.aspose.com/gis/net/).  
3. **Kiến thức cơ bản về C#** – bạn nên quen với việc tạo dự án console .NET.

## Import Namespaces
Đầu tiên, nhập các namespace cần thiết để làm việc với Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## How to Set Grid in a File GDB Layer
Đây là hướng dẫn chi tiết từng bước cho thấy cách cấu hình lưới, tạo lớp, và an toàn **thêm đối tượng vào lớp**.

### Step 1: Create a Dataset
Chúng ta bắt đầu bằng việc tạo một dataset File Geodatabase mới. Đây là nơi lớp sẽ được lưu.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Step 2: Define Precision Grid Options
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

### Step 3: Create a Layer with the Grid
Bây giờ chúng ta tạo một lớp mới trong dataset, áp dụng các tùy chọn lưới vừa định nghĩa. Chúng ta sẽ sử dụng hệ tham chiếu không gian WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Step 4: Add Features to the Layer
Chúng ta tạo hai đối tượng điểm. Điểm đầu tiên nằm trong lưới, trong khi điểm thứ hai cố ý nằm ngoài để minh họa **cách xử lý lỗi ngoài phạm vi**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Step 5: Handle Exceptions When Adding Out‑of‑Range Features
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

### Step 6: Clean Up
Các câu lệnh `using` tự động đóng và giải phóng dataset và lớp, đảm bảo mọi tài nguyên được giải phóng.

## Common Issues and Solutions
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Ngoại lệ: “Giá trị X … nằm ngoài phạm vi hợp lệ.”** | Các tọa độ nằm ngoài lưới độ chính xác. | Điều chỉnh `XOrigin`, `YOrigin`, hoặc `XYScale` để bao phủ dữ liệu của bạn, hoặc đảm bảo dữ liệu đầu vào nằm trong phạm vi đã định. |
| **Đối tượng không hiển thị trong trình xem GIS** | Lớp không được lưu hoặc hệ tham chiếu không đúng. | Kiểm tra `SpatialReferenceSystem.Wgs84` khớp với CRS của trình xem, và `Dataset.Create` đã thành công. |
| **Giá trị M bị bỏ qua** | `MScale` được đặt thành 0 hoặc quá thấp. | Đặt `MScale` hợp lý (ví dụ `1e4`) để lưu giá trị đo. |

## Frequently Asked Questions

**H: Tôi có thể dùng Aspose.GIS cho .NET với các định dạng file GIS khác không?**  
Đ: Có, Aspose.GIS hỗ trợ Shapefile, GeoJSON, KML và nhiều định dạng khác.

**H: Aspose.GIS cho .NET có tương thích với .NET Core không?**  
Đ: Hoàn toàn có. Thư viện hoạt động với .NET Framework, .NET Core và .NET 5/6+.

**H: Tôi có thể thực hiện các phép toán không gian như buffer hay intersection không?**  
Đ: Có, API cung cấp các phương thức cho buffer, intersect và tính khoảng cách.

**H: Aspose.GIS có khả năng chuyển đổi tọa độ không?**  
Đ: Có, bạn có thể chuyển đổi hình học giữa các hệ tham chiếu không gian khác nhau bằng công cụ reprojection tích hợp.

**H: Có phiên bản dùng thử không?**  
Đ: Có, bạn có thể tải bản dùng thử miễn phí từ [website](https://releases.aspose.com/gis/net/).

---

**Cập nhật lần cuối:** 2025-12-28  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}