---
title: 특정 CAD 형식 렌더링(CF2)
linktitle: 특정 CAD 형식 렌더링(CF2)
second_title: GroupDocs.Viewer .NET API
description: .NET용 Groupdocs.Viewer를 사용하여 CF2와 같은 특정 CAD 형식을 HTML, JPG, PNG 및 PDF로 렌더링하는 방법을 알아보세요.
weight: 12
url: /ko/net/rendering-cad-drawings/render-specific-cad-formats/
---
## 소개
이 자습서에서는 .NET용 Groupdocs.Viewer를 사용하여 특정 CAD 형식을 렌더링하는 방법을 살펴보겠습니다. Groupdocs.Viewer는 개발자가 외부 소프트웨어를 설치하지 않고도 응용 프로그램에 170개 이상의 문서 유형을 표시할 수 있는 강력한 문서 뷰어 API입니다. 특히 CF2와 같은 CAD 형식을 HTML, JPG, PNG 및 PDF와 같은 다양한 출력 형식으로 렌더링하는 데 중점을 둘 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 Visual Studio가 설치되어 있습니다.
-  .NET SDK용 Groupdocs.Viewer. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
- C# 프로그래밍 언어에 대한 기본 지식.
## 네임스페이스 가져오기
먼저 CAD 형식을 렌더링하는 데 필요한 필수 네임스페이스를 가져옵니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
이제 각 예를 여러 단계로 나누어 보겠습니다.
## CF2를 HTML로 렌더링
### 1단계: 렌더링된 HTML이 저장될 출력 디렉터리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2단계: HTML 출력의 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### 3단계: 뷰어 개체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션 설정
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 JPG로 렌더링
### 1단계: JPG 출력의 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### 2단계: 뷰어 개체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션 설정
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 PNG로 렌더링

### 1단계: PNG 출력의 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### 2단계: 뷰어 개체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션 설정
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 PDF로 렌더링
### 1단계: PDF 출력의 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### 2단계: 뷰어 개체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션 설정
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## 결론
이 튜토리얼에서는 .NET용 Groupdocs.Viewer를 사용하여 CF2와 같은 특정 CAD 형식을 렌더링하는 방법을 배웠습니다. 단계별 가이드를 따르면 문서 렌더링 기능을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.
## FAQ
### Groupdocs.Viewer는 CF2 이외의 다른 CAD 형식을 렌더링할 수 있습니까?
예, Groupdocs.Viewer는 DWG, DXF, DGN 등을 포함한 광범위한 CAD 형식을 지원합니다.
### Groupdocs.Viewer는 웹 응용 프로그램에서 문서를 렌더링하는 데 적합합니까?
물론, Groupdocs.Viewer는 브라우저에서 직접 문서를 렌더링하기 위해 웹 응용 프로그램에 원활하게 통합될 수 있습니다.
### Groupdocs.Viewer에는 렌더링을 위해 외부 종속성이 필요합니까?
아니요, Groupdocs.Viewer는 독립형 API이므로 외부 종속성이나 소프트웨어 설치가 필요하지 않습니다.
### 내 요구 사항에 따라 렌더링 옵션을 사용자 정의할 수 있습니까?
예, Groupdocs.Viewer는 특정 요구 사항에 맞게 사용자 정의할 수 있는 다양한 렌더링 옵션을 제공합니다.
### Groupdocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 Groupdocs.Viewer의 무료 평가판을 받을 수 있습니다.[여기](https://releases.groupdocs.com/).