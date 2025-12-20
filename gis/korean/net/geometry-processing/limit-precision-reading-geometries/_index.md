---
date: 2025-12-20
description: Aspose.GIS for .NET을 사용하여 벡터 레이어를 생성하고 지오메트리를 읽을 때 정밀도를 제한하는 방법을 배우세요.
  최적의 지리공간 데이터 처리를 위한 단계별 가이드.
linktitle: Limit Precision Reading Geometries
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET으로 벡터 레이어 생성 및 정밀도 제한
url: /ko/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.GIS for .NET을 사용하여 벡터 레이어 만들기 및 정밀도 제한

## Introduction
지리공간 데이터를 다룰 때, **벡터 레이어** 객체를 생성하고 읽는 과정에서 유지되는 숫자 상세 정도를 제어해야 할 경우가 많습니다. Aspose.GIS for .NET은 정밀도를 제한하는 작업을 간단하게 해 주며, 초고정밀도가 필요하지 않을 때 성능을 향상시키고 저장 용량을 줄일 수 있습니다. 이 튜토리얼에서는 벡터 레이어를 만드는 방법, 간단한 포인트 지오메트리를 기록하는 방법, 그리고 정확한 정밀도와 잘린 정밀도로 다시 읽는 방법을 정확히 보여줍니다.

## Quick Answers
- **“정밀도 제한”이란 무엇인가요?** 좌표 값을 정의된 소수점 자리수로 반올림합니다.  
- **왜 먼저 벡터 레이어를 생성해야 하나요?** 벡터 레이어는 포인트, 라인, 폴리곤과 같은 지오메트리를 저장하는 컨테이너입니다.  
- **사용 가능한 정밀도 모델은 무엇인가요?** `PrecisionModel.Exact` (반올림 없음) 및 `PrecisionModel.Rounding(n)` (*n* 소수점 자리수로 반올림).  
- **시도하려면 라이선스가 필요하나요?** 릴리스 페이지에서 무료 체험판을 제공하고 있습니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core, .NET 5/6+.

## Prerequisites
본 과정을 시작하기 전에 다음 전제 조건을 확인하십시오:
1. **Installation** – Aspose.GIS for .NET 라이브러리가 개발 환경에 설치되어 있어야 합니다. 설치되지 않은 경우 [releases page](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.
2. **Familiarity with .NET** – C# 및 .NET 프레임워크에 대한 기본 지식이 있어야 제공된 코드 예제를 이해하고 구현할 수 있습니다.
3. **Development Environment** – Visual Studio와 같은 .NET 개발 환경이 필요합니다.
4. **Document Directory** – 프로세스 중에 생성되는 shapefile을 저장하고 접근할 수 있는 디렉터리를 준비하십시오.

## Import Namespaces
지오메트리를 읽을 때 정밀도를 제한하는 기능을 구현하기 전에 필요한 네임스페이스를 가져오는지 확인합니다:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to Create Vector Layer
첫 번째 단계는 우리 지오메트리를 보관할 **벡터 레이어**를 **생성**하는 것입니다. 이 레이어는 Shapefile 형태로 저장되며, 이후 다른 정밀도 설정으로 다시 열 수 있습니다.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## Setting Precision Options
다음으로, 원하는 정밀도 모델을 지정하여 지오메트리를 읽는 옵션을 정의해야 합니다. 먼저 정확한 정밀도로 시작해 보겠습니다:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## Reading Geometries with Exact Precision
이제 지정한 옵션을 사용해 벡터 레이어를 열고 정확한 정밀도로 지오메트리를 읽어 보겠습니다:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Truncating Precision
정밀도를 특정 소수점 자리수로 잘라내고 싶다면, 정밀도 모델을 그에 맞게 조정하면 됩니다:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## Common Issues and Solutions
- **예상치 못한 좌표 값** – 레이어를 열기 **전** `options.XYPrecisionModel`을 설정했는지 확인하십시오. 열고 난 후에 변경해도 효과가 없습니다.
- **파일을 찾을 수 없음** – `path` 변수가 유효한 디렉터리를 가리키는지, 그리고 이전 단계에서 Shapefile이 정상적으로 생성되었는지 확인하십시오.
- **잘못된 지오메트리 유형** – 예제는 `Point`를 사용합니다. 다른 지오메트리 유형(예: `LineString`)을 사용할 경우 캐스팅이 실제 유형과 일치하도록 해야 합니다.

## Conclusion
결론적으로, 지오메트리를 읽을 때 정밀도를 관리하는 것은 지리공간 데이터 조작에서 중요한 요소입니다. Aspose.GIS for .NET은 이를 효율적으로 수행할 수 있는 강력한 기능을 제공합니다. 이 튜토리얼에 제시된 단계를 따르면 **벡터 레이어** 객체를 원활히 **생성**하고 요구 사항에 맞게 정밀도를 제한하여 애플리케이션에서 최적의 데이터 처리를 보장할 수 있습니다.

## FAQ's
### Aspose.GIS for .NET을 .NET Core 또는 .NET Standard와 같은 다른 .NET 프레임워크와 함께 사용할 수 있나요?
예, Aspose.GIS for .NET은 .NET Core 및 .NET Standard를 포함한 다양한 .NET 프레임워크와 호환됩니다.  
### Aspose.GIS for .NET의 체험판 버전이 제공되나요?
예, [releases page](https://releases.aspose.com/)에서 무료 체험판을 받을 수 있습니다.  
### Aspose.GIS for .NET에 대한 포괄적인 문서는 어디서 찾을 수 있나요?
자세한 정보와 예제는 [documentation](https://reference.aspose.com/gis/net/)을 참고하십시오.  
### Aspose.GIS for .NET의 임시 라이선스는 어떻게 얻을 수 있나요?
임시 라이선스는 Aspose.GIS용 [purchase page](https://purchase.aspose.com/temporary-license/)에서 구매할 수 있습니다.  
### Aspose.GIS for .NET에 대한 지원이나 도움을 어디서 받을 수 있나요?
질문, 토론, 지원이 필요하면 Aspose.GIS [forum](https://forum.aspose.com/c/gis/33)을 방문하십시오.

## Frequently Asked Questions
**Q: 정밀도 제한이 원본 shapefile에 영향을 미치나요?**  
A: 아니요. 정밀도는 지오메트리를 읽을 때만 적용되며, 원본 파일은 변경되지 않습니다.  

**Q: X와 Y 좌표에 서로 다른 정밀도 모델을 사용할 수 있나요?**  
A: 현재 Aspose.GIS는 두 축에 동일한 `XYPrecisionModel`을 적용합니다.  

**Q: 사용자 정의 반올림 함수를 설정할 수 있나요?**  
A: API는 기본 제공 `PrecisionModel.Rounding(int)` 메서드만 지원합니다. 사용자 정의 로직이 필요하면 읽은 후 좌표를 별도로 처리해야 합니다.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}