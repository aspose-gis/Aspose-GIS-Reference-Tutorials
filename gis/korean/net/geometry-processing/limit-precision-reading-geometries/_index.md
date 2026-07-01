---
date: 2026-04-03
description: Aspose.GIS for .NET를 사용하여 벡터 레이어를 생성하고 지오메트리를 읽을 때 정밀도를 제한하는 방법을 배웁니다.
  최적의 지리공간 데이터 처리를 위한 단계별 가이드.
keywords:
- create vector layer
- reduce shapefile size
- set precision model
linktitle: 정밀도 제한 지오메트리 읽기
second_title: Aspose.GIS .NET API
title: Aspose.GIS for .NET으로 벡터 레이어 만들기 및 정밀도 제한
url: /ko/net/geometry-processing/limit-precision-reading-geometries/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 벡터 레이어 만들기, Aspose.GIS for .NET으로 정밀도 제한

## 소개
지리공간 데이터를 다룰 때, 종종 **벡터 레이어 만들기** 객체를 생성하고 좌표 세부 사항의 소수점 자리수를 얼마나 사용할지 결정해야 합니다. 정밀도를 제한하면 처리 속도가 빨라질 뿐만 아니라 **shapefile 크기 감소** 할 수 있어 저장 및 전송이 더 효율적입니다. 이 튜토리얼에서는 벡터 레이어를 생성하고, 간단한 포인트 기하를 작성한 다음, 정확한 정밀도 모델과 반올림 정밀도 모델을 모두 사용하여 다시 읽는 과정을 살펴봅니다. 마지막까지 읽으면 애플리케이션의 정확도 요구 사항에 맞는 **정밀도 모델 설정** 옵션을 이해하게 됩니다.

## 빠른 답변
- **“정밀도 제한”은 무엇을 의미합니까?** 좌표 값을 정의된 소수점 자리수로 반올림합니다.  
- **왜 먼저 벡터 레이어를 생성해야 합니까?** 벡터 레이어는 포인트, 라인, 폴리곤과 같은 기하를 저장하는 컨테이너입니다.  
- **사용 가능한 정밀도 모델은 무엇입니까?** `PrecisionModel.Exact` (반올림 없음) 및 `PrecisionModel.Rounding(n)` (*n* 소수점 자리수로 반올림).  
- **이것을 시도하려면 라이선스가 필요합니까?** 무료 체험판은 릴리스 페이지에서 제공됩니다.  
- **지원되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core, and .NET 5/6+.

## 왜 정밀도를 제한하고 어떻게 도움이 됩니까?
- **성능 향상** – 자리수가 적을수록 파싱 및 직렬화할 데이터가 줄어듭니다.  
- **파일 크기 감소** – 좌표를 반올림하면 특히 대규모 데이터셋에서 shapefile 크기가 눈에 띄게 줄어들 수 있습니다.  
- **충분한 정확도** – 많은 GIS 분석은 서브밀리미터 정밀도를 필요로 하지 않으므로 2‑3 소수점 자리수로 반올림해도 충분합니다.

