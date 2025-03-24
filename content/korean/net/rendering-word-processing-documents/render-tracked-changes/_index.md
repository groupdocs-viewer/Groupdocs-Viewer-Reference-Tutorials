---
title: 추적된 변경 사항 렌더링
linktitle: 추적된 변경 사항 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 문서에서 추적된 변경 사항을 손쉽게 렌더링하는 방법을 알아보세요. 문서 관리 효율성을 높여보세요.
weight: 10
url: /ko/net/rendering-word-processing-documents/render-tracked-changes/
---

# 추적된 변경 사항 렌더링

## 소개
오늘날의 디지털 시대에 문서를 효율적으로 관리하고 보는 것은 기업과 개인 모두에게 중요합니다. 고급 기술의 출현으로 .NET용 GroupDocs.Viewer와 같은 솔루션은 Word 문서, PDF 등을 포함한 다양한 문서 형식과 상호 작용하는 방식에 혁명을 일으켰습니다. 이 포괄적인 가이드에서는 .NET용 GroupDocs.Viewer를 활용하여 문서에서 추적된 변경 내용을 원활하게 렌더링하는 방법을 자세히 살펴보겠습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치합니다.[웹사이트](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 시스템에 .NET Framework가 설치되어 있는지 확인하십시오.
3. 문서 디렉터리: 문서가 저장될 디렉터리를 준비합니다.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 프로젝트로 가져옵니다. 이러한 네임스페이스는 GroupDocs.Viewer 기능을 효과적으로 활용하는 데 필수적입니다.
## 단계:
1. IDE 열기: Visual Studio와 같이 선호하는 IDE(통합 개발 환경)를 시작합니다.
2. 프로젝트 만들기 또는 열기: 새 프로젝트를 시작하거나 GroupDocs.Viewer를 사용하려는 기존 프로젝트를 엽니다.
3. 네임스페이스 가져오기: 프로젝트 파일 또는 코드 파일 내에 다음 네임스페이스를 추가합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 제공된 예제를 여러 단계로 나누어 .NET용 GroupDocs.Viewer를 사용하여 추적된 변경 내용을 렌더링하는 과정을 안내하겠습니다.
## 1단계: 출력 디렉터리 설정
먼저 렌더링된 출력을 저장할 디렉터리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"`원하는 디렉토리의 경로로.
## 2단계: 페이지 파일 경로 형식 정의
페이지 파일 경로의 형식을 지정합니다. 이 형식은 렌더링된 페이지의 이름을 지정하고 저장하는 방법을 결정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 여기,`"page_{0}.html"` 페이지 이름이 다음과 같이 지정됨을 나타냅니다.`page_1.html`, `page_2.html`, 등등.
## 3단계: 뷰어 개체 초기화
 초기화`Viewer` 문서의 경로를 인수로 전달하여 개체를 지정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // 코드는 다음 단계에서 계속됩니다...
}
```
 반드시 교체하세요`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` 문서의 경로와 함께.
## 4단계: HTML 보기 옵션 구성
추적된 변경 사항 렌더링과 같은 렌더링 설정을 사용자 정의하려면 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
이 단계를 통해 출력 HTML에서 추적된 변경 내용을 렌더링할 수 있습니다.
## 5단계: 문서 렌더링
구성된 옵션을 사용하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
이 명령은 제공된 설정을 기반으로 렌더링 프로세스를 시작합니다.
## 6단계: 출력 디렉터리 표시
렌더링된 출력이 저장되는 위치를 사용자에게 알립니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 메시지는 사용자에게 성공적인 렌더링과 출력 파일을 찾을 수 있는 위치를 알려줍니다.

## 결론
결론적으로, .NET용 GroupDocs.Viewer는 문서에서 추적된 변경 사항을 쉽게 렌더링할 수 있는 강력한 솔루션을 제공합니다. 이 문서에 설명된 단계별 가이드를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 관리 효율성을 높일 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer를 사용하여 추적된 변경 사항을 다양한 문서 형식으로 렌더링할 수 있습니까?
예, GroupDocs.Viewer는 DOCX, PDF 등을 포함한 다양한 형식의 추적된 변경 내용 렌더링을 지원합니다.
### .NET용 GroupDocs.Viewer는 모든 .NET Framework 버전과 호환됩니까?
예, .NET용 GroupDocs.Viewer는 다양한 버전의 .NET Framework와 호환되므로 광범위한 호환성이 보장됩니다.
### GroupDocs.Viewer는 테스트 목적으로 무료 평가판을 제공합니까?
예, 구매 결정을 내리기 전에 GroupDocs.Viewer의 무료 평가판을 사용하여 기능을 살펴볼 수 있습니다.
### 특정 요구 사항을 충족하도록 렌더링 설정을 사용자 정의할 수 있습니까?
물론, GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 필요에 따라 렌더링 프로세스를 조정할 수 있습니다.
### GroupDocs.Viewer에 대해 문제가 발생하거나 질문이 있는 경우 어디서 도움을 구할 수 있습니까?
 지원 및 커뮤니티 지원을 받으려면 GroupDocs.Viewer 포럼을 방문하세요.[이 링크](https://forum.groupdocs.com/c/viewer/9).