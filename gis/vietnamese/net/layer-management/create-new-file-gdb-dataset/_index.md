---
title: Tạo tập dữ liệu GDB tệp mới
linktitle: Tạo tập dữ liệu GDB tệp mới
second_title: API Aspose.GIS .NET
description: Khám phá Aspose.GIS for .NET để dễ dàng tạo và quản lý bộ dữ liệu GIS. Tải xuống ngay để phát triển không gian địa lý liền mạch. #Aspose #GIS
weight: 10
url: /vi/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tập dữ liệu GDB tệp mới

## Giới thiệu
Trong lĩnh vực phát triển không gian địa lý, Aspose.GIS cho .NET nổi bật như một bộ công cụ mạnh mẽ để quản lý và thao tác dữ liệu Hệ thống thông tin địa lý (GIS). Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu hành trình vào GIS, hướng dẫn này sẽ hướng dẫn bạn qua quy trình tạo tập dữ liệu Cơ sở dữ liệu địa lý tệp (GDB) mới bằng Aspose.GIS cho .NET.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
-  Aspose.GIS for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.GIS for .NET. Bạn có thể tải nó xuống từ[Trang tải xuống Aspose.GIS cho .NET](https://releases.aspose.com/gis/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển của bạn với một IDE tương thích, chẳng hạn như Visual Studio và có hiểu biết cơ bản về lập trình .NET.
- Thư mục tài liệu: Thay thế "Thư mục tài liệu của bạn" trong đoạn mã bằng đường dẫn thích hợp nơi bạn muốn lưu trữ tập dữ liệu GDB của mình.
- Làm quen với C#: Hướng dẫn này giả sử bạn đã quen thuộc với ngôn ngữ lập trình C#.
## Nhập không gian tên
Trong các bước đầu tiên, hãy nhập các vùng tên cần thiết để tận dụng chức năng Aspose.GIS trong ứng dụng .NET của bạn:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Bước 1: Tạo tập dữ liệu GDB tệp mới
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Đầu ra: 0
    // Tiếp tục với các bước tiếp theo...
}
```
 Giải thích: Trong bước này, chúng tôi tạo bộ dữ liệu GDB mới bằng cách sử dụng`Dataset.Create` phương pháp. Chúng tôi chỉ định đường dẫn và trình điều khiển (FileGdb) để tạo Cơ sở dữ liệu địa lý tệp. Đầu ra của bàn điều khiển hiển thị số lớp ban đầu, số này bằng 0 tại thời điểm này.
## Bước 2: Tạo và điền Layer_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Giải thích: Bước này liên quan đến việc tạo một lớp có tên "layer_1" trong tập dữ liệu. Nó định nghĩa một thuộc tính có tên là "giá trị" thuộc loại số nguyên và điền vào lớp đó mười đối tượng, mỗi đối tượng có một dạng hình học điểm.
## Bước 3: Tạo và điền Layer_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Giải thích: Ở đây, chúng tôi tạo lớp thứ hai có tên là "layer_2" và thêm một đối tượng địa lý duy nhất có hình dạng chuỗi đường.
## Bước 4: Kiểm tra số lớp đã cập nhật
```csharp
Console.WriteLine(dataset.LayersCount); // Đầu ra: 2
```
Giải thích: Cuối cùng, chúng tôi kiểm tra số lớp được cập nhật sau khi thêm hai lớp. Trong trường hợp này, đầu ra phải là 2.
## Phần kết luận
Chúc mừng! Bạn đã tạo thành công tập dữ liệu File GDB mới và điền vào đó các lớp bằng Aspose.GIS cho .NET. Hướng dẫn này cung cấp hiểu biết cơ bản về cách làm việc với dữ liệu không gian địa lý trong môi trường .NET.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.GIS cho .NET với các thư viện GIS khác không?
Aspose.GIS for .NET là bộ công cụ độc lập; tuy nhiên, bạn có thể tích hợp nó với các thư viện .NET khác để nâng cao chức năng.
### Câu hỏi: Có diễn đàn cộng đồng nào hỗ trợ Aspose.GIS không?
 Có, bạn có thể tìm thấy sự hỗ trợ và thảo luận trên[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.GIS?
 Tham quan[Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) trang để biết thông tin về việc xin giấy phép tạm thời.
### Hỏi: Có sẵn các ví dụ và tài liệu bổ sung không?
 Khám phá cái[Tài liệu Aspose.GIS](https://reference.aspose.com/gis/net/) để biết thêm ví dụ và thông tin chi tiết.
### Câu hỏi: Tôi có thể mua Aspose.GIS cho .NET ở đâu?
 Bạn có thể mua Aspose.GIS cho .NET trên[trang mua hàng](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
