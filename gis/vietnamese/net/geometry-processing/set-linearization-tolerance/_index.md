---
date: 2025-12-21
description: Tìm hiểu cách tạo lớp vector, thiết lập dung sai tuyến tính hoá và thêm
  đối tượng vào lớp bằng Aspose.GIS cho .NET. Thực hiện theo hướng dẫn từng bước này
  để xuất tệp GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Tạo lớp Vector và thiết lập dung sai tuyến tính hoá bằng Aspose.GIS cho .NET
url: /vi/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Lớp Vector và Đặt Độ Dung Sai Đường Thẳng (Linearization Tolerance) bằng Aspose.GIS cho .NET

## Giới thiệu
Nếu bạn cần **tạo lớp vector** file, kiểm soát độ chính xác của đường cong, và xuất kết quả dưới dạng tài liệu GeoJSON, Aspose.GIS cho .NET giúp thực hiện một cách đơn giản. Trong hướng dẫn này bạn sẽ học cách cấu hình các tùy chọn GeoJSON, đặt độ dung sai linearization, và **thêm đối tượng (feature) vào lớp** — đồng thời giữ cho mã nguồn sạch sẽ và sẵn sàng cho môi trường production.

## Câu trả lời nhanh
- **“tạo lớp vector” có nghĩa là gì?** Nó tạo một bộ dữ liệu GIS vector mới (ví dụ: file GeoJSON) có thể lưu trữ các hình học và thuộc tính.  
- **Cách đặt độ dung sai?** Sử dụng thuộc tính `LinearizationTolerance` của `GeoJsonOptions`.  
- **Có thể xuất file GeoJSON không?** Có — chỉ cần tạo một `VectorLayer` với driver `Drivers.GeoJson`.  
- **Cần giấy phép không?** Giấy phép Aspose.GIS hợp lệ sẽ mở khóa tất cả tính năng; giấy phép tạm thời dùng cho mục đích đánh giá.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “tạo lớp vector” là gì?
Tạo một lớp vector có nghĩa là khởi tạo một container GIS mới (như file GeoJSON) có thể chứa các đối tượng hình học như điểm, đường và đa giác. Lớp này sẽ là đích cho bất kỳ hình học nào bạn tạo và bất kỳ thuộc tính nào bạn gắn vào.

## Tại sao cần cấu hình các tùy chọn GeoJSON?
Cấu hình các tùy chọn GeoJSON — đặc biệt là **độ dung sai linearization** — đảm bảo rằng các hình học cong (ví dụ: `CircularString`) được xấp xỉ với độ chính xác đáp ứng yêu cầu của ứng dụng. Bước này rất quan trọng khi bạn **xuất file GeoJSON** để sử dụng trong bản đồ web hoặc phân tích không gian.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Visual Studio** được cài đặt (bất kỳ phiên bản mới nào).  
2. **Giấy phép Aspose.GIS** (hoặc khóa đánh giá tạm thời).  
3. Thư viện **Aspose.GIS cho .NET** đã tải về và được tham chiếu trong dự án.  
4. Kiến thức cơ bản về **C#**.

## Nhập các Namespace
Đầu tiên, nhập các namespace cần thiết để trình biên dịch biết nơi tìm các lớp GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Hướng dẫn từng bước

### Bước 1: Cấu hình các tùy chọn GeoJSON (cách đặt độ dung sai)
Chúng ta sẽ tạo một đối tượng `GeoJsonOptions` và chỉ định cho Aspose.GIS mức độ gần gũi của hình học đã linearized so với đường cong gốc.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Bước 2: Xác định Đường dẫn Đầu ra (cách xuất GeoJSON)
Chỉ định nơi file kết quả sẽ được lưu. Thay thế placeholder bằng thư mục thực tế của bạn.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Bước 3: **Tạo Lớp Vector** với các tùy chọn đã cấu hình
Bây giờ chúng ta thực sự **tạo lớp vector** bằng phương thức `VectorLayer.Create`. Khối `using` đảm bảo tài nguyên được giải phóng đúng cách.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Bước 4: Xây dựng một Hình học (ví dụ: một chuỗi vòng tròn)
Ở đây chúng ta tạo một hình học mẫu — `CircularString`. Bạn có thể thay thế bằng bất kỳ WKT hợp lệ nào.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Bước 5: **Thêm Đối tượng (Feature) vào Lớp** và lưu
Cuối cùng, chúng ta tạo một feature, gán hình học cho nó, và thêm vào lớp. Đây là phần cốt lõi của thao tác **add feature to layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Khi khối `using` kết thúc, lớp sẽ tự động được ghi vào file được định nghĩa trong `path`, cung cấp cho bạn một file GeoJSON sẵn sàng sử dụng.

## Các vấn đề thường gặp & Mẹo
- **Đường dẫn không đúng** – Đảm bảo thư mục tồn tại và bạn có quyền ghi.  
- **Độ dung sai quá thấp** – Đặt `LinearizationTolerance` quá nhỏ có thể làm tăng kích thước file đáng kể. Điều chỉnh dựa trên nhu cầu độ chính xác của bạn.  
- **Lỗi giấy phép** – Nếu thấy cảnh báo về giấy phép, hãy xác minh rằng file giấy phép đã được tải đúng trước bất kỳ lời gọi nào tới Aspose.GIS.

## Câu hỏi thường gặp

**H: Aspose.GIS cho .NET có tương thích với các framework .NET khác không?**  
Đ: Có, nó hoạt động với .NET Framework, .NET Core và .NET 5/6/7.

**H: Tôi có thể sử dụng Aspose.GIS trong các dự án thương mại không?**  
Đ: Chắc chắn. Giấy phép thương mại loại bỏ mọi hạn chế đánh giá.

**H: Aspose.GIS có hỗ trợ các định dạng GIS khác ngoài GeoJSON không?**  
Đ: Có, nó hỗ trợ Shapefile, KML, GML và nhiều định dạng khác.

**H: Có phiên bản dùng thử không?**  
Đ: Bạn có thể tải bản dùng thử miễn phí từ trang web Aspose.

**H: Tôi có thể nhận hỗ trợ ở đâu?**  
Đ: Sử dụng diễn đàn Aspose hoặc liên kết hỗ trợ trong phần tài nguyên.

## Kết luận
Sau khi thực hiện các bước trên, bạn đã biết cách **tạo lớp vector**, cấu hình độ dung sai linearization, và **thêm đối tượng vào lớp** để tạo **file GeoJSON** một cách liền mạch. Hãy khám phá thêm các loại hình học và cách xử lý thuộc tính để tận dụng tối đa Aspose.GIS trong các dự án GIS .NET của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2025-12-21  
**Đã kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

---