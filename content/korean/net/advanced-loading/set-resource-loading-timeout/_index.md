---
title: 리소스 로딩 시간 초과 설정(고급)
linktitle: 리소스 로딩 시간 초과 설정(고급)
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer에서 리소스 로드 시간 초과를 효율적으로 구성하는 방법을 알아보세요. 정밀하고 안정적인 마스터 문서 렌더링.
weight: 13
url: /ko/net/advanced-loading/set-resource-loading-timeout/
---

# 리소스 로딩 시간 초과 설정(고급)

## 소개
.NET 개발 영역에서 GroupDocs.Viewer는 문서와 이미지를 정확하고 효율적으로 렌더링하기 위한 강력한 도구 세트를 제공합니다. 해당 기능을 활용하려면 리소스 로딩 시간 제한 설정을 포함한 복잡성을 이해해야 합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer에서 리소스 로드 시간 제한을 구성하는 프로세스를 자세히 살펴보겠습니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. .NET 개발에 대한 기본 지식: C# 프로그래밍 및 .NET 프레임워크 기본 사항에 대한 지식이 필수적입니다.
2.  .NET용 GroupDocs.Viewer 설치: 다음에서 .NET 라이브러리용 GroupDocs.Viewer를 다운로드하여 설치합니다.[다운로드 페이지](https://releases.groupdocs.com/viewer/net/).
3. 통합 개발 환경(IDE): 시스템에 Visual Studio와 같은 IDE가 설치되어 있습니다.

## 네임스페이스 가져오기
코딩 프로세스를 시작하기 전에 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 1단계: 출력 디렉터리 정의
먼저 렌더링된 문서가 저장될 디렉터리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"`렌더링된 문서를 저장하려는 경로를 사용하세요.
## 2단계: 페이지 파일 경로 형식 정의
개별 페이지의 파일 경로 형식을 정의합니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 이 형식은 다음과 같은 파일 이름을 생성합니다.`page_1.html`, `page_2.html`, 등을 지정된 출력 디렉터리 내에서 사용합니다.
## 3단계: 로드 옵션 구성
리소스 로드 시간 초과를 포함하여 로드 옵션을 구성합니다.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
이 예에서는 리소스 로드에 대한 제한 시간이 5초로 설정되어 있습니다.
## 4단계: 뷰어 개체 초기화
 초기화`Viewer` 렌더링할 문서와 정의된 로드 옵션이 있는 객체:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 바꾸다`TestFiles.WITH_EXTERNAL_IMAGE_DOC` 렌더링하려는 문서의 경로를 사용하세요.
## 5단계: HTML 보기 옵션 구성
포함된 리소스에 대한 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
이 구성을 사용하면 이미지와 같은 포함된 리소스가 렌더링된 HTML에 포함됩니다.
## 6단계: 문서 렌더링
구성된 옵션을 사용하여 문서를 렌더링합니다.
```csharp
viewer.View(options);
```
이 단계에서는 렌더링 프로세스가 시작됩니다.
## 7단계: 출력 디렉터리 표시
성공적인 렌더링과 출력 디렉터리의 위치를 나타내는 메시지를 표시합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
.NET용 GroupDocs.Viewer에서 리소스 로드 시간 초과를 마스터하는 것은 원활한 문서 렌더링 프로세스를 보장하는 데 중요합니다. 이 자습서를 따라하면 시간 초과를 효과적으로 구성하는 방법에 대한 통찰력을 얻고 .NET 개발의 숙련도를 높일 수 있습니다.
## FAQ
### 리소스 로딩 시간 초과 설정의 중요성은 무엇입니까?
리소스 로딩 시간 초과를 설정하면 렌더링 프로세스가 무기한 중단되지 않고 애플리케이션 안정성이 향상됩니다.
### 문서 유형에 따라 리소스 로딩 시간 초과를 사용자 정의할 수 있습니까?
예, 렌더링되는 문서의 복잡성과 크기에 따라 리소스 로딩 시간 초과를 조정할 수 있습니다.
### 더 짧은 시간 제한을 설정하면 성능에 영향이 있나요?
시간 초과가 짧을수록 지정된 기간 내에 리소스를 로드할 수 없는 경우 복잡한 문서의 렌더링이 불완전해질 수 있습니다.
### GroupDocs.Viewer는 다양한 문서 형식을 렌더링하는 데 적합합니까?
예, GroupDocs.Viewer는 PDF, DOCX, XLSX 등을 포함한 광범위한 문서 형식의 렌더링을 지원합니다.
### 리소스 로딩 시간 초과를 비활성화할 수 있나요?
권장되지는 않지만 특정 요구 사항에 따라 리소스 로딩 시간 초과를 높은 값으로 설정하거나 완전히 비활성화할 수 있습니다.