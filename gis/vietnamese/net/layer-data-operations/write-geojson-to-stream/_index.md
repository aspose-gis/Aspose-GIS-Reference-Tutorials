---
date: 2026-01-02
description: Tìm hiểu cách ghi GeoJSON vào luồng trong C# bằng Aspose.GIS cho .NET.
  Hiển thị các ví dụ GeoJSON C# và nâng cao các ứng dụng địa không gian của bạn.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Cách ghi GeoJSON vào luồng với Aspose.GIS cho .NET
url: /vi/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Ghi GeoJSON vào Stream

## Giới thiệu
Nếu bạn cần **cách ghi geojson** trực tiếp vào bộ nhớ hoặc stream tệp trong một ứng dụng .NET, bạn đang ở đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước chính xác để ghi GeoJSON vào một stream bằng thư viện Aspose.GIS cho .NET, và cũng sẽ chỉ cho bạn cách **hiển thị GeoJSON C#** trên console. Khi hoàn thành, bạn sẽ có một mẫu có thể tái sử dụng cho bất kỳ dự án không gian địa lý nào.

## Câu trả lời nhanh
- **“ghi GeoJSON vào stream” có nghĩa là gì?** Nó có nghĩa là tuần tự hoá một lớp vector thành định dạng GeoJSON và gửi các byte tới một đối tượng `Stream` (ví dụ: `MemoryStream`).  
- **Thư viện nào thực hiện việc này?** Aspose.GIS cho .NET cung cấp driver GeoJSON tích hợp.  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể chạy trên Linux không?** Có – Aspose.GIS đa nền tảng và hoạt động trên Windows, Linux và macOS.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “cách ghi geojson” trong .NET là gì?
Aspose.GIS cho phép bạn tạo một `VectorLayer`, thêm các feature, và sau đó tuần tự hoá lớp bằng driver `Drivers.GeoJson`. Driver này ghi trực tiếp văn bản GeoJSON vào bất kỳ `Stream` nào, cho phép bạn kiểm soát hoàn toàn nơi dữ liệu được lưu (bộ nhớ, tệp, mạng, v.v.).

## Tại sao nên dùng Aspose.GIS cho nhiệm vụ này?
- **Tuần tự hoá không phụ thuộc** – không cần thư viện JSON bên ngoài.  
- **Tuân thủ đầy đủ chuẩn GeoJSON** – hỗ trợ FeatureCollections, thuộc tính, và độ chính xác tọa độ.  
- **Đa nền tảng** – hoạt động giống nhau trên Windows, Linux và macOS.  
- **Tối ưu hiệu năng** – ghi trực tiếp vào stream mà không tạo chuỗi trung gian.

