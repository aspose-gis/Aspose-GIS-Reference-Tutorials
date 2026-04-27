---
date: 2026-01-13
description: Tìm hiểu cách tạo shapefile mới với Aspose.GIS cho .NET. Hướng dẫn từng
  bước này cho bạn biết cách định nghĩa lớp vector, thêm thuộc tính ngày và quản lý
  dữ liệu không gian.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Tạo Shapefile Mới
url: /vi/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Shapefile Mới

## Giới thiệu
Nếu bạn đang khám phá phát triển hệ thống thông tin địa lý (GIS) với .NET, Aspose.GIS là giải pháp hàng đầu của bạn. Thư viện mạnh mẽ này cho phép các nhà phát triển làm việc liền mạch với dữ liệu không gian, và trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách **tạo shapefile mới** bằng Aspose.GIS cho .NET. Bạn sẽ thấy tại sao việc định nghĩa một lớp vector và thêm thuộc tính ngày là các bước quan trọng cho các dự án GIS vững chắc.

## Câu trả lời nhanh
- **Câu hỏi hướng dẫn này dạy gì?** Cách tạo shapefile mới, định nghĩa lớp vector và thêm các thuộc tính (bao gồm trường ngày).  
- **Thư viện nào cần thiết?** Aspose.GIS cho .NET.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc học; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **IDE nào nên dùng?** Visual Studio (bất kỳ phiên bản mới nào).  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho ví dụ cơ bản.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình C#.
- Visual Studio đã được cài đặt trên máy của bạn.
- Thư viện Aspose.GIS cho .NET. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/gis/net/).

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
Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio và thêm thư viện Aspose.GIS.

## Bước 2: Xác định thư mục tài liệu
```csharp
string dataDir = "Your Document Directory";
```
Thay thế *Your Document Directory* bằng đường dẫn thực tế nơi bạn muốn lưu shapefile mới.

## Bước 3: Tạo VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Đoạn mã này **định nghĩa một lớp vector** và khai báo ba thuộc tính: một trường văn bản (`name`), một trường số nguyên (`age`), và một trường ngày‑giờ (`dob`). Thêm thuộc tính ngày là rất quan trọng cho các phân tích GIS theo thời gian.

## Bước 4: Thêm các đối tượng
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
Ở đây chúng ta tạo hai điểm, đặt từng thuộc tính riêng biệt và thêm các đối tượng vào lớp.

### Trường hợp 2: Đặt giá trị mới cho tất cả các thuộc tính
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Trong cách này chúng ta điền tất cả giá trị thuộc tính trong một lần gọi bằng một mảng đối tượng—rất tiện khi có nhiều thuộc tính.

## Tại sao điều này quan trọng
Tạo shapefile bằng chương trình cho phép bạn tự động hoá các pipeline dữ liệu, tạo bộ dữ liệu kiểm thử, hoặc tích hợp đầu ra GIS trực tiếp vào dịch vụ web. Bằng cách nắm vững **cách tạo shapefile** với Aspose.GIS, bạn sẽ có toàn quyền kiểm soát hình học đối tượng, schema thuộc tính và tuân thủ định dạng file.

## Những lỗi thường gặp & Mẹo
- **Dấu phân tách đường dẫn:** Sử dụng `Path.Combine` để tương thích đa nền tảng thay vì nối chuỗi.  
- **Thứ tự thuộc tính:** Thứ tự các giá trị trong `SetValues` phải khớp với thứ tự bạn đã thêm thuộc tính.  
- **Xử lý ngày:** Luôn sử dụng `DateTimeKind.Utc` nếu dữ liệu GIS của bạn sẽ được chia sẻ qua các múi giờ.

## Kết luận
Chúc mừng! Bạn đã tạo thành công một shapefile mới bằng Aspose.GIS cho .NET. Hướng dẫn này đã bao phủ các kiến thức cơ bản về thiết lập dự án, định nghĩa lớp vector và thêm các đối tượng—bao gồm cả thuộc tính ngày. Khi bạn khám phá sâu hơn, hãy tham khảo [tài liệu](https://reference.aspose.com/gis/net/) để biết các tính năng và chức năng nâng cao.

## Câu hỏi thường gặp
### H: Tôi có thể sử dụng Aspose.GIS với các ngôn ngữ lập trình khác không?
Aspose.GIS chủ yếu hỗ trợ .NET, nhưng cũng có các phiên bản cho Java.

### H: Có bản dùng thử miễn phí không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### H: Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?
Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để nhận hỗ trợ cộng đồng và thảo luận.

### H: Làm sao để tôi có được giấy phép tạm thời?
Nhận giấy phép tạm thời của bạn [tại đây](https://purchase.aspose.com/temporary-license/).

### H: Tôi có thể mua Aspose.GIS cho .NET ở đâu?
Bạn có thể mua thư viện [tại đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-01-13  
**Kiểm tra với:** Aspose.GIS 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}