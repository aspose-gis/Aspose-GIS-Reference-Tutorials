---
date: 2026-01-02
description: Tìm hiểu cách thêm đối tượng điểm khi đặt tên trường và đọc ID đối tượng
  bằng Aspose.GIS cho .NET. Hướng dẫn chi tiết từng bước cho các nhà phát triển.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Thêm đối tượng điểm và chỉ định tên trường Object ID và Geometry
url: /vi/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm đối tượng điểm và chỉ định tên Trường ID Đối tượng và Trường Hình học

## Giới thiệu
Bắt đầu hành trình khám phá Hệ thống Thông tin Địa lý (GIS) bằng Aspose.GIS cho .NET mở ra một thế giới đầy tiềm năng cho các nhà phát triển và người đam mê. Trong hướng dẫn này, **bạn sẽ học cách thêm đối tượng điểm** đồng thời **đặt tên các trường** và **đọc giá trị ID đối tượng**, giúp bạn kiểm soát toàn diện dữ liệu không gian của mình.

## Câu trả lời nhanh
- **Mục đích chính của hướng dẫn này là gì?** Để chỉ ra cách thêm đối tượng điểm và cấu hình tên Trường ID Đối tượng và Trường Hình học.  
- **Thư viện nào được sử dụng?** Aspose.GIS cho .NET.  
- **Có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép bắt buộc cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có thể đọc ID Đối tượng sau khi chèn không?** Có – hướng dẫn minh họa cách đọc ID đối tượng từ lớp dữ liệu.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
- Aspose.GIS cho .NET: Tải và cài đặt thư viện từ [here](https://releases.aspose.com/gis/net/).
- Thư mục tài liệu: Tạo một thư mục để lưu trữ các geodatabase.
- Môi trường .NET: Đảm bảo bạn có môi trường .NET hoạt động tốt.

## Nhập không gian tên
Để khởi động, bạn cần nhập các không gian tên cần thiết vào dự án. Những không gian tên này cung cấp các lớp và phương thức thiết yếu để tương tác với Aspose.GIS cho .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Bước 1: Thêm đối tượng điểm và chỉ định tên Trường ID Đối tượng và Trường Hình học
Trong bước này, bạn sẽ học cách thiết lập tên Trường ID Đối tượng và Trường Hình học cho dữ liệu GIS của mình. Điều này rất quan trọng để quản lý dữ liệu hiệu quả và có thể **đọc ID đối tượng** sau này.

### Bước 1.1: Đặt thư mục tài liệu
Bắt đầu bằng cách định nghĩa đường dẫn tới thư mục tài liệu của bạn:

```csharp
string dataDir = "Your Document Directory";
```

### Bước 1.2: Tạo GeoDatabase và Định nghĩa tùy chọn
Tạo một GeoDatabase với **các tên trường** mong muốn cho ID Đối tượng và Hình học:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Bước 1.3: Tạo và Thêm một Lớp
Tạo một lớp trong GeoDatabase và thêm một đối tượng đại diện cho hình học điểm:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Bước 1.4: Mở và Lấy dữ liệu từ Lớp
Mở lớp và lấy lại đối tượng mà bạn vừa thêm. Điều này minh họa cách **đọc ID đối tượng** từ bộ dữ liệu:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Tại sao cần đặt tên trường tùy chỉnh?
Việc tùy chỉnh tên Trường ID Đối tượng và Trường Hình học mang lại sự linh hoạt khi tích hợp với các cơ sở dữ liệu hiện có hoặc khi tuân thủ các quy ước đặt tên mà các ứng dụng downstream yêu cầu. Nó cũng làm cho dữ liệu tự mô tả hơn, giúp đơn giản hoá việc bảo trì và hợp tác.

## Những lỗi thường gặp và cách khắc phục
- **Thư mục không tồn tại** – Đảm bảo `dataDir` trỏ tới một thư mục có thực; nếu không, `Dataset.Create` sẽ ném ngoại lệ.
- **Xung đột tên trường** – Nếu đã tồn tại một trường cùng tên trong geodatabase, việc tạo sẽ thất bại. Hãy chọn tên duy nhất.
- **Không khớp hệ tham chiếu không gian** – Luôn đồng bộ hệ tham chiếu không gian (ví dụ: WGS84) với dữ liệu bạn dự định lưu trữ.

## Kết luận
Chúc mừng! Bạn đã học thành công cách **thêm đối tượng điểm**, **đặt tên trường**, và **đọc ID đối tượng** bằng Aspose.GIS cho .NET. Kiến thức nền tảng này sẽ giúp bạn xây dựng các ứng dụng GIS mạnh mẽ và quản lý dữ liệu không gian một cách tự tin.

## Câu hỏi thường gặp
### H: Tôi có thể sử dụng Aspose.GIS cho .NET trong các ứng dụng web không?
Đ: Có, Aspose.GIS cho .NET phù hợp cho cả ứng dụng desktop và web, cung cấp khả năng địa không gian đa dạng.

### H: Có phiên bản dùng thử trước khi mua không?
Đ: Có, bạn có thể khám phá các tính năng của Aspose.GIS cho .NET với bản dùng thử miễn phí có sẵn [here](https://releases.aspose.com/).

### H: Làm sao để lấy giấy phép tạm thời cho Aspose.GIS cho .NET?
Đ: Bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/) để đánh giá.

### H: Aspose.GIS cho .NET hỗ trợ những hệ tham chiếu không gian nào?
Đ: Aspose.GIS cho .NET hỗ trợ nhiều hệ tham chiếu không gian, mang lại sự linh hoạt cho các bộ dữ liệu địa lý khác nhau.

### H: Tôi có thể tìm trợ giúp hoặc thảo luận các câu hỏi liên quan đến Aspose.GIS ở đâu?
Đ: Ghé thăm diễn đàn Aspose.GIS [here](https://forum.aspose.com/c/gis/33) để được hỗ trợ và thảo luận.

## Các câu hỏi thường gặp bổ sung

**H: Tôi có thể thay đổi trường ID Đối tượng sau khi lớp đã được tạo không?**  
Đ: Không. Tên trường được xác định khi lớp được tạo; bạn phải tạo lại lớp với một đối tượng `FileGdbOptions` mới để thay đổi.

**H: Làm sao để lấy các giá trị thuộc tính khác ngoài ID Đối tượng?**  
Đ: Sử dụng `feature.GetValue<T>("FieldName")` trong đó `FieldName` là tên thuộc tính bạn muốn đọc.

**H: Có thể thêm nhiều đối tượng điểm trong một lần batch không?**  
Đ: Có. Lặp qua dữ liệu của bạn, tạo một đối tượng cho mỗi điểm, đặt hình học, và gọi `layer.Add(feature)` trong cùng một khối `using`.

**H: Aspose.GIS có hỗ trợ các loại hình học khác không?**  
Đ: Chắc chắn. Bạn có thể làm việc với `LineString`, `Polygon`, `MultiPoint`, và nhiều loại khác bằng cách tạo các đối tượng hình học tương ứng.

**H: Điều gì sẽ xảy ra nếu tôi cố đọc một ID Đối tượng không tồn tại?**  
Đ: Truy cập chỉ mục ngoài phạm vi (ví dụ: `layer[10]` khi chỉ có một đối tượng) sẽ ném `IndexOutOfRangeException`. Hãy luôn kiểm tra `layer.Count` trước.

---

**Cập nhật lần cuối:** 2026-01-02  
**Kiểm tra với:** Aspose.GIS cho .NET 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}