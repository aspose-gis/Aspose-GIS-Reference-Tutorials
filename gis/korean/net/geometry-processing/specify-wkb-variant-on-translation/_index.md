---
date: 2025-12-21
description: ExtendedPostGis 변형을 사용하여 Aspose.GIS for .NET으로 라인스트링 지오메트리를 생성하고 지오메트리를
  WKB로 변환하는 방법을 배웁니다.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Aspose.GIS .NET에서 라인스트링 지오메트리 및 WKB 변형 만들기
url: /ko/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET에서 변환 시 WKB 변형 지정하기

## 소개
지리 정보 시스템(GIS) 개발 분야에서 Aspose.GIS for .NET은 강력한 툴셋으로 돋보입니다. **linestring geometry**를 **생성**하고 그 다음 **geometry를 WKB로 변환**해야 한다면, 여기가 바로 적절한 곳입니다. 이 툴의 다재다능함과 효율성은 .NET 애플리케이션에 GIS 기능을 원활히 통합하려는 개발자들에게 최고의 선택이 됩니다. 이 문서는 Aspose.GIS for .NET을 활용하는 포괄적인 가이드를 제공하며, 특히 변환 과정에서 WKB(Well‑Known Binary) 변형을 지정하는 방법에 초점을 맞춥니다.

## 빠른 답변
- **WKB는 무엇의 약자입니까?** Well‑Known Binary, 기하 객체의 압축된 바이너리 표현입니다.  
- **SRID 정보를 저장할 수 있는 WKB 변형은 무엇입니까?** `ExtendedPostGis` (EWKB) 변형입니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **구현에 얼마나 걸립니까?** 기본 예제의 경우 보통 10분 이내입니다.

## Linestring Geometry란?
Linestring은 일련의 점을 직선 구간으로 연결한 단순한 기하 형태입니다. 도로, 강, 또는 GIS 데이터의 모든 선형 피처를 나타내는 데 일반적으로 사용됩니다.

## 왜 WKB 변형을 지정해야 할까요?
올바른 WKB 변형을 선택하면 공간 참조 시스템 식별자(SRID)와 같은 중요한 메타데이터가 기하 데이터를 저장하거나 교환할 때 보존됩니다. `ExtendedPostGis` 변형(EWKB)은 PostgreSQL/PostGIS 또는 SRID 정보가 바이너리에 포함된 시스템과 작업할 때 특히 유용합니다.

## 사전 요구 사항
Aspose.GIS for .NET에서 WKB 변형을 지정하는 구체적인 내용에 들어가기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:

### Aspose.GIS for .NET 설치
1. Aspose.GIS 다운로드: [download link](https://releases.aspose.com/gis/net/)에서 Aspose.GIS for .NET 패키지를 받으세요.  
2. 패키지 설치: 문서에 제공된 설치 지침을 따라 Aspose.GIS를 .NET 환경에 원활히 통합하세요.

### C# 프로그래밍에 대한 친숙도
1. 기본 C# 지식: C# 프로그래밍 언어의 구문 및 개념에 대한 기본 이해가 필요합니다.

## 네임스페이스 가져오기
Aspose.GIS for .NET을 시작하고 기능을 효과적으로 활용하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 다음은 단계별 가이드입니다:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

이 네임스페이스들을 통해 Aspose.GIS 기능에 접근할 수 있어 지리 데이터를 손쉽게 다룰 수 있습니다.

## linestring geometry를 만드는 방법?
제공된 예제를 여러 단계로 나누어 살펴보면, 변환 시 WKB 변형을 지정하는 과정을 자세히 이해할 수 있습니다.

### 단계 1: Geometry 객체 생성
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
이 단계에서는 지정된 좌표로 선형 피처를 나타내는 **linestring geometry**를 **생성**합니다.

### 단계 2: WKB 표현 생성
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
여기서는 `ExtendedPostGis` 변형을 사용해 **geometry를 WKB**로 **변환**하며, SRID 정보를 포함합니다.

### 단계 3: 파일에 쓰기
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
마지막으로 생성된 WKB 바이너리 데이터를 원하는 디렉터리의 `EWkbFile.ewkb` 파일에 씁니다.

## 일반적인 문제와 해결책
| 문제 | 원인 | 해결책 |
|-------|--------|----------|
| **Empty file** | `Path.Combine`가 존재하지 않는 디렉터리를 가리킵니다. | 대상 디렉터리가 존재하는지 확인하거나 `Directory.CreateDirectory`로 생성하십시오. |
| **Incorrect SRID** | 기본 `WkbVariant.Standard`를 사용하면 SRID가 손실됩니다. | SRID 보존이 필요할 때는 항상 `WkbVariant.ExtendedPostGis`를 사용하십시오. |
| **License exception** | 프로덕션 환경에서 유효한 라이선스 없이 실행했습니다. | 프로덕션 환경에서 코드를 실행하기 전에 임시 또는 정식 라이선스를 적용하십시오. |

## FAQ
### Aspose.GIS for .NET은 모든 . 버전과 호환됩니까?
Aspose.GIS for .NET은 다양한 .NET 버전과 호환되도록 설계되어 있어 개발자에게 유연성과 접근성을 제공합니다.

### Aspose.GIS for .NET을 사용하면서 지원이나 도움을 요청할 수 있습니까?
예, 전용 [Aspose.GIS 포럼](https://forum.aspose.com/c/gis/33)을 통해 전문가 및 다른 개발자에게 지원과 도움을 요청할 수 있습니다.

### Aspose.GIS for .NET은 무료 체험을 제공합니까?
예, [이 링크](https://releases.aspose.com/)에서 제공되는 무료 체험을 통해 Aspose.GIS for .NET의 기능과 역량을 확인할 수 있습니다.

### Aspose.GIS for .NET의 임시 라이선스는 어떻게 얻을 수 있습니까?
[임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)를 방문하여 안내에 따라 임시 라이선스를 받을 수 있습니다.

### Aspose.GIS for .NET 라이선스는 어디서 구매할 수 있습니까?
[이 링크](https://purchase.aspose.com/buy)에서 구매 페이지를 통해 Aspose.GIS for .NET 라이선스를 구매할 수 있습니다.

## 자주 묻는 질문
**Q: EWKB 파일을 PostGIS와 함께 사용할 수 있나요?**  
A: 예, `ExtendedPostGis` 변형은 SRID를 포함한 EWKB를 생성하며, PostGIS가 직접 읽을 수 있습니다.

**Q: WKB 파일을 다시 geometry 객체로 읽을 수 있나요?**  
A: 물론입니다. `Geometry.FromBinary(byteArray)`를 사용해 geometry를 재구성할 수 있습니다.

**Q: 라이브러리가 폴리곤과 같은 다른 geometry 타입을 지원하나요?**  
A: 예, Aspose.GIS는 포인트, linestring, 폴리곤, 멀티폴리곤 등 다양한 타입을 처리합니다.

**Q: geometry를 생성할 때 다른 SRID를 지정하려면 어떻게 해야 하나요?**  
A: `AsBinary`를 호출하기 전에 geometry 객체의 SRID를 설정합니다. 예: `geometry.SRID = 4326;`.

**Q: 이 코드는 .NET Core에서도 작동하나요?**  
A: 예, 동일한 API가 .NET Framework, .NET Core, .NET 5/6 전반에 걸쳐 작동합니다.

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS for .NET 23.9 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}