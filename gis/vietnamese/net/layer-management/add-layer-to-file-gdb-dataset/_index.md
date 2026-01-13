---
date: 2026-01-13
description: Tìm hiểu cách thêm lớp vào bộ dữ liệu File GDB bằng Aspose.GIS, hỗ trợ
  hệ tham chiếu không gian WGS84. Hãy làm theo hướng dẫn từng bước này để thêm lớp
  vào GDB trong .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Tham chiếu không gian WGS84 – Thêm lớp vào GDB bằng Aspose.GIS
url: /vi/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Thêm Lớp vào GDB bằng Aspose.GIS

## Giới thiệu
Sẵn sàng nâng cao quy trình GIS của bạn với Aspose.GIS cho .NET? Trong hướng dẫn này, bạn sẽ học **cách thêm một lớp vào bộ dữ liệu File GDB** khi làm việc với hệ tọa độ **spatial reference wgs84**. Chúng tôi sẽ hướng dẫn từng bước, từ việc chuẩn bị thư mục dữ liệu của bạn đến việc xác thực lớp mới tạo, để bạn có thể bắt đầu thao tác dữ liệu địa lý một cách tự tin.

## Câu trả lời nhanh
- **Hệ tọa độ chính được sử dụng là gì?** spatial reference wgs84 (WGS 84)  
- **Thư viện nào cung cấp API?** Aspose.GIS for .NET  
- **Tôi có cần giấy phép để thử nghiệm không?** Có – một giấy phép tạm thời của Aspose có sẵn.  
- **Tôi có thể thêm thuộc tính vào lớp mới không?** Chắc chắn, bạn có thể định nghĩa bất kỳ số lượng thuộc tính nào cho đối tượng.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Spatial reference wgs84 là gì?
Spatial reference wgs84 (World Geodetic System 1984) là hệ tọa độ địa lý được sử dụng rộng rãi nhất. Nó định nghĩa vĩ độ và kinh độ theo độ và đóng vai trò là CRS mặc định cho nhiều bộ dữ liệu GIS, bao gồm cả bộ dữ liệu chúng ta sẽ tạo trong hướng dẫn này.

## Tại sao nên sử dụng Aspose.GIS để thêm lớp?
- **Không phụ thuộc bên ngoài:** Hoạt động ngay mà không cần cài đặt thêm với mã .NET thuần.  
- **Kiểm soát đầy đủ schema:** Bạn có thể định nghĩa các thuộc tính tùy chỉnh và các loại hình học.  
- **Đa nền tảng:** Tương thích với môi trường Windows, Linux và macOS.  
- **Giấy phép mạnh mẽ:** Giấy phép tạm thời cho phép bạn đánh giá nhanh trước khi quyết định.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Thư viện Aspose.GIS cho .NET: Tải xuống và cài đặt thư viện từ [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Thư mục tài liệu: Tạo một thư mục riêng trên máy của bạn để lưu các tệp GIS.

## Nhập không gian tên
Thêm các câu lệnh `using` cần thiết vào dự án C# của bạn để có thể truy cập các lớp Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Bước 1: Sao chép thư mục
Đầu tiên, sao chép thư mục chứa bộ dữ liệu GDB gốc. Giữ một bản sao bảo vệ dữ liệu nguồn khi bạn thử nghiệm.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Bước 2: Mở bộ dữ liệu và xác minh khả năng tạo lớp
Mở bộ dữ liệu vừa sao chép và xác nhận rằng nó có thể tạo lớp mới. Thuộc tính `CanCreateLayers` phải trả về **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Bước 3: Tạo và điền dữ liệu cho lớp mới với spatial reference wgs84
Bây giờ chúng ta tạo một lớp có tên **data** và đặt rõ ràng spatial reference thành **Wgs84**. Chúng ta cũng thêm một thuộc tính đơn giản có tên **Name** và chèn một đối tượng điểm.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Bước 4: Mở và xác thực lớp đã thêm
Cuối cùng, mở lớp vừa tạo và xác thực nội dung của nó. Console sẽ hiển thị lớp chứa một đối tượng và thuộc tính **Name** khớp với giá trị chúng ta đã đặt.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Các vấn đề thường gặp & Mẹo
- **Đường dẫn không đúng:** Đảm bảo `dataDir` kết thúc bằng ký tự phân tách đường dẫn (`/` hoặc `\`) để các chuỗi nối lại tạo thành đường dẫn hợp lệ.  
- **Lỗi giấy phép:** Nếu bạn thấy cảnh báo giấy phép, áp dụng giấy phép tạm thời từ cổng Aspose trước khi chạy mã.  
- **Không khớp CRS:** Khi mở lớp trong công cụ GIS khác, xác nhận công cụ nhận diện WGS 84 (EPSG:4326) là hệ tọa độ.

## Câu hỏi thường gặp
### Hỏi: Tôi có thể sử dụng Aspose.GIS cho .NET cùng với các thư viện GIS khác không?
Aspose.GIS cho .NET được thiết kế để hoạt động độc lập, nhưng có thể tích hợp với các thư viện khác để tăng cường chức năng.

### Hỏi: Có giấy phép tạm thời để thử nghiệm không?
Có, bạn có thể lấy giấy phép tạm thời từ [đây](https://purchase.aspose.com/temporary-license/) để thử nghiệm và đánh giá.

### Hỏi: Aspose.GIS cho .NET hỗ trợ những hệ tham chiếu không gian nào?
Aspose.GIS cho .NET hỗ trợ một loạt các hệ tham chiếu không gian, cung cấp tính linh hoạt trong việc xử lý dữ liệu địa lý.

### Hỏi: Tôi có thể đóng góp cho cộng đồng Aspose.GIS không?
Chắc chắn! Tham gia thảo luận và chia sẻ kinh nghiệm của bạn trên [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Hỏi: Tôi có thể tìm tài liệu chi tiết cho Aspose.GIS cho .NET ở đâu?
Khám phá tài liệu chi tiết [tại đây](https://reference.aspose.com/gis/net/) để có thông tin sâu về Aspose.GIS cho .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS for .NET (latest stable version)  
**Author:** Aspose