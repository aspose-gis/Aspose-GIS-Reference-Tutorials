---
title: Nhận giá trị thuộc tính tính năng (Mặc định)
linktitle: Nhận giá trị thuộc tính tính năng (Mặc định)
second_title: API Aspose.GIS .NET
description: Mở khóa sức mạnh của Aspose.GIS cho .NET! Truy xuất và thao tác các giá trị thuộc tính đối tượng một cách dễ dàng bằng hướng dẫn từng bước này. Tải xuống bản dùng thử của bạn ngay bây giờ!
weight: 14
url: /vi/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nhận giá trị thuộc tính tính năng (Mặc định)

## Giới thiệu
Chào mừng đến với thế giới của Aspose.GIS cho .NET! Trong hướng dẫn toàn diện này, chúng ta sẽ đi sâu vào những điểm phức tạp của việc truy xuất các giá trị thuộc tính đối tượng bằng cách sử dụng các khả năng mạnh mẽ của Aspose.GIS. Cho dù bạn là nhà phát triển dày dạn hay chỉ mới bắt đầu, hướng dẫn này sẽ cung cấp cho bạn hướng dẫn từng bước, đảm bảo bạn khai thác toàn bộ tiềm năng của công cụ đáng chú ý này.
## Điều kiện tiên quyết
Trước khi chúng ta bắt tay vào cuộc phiêu lưu viết mã này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về C# và .NET framework.
-  Aspose.GIS cho .NET được cài đặt. Nếu không, hãy tải xuống từ[đây](https://releases.aspose.com/gis/net/).
- Một trình soạn thảo mã, chẳng hạn như Visual Studio, để theo dõi một cách liền mạch.
## Nhập không gian tên
Trong dự án C# của bạn, hãy đảm bảo bao gồm các không gian tên cần thiết:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Bây giờ, hãy chia nhỏ từng ví dụ thành một loạt các bước dễ thực hiện.
## Nhận giá trị thuộc tính tính năng (Mặc định)
### Bước 1: Thiết lập môi trường
Bắt đầu bằng cách xác định đường dẫn đến thư mục tài liệu của bạn:
```csharp
string dataDir = "Your Document Directory";
```
### Bước 2: Tạo lớp GeoJson
Tạo lớp GeoJson và xác định thuộc tính với các giá trị mặc định:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Bước 3: Xây dựng một tính năng
Xây dựng một tính năng bằng cách sử dụng thuộc tính được xác định:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Bước 4: Truy xuất giá trị
Truy xuất các giá trị thuộc tính với nhiều tình huống khác nhau:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // giá trị == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // giá trị == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // giá trị == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Đặt giá trị mặc định
### Bước 1: Tạo một lớp GeoJson khác
Lặp lại quy trình với lớp GeoJson khác và thuộc tính kép:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Bước 2: Xây dựng một tính năng (Lại)
```csharp
    Feature feature = layer.ConstructFeature();
```
### Bước 3: Truy xuất và đặt giá trị
Truy xuất và đặt các giá trị thuộc tính, hiển thị các giá trị mặc định:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // giá trị == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // giá trị == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // giá trị == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Chúc mừng! Bạn đã khai thác thành công sức mạnh của Aspose.GIS cho .NET trong việc truy xuất và thao tác các giá trị thuộc tính đối tượng.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá các sắc thái của việc truy xuất các giá trị thuộc tính đối tượng bằng Aspose.GIS cho .NET. Với API trực quan và khả năng mạnh mẽ, Aspose.GIS mở ra một thế giới khả năng phát triển GIS trong môi trường .NET.
## Các câu hỏi thường gặp
### Aspose.GIS có tương thích với .NET Core không?
Có, Aspose.GIS hoàn toàn tương thích với .NET Core, cung cấp hỗ trợ đa nền tảng.
### Tôi có thể sử dụng Aspose.GIS cho các dự án thương mại không?
Tuyệt đối! Aspose.GIS đi kèm với giấy phép thương mại cho phép bạn sử dụng nó trong các ứng dụng thương mại của mình mà không có bất kỳ hạn chế nào.
### Tôi có thể tìm thêm sự hỗ trợ và nguồn lực ở đâu?
 Tham quan[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được hỗ trợ cộng đồng và khám phá[tài liệu](https://reference.aspose.com/gis/net/) để biết thông tin chuyên sâu.
### Có bản dùng thử miễn phí không?
 Có, bạn có thể khám phá Aspose.GIS với bản dùng thử miễn phí. Tải xuống[đây](https://releases.aspose.com/).
### Làm cách nào để có được giấy phép tạm thời cho mục đích thử nghiệm?
 Để có giấy phép tạm thời, hãy truy cập[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
