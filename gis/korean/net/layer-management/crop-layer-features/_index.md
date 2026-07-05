---
date: 2026-07-05
description: Aspose.GIS for .NET를 사용하여 Crop Layer Features를 자르는 방법을 배우세요. 여기에는 polygon을
  사용한 raster 자르기, raster cell size 추출, raster extent 가져오기가 포함됩니다. 지금 free trial을 다운로드하세요.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Crop Layer Features 방법
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET와 함께 Crop Layer Features 하는 방법
url: /ko/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 레이어 기능 자르기

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **레이어 자르기** 기능을 배우게 됩니다. 이 강력한 라이브러리를 통해 **다각형으로 래스터 자르기**, **래스터 셀 크기 추출**, 그리고 **래스터 범위 가져오기**를 수행하여 정밀한 지리공간 분석을 할 수 있습니다. 웹 지도용 데이터를 준비하든, 위성 이미지를 다듬든, 관심 영역을 분리하든, 이 단계별 가이드는 작업을 빠르고 신뢰성 있게 수행하는 방법을 정확히 보여줍니다.

## 빠른 답변
- **“crop layer”는 무엇을 의미합니까?** 제공된 기하학의 경계에 맞게 래스터 또는 벡터 레이어를 잘라내어 외부의 모든 것을 버립니다.  
- **이 예제에서 사용된 기하학은 무엇입니까?** WKT(Well‑Known Text) 형식으로 정의된 다각형입니다.  
- **자른 후 셀 크기를 추출할 수 있나요?** 예 – `CellSize` 속성은 래스터 셀의 너비와 높이를 반환합니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 동작하지만, 실제 사용을 위해서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “레이어 자르기”란 무엇입니까?
**레이어를 자른다는 것은 데이터세트를 특정 지리 영역으로 제한하고 외부를 버리는 것을 의미합니다.** 이 작업은 파일 크기를 줄이고 이후 처리 속도를 높이며, 관심 있는 영역에 대한 분석에 집중할 수 있게 합니다. 데이터를 관심 영역으로 제한함으로써 스타일링, 분석, 게시와 같은 후속 작업 흐름을 단순화하면서 원래 좌표 참조 시스템과 메타데이터를 보존합니다.

## 왜 Aspose.GIS를 사용해 레이어를 자르나요?
**Aspose.GIS는 전체 이미지를 메모리에 로드하지 않고도 최대 2 GB 크기의 래스터 파일을 처리하며, GeoTIFF, JPEG2000, PNG를 포함한 30가지 이상의 래스터 형식을 지원합니다.** 이 라이브러리는 한 줄의 `Crop` 호출, 자동 CRS 처리, 그리고 다중 스레드 성능을 제공하여 일반 서버에서 500 MB GeoTIFF를 1초 미만으로 잘라낼 수 있습니다.

## 전제 조건
지리공간 조작의 마법을 다루기 전에, 다음 전제 조건이 준비되어 있는지 확인하십시오:

