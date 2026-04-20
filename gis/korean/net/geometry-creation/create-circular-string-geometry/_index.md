---
date: 2026-02-15
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 만들고 원형 스트링 지오메트리를 추가하는 방법을 배우세요 – GIS
  애플리케이션을 빠르게 구축하는 방법입니다.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET에서 벡터 레이어 및 원형 문자열 만들기
url: /ko/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET을 사용하여 벡터 레이어 및 원형 문자열 지오메트리 만들기

## 소개
.NET 플랫폼에서 GIS 애플리케이션을 구축하고 있다면, 첫 번째 단계는 **벡터 레이어** 객체를 생성하여 공간 피처를 저장하는 것입니다. Aspose.GIS for .NET은 이 과정을 간단하게 만들어 주며, 원형 문자열과 같은 고급 지오메트리로 레이어를 풍부하게 할 수 있게 해줍니다. 이 튜토리얼에서는 **벡터 레이어**를 **생성하고**, **원형 문자열** 지오메트리를 **추가한 뒤**, 결과를 Shapefile로 저장하는 방법을 깔끔하고 프로덕션 수준의 C# 코드로 배워볼 수 있습니다.

## 빠른 답변
- **“create vector layer”는 무엇을 의미하나요?** 공간 피처(점, 선, 폴리곤 등)를 담을 수 있는 새로운 컨테이너(레이어)를 생성합니다.  
- **원형 문자열을 나타내는 클래스는?** `Aspose.Gis.Geometries` 네임스페이스의 `CircularString`.  
- **레이어를 Shapefile로 저장할 수 있나요?** 예 – 레이어를 생성할 때 `Drivers.Shapefile`을 사용하면 됩니다.  
- **개발에 라이선스가 필요하나요?** 평가용 임시 라이선스로도 충분하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## “create vector layer”란 무엇인가요?
벡터 레이어는 단일 데이터 소스에 저장된 벡터 피처(점, 선, 폴리곤)를 논리적으로 그룹화한 것입니다. Aspose.GIS에서는 `VectorLayer.Create` 메서드를 호출하고 대상 파일 경로와 원하는 드라이버(예: Shapefile)를 전달하여 레이어를 인스턴스화합니다. 레이어가 생성되면 피처를 추가하고, 지오메트리를 할당하며, 공간 연산을 수행할 수 있습니다.

## 왜 원형 문자열을 추가하나요?
원형 문자열은 **선형 지오메트리**의 한 종류로, 일련의 점을 사용해 호를 근사합니다. 곡선 도로, 강 굽이 등 부드러운 곡선이 필요한 경우, 많은 작은 선분을 사용하지 않고도 표현할 수 있어 유용합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있어야 합니다:

