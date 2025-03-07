---
title: Làm chủ GIS - Thêm lớp vào GDB với Aspose.GIS cho .NET
linktitle: Thêm lớp vào tập dữ liệu GDB
second_title: API Aspose.GIS .NET
description: Khai phá sức mạnh của GIS với Aspose.GIS cho .NET! Tìm hiểu cách thêm lớp vào bộ dữ liệu File GDB trong hướng dẫn từng bước này. #dữ liệu địa lý #Aspose #GIS
weight: 16
url: /vi/net/layer-management/add-layer-to-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm chủ GIS - Thêm lớp vào GDB với Aspose.GIS cho .NET

## Giới thiệu
Bạn đã sẵn sàng nâng cao khả năng GIS của mình bằng Aspose.GIS cho .NET chưa? Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình thêm lớp vào tập dữ liệu Cơ sở dữ liệu địa lý tệp (GDB). Aspose.GIS cho .NET cung cấp các tính năng mạnh mẽ để thao tác thông tin địa lý và với hướng dẫn này, bạn sẽ có thể tích hợp liền mạch các lớp bổ sung vào tập dữ liệu của mình.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.GIS for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.GIS cho tài liệu .NET](https://reference.aspose.com/gis/net/).
- Thư mục Tài liệu: Tạo một thư mục tài liệu chuyên dụng trên máy của bạn để lưu trữ và quản lý các tệp liên quan đến GIS.
## Nhập không gian tên
Trong dự án .NET của bạn, hãy đảm bảo nhập các vùng tên cần thiết để truy cập các chức năng của Aspose.GIS. Sử dụng đoạn mã sau:
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
Trước khi tiếp tục, hãy sao chép thư mục chứa tập dữ liệu GDB của bạn. Bước này đảm bảo tập dữ liệu gốc vẫn còn nguyên. Sử dụng đoạn mã được cung cấp:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Bước 2: Mở bộ dữ liệu và kiểm tra khả năng tạo
 Mở tập dữ liệu trùng lặp và kiểm tra xem nó có thể tạo lớp hay không. Điều này được khẳng định bởi sự có mặt của`True` trong đầu ra giao diện điều khiển.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // ĐÚNG VẬY
```
## Bước 3: Tạo và điền một lớp mới
Tạo một lớp mới trong tập dữ liệu, xác định hệ thống tham chiếu không gian, các thuộc tính và đối tượng mẫu của nó. Đoạn mã này thể hiện quá trình:
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
Mở lớp bạn vừa tạo và xác thực nội dung của nó. Kiểm tra số lượng và truy xuất các giá trị thuộc tính bằng mã sau:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Tên_1"
}
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm lớp vào tập dữ liệu File GDB bằng Aspose.GIS cho .NET. Với những kỹ năng mới này, bạn có thể thao tác hiệu quả dữ liệu địa lý trong các dự án GIS của mình.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.GIS cho .NET với các thư viện GIS khác không?
Aspose.GIS cho .NET được thiết kế để hoạt động độc lập nhưng nó có thể được tích hợp với các thư viện khác để nâng cao chức năng.
### Hỏi: Giấy phép tạm thời có sẵn cho mục đích thử nghiệm không?
 Có, bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/) để kiểm tra và đánh giá.
### Câu hỏi: Aspose.GIS cho .NET hỗ trợ những hệ thống tham chiếu không gian nào?
Aspose.GIS for .NET hỗ trợ nhiều hệ thống tham chiếu không gian, mang lại sự linh hoạt trong việc xử lý dữ liệu địa lý.
### Câu hỏi: Tôi có thể đóng góp cho cộng đồng Aspose.GIS không?
 Tuyệt đối! Tham gia thảo luận và chia sẻ kinh nghiệm của bạn về[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về Aspose.GIS cho .NET ở đâu?
 Khám phá tài liệu toàn diện[đây](https://reference.aspose.com/gis/net/) để biết thông tin chuyên sâu về Aspose.GIS cho .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
