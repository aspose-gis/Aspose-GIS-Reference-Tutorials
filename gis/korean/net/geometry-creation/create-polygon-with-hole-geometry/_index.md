---
title: Aspose.GIS를 사용하여 구멍 형상으로 다각형 만들기
linktitle: 구멍 형상을 사용하여 다각형 생성
second_title: Aspose.GIS .NET API
description: .NET용 Aspose.GIS를 사용하여 구멍 형상으로 다각형을 만드는 방법을 알아보세요. 코드 예제가 포함된 단계별 튜토리얼입니다.
weight: 13
url: /ko/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS를 사용하여 구멍 형상으로 다각형 만들기

## 소개
이 튜토리얼에서는 Aspose.GIS for .NET을 사용하여 구멍 형상이 있는 다각형을 생성하는 과정을 안내합니다. Aspose.GIS는 개발자가 .NET 애플리케이션에서 지리공간 데이터로 작업할 수 있도록 하는 강력한 라이브러리입니다. 
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET 라이브러리용 Aspose.GIS: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/gis/net/).
2. 개발 환경: Visual Studio 또는 기타 .NET IDE가 설치된 개발 환경이 설정되어 있는지 확인하세요.
## 네임스페이스 가져오기
먼저 Aspose.GIS 기능을 사용하려면 필요한 네임스페이스를 가져와야 합니다. 수행 방법은 다음과 같습니다.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이제 Aspose.GIS for .NET을 사용하여 구멍 형상이 있는 다각형을 생성해 보겠습니다.
## 1단계: 다각형 개체 만들기
```csharp
Polygon polygon = new Polygon();
```
## 2단계: 외부 링 정의
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## 3단계: 내부 링(구멍) 정의
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## 4단계: 외부 링 지정 및 다각형에 내부 링 추가
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## 결론
축하해요! .NET용 Aspose.GIS를 사용하여 구멍 형상으로 다각형을 만드는 방법을 성공적으로 배웠습니다. 이 지식은 그러한 기하학적 구조가 필수적인 다양한 지리공간 애플리케이션에 도움이 될 것입니다.
## FAQ
### 1. Aspose.GIS란 무엇입니까?
Aspose.GIS는 개발자가 지리공간 데이터로 작업하여 다양한 지리공간 파일 형식을 생성하고 읽고 조작할 수 있도록 하는 .NET 라이브러리입니다.
### 2. Aspose.GIS를 상업용 프로젝트에 사용할 수 있나요?
 예, 라이선스를 구매하면 개인 및 상업용 프로젝트 모두에 Aspose.GIS를 사용할 수 있습니다. 방문하다[여기](https://purchase.aspose.com/buy) 상세 사항은.
### 3. Aspose.GIS에 대한 무료 평가판이 있습니까?
 예, 다음에서 Aspose.GIS 무료 평가판을 이용할 수 있습니다.[여기](https://releases.aspose.com/).
### 4. Aspose.GIS에 대한 지원은 어디서 찾을 수 있나요?
 Aspose.GIS에 대한 지원은 다음에서 찾을 수 있습니다.[Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33).
### 5. Aspose.GIS에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 Aspose.GIS에 대한 임시 라이선스는 다음에서 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
