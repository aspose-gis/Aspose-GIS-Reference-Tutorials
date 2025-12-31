---
date: 2025-12-31
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 생성하고 레이어의 공간 참조 시스템을 설정하는 방법을 배웁니다.
  공간 참조 정의, 포인트 피처 추가 및 EPSG 코드 조회를 마스터하세요.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: 벡터 레이어 생성 및 레이어 공간 참조 시스템 설정
url: /ko/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 벡터 레이어 생성 및 레이어 공간 참조 시스템 설정

## 소개
광범위한 지리 정보 시스템(GIS) 환경에서 **Aspose.GIS for .NET**은 개발자를 위한 강력하고 다재다능한 도구로 돋보입니다. 이 튜토리얼에서는 **벡터 레이어를 생성**하고, 공간 참조를 정의하며, 포인트 피처를 추가하고, EPSG 코드를 가져오는 과정을 단계별로 명확히 안내합니다. 숙련된 GIS 엔지니어이든 이제 막 시작하는 초보자이든, 이 기술을 통해 shapefile 좌표계를 올바르게 설정하고 공간 데이터 워크플로의 신뢰성을 높일 수 있습니다.

## 빠른 답변
- **“벡터 레이어 생성”은 무엇을 의미하나요?** 새 GIS 레이어(예: Shapefile)를 만들어 포인트, 라인, 폴리곤과 같은 기하를 저장할 수 있게 합니다.  
- **예제에서 사용된 EPSG 코드는 무엇인가요?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **레이어를 만든 후 포인트 피처를 추가할 수 있나요?** 예—`ConstructFeature()`를 사용하고 `Point` 기하를 할당하면 됩니다.  
- **레이어의 CRS를 어떻게 가져오나요?** `layer.SpatialReferenceSystem.EpsgCode` 또는 `.Name`을 읽습니다.  
- **Aspose.GIS에 라이선스가 필요한가요?** 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 라이선스가 필요합니다.

## 전제 조건
튜토리얼을 진행하기 전에 다음 사항을 준비하십시오:
- .NET 프로그래밍에 대한 기본 지식.  
- 시스템에 Visual Studio가 설치되어 있음.  
- [여기](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있는 Aspose.GIS for .NET 라이브러리.  
- GIS에서 공간 참조 시스템에 대한 기본 이해.

## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.GIS가 제공하는 기능에 접근하려면 필요한 네임스페이스를 가져와야 합니다. 다음 코드 스니펫을 사용하십시오:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## 단계 1: 문서 디렉터리 지정
문서 디렉터리 경로를 지정합니다. 이 경로에 공간 데이터 파일이 저장됩니다.

```csharp
string dataDir = "Your Document Directory";
```

## 단계 2: 공간 참조 정의 및 Shapefile 좌표계 설정
Shapefile 경로를 정의하고, EPSG 코드(예제에서는 26918)를 사용해 **공간 참조를 정의**합니다. 이 단계는 레이어의 **Shapefile 좌표계를 설정**합니다.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## 단계 3: 벡터 레이어 생성
이제 지정한 Shapefile 경로, 드라이버 유형(Shapefile) 및 방금 정의한 공간 참조 시스템을 사용해 **벡터 레이어를 생성**합니다.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## 단계 4: 레이어에 포인트 피처 추가
새 피처를 구성하고 좌표가 60, 24인 `Point` 기하를 설정해 **포인트 피처를 추가**합니다. 그런 다음 피처를 벡터 레이어에 추가합니다.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## 단계 5: 공간 참조 시스템 정보 가져오기 (EPSG 코드 가져오기)
벡터 레이어를 열고 EPSG 코드와 사람이 읽을 수 있는 이름과 같은 공간 참조 시스템 정보를 가져옵니다. 이는 **EPSG 코드를 가져오기**와 **레이어 CRS 설정**을 보여줍니다.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

위 단계를 필요에 맞게 반복하면 **벡터 레이어 생성**과 Aspose.GIS for .NET을 활용한 공간 참조에 능숙해질 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|----------|-----------|
| **레이어를 열 수 없음** | 잘못된 드라이버 또는 손상된 파일 경로 | `Drivers.Shapefile`을 확인하고 `path`가 존재하는 `.shp` 파일을 가리키는지 확인하십시오. |
| **잘못된 CRS 표시** | 잘못된 EPSG 코드를 사용함 | 권위 있는 소스(e.g., EPSG.io)에서 EPSG 코드를 다시 확인하십시오. |
| **피처가 저장되지 않음** | `using` 블록 내에서 `layer.Add(feature)`를 호출하지 않음 | 레이어가 해제되기 전에 `Add` 메서드가 실행되었는지 확인하십시오. |

## 자주 묻는 질문
### Aspose.GIS가 다른 GIS 라이브러리와 호환되나요?
예, Aspose.GIS는 다른 GIS 라이브러리와 잘 통합되며 함께 사용할 수 있습니다.

### Aspose.GIS를 데스크톱 및 웹 애플리케이션 모두에 사용할 수 있나요?
물론입니다! Aspose.GIS는 데스크톱 및 웹 기반 애플리케이션 모두에서 활용할 수 있는 다목적 솔루션입니다.

### Aspose.GIS에 대한 라이선스 옵션이 있나요?
예, 라이선스 옵션을 확인하고 구매는 [여기](https://purchase.aspose.com/buy)에서 진행할 수 있습니다.

### Aspose.GIS에 대한 무료 체험판이 있나요?
네! 무료 체험판은 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

### Aspose.GIS 관련 문의에 대한 지원은 어디서 받을 수 있나요?
지원이나 문의 사항이 있으면 [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)을 방문하십시오.

## 추가 자주 묻는 질문
**Q: 기존 Shapefile의 CRS를 어떻게 변경하나요?**  
A: 레이어를 열고 원하는 EPSG 코드를 사용해 새로운 `SpatialReferenceSystem`을 만든 뒤, 저장하기 전에 `layer.SpatialReferenceSystem`에 할당합니다.

**Q: 동일한 방법으로 다른 기하 유형(예: 폴리곤)을 추가할 수 있나요?**  
A: 예—`new Point(x, y)`를 `new Polygon(...)` 또는 `new LineString(...)` 등으로 교체하면 됩니다.

**Q: 대용량 데이터셋을 효율적으로 작업할 수 있나요?**  
A: 스트리밍 API(`VectorLayer.Create`와 `FeatureCollection` 사용)와 레이어를 즉시 해제하여 리소스를 확보하면 대규모 데이터를 효율적으로 처리할 수 있습니다.

**Q: Aspose.GIS가 좌표 변환을 지원하나요?**  
A: 예—`Geometry.Transform(targetSrs)`를 사용해 서로 다른 공간 참조 간에 기하를 재투영할 수 있습니다.

**Q: 지원되는 .NET 버전은 무엇인가요?**  
A: Aspose.GIS는 .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7을 지원합니다.

## 결론
이 튜토리얼에서는 **벡터 레이어를 생성**, 공간 참조를 정의, **포인트 피처를 추가**, 그리고 Aspose.GIS for .NET을 사용해 **EPSG 코드를 가져오는** 방법을 살펴보았습니다. 이러한 단계를 숙달하면 shapefile 좌표계를 정확히 설정하고 레이어 CRS를 관리하며 신뢰성 높은 GIS 애플리케이션을 구축할 수 있습니다.

---

**마지막 업데이트:** 2025-12-31  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}