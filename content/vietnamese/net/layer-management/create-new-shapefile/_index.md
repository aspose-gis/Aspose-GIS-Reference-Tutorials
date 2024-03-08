---
title: Tạo Shapefile mới
linktitle: Tạo Shapefile mới
second_title: API Aspose.GIS .NET
description: Tìm hiểu cách tạo một tệp hình dạng mới bằng Aspose.GIS cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi và khám phá sức mạnh của thao tác dữ liệu không gian.
type: docs
weight: 12
url: /vi/net/layer-management/create-new-shapefile/
---
## Giới thiệu
Nếu bạn đang nghiên cứu phát triển hệ thống thông tin địa lý (GIS) bằng .NET, Aspose.GIS là giải pháp phù hợp cho bạn. Thư viện mạnh mẽ này trao quyền cho các nhà phát triển làm việc liền mạch với dữ liệu không gian và trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo một tệp hình dạng mới bằng Aspose.GIS cho .NET.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
- Visual Studio được cài đặt trên máy của bạn.
-  Aspose.GIS cho thư viện .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/gis/net/).
## Nhập không gian tên
Bắt đầu bằng cách nhập các không gian tên cần thiết để tận dụng chức năng của Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio và bao gồm thư viện Aspose.GIS.
## Bước 2: Xác định thư mục tài liệu
```csharp
string dataDir = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế nơi bạn muốn lưu tệp hình dạng mới của mình.
## Bước 3: Tạo VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //thêm thuộc tính trước khi thêm tính năng
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Đoạn mã này thiết lập lớp vectơ và xác định các thuộc tính cho các đối tượng địa lý của bạn.
## Bước 4: Thêm tính năng
### Trường hợp 1: Đặt giá trị riêng lẻ
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Trường hợp 2: Đặt giá trị mới cho tất cả thuộc tính
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Phần kết luận
 Chúc mừng! Bạn đã tạo thành công một tệp hình dạng mới bằng Aspose.GIS cho .NET. Hướng dẫn này đề cập đến những điều cơ bản về thiết lập dự án của bạn, xác định các thuộc tính và thêm các tính năng. Khi bạn khám phá thêm, hãy tham khảo[tài liệu](https://reference.aspose.com/gis/net/) cho các tính năng và chức năng nâng cao.
## Các câu hỏi thường gặp
### Câu hỏi: Tôi có thể sử dụng Aspose.GIS với các ngôn ngữ lập trình khác không?
Aspose.GIS chủ yếu hỗ trợ .NET, nhưng cũng có phiên bản dành cho Java.
### Hỏi: Có bản dùng thử miễn phí không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
 Tham quan[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được cộng đồng hỗ trợ và thảo luận.
### Hỏi: Làm thế nào tôi có thể xin được giấy phép tạm thời?
 Nhận giấy phép tạm thời của bạn[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Tôi có thể mua Aspose.GIS cho .NET ở đâu?
 Bạn có thể mua thư viện[đây](https://purchase.aspose.com/buy).