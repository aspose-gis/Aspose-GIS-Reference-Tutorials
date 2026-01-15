---
date: 2026-01-15
description: Aspose.GIS for .NET를 탐색하여 공간 참조 시스템이 있는 벡터 레이어를 생성하세요. SRS 설정, 레이어 생성
  및 GIS 데이터 관리 방법을 배우세요. 지금 다운로드하세요!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: SRS와 함께 벡터 레이어 만들기
url: /ko/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# SRS로 벡터 레이어 만들기

## 소개
Aspose.GIS for .NET은 개발자가 **벡터 레이어** 객체를 생성하고 .NET 애플리케이션에서 지리 정보 시스템(GIS) 데이터를 원활하게 다룰 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 공간 참조 시스템(SRS)을 사용하여 벡터 레이어를 만드는 방법, 공간 참조를 설정해야 하는 이유, 그리고 실제 프로젝트에 가져다 주는 이점에 대해 단계별로 살펴봅니다. 이 가이드를 마치면 .NET 솔루션에 GIS 기능을 자신 있게 통합할 수 있습니다.

## 빠른 답변
- **이 튜토리얼의 주요 목적은 무엇인가요?** Aspose.GIS for .NET을 사용해 지정된 SRS로 벡터 레이어를 만드는 방법을 보여주기 위함입니다.  
- **예제에서 사용된 투영법은 무엇인가요?** World Mercator (EPSG:3395).  
- **코드를 실행하려면 라이선스가 필요하나요?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **다른 GIS 포맷에도 같은 방법을 적용할 수 있나요?** 예, Shapefile, GeoJSON, KML 등에도 동일한 SRS 처리 방식이 적용됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 벡터 레이어란 무엇이며 왜 공간 참조를 설정해야 할까요?
**벡터 레이어**는 기하학적 피처(점, 선, 폴리곤)와 속성 데이터를 함께 저장합니다. **공간 참조**(SRS)를 지정하면 GIS 소프트웨어가 해당 좌표를 지구 표면상의 어느 위치로 해석해야 하는지 알 수 있습니다. 올바른 SRS를 설정하면 정확한 측정, 다른 레이어와의 올바른 겹침, 신뢰할 수 있는 지도 시각화를 보장합니다.

## 사전 준비
시작하기 전에 다음을 준비하세요:

- C# 및 .NET 개발에 대한 기본 지식.  
- Aspose.GIS for .NET 라이브러리 설치. **[여기](https://releases.aspose.com/gis/net/)**에서 다운로드할 수 있습니다.  
- 개발 환경(Visual Studio, VS Code 또는 기타 C# IDE).

## 네임스페이스 가져오기
C# 파일 상단에 필요한 네임스페이스를 가져와야 합니다:

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

## 공간 참조(SRS) 설정 – 단계 1
World Mercator 투영법을 예시로 **프로젝션된 공간 참조 시스템**을 만들어 보겠습니다. 이는 레이어에 **SRS를 설정하는 방법**을 보여줍니다.

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

## 레이어 생성 – 단계 2
이제 **벡터 레이어**(Shapefile)를 생성하고, 방금 정의한 SRS를 사용하는 피처를 추가합니다. 이 부분은 Aspose.GIS를 사용해 **레이어를 만드는 방법**을 설명합니다.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **팁:** 피처를 추가하기 전에 해당 기하학의 `SpatialReferenceSystem`이 레이어의 SRS와 일치하는지 반드시 확인하세요. 일치하지 않으면 위와 같이 `GisException`이 발생합니다.

## 공간 참조 시스템 확인 – 단계 3
마지막으로 레이어를 열어 SRS가 올바르게 적용되었는지 확인합니다.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

`IsEquivalent` 호출이 `true`를 반환하면 원하는 공간 참조를 사용해 **벡터 레이어를 성공적으로 생성**한 것입니다.

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|-----------|-----------|
| 피처 추가 시 `GisException` 발생 | 기하학이 레이어와 다른 SRS를 사용 | 피처 추가 전에 `feature.Geometry.SpatialReferenceSystem`을 레이어의 SRS로 설정 |
| GIS 소프트웨어에서 레이어가 비어 있음 | `.prj` 파일 없이 shapefile이 생성됨 | 레이어 생성 시 `projectedSrs` 객체를 반드시 전달 |
| 좌표 값이 예상과 다름 | 투영 파라미터(예: 중앙 자오선) 오류 | `AddProjectionParameter`에 전달한 파라미터를 재검토 |

## FAQ
### Aspose.GIS가 모든 GIS 파일 포맷과 호환되나요?
Aspose.GIS는 Shapefile, GeoJSON, KML 등 다양한 GIS 포맷을 지원합니다. 전체 목록은 **[문서](https://reference.aspose.com/gis/net/)**를 확인하세요.

### Aspose.GIS를 웹 애플리케이션에서 사용할 수 있나요?
물론입니다! Aspose.GIS for .NET은 웹, 데스크톱, 모바일 애플리케이션 모두에서 활용할 수 있습니다.

### Aspose.GIS 지원을 어디서 받을 수 있나요?
질문이나 문제가 있을 경우 **[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)**에서 커뮤니티 도움을 받을 수 있습니다.

### 무료 체험판을 제공하나요?
네, **[여기](https://releases.aspose.com/)**에서 무료 체험판을 받아 기능을 직접 확인해 보세요.

### Aspose.GIS 라이선스는 어떻게 구매하나요?
라이선스 구매는 **[구매 페이지](https://purchase.aspose.com/buy)**에서 진행할 수 있습니다.

## 추가 FAQ

**Q: 다른 SRS를 가진 기하학을 추가하면 어떻게 되나요?**  
A: Aspose.GIS는 `GisException`을 발생시킵니다. 기하학을 재투영하거나 레이어와 동일한 SRS를 사용하도록 해야 합니다.

**Q: 기존 레이어의 SRS를 변경할 수 있나요?**  
A: 가능합니다. 원하는 SRS로 새 레이어를 만든 뒤 피처를 복사하고 필요에 따라 재투영하면 됩니다.

**Q: 3D 좌표를 다룰 수 있나요?**  
A: Aspose.GIS는 Z 좌표를 지원합니다. Z 값을 받는 기하학 생성자를 사용하면 됩니다.

**Q: 라이브러리가 자동으로 기준면 변환을 처리하나요?**  
A: `Geometry.Transform`을 사용해 기하학을 재투영하면 Aspose.GIS가 필요한 기준면 이동을 자동으로 수행합니다.

**Q: 공식적으로 테스트된 .NET 버전은 어떤 것이 있나요?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7에서 테스트되었습니다.

## 결론
이제 Aspose.GIS for .NET을 사용해 **맞춤형 공간 참조 시스템**을 가진 **벡터 레이어를 생성**하는 방법을 익혔습니다. 올바른 SRS를 설정하고, 기하학을 일관되게 다루며, 레이어 메타데이터를 검증함으로써 표준 GIS 소프트웨어와 원활히 연동되는 견고한 GIS 애플리케이션을 구축할 수 있습니다.

---

**최종 업데이트:** 2026-01-15  
**테스트 환경:** Aspose.GIS 24.11 for .NET (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}