---
title: PDF에서 문자 그룹화 비활성화
linktitle: PDF에서 문자 그룹화 비활성화
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 PDF에서 문자 그룹화를 비활성화하는 방법을 알아보세요. 원활한 문서 렌더링을 위한 단계별 튜토리얼을 따르십시오.
weight: 11
url: /ko/net/pdf-rendering-options/disable-characters-grouping-pdf/
---
## 소개
.NET 개발 세계에서는 문서 보기를 처리하는 것이 때로 어려울 수 있으며, 특히 PDF와 같은 형식을 처리할 때 더욱 그렇습니다. 그러나 올바른 도구와 지식을 사용하면 이 프로세스를 효율적으로 간소화할 수 있습니다. 이러한 문제를 해결해주는 도구 중 하나가 .NET용 GroupDocs.Viewer입니다. 이 강력한 라이브러리를 통해 개발자는 .NET 애플리케이션 내에서 다양한 문서 유형을 원활하게 렌더링하고 표시할 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[공식 다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3. 기본 C# 지식: C# 프로그래밍 언어 기본 사항을 숙지하세요.
4. 문서 파일: PDF, 이미지 등 렌더링하려는 문서 파일을 준비합니다.

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 프로젝트로 가져오겠습니다. 이러한 네임스페이스는 GroupDocs.Viewer에서 필요한 기능에 대한 액세스를 제공합니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 제공된 예제를 관리 가능한 단계로 분석해 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
여기서는 렌더링된 HTML 페이지가 저장될 디렉터리를 저장하는 변수를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 단계에서는 문서의 각 페이지에 대해 생성된 HTML 파일의 이름을 지정하기 위한 형식을 설정합니다.
## 3단계: 뷰어 개체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.HIEROGLYPHS_PDF))
```
여기서는 렌더링하려는 PDF 파일의 경로를 전달하여 Viewer 개체를 초기화합니다.
## 4단계: HTML 보기 옵션 구성
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.PdfOptions.DisableCharsGrouping = true;
```
이 단계에서는 PDF의 문자 그룹화를 비활성화하도록 지정하여 HTML 보기 옵션을 설정합니다.
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
 마지막으로 우리는`View` 문서를 렌더링하기 위해 구성된 옵션을 전달하는 뷰어 개체의 메서드입니다.
## 6단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 단계에서는 문서가 성공적으로 렌더링되었음을 나타내는 메시지를 출력하고 출력을 찾을 수 있는 위치를 제공합니다.

## 결론
결론적으로, 이 튜토리얼에 설명된 단계를 따르면 .NET용 GroupDocs.Viewer를 사용하여 PDF 문서에서 문자 그룹화를 쉽게 비활성화할 수 있습니다. 이 라이브러리는 .NET 애플리케이션 내에서 문서 보기 및 조작 프로세스를 단순화하여 개발자에게 문서 관리 기능을 향상시킬 수 있는 강력한 도구 세트를 제공합니다.
## FAQ
### GroupDocs.Viewer는 모든 버전의 .NET과 호환됩니까?
예, GroupDocs.Viewer는 다양한 버전의 .NET과 호환되므로 유연성과 통합 용이성을 보장합니다.
### GroupDocs.Viewer를 사용하여 PDF 이외의 문서를 렌더링할 수 있습니까?
전적으로! GroupDocs.Viewer는 Microsoft Office 파일, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 공식 사이트에서 .NET용 GroupDocs.Viewer 무료 평가판에 액세스할 수 있습니다.[릴리스 페이지](https://releases.groupdocs.com/).
### GroupDocs.Viewer의 임시 라이센스를 얻으려면 어떻게 해야 합니까?
GroupDocs.Viewer의 임시 라이센스는 다음에서 얻을 수 있습니다.[임시 라이센스 페이지](https://purchase.groupdocs.com/temporary-license/).
### GroupDocs.Viewer 관련 쿼리에 대한 지원은 어디서 찾을 수 있나요?
 GroupDocs.Viewer에 관한 지원이나 도움이 필요하면 다음을 방문하세요.[공식 포럼](https://forum.groupdocs.com/c/viewer/9).