---
title: Chuyển đổi GeoJSON sang tệp GDB được làm sáng tỏ
linktitle: Chuyển đổi lớp GeoJSON thành tệp GDB
second_title: API Aspose.GIS .NET
description: Mở khóa những kỳ quan không gian địa lý với Aspose.GIS cho .NET! Dễ dàng chuyển đổi các lớp GeoJSON thành Cơ sở dữ liệu địa lý tệp. Thử ngay bây giờ! #Aspose #GIS
type: docs
weight: 17
url: /vi/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## Giới thiệu
Trong lĩnh vực năng động của Hệ thống thông tin địa lý (GIS), khả năng chuyển đổi liền mạch dữ liệu giữa các định dạng khác nhau là rất quan trọng. Aspose.GIS cho .NET nổi lên như một đồng minh mạnh mẽ, cung cấp một bộ công cụ toàn diện để xử lý dữ liệu không gian địa lý một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình chuyển đổi lớp GeoJSON thành Cơ sở dữ liệu địa lý tệp (Tệp GDB) bằng Aspose.GIS cho .NET.
## Điều kiện tiên quyết
Trước khi bắt tay vào hành trình không gian địa lý này, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức làm việc về lập trình .NET.
-  Aspose.GIS cho .NET được cài đặt. Nếu không, hãy tải xuống từ[đây](https://releases.aspose.com/gis/net/) và làm theo hướng dẫn cài đặt.
## Nhập không gian tên
Để bắt đầu quá trình chuyển đổi, hãy bắt đầu bằng cách nhập các vùng tên cần thiết:
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
Bây giờ, hãy chia nhỏ quy trình thành hướng dẫn từng bước:
## Bước 1: Thiết lập lớp GeoJSON
Bắt đầu bằng cách tạo lớp GeoJSON với các thuộc tính và tính năng có liên quan. Đây là một đoạn để hướng dẫn bạn:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Thêm thuộc tính
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Xây dựng và thêm tính năng
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Bước 2: Sao chép tập dữ liệu thử nghiệm
Để duy trì tính toàn vẹn của dữ liệu thử nghiệm của bạn, hãy tạo một bản sao của tập dữ liệu. Sử dụng đoạn mã sau:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Bước 3: Chuyển đổi GeoJSON sang tệp GDB
Bây giờ là lúc thực hiện chuyển đổi. Sử dụng đoạn mã sau:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Sao chép thuộc tính
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Thêm các tính năng
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã điều hướng địa hình hấp dẫn khi chuyển đổi lớp GeoJSON thành Cơ sở dữ liệu địa lý tệp bằng cách sử dụng Aspose.GIS cho .NET. Được trang bị kiến thức này, giờ đây bạn đã được trang bị để thao tác liền mạch dữ liệu không gian địa lý trong các ứng dụng .NET của mình.
## Câu hỏi thường gặp
### Aspose.GIS có tương thích với .NET framework mới nhất không?
Có, Aspose.GIS tương thích với các phiên bản .NET framework mới nhất.
### Tôi có thể chuyển đổi các định dạng không gian địa lý khác bằng Aspose.GIS không?
Tuyệt đối! Aspose.GIS hỗ trợ một loạt các định dạng không gian địa lý để thao tác dữ liệu linh hoạt.
### Có phiên bản dùng thử cho Aspose.GIS không?
 Có, bạn có thể khám phá các chức năng của Aspose.GIS bằng cách tải xuống phiên bản dùng thử[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được hỗ trợ cho các truy vấn liên quan đến Aspose.GIS?
 Đi tới Aspose.GIS[diễn đàn](https://forum.aspose.com/c/gis/33) để được hỗ trợ tận tình.
### Tôi có thể xin giấy phép tạm thời cho Aspose.GIS không?
 Có, bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).