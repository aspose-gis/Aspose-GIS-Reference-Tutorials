---
title: GeoJSON에서 파일 GDB로의 변환에 대한 이해
linktitle: GeoJSON 레이어를 파일 GDB로 변환
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS로 지리공간의 경이로움을 느껴보세요! GeoJSON 레이어를 파일 지리 데이터베이스로 쉽게 변환하세요. 지금 사용해 보세요! #Aspose #GIS
type: docs
weight: 17
url: /ko/net/layer-management/convert-geojson-layer-to-file-gdb/
---
## 소개
지리 정보 시스템(GIS)의 동적 영역에서는 다양한 형식 간에 데이터를 원활하게 변환하는 기능이 중요합니다. Aspose.GIS for .NET은 지리공간 데이터를 쉽게 처리할 수 있는 포괄적인 도구 모음을 제공하는 강력한 동맹으로 등장합니다. 이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 GeoJSON 레이어를 파일 지리 데이터베이스(File GDB)로 변환하는 프로세스를 자세히 살펴보겠습니다.
## 전제조건
이 지리공간적 여정을 시작하기 전에 다음 전제조건이 갖추어져 있는지 확인하십시오.
- .NET 프로그래밍에 대한 실무 지식.
-  .NET용 Aspose.GIS가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드하십시오.[여기](https://releases.aspose.com/gis/net/) 설치 지침을 따르십시오.
## 네임스페이스 가져오기
변환 프로세스를 시작하려면 필요한 네임스페이스를 가져오는 것부터 시작하세요.
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
이제 프로세스를 단계별 가이드로 나누어 보겠습니다.
## 1단계: GeoJSON 레이어 설정
관련 속성과 기능이 포함된 GeoJSON 레이어를 생성하는 것부터 시작하세요. 다음은 안내하는 스니펫입니다.
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // 속성 추가
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //기능 구성 및 추가
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
## 2단계: 테스트 데이터 세트 복사
테스트 데이터의 무결성을 유지하려면 데이터세트의 복사본을 만드세요. 다음 코드 조각을 사용하세요.
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## 3단계: GeoJSON을 파일 GDB로 변환
이제 변환을 수행할 차례입니다. 다음 코드를 활용하세요:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // 속성 복사
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // 기능 추가
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## 결론
이 튜토리얼에서는 .NET용 Aspose.GIS를 사용하여 GeoJSON 레이어를 파일 지리 데이터베이스로 변환하는 흥미로운 지형을 탐색했습니다. 이러한 지식을 갖추고 있으면 이제 .NET 애플리케이션에서 지리공간 데이터를 원활하게 조작할 수 있습니다.
## 자주 묻는 질문
### Aspose.GIS는 최신 .NET 프레임워크와 호환됩니까?
예, Aspose.GIS는 최신 .NET 프레임워크 버전과 호환됩니다.
### Aspose.GIS를 사용하여 다른 지리공간 형식을 변환할 수 있나요?
전적으로! Aspose.GIS는 다양한 데이터 조작을 위해 다양한 지리공간 형식을 지원합니다.
### Aspose.GIS에 사용할 수 있는 평가판이 있습니까?
 예, 평가판을 다운로드하여 Aspose.GIS의 기능을 탐색할 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.GIS 관련 쿼리에 대한 지원을 어떻게 받을 수 있나요?
 Aspose.GIS로 이동하세요.[법정](https://forum.aspose.com/c/gis/33) 전담 지원을 위해.
### Aspose.GIS에 대한 임시 라이선스를 얻을 수 있나요?
 예, 임시 라이센스를 확보할 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).