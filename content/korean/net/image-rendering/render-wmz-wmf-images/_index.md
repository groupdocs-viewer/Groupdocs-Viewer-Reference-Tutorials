---
title: WMZ 및 WMF 이미지 렌더링
linktitle: WMZ 및 WMF 이미지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램에서 WMZ 및 WMF 이미지를 쉽게 렌더링할 수 있습니다. 문서 처리 기능을 쉽게 향상하세요.
weight: 18
url: /ko/net/image-rendering/render-wmz-wmf-images/
---
## 소개

소프트웨어 개발 영역에서는 다양한 문서 형식을 효율적으로 처리하고 렌더링하는 것이 무엇보다 중요합니다. .NET용 GroupDocs.Viewer는 다양한 문서 형식의 렌더링을 용이하게 하여 .NET 응용 프로그램 내에서 원활한 통합과 향상된 사용자 경험을 보장하는 강력한 도구입니다. 그 기능 중에는 문서 처리 시나리오에서 자주 접하는 작업인 WMZ 및 WMF 이미지 렌더링이 있습니다.

## 전제조건

.NET용 GroupDocs.Viewer를 사용하여 WMZ 및 WMF 이미지의 렌더링 프로세스를 시작하기 전에 충족해야 할 몇 가지 전제 조건이 있습니다.

1.  .NET용 GroupDocs.Viewer 설치: 제공된 파일에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치하여 시작합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/). 올바른 설정을 위해 설치 지침을 따르십시오.

2.  라이센스 취득: .NET용 GroupDocs.Viewer를 활용하려면 라이센스를 취득해야 합니다. 다음 중 하나에서 임시 라이센스를 선택할 수 있습니다.[임시 라이센스 페이지](https://purchase.groupdocs.com/temporary-license/) 또는 다음 사이트에서 정식 라이센스를 구매하세요.[구매 페이지](https://purchase.groupdocs.com/buy).

3. .NET 환경에 대한 지식: 렌더링 프로세스를 효과적으로 구현하려면 .NET 프레임워크 및 C# 프로그래밍 언어에 대한 기본적인 이해가 필수적입니다.

4.  프로젝트에 통합: .NET용 GroupDocs.Viewer가 .NET 프로젝트에 제대로 통합되었는지 확인하세요. 통합에 대한 자세한 지침은 설명서를 참조하세요.[선적 서류 비치](https://tutorials.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기

렌더링 프로세스를 진행하기 전에 필요한 네임스페이스를 C# 코드로 가져오는 것이 중요합니다. 이러한 네임스페이스는 WMZ 및 WMF 이미지를 렌더링하는 데 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

이제 전제 조건을 다루고 필수 네임스페이스를 가져왔으므로 렌더링 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: WMZ 이미지를 HTML로 렌더링

WMZ 이미지를 HTML 형식으로 렌더링하려면 다음 단계를 따르세요.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.html");

// HTML로
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

## 2단계: WMZ 이미지를 JPG로 렌더링

WMZ 이미지를 JPG 형식으로 렌더링하려면 다음을 수행하십시오.

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 3단계: WMZ 이미지를 PNG로 렌더링

WMZ 이미지를 PNG 형식으로 렌더링하려면 다음 지침을 따르십시오.

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 4단계: WMZ 이미지를 PDF로 렌더링

WMZ 이미지를 PDF 형식으로 렌더링하려면 다음을 수행하십시오.

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 결론

결론적으로 .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 WMZ 및 WMF 이미지를 쉽게 렌더링할 수 있는 포괄적인 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 렌더링 기능을 프로젝트에 원활하게 통합하여 문서 처리 기능을 향상시킬 수 있습니다.

## FAQ

### 질문 1: .NET용 GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?

A1: .NET용 GroupDocs.Viewer는 .NET Core 및 .NET Framework를 포함한 광범위한 .NET 프레임워크와 호환됩니다.

### Q2: WMZ 및 WMF 이미지의 렌더링 옵션을 사용자 정의할 수 있습니까?

A2: 예, .NET용 GroupDocs.Viewer는 이미지 렌더링을 위한 광범위한 사용자 정의 옵션을 제공하므로 요구 사항에 따라 출력을 조정할 수 있습니다.

### 질문 3: .NET용 GroupDocs.Viewer에 대한 기술 지원이 제공됩니까?

 A3: 예, 전용 사이트를 통해 .NET용 GroupDocs.Viewer에 대한 기술 지원에 액세스할 수 있습니다.[지원 포럼](https://forum.groupdocs.com/c/viewer/9).

### 질문 4: .NET용 GroupDocs.Viewer는 모바일 장치에서 문서 보기를 지원합니까?

A4: 예, .NET용 GroupDocs.Viewer는 반응형 문서 보기 기능을 제공하여 휴대폰 및 태블릿을 포함한 다양한 장치에서 최적의 성능을 보장합니다.

### 질문 5: 구매하기 전에 .NET용 GroupDocs.Viewer를 사용해 볼 수 있습니까?

 A5: 예, 무료 평가판에 액세스하여 .NET용 GroupDocs.Viewer의 기능을 탐색할 수 있습니다.[여기](https://releases.groupdocs.com/).