- Aspose.GIS for .NET 라이브러리: .NET 프로젝트에 Aspose.GIS 라이브러리가 설치되어 있는지 확인하십시오. [here](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.  
- 문서 디렉터리: 문서를 저장할 디렉터리를 설정하십시오. 제공된 코드에서 `"Your Document Directory"`를 실제 문서 디렉터리 경로로 교체하십시오.

이제 단계별 가이드를 살펴보겠습니다.

## 네임스페이스 가져오기
`Aspose.Gis` 네임스페이스에는 래스터 및 벡터 처리를 위한 모든 핵심 타입이 포함되어 있습니다. 이를 가져와 `Layer`, `Geometry` 및 관련 클래스를 사용할 수 있습니다.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## 다각형으로 레이어를 어떻게 자르나요?
`Crop`은 `Layer` 클래스의 메서드로, 기하학으로 정의된 래스터 부분집합을 추출합니다.  
소스 래스터를 로드하고, 다각형 기하학을 정의한 뒤 `Crop` 메서드를 호출하면 전체 작업이 한 줄의 코드로 수행됩니다. 이 메서드는 다각형 내부의 픽셀만 포함하는 새로운 래스터를 반환하며, 원래 공간 참조를 자동으로 보존합니다.

## 단계 1: 레이어 열기 및 자르기 (다각형으로 래스터 자르기)
`Layer`는 열고, 조회하고, 편집할 수 있는 래스터 데이터셋을 나타냅니다.  
`Layer` 클래스는 열고, 조회하고, 편집할 수 있는 래스터 데이터셋을 나타냅니다. GeoTIFF를 열고 다각형으로 자르면 몇 줄의 코드만으로 관심 영역을 분리할 수 있습니다.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## 단계 2: 래스터 정보 가져오기 (래스터 셀 크기 추출 및 래스터 범위 가져오기)
`CellSize`는 각 래스터 셀의 너비와 높이를 좌표 단위로 제공합니다.  
`Extent`는 래스터의 지리적 경계 상자를 반환합니다.  
`CellSize` 속성은 각 래스터 셀의 너비와 높이를 좌표 단위로 제공하고, `Extent` 속성은 잘린 래스터의 지리적 경계 상자를 반환합니다. 이 두 정보는 면적 측정이나 재투영과 같은 후속 계산에 필수적입니다.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## 단계 3: 정보 표시
추출된 정보를 출력하여 레이어 자르기 과정이 지리공간 데이터에 미치는 영향을 이해하십시오.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

필요에 따라 이 단계를 반복하여 지리공간 데이터를 정제하고 프로젝트 요구에 맞게 맞춤화하십시오.

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|-------|----------|
| **다각형 방향 오류** | WKT 다각형이 오른손 규칙(외부 링은 반시계 방향)을 따르는지 확인하십시오. |
| **공간 참조 누락** | 소스 GeoTiff에 CRS가 포함되어 있는지 확인하고, 없으면 자르기 전에 수동으로 설정하십시오. |
| **대용량 래스터에서 성능 저하** | 다운샘플된 복사본에 `layer.Crop`을 사용하거나 래스터를 타일로 처리하십시오. |

## 자주 묻는 질문
**Q: Aspose.GIS for .NET에 임시 라이선스가 제공되나요?**  
A: 예, [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 얻을 수 있습니다.

**Q: Aspose.GIS for .NET에 대한 포괄적인 문서는 어디서 찾을 수 있나요?**  
A: 문서는 [here](https://reference.aspose.com/gis/net/)에서 확인할 수 있습니다.

**Q: Aspose.GIS for .NET에 대한 지원을 받거나 커뮤니티와 연결하려면 어떻게 해야 하나요?**  
A: 지원 및 커뮤니티 참여를 위해 [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) 를 방문하십시오.

**Q: Aspose.GIS for .NET의 무료 체험판을 다운로드할 수 있나요?**  
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: Aspose.GIS for .NET을 어디서 구매할 수 있나요?**  
A: 라이브러리를 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 한 번에 여러 레이어를 자를 수 있나요?**  
A: 예—각 레이어를 순회하면서 원하는 기하학으로 동일한 `Crop` 호출을 적용하면 됩니다.

**Q: API가 다른 래스터 형식(e.g., JPEG2000)을 지원하나요?**  
A: Aspose.GIS는 JPEG2000, PNG 등을 포함한 기본 GDAL 드라이버가 노출하는 모든 형식을 지원합니다.

## 결론
이 가이드를 따라 하면 이제 Aspose.GIS for .NET을 사용하여 **레이어 자르기** 기능을 효율적으로 수행하는 방법을 알게 됩니다. **다각형으로 래스터 자르기**, **래스터 셀 크기 추출**, **래스터 범위 가져오기**를 쉽게 수행하여 모든 프로젝트 요구에 맞출 수 있습니다. 재투영, 래스터 스타일링, 벡터 분석을 위한 추가 API를 탐색하여 지리공간 워크플로우의 전체 잠재력을 활용하십시오.

---

**마지막 업데이트:** 2026-07-05  
**테스트 대상:** Aspose.GIS 24.10 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.GIS for .NET을 사용하여 다각형 기하학 만들기](/gis/net/geometry-creation/create-polygon-geometry/)
- [레이어 속성 가져오기 – Aspose.GIS for .NET을 사용한 레이어 속성 정보 검색](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [C#로 다각형 기하학 만들기 및 Aspose.GIS for .NET으로 교차 확인](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}