## 전제 조건
이 과정을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:
1. **설치** – Aspose.GIS for .NET 라이브러리가 개발 환경에 설치되어 있어야 합니다. 설치되지 않은 경우 [releases page](https://releases.aspose.com/gis/net/)에서 다운로드할 수 있습니다.
2. **.NET에 대한 친숙도** – C# 및 .NET 프레임워크에 대한 기본 지식이 제공된 코드 예제를 이해하고 구현하는 데 필요합니다.
3. **개발 환경** – Visual Studio와 같은 .NET 개발 환경이 필요합니다.
4. **문서 디렉터리** – 프로세스 중에 생성된 shapefile을 저장하고 액세스할 수 있는 디렉터리를 설정하십시오.

## 네임스페이스 가져오기
기하를 읽을 때 정밀도를 제한하는 기능을 구현하기 전에 필요한 네임스페이스를 가져오는지 확인합시다:
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

## 벡터 레이어 만드는 방법
첫 번째 단계는 우리 기하를 보관할 **벡터 레이어 만들기** 입니다. 이 레이어는 Shapefile로 저장되어 나중에 다른 정밀도 설정으로 다시 열 수 있습니다.
```csharp
string path = "Your Document Directory" + "LimitPrecisionWhenReadingGeometries_out.shp";
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
	var feature = layer.ConstructFeature();
	feature.Geometry = new Point(1.10234, 2.09743);
	layer.Add(feature);
}
```

## 정밀도 옵션 설정
다음으로, 기하를 읽기 위한 옵션을 정의하고 원하는 정밀도 모델을 지정해야 합니다. 정확한 정밀도로 시작할 수 있습니다:
```csharp
var options = new ShapefileOptions();
// read data as‑is.
options.XYPrecisionModel = PrecisionModel.Exact;
```

## 정확한 정밀도로 기하 읽기
이제 지정된 옵션으로 벡터 레이어를 열어 정확한 정밀도로 기하를 읽어봅시다:
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.10234, 2.09743
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 정밀도 절단
정밀도를 특정 소수점 자리수로 절단하려면 정밀도 모델을 그에 맞게 조정할 수 있습니다:
```csharp
options.XYPrecisionModel = PrecisionModel.Rounding(2);
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile, options))
{
	var point = (IPoint)layer[0].Geometry;
	// 1.1, 2.1
	Console.WriteLine("{0}, {1}", point.X, point.Y);
}
```

## 다양한 시나리오에 대한 정밀도 모델 설정 방법
`Exact`와 `Rounding`을 언제 사용해야 할지 궁금할 수 있습니다. 다음은 두 가지 일반적인 시나리오입니다:

| 시나리오 | 권장 모델 | 이유 |
|----------|-------------------|--------|
| 고정밀 과학 분석 | `PrecisionModel.Exact` | 좌표 세부 정보 손실 없음 |
| 웹 매핑 타일 또는 모바일 앱 | `PrecisionModel.Rounding(2)` | 파일 크기를 줄이고 렌더링 속도를 높임 |

올바른 모델을 선택하는 것은 정확도와 성능의 균형을 맞추는 **정밀도 모델 설정** 의사결정 과정의 일부입니다.

## 일반적인 문제 및 해결책
- **예상치 못한 좌표 값** – 레이어를 열기 *앞에* `options.XYPrecisionModel`을 설정했는지 확인하십시오. 열고 난 후에 변경해도 효과가 없습니다.  
- **파일을 찾을 수 없음** – `path` 변수가 유효한 디렉터리를 가리키고 이전 단계에서 Shapefile이 성공적으로 생성되었는지 확인하십시오.  
- **잘못된 기하 유형** – 예제는 `Point`를 사용합니다. 다른 기하 유형(예: `LineString`)의 경우 캐스팅이 실제 유형과 일치해야 합니다.  

## Shapefile 크기 감소를 위한 팁
- `PrecisionModel.Rounding`을 사용하여 정확도 요구 사항을 충족하는 최소 소수점 자리수를 선택하십시오.  
- 레이어를 쓰기 전에 불필요한 속성 필드를 제거하십시오.  
- 전송이 필요할 경우 표준 ZIP 유틸리티를 사용해 결과 `.shp`, `.shx`, `.dbf` 파일을 압축하십시오.

## 결론
결론적으로, 기하를 읽을 때 정밀도를 관리하는 것은 지리공간 데이터 조작의 중요한 측면입니다. Aspose.GIS for .NET은 이를 효율적으로 달성할 수 있는 강력한 기능을 제공합니다. 위 단계들을 따르면 **벡터 레이어 만들기** 객체를 원활히 생성하고, **정밀도 모델 설정**을 수행하며, 필요에 따라 **shapefile 크기 감소**도 할 수 있어 애플리케이션에서 최적의 데이터 처리를 보장합니다.

## FAQ
### Aspose.GIS for .NET을 .NET Core 또는 .NET Standard와 같은 다른 .NET 프레임워크와 함께 사용할 수 있나요?
예, Aspose.GIS for .NET은 .NET Core 및 .NET Standard를 포함한 다양한 .NET 프레임워크와 호환됩니다.

### Aspose.GIS for .NET용 체험판이 제공됩니까?
예, [releases page](https://releases.aspose.com/)에서 무료 체험판을 받을 수 있습니다.

### Aspose.GIS for .NET에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?
자세한 정보와 예제는 [documentation](https://reference.aspose.com/gis/net/)을 참고하십시오.

### Aspose.GIS for .NET의 임시 라이선스는 어떻게 얻을 수 있나요?
임시 라이선스는 Aspose.GIS의 [purchase page](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

### Aspose.GIS for .NET에 대한 지원이나 도움은 어디에서 받을 수 있나요?
문의, 토론 또는 지원이 필요하면 Aspose.GIS [forum](https://forum.aspose.com/c/gis/33)을 방문하십시오.

## 자주 묻는 질문
**Q: 정밀도 제한이 원본 shapefile에 영향을 줍니까?**  
A: 아니요. 정밀도는 기하를 읽을 때만 적용되며, 원본 파일은 변경되지 않습니다.

**Q: X와 Y 좌표에 서로 다른 정밀도 모델을 사용할 수 있나요?**  
A: Aspose.GIS는 현재 두 축에 동일한 `XYPrecisionModel`을 적용합니다.

**Q: 사용자 정의 반올림 함수를 설정할 수 있나요?**  
A: API는 내장된 `PrecisionModel.Rounding(int)` 메서드만 지원합니다. 사용자 정의 로직이 필요하면 읽은 후 좌표를 후처리해야 합니다.

---

**마지막 업데이트:** 2026-04-03  
**테스트 환경:** Aspose.GIS 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}