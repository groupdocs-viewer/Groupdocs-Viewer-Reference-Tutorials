---
"description": "GroupDocs.Viewer for .NET에서 리소스 로딩 시간 초과를 효율적으로 구성하는 방법을 알아보세요. 정밀하고 안정적으로 문서 렌더링을 마스터하세요."
"linktitle": "리소스 로딩 시간 초과 설정(고급)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "리소스 로딩 시간 초과 설정(고급)"
"url": "/ko/net/advanced-loading/set-resource-loading-timeout/"
"weight": 13
---

# 리소스 로딩 시간 초과 설정(고급)

## 소개
.NET 개발 분야에서 GroupDocs.Viewer는 문서와 이미지를 정확하고 효율적으로 렌더링할 수 있는 강력한 도구 모음을 제공합니다. 이 기능을 활용하려면 리소스 로딩 시간 제한 설정을 포함하여 복잡한 세부 사항을 이해해야 합니다. 이 튜토리얼에서는 .NET용 GroupDocs.Viewer에서 리소스 로딩 시간 제한을 구성하는 과정을 자세히 살펴보겠습니다.

![.NET용 GroupDocs.Viewer에서 리소스 로딩 시간 초과 설정(고급)](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## 필수 조건
이 튜토리얼을 시작하기 전에 다음 필수 조건이 충족되었는지 확인하세요.
1. .NET 개발에 대한 기본 지식: C# 프로그래밍과 .NET 프레임워크 기본에 대한 지식이 필수입니다.
2. .NET용 GroupDocs.Viewer 설치: 다음에서 .NET용 GroupDocs.Viewer 라이브러리를 다운로드하여 설치하세요. [다운로드 페이지](https://releases.groupdocs.com/viewer/net/).
3. 통합 개발 환경(IDE): Visual Studio와 같은 IDE를 시스템에 설치합니다.

## 네임스페이스 가져오기
코딩 과정을 시작하기 전에 필요한 네임스페이스를 가져오세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉토리 정의
먼저, 렌더링된 문서가 저장될 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 렌더링된 문서를 저장할 경로를 입력합니다.
## 2단계: 페이지 파일 경로 형식 정의
개별 페이지의 파일 경로에 대한 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 형식은 다음과 같은 파일 이름을 생성합니다. `page_1.html`, `page_2.html`지정된 출력 디렉토리 내에서 등을 실행합니다.
## 3단계: 로드 옵션 구성
리소스 로딩 시간 제한을 포함한 로드 옵션을 구성합니다.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
이 예에서는 리소스 로딩에 5초의 시간 초과가 설정되었습니다.
## 4단계: 뷰어 객체 초기화
초기화 `Viewer` 렌더링할 문서와 정의된 로드 옵션이 있는 개체:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
바꾸다 `TestFiles.WITH_EXTERNAL_IMAGE_DOC` 렌더링하려는 문서의 경로를 포함합니다.
## 5단계: HTML 보기 옵션 구성
내장된 리소스에 대한 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
이 구성은 이미지와 같은 내장된 리소스가 렌더링된 HTML에 포함되도록 보장합니다.
## 6단계: 문서 렌더링
구성된 옵션을 사용하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
이 단계에서는 렌더링 프로세스가 시작됩니다.
## 7단계: 출력 디렉토리 표시
렌더링이 성공적으로 완료되었음을 나타내는 메시지와 출력 디렉토리 위치를 표시합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
GroupDocs.Viewer for .NET에서 리소스 로딩 시간 초과를 완벽하게 이해하는 것은 원활한 문서 렌더링 프로세스를 보장하는 데 매우 중요합니다. 이 튜토리얼을 따라 하면 시간 초과를 효과적으로 구성하는 방법을 익혀 .NET 개발에 대한 숙련도를 향상시킬 수 있습니다.
## 자주 묻는 질문
### 리소스 로딩 시간 초과를 설정하는 것은 무슨 의미인가요?
리소스 로딩 시간 초과를 설정하면 렌더링 프로세스가 무기한 중단되지 않아 애플리케이션 안정성이 향상됩니다.
### 리소스 로딩 시간 초과를 문서 유형에 따라 사용자 지정할 수 있나요?
네, 리소스 로딩 시간 초과는 렌더링되는 문서의 복잡성과 크기에 따라 조정할 수 있습니다.
### 타임아웃을 짧게 설정하면 성능에 영향을 미치나요?
지정된 기간 내에 리소스를 로드할 수 없는 경우, 더 짧은 시간 제한으로 인해 복잡한 문서의 렌더링이 불완전해질 수 있습니다.
### GroupDocs.Viewer는 다양한 문서 형식을 렌더링하는 데 적합합니까?
네, GroupDocs.Viewer는 PDF, DOCX, XLSX 등 다양한 문서 형식 렌더링을 지원합니다.
### 리소스 로딩 시간 초과를 비활성화할 수 있나요?
권장하지는 않지만, 리소스 로딩 시간 초과는 특정 요구 사항에 따라 높은 값으로 설정하거나 완전히 비활성화할 수 있습니다.