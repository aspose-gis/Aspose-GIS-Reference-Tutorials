---
title: Tạo tệp GDB với một lớp
linktitle: Tạo tệp GDB với một lớp
second_title: API Aspose.GIS .NET
description: Mở khóa tiềm năng quản lý dữ liệu không gian địa lý trong .NET với Aspose.GIS. Tìm hiểu cách tạo Cơ sở dữ liệu địa lý tệp và các lớp theo từng bước. Tải ngay!
type: docs
weight: 11
url: /vi/net/layer-management/create-file-gdb-with-single-layer/
---
## Giới thiệu
Bạn đã sẵn sàng nâng cao các ứng dụng không gian địa lý của mình bằng các cơ sở dữ liệu và lớp tệp địa lý mạnh mẽ chưa? Không cần tìm đâu xa ngoài Aspose.GIS cho .NET. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Cơ sở dữ liệu địa lý tệp (GDB) với một lớp duy nhất bằng cách sử dụng Aspose.GIS cho .NET. Khai thác sức mạnh của việc quản lý và trực quan hóa dữ liệu không gian trong các ứng dụng .NET của bạn một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1.  Aspose.GIS for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.GIS. Bạn có thể tải nó xuống từ[Trang tải xuống Aspose.GIS cho .NET](https://releases.aspose.com/gis/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển .NET hoạt động trên máy của bạn.
3. Thư mục Tài liệu: Chọn hoặc tạo một thư mục trên hệ thống nơi bạn sẽ lưu trữ các tệp dữ liệu không gian địa lý của mình.
## Nhập không gian tên
Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án .NET của mình. Các không gian tên này sẽ cung cấp quyền truy cập vào các chức năng của Aspose.GIS. Thêm các dòng sau vào đầu tệp mã của bạn:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Bước 1: Thiết lập thư mục tài liệu của bạn
```csharp
string dataDir = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục mà bạn muốn lưu trữ các tệp dữ liệu không gian địa lý của mình.
## Bước 2: Tạo cơ sở dữ liệu địa lý tệp với một lớp
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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
Đoạn mã này tạo Cơ sở dữ liệu địa lý tệp với một lớp duy nhất và thêm tính năng dòng vào đó.
## Bước 3: Mở cơ sở dữ liệu địa lý tệp và truy xuất thông tin lớp
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Đầu ra: Số lượng tính năng: 1
}
```
Trong bước này, chúng tôi mở Cơ sở dữ liệu địa lý tệp đã tạo, truy xuất lớp có tên là "lớp" và in số lượng đối tượng địa lý trong lớp.
## Phần kết luận
Chúc mừng! Bạn đã tạo thành công Cơ sở dữ liệu địa lý tệp với một lớp duy nhất bằng Aspose.GIS cho .NET. Khám phá khả năng quản lý dữ liệu không gian rộng lớn trong ứng dụng của bạn một cách dễ dàng.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.GIS cho .NET trong các dự án .NET hiện tại của mình không?
Có, Aspose.GIS cho .NET có thể được tích hợp liền mạch vào các dự án .NET hiện có của bạn.
### Có phiên bản dùng thử cho Aspose.GIS cho .NET không?
 Có, bạn có thể khám phá các tính năng của Aspose.GIS cho .NET bằng cách tải xuống[phiên bản dùng thử miễn phí](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu chi tiết về Aspose.GIS cho .NET ở đâu?
 Tham khảo đến[tài liệu](https://reference.aspose.com/gis/net/) để biết thông tin toàn diện về Aspose.GIS cho .NET.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.GIS cho .NET?
 Tham quan[Diễn đàn Aspose.GIS](https://forum.aspose.com/c/gis/33) để được cộng đồng hỗ trợ và giúp đỡ.
### Giấy phép tạm thời có sẵn cho Aspose.GIS cho .NET không?
 Có, bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) cho Aspose.GIS cho .NET.