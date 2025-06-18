---
"description": "GroupDocs.Viewer for .NET을 사용하여 문서의 변경 사항 추적을 손쉽게 구현하는 방법을 알아보세요. 문서 관리 효율성을 높여 보세요."
"linktitle": "추적된 변경 사항 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "추적된 변경 사항 렌더링"
"url": "/ko/net/rendering-word-processing-documents/render-tracked-changes/"
"weight": 10
---

# 추적된 변경 사항 렌더링

## 소개
오늘날의 디지털 시대에는 기업과 개인 모두에게 문서를 효율적으로 관리하고 확인하는 것이 매우 중요합니다. 첨단 기술의 등장으로 GroupDocs.Viewer for .NET과 같은 솔루션은 Word 문서, PDF 등 다양한 문서 형식을 사용하는 방식에 혁신을 가져왔습니다. 이 종합 가이드에서는 GroupDocs.Viewer for .NET을 활용하여 문서의 추적된 변경 내용을 원활하게 표시하는 방법을 자세히 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 필수 조건을 충족하는지 확인하세요.
1. .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [웹사이트](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: 시스템에 .NET Framework가 설치되어 있는지 확인하세요.
3. 문서 디렉토리: 문서를 저장할 디렉토리를 준비하세요.

## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 프로젝트에 가져오세요. 이러한 네임스페이스는 GroupDocs.Viewer 기능을 효과적으로 활용하는 데 필수적입니다.
## 단계:
1. IDE 열기: Visual Studio 등 원하는 통합 개발 환경(IDE)을 실행합니다.
2. 프로젝트 만들기 또는 열기: GroupDocs.Viewer를 사용할 새 프로젝트를 시작하거나 기존 프로젝트를 엽니다.
3. 네임스페이스 가져오기: 프로젝트 파일이나 코드 파일 내에 다음 네임스페이스를 추가합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 제공된 예제를 여러 단계로 나누어 .NET용 GroupDocs.Viewer를 사용하여 추적된 변경 사항을 렌더링하는 방법을 안내해 보겠습니다.
## 1단계: 출력 디렉토리 설정
먼저, 렌더링된 출력을 저장할 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 원하는 디렉토리 경로를 입력하세요.
## 2단계: 페이지 파일 경로 형식 정의
페이지 파일 경로의 형식을 지정합니다. 이 형식은 렌더링된 페이지의 이름과 저장 방식을 결정합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
여기, `"page_{0}.html"` 페이지 이름이 다음과 같이 지정됨을 나타냅니다. `page_1.html`, `page_2.html`, 등등.
## 3단계: 뷰어 객체 초기화
초기화 `Viewer` 문서의 경로를 인수로 전달하여 객체를 생성합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // 코드는 다음 단계에서 계속됩니다...
}
```
교체를 확인하세요 `TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` 문서 경로를 포함합니다.
## 4단계: HTML 보기 옵션 구성
추적된 변경 사항 렌더링과 같은 렌더링 설정을 사용자 지정하기 위해 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
이 단계에서는 추적된 변경 사항을 출력 HTML에 렌더링할 수 있습니다.
## 5단계: 문서 렌더링
구성된 옵션을 사용하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
이 명령은 제공된 설정에 따라 렌더링 프로세스를 시작합니다.
## 6단계: 출력 디렉토리 표시
렌더링된 출력이 저장된 위치를 사용자에게 알려줍니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 메시지는 사용자에게 렌더링이 성공적으로 완료되었음을 알리고 출력 파일을 찾을 수 있는 위치를 알려줍니다.

## 결론
결론적으로, GroupDocs.Viewer for .NET은 문서의 변경 사항 추적을 손쉽게 렌더링하는 강력한 솔루션을 제공합니다. 이 문서에 설명된 단계별 가이드를 따라 하면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 관리 효율성을 향상시킬 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET을 사용하여 다양한 문서 형식의 추적된 변경 사항을 렌더링할 수 있나요?
네, GroupDocs.Viewer는 DOCX, PDF 등 다양한 형식으로 추적된 변경 내용을 렌더링하는 것을 지원합니다.
### GroupDocs.Viewer for .NET은 모든 .NET Framework 버전과 호환됩니까?
네, GroupDocs.Viewer for .NET은 다양한 버전의 .NET Framework와 호환되므로 광범위한 호환성이 보장됩니다.
### GroupDocs.Viewer는 테스트 목적으로 무료 체험판을 제공합니까?
네, GroupDocs.Viewer의 무료 체험판을 이용해 구매 결정을 내리기 전에 기능을 체험해 보실 수 있습니다.
### 특정 요구 사항을 충족하도록 렌더링 설정을 사용자 정의할 수 있나요?
물론입니다. GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 사용자의 요구 사항에 맞게 렌더링 프로세스를 조정할 수 있습니다.
### GroupDocs.Viewer에 관해 문제가 발생하거나 궁금한 점이 있으면 어디에서 도움을 받을 수 있나요?
지원 및 커뮤니티 지원을 받으려면 GroupDocs.Viewer 포럼을 방문하세요. [이 링크](https://forum.groupdocs.com/c/viewer/9).