## Yêu cầu trước
1. **Aspose.GIS cho .NET** – tải về [tại đây](https://releases.aspose.com/gis/net/).  
2. **Thư mục tài liệu** – quyết định nơi bạn muốn lưu các tệp tạm thời hoặc stream đầu ra.

Bây giờ, chúng ta sẽ đi vào phần mã.

## Nhập các Namespace
Đầu tiên, bao gồm các namespace cho phép bạn truy cập các lớp Aspose.GIS và các tiện ích I/O chuẩn của .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Bước 1: Thiết lập Thư mục Tài liệu
Xác định thư mục sẽ chứa bất kỳ tệp tạm thời nào bạn có thể cần.

```csharp
string dataDir = "Your Document Directory";
```

Thay `"Your Document Directory"` bằng đường dẫn thực tế trên máy của bạn.

## Bước 2: Tạo Memory Stream
`MemoryStream` cho phép bạn giữ GeoJSON trong bộ nhớ, rất phù hợp cho API hoặc khi bạn muốn trả dữ liệu trực tiếp cho client.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Bước 3: Tạo Vector Layer với Driver GeoJSON
Trong khối memory‑stream, tạo một `VectorLayer` sử dụng driver GeoJSON. Điều này báo cho Aspose.GIS tuần tự hoá lớp dưới dạng GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Bước 4: Định nghĩa Thuộc tính Feature
Thêm các định nghĩa thuộc tính sẽ xuất hiện dưới dạng properties trong kết quả GeoJSON cuối cùng.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Bước 5: Xây dựng và Thêm Features
Tạo hai điểm mẫu, gán giá trị thuộc tính, và thêm chúng vào layer.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Bước 6: Hiển thị Kết quả GeoJSON C#
Sau khi layer đã được điền dữ liệu, chuyển các byte của stream thành chuỗi UTF‑8 và ghi ra console. Điều này minh họa cách **hiển thị GeoJSON C#**.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Bạn sẽ thấy một FeatureCollection GeoJSON hợp lệ được in ra terminal.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Đầu ra rỗng | Vị trí stream ở cuối khi đọc | Gọi `memoryStream.Position = 0;` trước khi chuyển sang chuỗi. |
| Hình học không hợp lệ | Tọa độ nằm ngoài phạm vi cho phép | Kiểm tra vĩ độ từ -90 đến 90, kinh độ từ -180 đến 180. |
| Ngoại lệ giấy phép | Chạy mà không có giấy phép hợp lệ trong môi trường sản xuất | Áp dụng giấy phép tạm thời hoặc đầy đủ bằng `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Câu hỏi thường gặp
### Tôi có thể dùng Aspose.GIS cho .NET trên cả Windows và Linux không?
Có, Aspose.GIS cho .NET tương thích với cả hai hệ thống Windows và Linux.  

### Có bản dùng thử miễn phí không?
Chắc chắn! Bạn có thể khám phá bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).  

### Tôi có thể tìm tài liệu chi tiết ở đâu?
Xem tài liệu [tại đây](https://reference.aspose.com/gis/net/).  

### Làm sao để lấy giấy phép tạm thời?
Giấy phép tạm thời có sẵn [tại đây](https://purchase.aspose.com/temporary-license/).  

### Cần hỗ trợ hoặc có câu hỏi khác?
Truy cập diễn đàn hỗ trợ của chúng tôi [tại đây](https://forum.aspose.com/c/gis/33).

## FAQ
**H: Tôi có thể ghi GeoJSON trực tiếp vào tệp thay vì memory stream không?**  
Đ: Có—thay `MemoryStream` bằng `FileStream` và cung cấp đường dẫn tệp. Driver vẫn hoạt động như bình thường.

**H: Làm sao kiểm soát thụt lề hoặc định dạng của GeoJSON được tạo?**  
Đ: Aspose.GIS ghi JSON dạng nén theo mặc định. Để có đầu ra đẹp, bạn có thể xử lý chuỗi sau bằng `JsonSerializerOptions { WriteIndented = true }`.

**H: Có thể thêm các hình học phức tạp hơn (ví dụ: polygon) vào layer không?**  
Đ: Chắc chắn. Tạo đối tượng `Polygon` hoặc `LineString`, gán cho `Feature.Geometry`, và thêm feature như trên.

**H: Các bộ dữ liệu lớn có phù hợp với `MemoryStream` không?**  
Đ: Đối với các collection rất lớn, hãy cân nhắc ghi trực tiếp vào tệp hoặc sử dụng `BufferedStream` để tránh tiêu thụ bộ nhớ quá mức.

**H: Driver GeoJSON có hỗ trợ định nghĩa CRS (Hệ tọa độ) không?**  
Đ: Có—đặt thuộc tính `SpatialReferenceSystem` của layer trước khi thêm các feature nếu bạn cần CRS khác WGS84.

## Kết luận
Bạn đã có một mẫu hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **cách ghi geojson** vào bất kỳ stream .NET nào bằng Aspose.GIS. Dù bạn cần trả GeoJSON từ API web, lưu vào tệp, hoặc chỉ hiển thị trên console, các bước trên đã bao phủ toàn bộ quy trình. Hãy khám phá thêm thư viện để làm việc với các định dạng khác như Shapefile, KML hoặc GML, và tiếp tục xây dựng các ứng dụng không gian địa lý phong phú hơn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-02  
**Được kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

---