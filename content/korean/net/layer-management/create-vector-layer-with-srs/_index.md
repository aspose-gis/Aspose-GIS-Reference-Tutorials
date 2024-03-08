---
title: SRS를 사용하여 벡터 레이어 만들기
linktitle: SRS를 사용하여 벡터 레이어 만들기
second_title: Aspose.GIS .NET API
description: 원활한 GIS 통합의 핵심인 .NET용 Aspose.GIS를 살펴보세요. 지정된 공간 참조 시스템을 사용하여 벡터 레이어를 쉽게 생성할 수 있습니다. 지금 다운로드하세요!
type: docs
weight: 13
url: /ko/net/layer-management/create-vector-layer-with-srs/
---
## 소개
Aspose.GIS for .NET은 개발자가 .NET 애플리케이션에서 GIS(지리 정보 시스템) 데이터를 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 공간 참조 시스템(SRS)을 사용하여 벡터 레이어를 생성하는 방법에 중점을 둘 것입니다. 이 가이드가 끝나면 GIS 기능을 .NET 프로젝트에 쉽게 통합할 수 있게 됩니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 및 .NET 개발에 대한 기본 지식.
-  .NET 라이브러리용 Aspose.GIS가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/gis/net/).
- 개발 환경이 설정되고 준비되었습니다.
## 네임스페이스 가져오기
C# 파일 시작 부분에 필요한 네임스페이스를 가져왔는지 확인하세요.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## 1단계: 투영 공간 참조 시스템 설정
World Mercator 투영을 예로 사용하여 투영된 SRS(공간 참조 시스템)를 만들어 보겠습니다. 다음과 같이하세요:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## 2단계: 벡터 레이어 생성 및 기능 추가
이제 쉐이프파일을 생성하고 지정된 SRS를 사용하여 기능을 추가해 보겠습니다.
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // 기하학에 다른 SRS가 있으므로 예외가 발생합니다.
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## 3단계: 공간 참조 시스템 확인
마지막으로 레이어를 열고 공간 참조 시스템을 확인해 보겠습니다.
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / 월드 메르카토르"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // true를 반환해야 함
}
```
다음 단계를 수행하면 Aspose.GIS for .NET을 사용하여 지정된 공간 참조 시스템이 있는 벡터 레이어를 성공적으로 생성했습니다.
## 결론
Aspose.GIS 덕분에 GIS 기능을 .NET 애플리케이션에 통합하는 것이 그 어느 때보다 쉬워졌습니다. 손쉽게 벡터 레이어를 생성하고 공간 참조 시스템을 관리하는 기능을 통해 강력한 지리공간 기능으로 프로젝트를 향상시킬 수 있습니다.
## 자주 묻는 질문
### Aspose.GIS는 모든 GIS 파일 형식과 호환됩니까?
 Aspose.GIS는 Shapefile, GeoJSON, KML 등을 포함한 다양한 GIS 형식을 지원합니다. 을 체크 해봐[선적 서류 비치](https://reference.aspose.com/gis/net/) 전체 목록을 보려면.
### 웹 애플리케이션에서 Aspose.GIS를 사용할 수 있나요?
전적으로! .NET용 Aspose.GIS는 다목적이며 웹 애플리케이션, 데스크톱 애플리케이션, 심지어 모바일 앱에서도 사용할 수 있습니다.
### Aspose.GIS에 대한 지원은 어디서 받을 수 있나요?
 다음에서 유용한 커뮤니티를 찾을 수 있습니다.[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33) 귀하가 직면할 수 있는 모든 질문이나 문제에 대해.
### 무료 평가판이 제공되나요?
 예, 무료 평가판을 통해 Aspose.GIS의 기능을 탐색할 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.GIS 라이선스는 어떻게 구매할 수 있나요?
 라이센스를 구입하려면 다음을 방문하십시오.[구매 페이지](https://purchase.aspose.com/buy).