---
date: 2026-06-30
description: Tìm hiểu cách tạo shapefile bằng Aspose.GIS cho .NET. Hướng dẫn từng
  bước này cho bạn biết cách định nghĩa vector layer, thêm date attribute, và quản
  lý spatial data một cách hiệu quả.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Tạo Shapefile mới
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Cách tạo Shapefile với Aspose.GIS cho .NET
url: /vi/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Shapefile Mới

## Giới thiệu
Nếu bạn đang khám phá phát triển hệ thống thông tin địa lý (GIS) với .NET, Aspose.GIS là giải pháp hàng đầu của bạn để **cách tạo shapefile** một cách lập trình. Thư viện này cho phép bạn kiểm soát hoàn toàn các lớp vector, lược đồ thuộc tính và tuân thủ định dạng tệp, vì vậy bạn có thể tự động hoá các quy trình dữ liệu hoặc tạo bộ dữ liệu thử nghiệm trong vài phút.

## Câu trả lời nhanh
- **Mục tiêu của hướng dẫn này là gì?** Cách tạo một shapefile mới, định nghĩa một lớp vector và thêm các thuộc tính (bao gồm một trường ngày).  
- **Thư viện nào được yêu cầu?** Aspose.GIS cho .NET.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc học; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **IDE nào nên dùng?** Visual Studio (bất kỳ phiên bản mới nào).  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho ví dụ cơ bản.

## Cách tạo shapefile với Aspose.GIS cho .NET?
Tải thư viện Aspose.GIS, đặt thư mục đầu ra, tạo một `VectorLayer`, định nghĩa các thuộc tính và thêm các đối tượng—toàn bộ quy trình này có thể được viết trong dưới 30 dòng C#. Thư viện tự động xử lý việc tạo hình học, kiểu dữ liệu thuộc tính và ghi tệp, vì vậy bạn không cần quản lý các thông số kỹ thuật cấp thấp của Shapefile.

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
Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio và bao gồm thư viện Aspose.GIS.

## Bước 2: Xác định thư mục tài liệu
```csharp
string dataDir = "Your Document Directory";
```
Thay thế *Your Document Directory* bằng đường dẫn thực tế nơi bạn muốn lưu shapefile mới của mình.

## Bước 3: Tạo VectorLayer
Lớp `VectorLayer` đại diện cho một lớp shapefile duy nhất lưu trữ dữ liệu hình học và thuộc tính.  
Trong bước này chúng ta định nghĩa một lớp vector và khai báo ba thuộc tính: một trường văn bản (`name`), một trường số nguyên (`age`), và một trường ngày‑giờ (`dob`). Thêm thuộc tính ngày là rất quan trọng cho các phân tích **shapefile GIS thời gian**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Bước 4: Thêm đối tượng
### Trường hợp 1: Đặt giá trị riêng lẻ
Phương thức `SetValues` gán các giá trị thuộc tính cho một đối tượng theo thứ tự chúng được định nghĩa.  
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
Ở đây chúng ta tạo hai điểm, đặt mỗi thuộc tính riêng biệt và thêm các đối tượng vào lớp.

### Trường hợp 2: Đặt giá trị mới cho tất cả thuộc tính
Ngoài ra, bạn có thể cung cấp tất cả các giá trị thuộc tính cùng một lúc bằng cách sử dụng `SetValues` với một mảng đối tượng.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Trong cách tiếp cận này chúng ta điền tất cả các giá trị thuộc tính trong một lần gọi bằng mảng đối tượng—rất tiện khi bạn có nhiều thuộc tính.

## Tại sao điều này quan trọng?
Việc tạo shapefile một cách lập trình cho phép bạn tự động hoá các quy trình dữ liệu, tạo bộ dữ liệu thử nghiệm, hoặc nhúng kết quả GIS trực tiếp vào các dịch vụ web. Aspose.GIS hỗ trợ **hơn 30 định dạng vector và raster** và có thể ghi các shapefile hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, mang lại tốc độ và khả năng mở rộng.

## Những lỗi thường gặp & Mẹo
- **Dấu phân tách đường dẫn:** Sử dụng `Path.Combine` để tương thích đa nền tảng thay vì nối chuỗi.  
- **Thứ tự thuộc tính:** Thứ tự các giá trị trong `SetValues` phải khớp với thứ tự bạn đã thêm các thuộc tính.  
- **Xử lý ngày:** Luôn sử dụng `DateTimeKind.Utc` nếu dữ liệu GIS của bạn sẽ được chia sẻ qua các múi giờ.

## Kết luận
Chúc mừng! Bạn đã tạo thành công một shapefile mới bằng Aspose.GIS cho .NET. Hướng dẫn này đã bao phủ các kiến thức cơ bản về thiết lập dự án, định nghĩa lớp vector và thêm các đối tượng—bao gồm cả thuộc tính ngày. Khi bạn khám phá sâu hơn, hãy tham khảo [tài liệu](https://reference.aspose.com/gis/net/) để biết các tính năng và chức năng nâng cao.

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng Aspose.GIS với các ngôn ngữ lập trình khác không?**  
A: Aspose.GIS chủ yếu hỗ trợ .NET, nhưng cũng có các phiên bản cho Java.

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm hỗ trợ cho Aspose.GIS ở đâu?**  
A: Truy cập [diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được cộng đồng hỗ trợ và thảo luận.

**Q: Làm sao tôi có thể nhận giấy phép tạm thời?**  
A: Nhận giấy phép tạm thời của bạn [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể mua Aspose.GIS cho .NET ở đâu?**  
A: Bạn có thể mua thư viện [tại đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-06-30  
**Kiểm tra với:** Aspose.GIS 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Lấy Thuộc tính Lớp – Truy xuất Thông tin Thuộc tính Lớp với Aspose.GIS cho .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Tạo Lớp Vector và Đặt Hệ thống Tham chiếu Không gian cho Lớp](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Tạo Lớp Vector trong File GDB – Hướng dẫn Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}