---
"description": "Groupdocs.Viewer for .NET을 사용하여 CF2와 같은 특정 CAD 형식을 HTML, JPG, PNG, PDF로 렌더링하는 방법을 알아보세요."
"linktitle": "렌더링 특정 CAD 형식(CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "렌더링 특정 CAD 형식(CF2)"
"url": "/ko/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
type: docs
---
# 렌더링 특정 CAD 형식(CF2)

## 소개
이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 특정 CAD 형식을 렌더링하는 방법을 살펴보겠습니다. Groupdocs.Viewer는 개발자가 외부 소프트웨어를 설치하지 않고도 애플리케이션에서 170개 이상의 문서 유형을 표시할 수 있도록 해주는 강력한 문서 뷰어 API입니다. 특히 CF2와 같은 CAD 형식을 HTML, JPG, PNG, PDF 등 다양한 출력 형식으로 렌더링하는 방법을 중점적으로 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기에 앞서 다음 필수 조건이 충족되었는지 확인하세요.
- 시스템에 Visual Studio가 설치되어 있어야 합니다.
- .NET SDK용 Groupdocs.Viewer입니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
- C# 프로그래밍 언어에 대한 기본 지식.
## 네임스페이스 가져오기
먼저, CAD 형식을 렌더링하는 데 필요한 네임스페이스를 가져오겠습니다.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
이제 각 예를 여러 단계로 나누어 보겠습니다.
## CF2를 HTML로 렌더링
### 1단계: 렌더링된 HTML이 저장될 출력 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2단계: HTML 출력에 대한 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### 3단계: 뷰어 객체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션을 설정하세요
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 JPG로 렌더링
### 1단계: JPG 출력에 대한 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### 2단계: 뷰어 객체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션을 설정하세요
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 PNG로 렌더링

### 1단계: PNG 출력에 대한 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### 2단계: 뷰어 객체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션을 설정하세요
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2를 PDF로 렌더링
### 1단계: PDF 출력에 대한 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### 2단계: 뷰어 객체를 초기화하고 입력 CF2 파일을 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // 필요한 경우 추가 렌더링 옵션을 설정하세요
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## 결론
이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 CF2와 같은 특정 CAD 형식을 렌더링하는 방법을 알아보았습니다. 단계별 가이드를 따라 하면 문서 렌더링 기능을 .NET 애플리케이션에 쉽게 통합할 수 있습니다.
## 자주 묻는 질문
### Groupdocs.Viewer는 CF2 외의 다른 CAD 형식을 렌더링할 수 있나요?
네, Groupdocs.Viewer는 DWG, DXF, DGN 등 다양한 CAD 형식을 지원합니다.
### Groupdocs.Viewer는 웹 애플리케이션에서 문서를 렌더링하는 데 적합합니까?
물론입니다. Groupdocs.Viewer는 웹 애플리케이션에 완벽하게 통합되어 브라우저에서 바로 문서를 렌더링할 수 있습니다.
### Groupdocs.Viewer는 렌더링을 위해 외부 종속성이 필요합니까?
아니요, Groupdocs.Viewer는 독립형 API이므로 외부 종속성이나 소프트웨어 설치가 필요하지 않습니다.
### 내 요구 사항에 맞게 렌더링 옵션을 사용자 정의할 수 있나요?
네, Groupdocs.Viewer는 사용자의 특정 요구 사항에 맞게 사용자 정의할 수 있는 다양한 렌더링 옵션을 제공합니다.
### Groupdocs.Viewer의 평가판이 있나요?
예, Groupdocs.Viewer의 무료 평가판을 받을 수 있습니다. [여기](https://releases.groupdocs.com/).