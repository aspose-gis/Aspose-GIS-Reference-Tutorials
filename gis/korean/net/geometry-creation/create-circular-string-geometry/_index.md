---
date: 2025-12-12
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 만들고 원형 스트링 기하를 추가하는 방법을 배우세요 – GIS
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

# Aspose.GIS for .NET을 사용한 벡터 레이어 및 원형 스트링 기하학 만들기

## Introduction
.NET 플랫폼에서 GIS 애플리케이션을 구축하고 있다면, 첫 번째 단계는 **벡터 레이어를 생성**하여 공간 피처를 저장하는 객체를 만드는 경우가 많습니다. Aspose.GIS for .NET은 이 과정을 간단하게 해 주며, 원형 스트링과 같은 고급 기하학으로 레이어를 풍부하게 만들 수 있습니다. 이 튜토리얼에서는 벡터 레이어를 생성하고, 원형 스트링 기하학을 추가한 뒤, 결과를 Shapefile로 저장하는 방법을 깔끔하고 프로덕션 수준의 C# 코드로 배워봅니다.

## Quick Answers
- **“벡터 레이어 생성”은 무엇을 의미하나요?** 포인트, 라인, 폴리곤과 같은 공간 피처를 담을 수 있는 새로운 컨테이너(레이어)를 생성합니다.  
- **원형 스트링을 나타내는 클래스는?** `Aspose.Gis.Geometries`의 `CircularString`.  
- **레이어를 Shapefile로 저장할 수 있나요?** 예 – 레이어를 생성할 때 `Drivers.Shapefile`을 사용합니다.  
- **개발에 라이선스가 필요하나요?** 평가용 임시 라이선스로 충분하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
벡터 레이어는 하나의 데이터 소스에 저장된 벡터 피처(포인트, 라인, 폴리곤)를 논리적으로 그룹화한 것입니다. Aspose.GIS에서는 `VectorLayer.Create`를 호출하고 대상 파일 경로와 원하는 드라이버(예: Shapefile)를 전달하여 레이어를 인스턴스화합니다. 레이어가 생성되면 피처를 추가하고, 기하학을 할당하며, 공간 연산을 수행할 수 있습니다.

## Why add a circular string?
원형 스트링은 **선형 기하학**의 일종으로, 점들의 연속을 이용해 호를 근사합니다. 곡선 도로, 강의 굽힘 등 부드러운 곡선이 필요한 경우, 많은 작은 라인 세그먼트를 사용하지 않고도 표현할 수 있어 유용합니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있어야 합니다:

- **.NET Framework 또는 .NET Core**가 머신에 설치되어 있어야 합니다.  
- **Aspose.GIS for .NET** 라이브러리 – 공식 사이트 **[here](https://releases.aspose.com/gis/net/)**에서 다운로드합니다.  
- **Visual Studio** 또는 **JetBrains Rider**와 같은 IDE.  
- **C#** 프로그래밍에 대한 기본 지식.

## Import Namespaces
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

## Step‑by‑Step Guide

### Step 1: Define the output file path
Shapefile이 기록될 위치를 설정합니다.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

`"Your Document Directory"`를 실제 시스템 폴더 경로로 교체하세요.

### Step 2: **Create vector layer**
`Create` 메서드를 사용해 `VectorLayer`를 엽니다. 이것이 **벡터 레이어 생성** 작업의 핵심입니다.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Step 3: Construct a new feature
피처는 레이어 안에 있는 단일 공간 레코드를 나타냅니다.

```csharp
    var feature = layer.ConstructFeature();
```

### Step 4: Build the circular string geometry
곡선 형태를 정의하는 점들을 추가합니다. 점들의 순서가 동일한 위치에서 시작하고 끝나는 호를 만들며, 닫힌 원형 스트링을 형성합니다.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Step 5: Assign geometry and add the feature to the layer
기하학을 피처에 연결하고 레이어에 저장합니다.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

`using` 블록이 종료되면 레이어가 자동으로 디스크의 Shapefile에 플러시됩니다.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **File path invalid** | 디렉터리가 존재하고 쓰기 권한이 있는지 확인하세요. |
| **CircularString appears as a straight line** | 점이 올바른 순서로 추가되었는지 확인하세요; 닫힌 형태를 만들려면 첫 번째와 마지막 점이 동일해야 합니다. |
| **License exception** | 개발 중에는 임시 라이선스를 적용하고, 프로덕션에서는 정식 라이선스를 구매하세요. |

## Frequently Asked Questions

### Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
예, Aspose.GIS for .NET은 Framework 4.5부터 최신 .NET 8까지 다양한 .NET 버전에서 작동하도록 설계되었습니다.

### Can I integrate Aspose.GIS for .NET with other GIS libraries?
물론입니다! 다른 라이브러리로 데이터를 읽고, Aspose.GIS로 조작한 뒤, 다시 기록할 수 있습니다. 유연한 API 덕분에 가능합니다.

### Does Aspose.GIS for .NET support spatial data visualization?
예, 라이브러리에는 지도와 기하학의 시각적 표현을 생성할 수 있는 렌더링 유틸리티가 포함되어 있습니다.

### Is there a community forum where I can seek assistance with Aspose.GIS for .NET?
예, Aspose.GIS 포럼 **[here](https://forum.aspose.com/c/gis/33)**에서 질문을 하고 경험을 공유할 수 있습니다.

### Can I obtain a temporary license to evaluate Aspose.GIS for .NET?
물론입니다! 임시 평가 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

### How do I add more complex geometries (e.g., MultiLineString) to the same layer?
적절한 기하학 객체(예: `MultiLineString`)를 생성하고, 개별 `LineString` 객체들을 채워 넣은 뒤, `feature.Geometry`에 할당하고 원형 스트링과 동일하게 피처를 추가하면 됩니다.

## Conclusion
이 단계를 따라 하면 Aspose.GIS for .NET을 사용해 **벡터 레이어** 객체를 만들고 원형 스트링 기하학으로 풍부하게 할 수 있습니다. 이 기반을 바탕으로 교통망 매핑, 환경 데이터 시각화, 맞춤형 공간 분석 도구 등 보다 풍부한 GIS 솔루션을 구축할 수 있습니다.

---

**Last Updated:** 2025-12-12  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}