- **.NET Framework 또는 .NET Core**가 머신에 설치되어 있어야 합니다.  
- **Aspose.GIS for .NET** 라이브러리 – 공식 사이트 **[here](https://releases.aspose.com/gis/net/)**에서 다운로드하세요.  
- **Visual Studio** 또는 **JetBrains Rider**와 같은 IDE.  
- **C#** 프로그래밍에 대한 기본적인 이해.

## 네임스페이스 가져오기
C# 파일에 필요한 네임스페이스를 추가합니다:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 단계별 가이드

### 단계 1: 출력 파일 경로 정의
Shapefile이 기록될 위치를 지정합니다.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"`를 시스템에 실제 존재하는 폴더 경로로 교체하세요.

### 단계 2: **Create vector layer**
`Create` 메서드를 사용해 `VectorLayer`를 엽니다. 이것이 **create vector layer** 작업의 핵심입니다.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### 단계 3: 새 피처 구성
피처는 레이어 안에 저장되는 단일 공간 레코드를 나타냅니다.

```csharp
    var feature = layer.ConstructFeature();
```

### 단계 4: 원형 문자열 지오메트리 구축
곡선 형태를 정의하는 점들을 추가합니다. 점들의 순서가 동일한 위치에서 시작하고 끝나는 호를 만들며, 이를 통해 닫힌 원형 문자열이 생성됩니다.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### 단계 5: 지오메트리를 할당하고 피처를 레이어에 추가
지오메트리를 피처에 연결하고 레이어에 저장합니다.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` 블록이 종료되면 레이어는 자동으로 디스크에 있는 Shapefile로 플러시됩니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **File path invalid** | 디렉터리가 존재하고 쓰기 권한이 있는지 확인하세요. |
| **CircularString appears as a straight line** | 점이 올바른 순서로 추가되었는지 확인하세요; 닫힌 형태를 만들려면 첫 번째와 마지막 점이 동일해야 합니다. |
| **License exception** | 개발 중에는 임시 라이선스를 적용하고, 프로덕션에서는 정식 라이선스를 구매하세요. |

## 자주 묻는 질문

### Aspose.GIS for .NET은 모든 .NET Framework 버전과 호환되나요?
예, Aspose.GIS for .NET은 Framework 4.5부터 최신 .NET 8까지 다양한 .NET 버전에서 동작하도록 설계되었습니다.

### Aspose.GIS for .NET을 다른 GIS 라이브러리와 통합할 수 있나요?
물론입니다! 다른 라이브러리로 데이터를 읽고, Aspose.GIS로 조작한 뒤, 다시 저장할 수 있습니다. 유연한 API 덕분에 쉽게 연동할 수 있습니다.

### Aspose.GIS for .NET은 공간 데이터 시각화를 지원하나요?
예, 라이브러리에는 지도와 지오메트리의 시각적 표현을 생성할 수 있는 렌더링 유틸리티가 포함되어 있습니다.

### Aspose.GIS for .NET에 대한 지원을 받을 수 있는 커뮤니티 포럼이 있나요?
예, 질문을 올리고 경험을 공유할 수 있는 Aspose.GIS 포럼 **[here](https://forum.aspose.com/c/gis/33)**을 방문하세요.

### Aspose.GIS for .NET을 평가하기 위한 임시 라이선스를 받을 수 있나요?
물론입니다! 임시 평가 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 제공됩니다.

### 동일 레이어에 더 복잡한 지오메트리(예: MultiLineString)를 추가하려면 어떻게 해야 하나요?
해당 지오메트리 객체(`MultiLineString`)를 생성하고 개별 `LineString` 객체들을 채운 뒤, `feature.Geometry`에 할당하고 피처를 레이어에 추가하면 됩니다. 원형 문자열과 동일한 방식입니다.

## FAQ (빠른 참고)

**Q:** 프로그래밍 방식으로 **create vector layer**를 어떻게 하나요?  
**A:** `using` 블록 안에서 `VectorLayer.Create(path, Drivers.Shapefile)`(또는 다른 드라이버)를 호출합니다.

**Q:** 원형 문자열에 점을 추가하는 메서드는?  
**A:** 각 좌표마다 `circularString.AddPoint(x, y)`를 사용합니다.

**Q:** 동일 레이어에 여러 지오메트리를 저장할 수 있나요?  
**A:** 예, 각 지오메트리마다 새 피처를 만들고 `layer.Add(feature)`로 추가하면 됩니다.

**Q:** Shapefile이 생성되지 않을 때는 어떻게 해야 하나요?  
**A:** 출력 디렉터리가 존재하고 쓰기 권한이 있는지, 그리고 드라이버(`Drivers.Shapefile`)가 올바르게 지정되었는지 확인하세요.

**Q:** 평가 빌드에 라이선스가 필요하나요?  
**A:** 개발 및 테스트 단계에서는 임시 라이선스로 충분하지만, 프로덕션 배포 시에는 정식 라이선스가 필요합니다.

## 결론
이 단계들을 따라 하면 Aspose.GIS for .NET을 사용해 **벡터 레이어** 객체를 **생성하고**, **원형 문자열** 지오메트리를 추가하는 방법을 익히게 됩니다. 이를 기반으로 교통 네트워크 매핑, 환경 데이터 시각화, 맞춤형 공간 분석 도구 등 보다 풍부한 GIS 솔루션을 구축할 수 있습니다.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}