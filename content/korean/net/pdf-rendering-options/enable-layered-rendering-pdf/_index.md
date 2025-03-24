---
title: PDF에서 계층화된 렌더링 활성화
linktitle: PDF에서 계층화된 렌더링 활성화
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 계층화된 렌더링을 활성화하는 방법을 알아보세요. 손쉽게 문서 보기 경험을 향상하세요.
weight: 15
url: /ko/net/pdf-rendering-options/enable-layered-rendering-pdf/
---

# PDF에서 계층화된 렌더링 활성화

## 소개
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 계층화된 렌더링을 활성화하는 프로세스를 자세히 살펴보겠습니다. 계층화된 렌더링을 통해 향상된 문서 표시 및 조작이 가능해 사용자에게 보다 대화형 보기 환경을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET용 GroupDocs.Viewer: 프로젝트에서 .NET용 GroupDocs.Viewer를 사용하는 데 필요한 패키지나 라이브러리를 설치했는지 확인하세요.
2. Visual Studio: 제공된 예제를 코딩하고 실행하려면 시스템에 Visual Studio가 설치되어 있어야 합니다.
3. C#의 기본 이해: 이 자습서에서는 C# 프로그래밍 언어 구문 및 개념에 익숙하다고 가정합니다.

## 네임스페이스 가져오기
필요한 네임스페이스를 프로젝트로 가져오는 것부터 시작하세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 출력을 저장할 디렉터리 경로를 지정해야 합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 이 단계에서는 렌더링된 출력에서 개별 페이지의 파일 경로 형식을 설정합니다.`{0}` 페이지 번호에 대한 자리 표시자입니다.
## 3단계: 계층화된 렌더링 활성화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 여기서는`Viewer` 개체를 선택하고 처리할 PDF 문서를 지정합니다. 그런 다음 구성합니다.`HtmlViewOptions` 정의된 페이지 파일 경로 형식을 사용합니다. 설정으로`EnableLayeredRendering` 재산`true` ~에`PdfOptions`, PDF 문서에 대한 레이어 렌더링을 활성화합니다.
## 4단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로 소스 문서가 성공적으로 렌더링되었음을 나타내는 메시지를 인쇄하고 사용자에게 지정된 디렉터리의 출력을 확인하라는 메시지를 표시합니다.

## 결론
.NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 계층화된 렌더링을 활성화하면 문서 보기 기능이 향상되어 사용자에게 더욱 풍부하고 대화형 환경을 제공합니다. 이 자습서에 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### PDF 문서의 레이어 렌더링이란 무엇입니까?
계층화된 렌더링을 사용하면 PDF 문서 내의 다양한 구성 요소를 분리하고 조작할 수 있으므로 대화형 보기와 향상된 사용자 경험이 가능합니다.
### 렌더링된 문서의 출력 디렉터리를 사용자 정의할 수 있나요?
예, 요구 사항에 따라 출력에 대한 디렉터리 경로를 지정할 수 있습니다.
### GroupDocs.Viewer는 PDF 외에 다른 파일 형식을 지원합니까?
예, GroupDocs.Viewer는 Word, Excel, PowerPoint 등을 포함한 광범위한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환되나요?
예, GroupDocs.Viewer는 .NET Framework 및 .NET Core 환경 모두와 호환됩니다.
### 추가 지원이나 지원은 어디서 찾을 수 있나요?
뷰어 라이브러리에 관한 질문이나 지원이 필요하면 GroupDocs.Viewer 포럼을 방문하세요.