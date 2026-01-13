---
date: 2026-01-13
description: Aspose.GIS for .NET를 사용하여 레이어 기능을 자르는 방법을 배우세요. 여기에는 폴리곤으로 래스터를 자르는 방법,
  래스터 셀 크기를 추출하는 방법, 그리고 래스터 범위를 가져오는 방법이 포함됩니다. 지금 무료 체험판을 다운로드하세요.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET로 레이어 피처 자르기
url: /ko/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 레이어 기능 자르기 방법

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **레이어를 자르는 방법**을 배우게 됩니다. 이 강력한 접근 방식으로 **폴리곤으로 래스터 자르기**, **래스터 셀 크기 추출**, **래스터 범위 가져오기**를 수행하여 정밀한 지리공간 분석을 할 수 있습니다. 웹 지도용 데이터를 준비하든, 위성 영상을 다듬든, 관심 영역을 분리하든, 이 단계별 가이드는 작업을 정확히 수행하는 방법을 보여줍니다.

## 빠른 답변
- **“crop layer”는 무엇을 의미하나요?** 제공된 기하학의 경계에 맞게 래스터 또는 벡터 레이어를 잘라냅니다.  
- **이 예제에서 사용된 기하학은 무엇인가요?** WKT 형식으로 정의된 폴리곤입니다.  
- **자른 후 셀 크기를 추출할 수 있나요?** 예 – `CellSize` 속성이 해당 정보를 제공합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 동작하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “레이어 자르기”란 무엇인가요?
레이어를 자른다는 것은 데이터셋을 특정 지리 영역으로 제한하고, 정의된 형태 밖에 있는 모든 데이터를 버리는 것을 의미합니다. 이렇게 하면 파일 크기가 감소하고 처리 속도가 빨라지며, 관심 있는 영역에 분석을 집중할 수 있습니다.

## 왜 Aspose.GIS를 사용해 레이어를 자르나요?
- **고성능 래스터 처리** – 대용량 GeoTiff 파일에 이상적입니다.  
- **간단한 API** – 어떤 기하학이든 한 줄 `Crop` 호출로 처리합니다.  
- **전체 .NET 호환성** – 데스크톱, 서버, 클라우드 앱에서 작동합니다.  
- **정확한 공간 참조 처리** – CRS 정보를 자동으로 보존합니다.

## 전제 조건
지리공간 조작의 마법을 다루기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:

- Aspose.GIS for .NET 라이브러리: .NET 프로젝트에 Aspose.GIS 라이브러리가 설치되어 있는지 확인하십시오. [here](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.  
- 문서 디렉터리: 문서를 저장할 디렉터리를 설정하십시오. 제공된 코드의 `"Your Document Directory"`를 실제 문서 디렉터리 경로로 교체합니다.

이제 단계별 가이드를 살펴보겠습니다.

## 네임스페이스 가져오기
Aspose.GIS의 전체 기능을 활용하려면 필요한 네임스페이스를 가져옵니다:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 1단계: 레이어 열기 및 자르기 (폴리곤으로 래스터 자르기)
정의된 폴리곤을 기준으로 GeoTiff 레이어를 열고 자릅니다. 이렇게 하면 지리공간 데이터가 특정 관심 영역으로 정제됩니다.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 2단계: 래스터 정보 가져오기 (래스터 셀 크기 추출 및 래스터 범위 가져오기)
레이어를 자른 후, 셀 크기, 공간 참조 시스템, 경계와 같은 래스터 데이터의 핵심 정보를 추출합니다.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 3단계: 정보 표시
추출된 정보를 출력하여 자르기 과정이 지리공간 데이터에 미친 영향을 이해합니다.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

프로젝트 요구사항에 맞게 지리공간 데이터를 정제하고 맞춤화하려면 필요에 따라 이 단계를 반복하십시오.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **잘못된 폴리곤 방향** | WKT 폴리곤이 오른손 규칙(외부 링은 반시계 방향)을 따르는지 확인하십시오. |
| **공간 참조 누락** | 원본 GeoTiff에 CRS가 포함되어 있는지 확인하고, 없을 경우 자르기 전에 수동으로 설정하십시오. |
| **대용량 래스터에서 성능 저하** | 다운샘플된 복사본에 `layer.Crop`을 사용하거나 래스터를 타일 단위로 처리하십시오. |

## 자주 묻는 질문
### Q: Aspose.GIS for .NET에 임시 라이선스가 제공되나요?
A: 예, [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

### Q: Aspose.GIS for .NET에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?
A: 문서는 [here](https://reference.aspose.com/gis/net/)에서 확인할 수 있습니다.

### Q: Aspose.GIS for .NET에 대한 지원을 받거나 커뮤니티와 연결하려면 어떻게 해야 하나요?
A: 지원 및 커뮤니티 참여를 위해 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)을 방문하십시오.

### Q: Aspose.GIS for .NET의 무료 체험판을 다운로드할 수 있나요?
A: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 다운로드할 수 있습니다.

### Q: Aspose.GIS for .NET을 어디서 구매할 수 있나요?
A: 라이브러리는 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

### Q: 한 번에 여러 레이어를 자를 수 있나요?
A: 예—각 레이어를 순회하면서 원하는 기하학으로 동일한 `Crop` 호출을 적용하면 됩니다.

### Q: API가 다른 래스터 형식(e.g., JPEG2000)을 지원하나요?
A: Aspose.GIS는 JPEG2000, PNG 등 기본 GDAL 드라이버가 제공하는 모든 형식을 지원합니다.

## 결론
이 가이드를 따라 하면 Aspose.GIS for .NET을 사용하여 **레이어를 자르는 방법**을 효율적으로 알게 됩니다. 이제 **폴리곤으로 래스터 자르기**, **래스터 셀 크기 추출**, **래스터 범위 가져오기**를 손쉽게 수행하여 모든 프로젝트 요구에 맞출 수 있습니다. 재투영, 래스터 스타일링, 벡터 분석 등 추가 API를 탐색하여 지리공간 워크플로우의 전체 잠재력을 활용해 보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-13  
**테스트 환경:** Aspose.GIS 24.10 for .NET  
**작성자:** Aspose