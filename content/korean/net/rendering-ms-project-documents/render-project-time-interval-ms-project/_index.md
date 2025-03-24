---
title: 렌더별 프로젝트 시간 간격(MS 프로젝트)
linktitle: 렌더별 프로젝트 시간 간격(MS 프로젝트)
second_title: GroupDocs.Viewer .NET API
description: 효율적인 문서 보기를 위해 .NET용 GroupDocs.Viewer를 응용 프로그램에 완벽하게 통합하세요. 다양한 렌더링 기능으로 생산성을 향상하세요.
weight: 12
url: /ko/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---

# 렌더별 프로젝트 시간 간격(MS 프로젝트)

## 소개
소프트웨어 개발 영역에서는 다양한 문서 형식을 효율적으로 처리하고 렌더링하는 것이 무엇보다 중요합니다. 문서 보기이든 조작이든 올바른 도구를 사용하면 생산성을 크게 향상하고 프로세스를 간소화할 수 있습니다. .NET용 GroupDocs.Viewer는 개발자에게 문서 보기 기능을 .NET 응용 프로그램에 원활하게 통합할 수 있는 기능을 제공하는 다목적 솔루션으로 탁월합니다.
## 전제조건
.NET용 GroupDocs.Viewer 통합을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET Framework에 대한 지식
C# 프로그래밍 언어 및 Visual Studio IDE를 포함하여 .NET 프레임워크에 대한 기본적인 이해가 있는지 확인하세요.
### 2. .NET용 GroupDocs.Viewer 설치
 다음에서 .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요.[다운로드 링크](https://releases.groupdocs.com/viewer/net/). 개발 환경 내에서 라이브러리를 설정하려면 제공된 설치 지침을 따르십시오.
### 3. 유효한 면허증 또는 임시 면허증
 다음에서 유효한 라이센스를 취득하십시오.[그룹문서](https://purchase.groupdocs.com/buy) 또는 임시 면허를 취득하세요.[여기](https://purchase.groupdocs.com/temporary-license/) .NET용 GroupDocs.Viewer의 전체 기능을 활용합니다.
### 4. 샘플 문서
렌더링 기능을 테스트할 준비가 된 MS 프로젝트 파일과 같은 샘플 문서를 준비합니다.

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 프로젝트에 통합하세요.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

MS 프로젝트 파일의 특정 프로젝트 시간 간격을 여러 단계로 렌더링하는 예를 분석해 보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 HTML 페이지가 저장될 디렉터리를 지정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
렌더링된 각 HTML 페이지의 파일 경로 형식을 설정합니다.
## 3단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
샘플 MS 프로젝트 파일에 대한 경로를 전달하여 뷰어 클래스의 인스턴스를 만듭니다.
## 4단계: HTML 보기 옵션 구성
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
렌더링을 위한 HTML 보기 옵션을 구성하고 포함된 리소스의 형식을 지정합니다.
## 5단계: 프로젝트 관리 보기 정보 검색
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
프로젝트 관리 보기 정보를 검색하여 프로젝트의 시작 날짜와 종료 날짜를 결정합니다.
## 6단계: 시작 및 종료 날짜 설정
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
렌더링할 프로젝트 간격의 시작 및 종료 날짜를 설정합니다.
## 7단계: 문서 렌더링
```csharp
viewer.View(options);
```
지정된 옵션을 사용하여 렌더링 프로세스를 시작합니다.
## 8단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
성공적인 렌더링에 대해 사용자에게 알리고 출력이 저장된 디렉터리를 표시합니다.

## 결론
.NET용 GroupDocs.Viewer를 프로젝트에 통합하면 문서 보기 작업을 효율적으로 처리하고 사용자 경험과 생산성을 향상시킬 수 있습니다. 제공된 단계별 가이드를 따르면 문서 렌더링 기능을 .NET 애플리케이션에 원활하게 통합할 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 모든 문서 형식과 호환됩니까?
.NET용 GroupDocs.Viewer는 Microsoft Office, PDF, CAD 등을 포함한 광범위한 문서 형식을 지원합니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있습니까?
예, 페이지 레이아웃, 워터마킹, 페이지 회전 등 렌더링 프로세스의 다양한 측면을 사용자 정의할 수 있습니다.
### .NET용 GroupDocs.Viewer는 웹 응용 프로그램에 적합합니까?
물론 .NET용 GroupDocs.Viewer는 웹 응용 프로그램에 완벽하게 통합되어 문서 보기 기능을 제공할 수 있습니다.
### .NET용 GroupDocs.Viewer는 모바일 플랫폼을 지원합니까?
예, .NET용 GroupDocs.Viewer는 모바일 플랫폼을 지원하므로 반응형 문서 보기 기능이 있는 응용 프로그램을 만들 수 있습니다.
### .NET용 GroupDocs.Viewer에 대한 도움을 구할 수 있는 커뮤니티 포럼이 있습니까?
 네, 방문하실 수 있습니다[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 질문하고, 아이디어를 공유하고, 다른 사용자 및 개발자와 상호 작용합니다.