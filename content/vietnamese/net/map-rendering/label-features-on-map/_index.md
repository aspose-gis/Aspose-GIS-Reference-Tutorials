---
title: Nắm vững việc ghi nhãn tính năng với Aspose.GIS cho .NET
linktitle: Đặc điểm nhãn trên bản đồ
second_title: API Aspose.GIS .NET
description: Khám phá Aspose.GIS cho .NET và nắm vững nghệ thuật ghi nhãn đối tượng trên bản đồ. Nâng cao trực quan hóa không gian địa lý của bạn một cách dễ dàng. #Aspose #GIS
type: docs
weight: 11
url: /vi/net/map-rendering/label-features-on-map/
---
## Giới thiệu
Trong thế giới trực quan hóa dữ liệu không gian địa lý, các tính năng ghi nhãn trên bản đồ đóng một vai trò quan trọng trong việc truyền tải thông tin một cách hiệu quả. Aspose.GIS for .NET cung cấp một bộ công cụ mạnh mẽ để đạt được điều này một cách liền mạch. Trong hướng dẫn này, chúng ta sẽ khám phá các phương pháp ghi nhãn điểm khác nhau trên bản đồ bằng Aspose.GIS, nâng cao khả năng trực quan hóa bản đồ của bạn bằng các nhãn thông tin.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về C# và .NET framework.
-  Aspose.GIS cho .NET được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/gis/net/).
- Tệp GeoJSON chứa dữ liệu điểm. Nếu không có, bạn có thể sử dụng tệp mẫu để kiểm tra.
## Nhập không gian tên
Trong mã C# của bạn, hãy đảm bảo bạn nhập các vùng tên cần thiết để làm việc với Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Bây giờ, hãy chia mỗi ví dụ thành nhiều bước theo định dạng hướng dẫn từng bước.
##  Ghi nhãn điểm

### Bước 1: Đặt đường dẫn đến thư mục tài liệu của bạn:
```csharp
string dataDir = "Your Document Directory";
```
### Bước 2: Tạo bản đồ với ký hiệu điểm đánh dấu đơn giản:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Thêm một lớp vectơ và áp dụng nhãn
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Hiển thị bản đồ thành tệp SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Ghi nhãn điểm theo kiểu

Thực hiện theo bước 1 và 2 từ ví dụ trước.

### Bước 1: Tùy chỉnh kiểu ghi nhãn:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Các bước còn lại giữ nguyên
```
## Ghi nhãn điểm đã đặt

Thực hiện theo bước 1 và 2 từ ví dụ đầu tiên.
### Bước 2: Tùy chỉnh vị trí nhãn:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Các bước còn lại giữ nguyên
```
## Dựa trên tính năng ghi nhãn điểm

Thực hiện theo bước 1 và 2 từ ví dụ đầu tiên.

### Bước 1: Thực hiện ghi nhãn dựa trên tính năng:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Truy xuất dân số từ đối tượng địa lý.
        var population = feature.GetValue<int>("population");
        // Kích thước phông chữ được tính toán và dựa trên dân số.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Mức độ ưu tiên của nhãn cũng dựa trên dân số.
        // Mức độ ưu tiên càng lớn thì khả năng xuất hiện nhãn trên ảnh đầu ra càng cao.
        labeling.Priority = population;
    }
};
// Các bước còn lại giữ nguyên
```
## Phần kết luận
Chúc mừng! Bạn đã học cách nâng cao khả năng trực quan hóa bản đồ của mình bằng cách gắn nhãn cho các tính năng bằng Aspose.GIS cho .NET. Thử nghiệm với các kiểu và vị trí khác nhau để tạo bản đồ hấp dẫn phù hợp với dữ liệu của bạn.
## Câu hỏi thường gặp
### Tôi có thể gắn nhãn các tính năng bằng phông chữ tùy chỉnh không?
Có, bạn có thể tùy chỉnh kiểu và kích thước phông chữ trong cấu hình ghi nhãn.
### Aspose.GIS có tương thích với các định dạng dữ liệu GIS khác không?
Aspose.GIS hỗ trợ nhiều định dạng không gian địa lý khác nhau, bao gồm GeoJSON, Shapefile, v.v.
### Làm cách nào tôi có thể xử lý các tập dữ liệu lớn để ghi nhãn?
Aspose.GIS được tối ưu hóa về hiệu suất, nhưng hãy cân nhắc sử dụng cấu hình dựa trên tính năng để ưu tiên các nhãn dựa trên thuộc tính dữ liệu.
### Có sẵn các tùy chọn vị trí nhãn nâng cao không?
Có, bạn có thể tinh chỉnh vị trí nhãn bằng cách sử dụng các tùy chọn như xoay, điểm neo và khoảng cách.
### Tôi có thể tự động tạo nhãn theo quy trình hàng loạt không?
Hoàn toàn có thể, bạn có thể tích hợp Aspose.GIS vào quy trình làm việc tự động của mình để tạo nhãn hàng loạt.