---
date: 2025-12-20
description: Aspose.GIS for .NET을 사용하여 구멍이 있는 폴리곤을 만드는 방법을 배웁니다. 이 가이드는 폴리곤에 구멍을 만들고
  지리공간 데이터를 다루는 방법을 보여줍니다.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS를 사용하여 구멍이 있는 폴리곤 생성
url: /ko/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 구멍이 있는 폴리곤 기하학 만들기

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **구멍이 있는 폴리곤** 기하학을 **생성**하는 방법을 배웁니다. 매핑 애플리케이션을 구축하든, 공간 분석을 수행하든, GIS 서비스용 데이터를 준비하든, 폴리곤 내부에 구멍을 삽입하는 방법을 아는 것은 필수적입니다. 환경 설정부터 최종 폴리곤 객체 생성까지 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **“구멍이 있는 폴리곤을 만든다”는 의미는?** 폴리곤 내부에 하나 이상의 내부 링(구멍)을 포함하여 해당 영역을 제외하는 폴리곤을 만드는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리하나요?** Aspose.GIS for .NET이 외부 링과 내부 링을 완벽히 지원합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **소요 시간은?** 구현 및 테스트에 일반적으로 10 분 이내가 소요됩니다.

## “구멍이 있는 폴리곤을 만든다”는 의미
구멍이 있는 폴리곤을 만든다는 것은 **외부 링**(외곽 경계)과 하나 이상의 **내부 링**(빈 공간)을 정의하는 것을 말합니다. 내부 링은 *구멍*이라고도 하며, 폴리곤 표면에 포함되지 않는 영역을 나타냅니다.

## Aspose.GIS로 폴리곤에 구멍을 만드는 이유
- **정확한 공간 모델링:** 토지 구획 내 호수나 건물 내부의 안뜰 등 현실 세계의 특징은 구멍이 필요합니다.  
- **상호 운용성:** Shapefile, GeoJSON, GML 등 형식은 내부 링을 기본 지원하며, Aspose.GIS가 이를 보존합니다.  
- **성능:** 라이브러리가 기하학 유효성을 자동으로 관리하므로 별도의 검증 코드를 작성할 필요가 없습니다.

## 사전 준비
시작하기 전에 다음 항목을 준비하십시오:
1. Aspose.GIS for .NET 라이브러리: [여기](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.  
2. 개발 환경: Visual Studio 또는 기타 .NET IDE가 설치된 개발 환경을 확보하십시오.

## 네임스페이스 가져오기
먼저 Aspose.GIS 기능을 사용하기 위해 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이제 Aspose.GIS for .NET을 사용하여 구멍이 있는 폴리곤 기하학을 만들 차례입니다.

## 단계 1: Polygon 객체 생성
외부 링과 내부 링을 모두 담을 빈 `Polygon` 객체를 인스턴스화합니다.

```csharp
Polygon polygon = new Polygon();
```

## 단계 2: 외부 링 정의
외부 링은 폴리곤의 외곽 경계를 정의합니다. 시계 방향으로 점을 추가하여 닫힌 형태를 만듭니다.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 단계 3: 내부 링(구멍) 정의
다음으로 내부 링, 즉 **구멍**을 생성합니다. 점은 일반적으로 반시계 방향으로 추가하지만, Aspose.GIS가 방향을 자동으로 처리합니다.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 단계 4: 외부 링 할당 및 내부 링 추가
마지막으로 외부 링을 폴리곤에 연결하고 내부 링(구멍)을 추가합니다. 여러 개의 구멍이 필요하면 `AddInteriorRing` 메서드를 여러 번 호출하면 됩니다.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| GIS 뷰어에 구멍이 표시되지 않음 | 내부 링 방향이 외부 링과 동일하게 설정됨 | 내부 링을 외부 링과 반대 방향(반시계 방향)으로 추가하십시오. |
| 폴리곤 유효성 오류 | 링이 닫히지 않음(첫 번째 점 ≠ 마지막 점) | 각 링의 첫 번째 점을 마지막 점으로 다시 추가하십시오(위 예시 참고). |
| 예상치 못한 빈 기하학 | 내부 링을 추가하기 전에 `ExteriorRing`을 할당하지 않음 | 먼저 `polygon.ExteriorRing`을 설정한 뒤 내부 링을 추가하십시오. |

## 결론
축하합니다! 이제 Aspose.GIS for .NET을 사용하여 **구멍이 있는 폴리곤** 기하학을 만드는 방법을 성공적으로 익혔습니다. 이 기술은 내부 공백이 있는 복잡한 형태를 표현해야 하는 다양한 지리공간 시나리오에서 기본이 됩니다.

## 자주 묻는 질문
### 1. Aspose.GIS란?
Aspose.GIS는 .NET 개발자가 다양한 지리공간 파일 형식을 생성, 읽기 및 조작할 수 있게 해주는 라이브러리입니다.

### 2. 상업 프로젝트에 Aspose.GIS를 사용할 수 있나요?
예, 라이선스를 구매하면 개인 및 상업 프로젝트 모두에 Aspose.GIS를 사용할 수 있습니다. 자세한 내용은 [여기](https://purchase.aspose.com/buy)를 참조하십시오.

### 3. Aspose.GIS 무료 체험판이 있나요?
예, [여기](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 받을 수 있습니다.

### 4. Aspose.GIS 지원을 어디서 받을 수 있나요?
[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 지원을 받을 수 있습니다.

### 5. Aspose.GIS 임시 라이선스를 어떻게 얻나요?
[여기](httpshttps://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 발급받을 수 있습니다.

---

**마지막 업데이트:** 2025-12-20  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}