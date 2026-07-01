---
date: 2026-04-03
description: Aspose.GIS for .NET를 사용하여 구멍이 있는 폴리곤을 만드는 방법을 배웁니다. 이 가이드는 폴리곤에 구멍을 만드는
  방법과 지리공간 데이터를 다루는 방법을 보여줍니다.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: 구멍이 있는 다각형 만들기
second_title: Aspose.GIS .NET API
title: Aspose.GIS를 사용하여 구멍이 있는 폴리곤 만들기
url: /ko/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 구멍이 있는 폴리곤 생성

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 **구멍이 있는 폴리곤** 지오메트리를 생성합니다. 매핑 애플리케이션을 구축하거나, 공간 분석을 수행하거나, GIS 서비스용 데이터를 준비하든, 폴리곤 내부에 구멍을 삽입하는 방법을 아는 것은 필수적입니다. 환경 설정부터 최종 폴리곤 객체 생성까지 전체 과정을 단계별로 안내합니다.

## 빠른 답변
- **“구멍이 있는 폴리곤 생성”이 의미하는 것은?** 폴리곤 내부에 하나 이상의 내부 링(구멍)을 포함하여 해당 영역에서 제외되는 폴리곤을 만드는 것을 의미합니다.  
- **어떤 라이브러리가 이를 처리합니까?** Aspose.GIS for .NET은 외부 링과 내부 링에 대한 전체 지원을 제공합니다.  
- **라이선스가 필요합니까?** 무료 체험판은 개발에 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5 이상, .NET Core 3.1 이상, .NET 5/6/7.  
- **소요 시간은 얼마나 됩니까?** 구현 및 테스트에 일반적으로 10분 미만이 걸립니다.

## Aspose.GIS를 사용하여 폴리곤에 구멍 추가 방법
구멍을 추가하는 것은 **내부 링**을 정의하고 이를 폴리곤에 연결하는 것만으로 간단합니다. 라이브러리가 방향과 유효성을 자동으로 처리하므로, 필요한 빈 공간을 나타내는 좌표에만 집중하면 됩니다.

## “구멍이 있는 폴리곤 생성”이란?
구멍이 있는 폴리곤을 만드는 것은 외부 경계를 정의하는 **외부 링**과 빈 공간을 파내는 하나 이상의 **내부 링**을 정의하는 것을 포함합니다. 내부 링은 종종 *구멍*이라고 불리며, 이는 폴리곤 표면의 일부가 아닌 영역을 나타냅니다.

## Aspose.GIS를 사용하여 폴리곤에 구멍을 만드는 이유
- **정확한 공간 모델링:** 토지 구획 내 호수나 건물 내부의 안뜰과 같은 실제 특징은 구멍이 필요합니다.  
- **상호 운용성:** Shapefile, GeoJSON, GML 등과 같은 포맷은 내부 링을 기본적으로 지원하며, Aspose.GIS는 이를 보존합니다.  
- **성능:** 라이브러리가 지오메트리 유효성을 관리하므로, 별도의 검증 코드를 작성할 필요가 없습니다.

## 구멍이 있는 폴리곤의 실제 적용 사례
1. **내부에 호수가 있는 토지 구획** – 호수를 구멍으로 모델링하여 구획 면적에 포함되지 않게 합니다.  
2. **안뜰이 있는 건물 외곽선** – 안뜰을 건물 외곽선에서 제외합니다.  
3. **보다 큰 보전 지역 내 보호 구역** – 별도 레이어를 만들지 않고 제한 구역을 제외할 수 있습니다.

## 전제 조건
시작하기 전에 다음 전제 조건을 확인하십시오:
1. Aspose.GIS for .NET 라이브러리: [here](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.  
2. 개발 환경: Visual Studio 또는 기타 .NET IDE가 설치된 개발 환경이 준비되어 있는지 확인하십시오.

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

이제 Aspose.GIS for .NET을 사용하여 구멍이 있는 폴리곤 지오메트리를 생성해 보겠습니다.

## 단계 1: 폴리곤 객체 생성
외부 및 내부 링을 모두 보유할 빈 `Polygon` 객체를 인스턴스화합니다.

```csharp
Polygon polygon = new Polygon();
```

## 단계 2: 외부 링 정의
외부 링은 폴리곤의 외부 경계를 정의합니다. 시계 방향으로 점을 추가하여 닫힌 형태를 만듭니다.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## 단계 3: 내부 링 정의 (구멍)
다음으로 내부 링을 생성합니다—이는 폴리곤 면적에서 제외될 **구멍**입니다. 점은 일반적으로 반시계 방향으로 추가하지만, Aspose.GIS가 방향을 자동으로 처리합니다.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## 단계 4: 외부 링 할당 및 내부 링(구멍) 추가
마지막으로 외부 링을 폴리곤에 연결하고 내부 링(구멍)을 추가합니다. 여러 개의 구멍이 필요하면 `AddInteriorRing` 메서드를 여러 번 호출할 수 있습니다.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## 팁 및 모범 사례
- **방향은 가독성에 중요** – Aspose.GIS가 자동으로 방향을 교정하지만, 외부 링은 시계 방향, 내부 링은 반시계 방향으로 유지하면 GIS 뷰어에서 지오메트리를 더 쉽게 확인할 수 있습니다.  
- **각 링을 닫기** – 첫 번째 좌표를 마지막 점으로 반복해서 입력하면 유효한 폐쇄 형태가 보장됩니다.  
- **생성 후 검증** – 저장하기 전에 `polygon.IsValid`를 호출하여 지오메트리가 OGC 표준을 준수하는지 확인할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| GIS 뷰어에 구멍이 표시되지 않음 | 내부 링 방향이 반대 | 외부 링과 반대 방향(반시계 방향)으로 점을 추가하십시오. |
| 폴리곤 유효성 오류 | 링이 닫히지 않음(첫 번째 ≠ 마지막 점) | 각 링에서 첫 번째 점을 마지막 점으로 반복하십시오(위와 같이). |
| 예상치 못한 빈 지오메트리 | 내부 링을 추가하기 전에 `ExteriorRing` 할당을 잊음 | 먼저 `polygon.ExteriorRing`을 설정하고, 그 다음 `AddInteriorRing`을 호출하십시오. |

## 자주 묻는 질문
### 1. Aspose.GIS란?
Aspose.GIS는 .NET 개발자가 지리공간 데이터를 다룰 수 있게 해 주는 라이브러리로, 다양한 지리공간 파일 형식을 생성, 읽기 및 조작할 수 있습니다.

### 2. Aspose.GIS를 상업 프로젝트에 사용할 수 있나요?
예, 개인 및 상업 프로젝트 모두에 Aspose.GIS를 사용할 수 있으며, 라이선스를 구매하면 됩니다. 자세한 내용은 [here](https://purchase.aspose.com/buy)에서 확인하십시오.

### 3. Aspose.GIS 무료 체험판이 있나요?
예, [here](https://releases.aspose.com/)에서 Aspose.GIS 무료 체험판을 이용할 수 있습니다.

### 4. Aspose.GIS 지원을 어디서 찾을 수 있나요?
[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)에서 지원을 받을 수 있습니다.

### 5. Aspose.GIS 임시 라이선스를 어떻게 얻을 수 있나요?
[here](https://purchase.aspose.com/temporary-license/)에서 Aspose.GIS 임시 라이선스를 받을 수 있습니다.

---

**마지막 업데이트:** 2026-04-03  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}