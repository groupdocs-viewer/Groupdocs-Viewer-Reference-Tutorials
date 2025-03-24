---
title: Visio 그림 렌더링
linktitle: Visio 그림 렌더링
second_title: GroupDocs.Viewer .NET API
description: 이 포괄적인 기능을 통해 .NET용 GroupDocs.Viewer를 사용하여 Visio 그림을 렌더링하는 방법을 알아보세요. .NET 애플리케이션의 문서 보기 기능을 향상시킵니다.
weight: 10
url: /ko/net/rendering-visio-documents/render-visio-figures/
---
## 소개
오늘날의 디지털 시대에 문서 렌더링은 다양한 응용 프로그램에서 중요한 역할을 합니다. 웹사이트에 문서를 표시하거나 다른 형식으로 변환하는 경우 효율적인 렌더링이 필수적입니다. .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 문서를 보고 조작하기 위한 강력한 솔루션을 제공합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 Visio 그림을 렌더링하는 방법을 자세히 알아보고 프로세스를 간단한 단계로 나누어 보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. 환경 설정: .NET 개발을 위한 작업 환경이 있는지 확인하십시오.
2.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3. C#의 기본 이해: C# 프로그래밍 언어 기본 사항을 숙지하세요.
4. 샘플 Visio 문서: 렌더링할 샘플 Visio 문서를 준비합니다.

## 네임스페이스 가져오기
C# 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작합니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. HTML로 렌더링
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 출력 디렉터리: 렌더링된 HTML이 저장될 디렉터리를 정의합니다.
- 페이지 파일 경로 형식: HTML 페이지의 경로 형식을 지정합니다.
- 뷰어 초기화: Visio 문서의 경로로 뷰어 개체를 초기화합니다.
- HTML 보기 옵션: HTML 렌더링 옵션을 구성합니다.
- Visio 렌더링 옵션: 그림만 렌더링, 그림 너비 등 Visio 렌더링과 관련된 옵션을 설정합니다.
## 2. JPG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- HTML로 렌더링하는 것과 유사하게 JPG 형식으로 렌더링하기 위한 옵션을 구성합니다.
## 3. PNG로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PNG 형식으로 렌더링하기 위한 구성은 JPG 렌더링과 비슷한 패턴을 따릅니다.
## 4. PDF로 렌더링
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- PDF로 렌더링하려면 PDF 형식과 관련된 옵션을 구성하세요.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 Visio 그림을 렌더링하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자 경험과 생산성을 향상시킬 수 있습니다.
## FAQ
### Visio 그림의 렌더링 옵션을 사용자 지정할 수 있나요?
예, .NET용 GroupDocs.Viewer는 그림 너비, 그림만 렌더링 등을 포함하여 렌더링을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer는 대규모 문서 렌더링에 적합합니까?
물론 .NET용 GroupDocs.Viewer는 대규모 문서 렌더링을 효율적으로 처리하는 데 최적화되어 있습니다.
### GroupDocs.Viewer는 Visio 외에 다른 문서 형식을 지원합니까?
예, GroupDocs.Viewer는 PDF, Microsoft Office, AutoCAD 등을 포함한 광범위한 문서 형식을 지원합니다.
### GroupDocs.Viewer를 웹 응용 프로그램에 통합할 수 있나요?
예, GroupDocs.Viewer는 문서 보기 및 조작을 위해 웹 응용 프로그램에 완벽하게 통합될 수 있습니다.
### 구매하기 전에 테스트할 수 있는 평가판이 있나요?
예, 무료 평가판을 이용하실 수 있습니다.[웹사이트](https://releases.groupdocs.com/) .NET용 GroupDocs.Viewer의 기능을 테스트합니다.