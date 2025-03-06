---
title: 개체 ID 및 형상 필드 이름 지정
linktitle: 개체 ID 및 형상 필드 이름 지정
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS로 GIS의 마법을 탐험해보세요! 지리공간 데이터를 손쉽게 관리하세요. 지금 다운로드하여 공간 지능의 힘을 발휘해보세요.
weight: 20
url: /ko/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 개체 ID 및 형상 필드 이름 지정

## 소개
.NET용 Aspose.GIS를 사용하여 지리 정보 시스템(GIS) 영역으로의 여행을 시작하면 개발자와 애호가 모두에게 가능성의 세계가 열립니다. 이 강력한 라이브러리를 사용하면 지리공간 데이터를 쉽게 처리할 수 있습니다. 이 튜토리얼에서는 객체 ID 및 기하학 필드 이름을 지정하는 과정을 안내하여 GIS 작업의 기초를 마련합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.GIS: 다음에서 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/gis/net/).
- 문서 디렉터리: 지오데이터베이스를 저장할 문서 디렉터리를 설정합니다.
- .NET 환경: 작동하는 .NET 환경이 있는지 확인하세요.
## 네임스페이스 가져오기
작업을 시작하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이러한 네임스페이스는 .NET용 Aspose.GIS와 상호 작용하기 위한 필수 클래스와 메서드를 제공합니다.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## 1단계: 개체 ID 및 형상 필드 이름 지정
이 단계에서는 GIS 데이터에 대한 객체 ID 및 기하학 필드 이름을 설정하는 방법을 배우게 됩니다. 이는 효율적인 데이터 관리에 매우 중요합니다.
## 1.1단계: 문서 디렉터리 설정
문서 디렉터리의 경로를 정의하는 것부터 시작하세요.
```csharp
string dataDir = "Your Document Directory";
```
## 1.2단계: 지리 데이터베이스 생성 및 옵션 정의
지정된 개체 ID 및 도형 필드 이름을 사용하여 GeoDatabase를 만듭니다.
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // 개체 ID 필드 이름 지정
        GeometryFieldName = "POINT",       // 기하학 필드 이름 지정
    };
```
## 1.3단계: 레이어 생성 및 추가
GeoDatabase 내에 레이어를 생성하고 특정 지오메트리가 포함된 기능을 추가합니다.
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //형상을 지정합니다(이 경우 점).
    layer.Add(feature);
}
```
## 1.4단계: 레이어에서 데이터 열기 및 검색
레이어를 열고 지정된 개체 ID를 기반으로 데이터를 검색합니다.
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // 출력: 1
}
```
## 결론
축하해요! Aspose.GIS for .NET을 사용하여 객체 ID 및 기하학 필드 이름을 지정하는 프로세스를 성공적으로 탐색했습니다. 이는 GIS 프로젝트를 위한 견고한 기반을 마련하여 지리공간 데이터를 쉽게 관리할 수 있게 해줍니다.
## 자주 묻는 질문
### Q: 내 웹 애플리케이션에서 .NET용 Aspose.GIS를 사용할 수 있습니까?
A: 예, Aspose.GIS for .NET은 데스크톱과 웹 애플리케이션 모두에 적합하며 다양한 지리공간 기능을 제공합니다.
### Q: 구매하기 전에 체험판을 사용할 수 있나요?
 A: 예, 무료 평가판을 통해 .NET용 Aspose.GIS의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: .NET용 Aspose.GIS의 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 임시 면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 평가 목적으로.
### Q: Aspose.GIS for .NET은 어떤 공간 참조 시스템을 지원합니까?
A: Aspose.GIS for .NET은 다양한 공간 참조 시스템을 지원하여 다양한 지리적 데이터세트에 대한 유연성을 제공합니다.
### Q: Aspose.GIS 관련 쿼리에 대해 도움을 구하거나 논의할 수 있는 곳은 어디입니까?
 A: Aspose.GIS 포럼을 방문하세요.[여기](https://forum.aspose.com/c/gis/33) 지원과 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
