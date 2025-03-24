---
title: Outlook 데이터 파일에서 렌더링할 항목 수 제한
linktitle: Outlook 데이터 파일에서 렌더링할 항목 수 제한
second_title: GroupDocs.Viewer .NET API
description: .NET용 Groupdocs.Viewer를 사용하여 Outlook 데이터 파일에서 렌더링되는 항목 수를 제한하는 방법을 알아보세요. 원활한 통합을 위해 단계별로 따라해보세요.
weight: 12
url: /ko/net/rendering-outlook-data-files/limit-items-to-render-outlook-data-files/
---

# Outlook 데이터 파일에서 렌더링할 항목 수 제한

## 소개
.NET용 Groupdocs.Viewer는 문서 보기 기능을 .NET 응용 프로그램에 원활하게 통합하려는 개발자를 위한 강력한 도구입니다. 응용 프로그램 내에서 PDF, Microsoft Office 문서 또는 Outlook 데이터 파일을 표시해야 하는 경우 Groupdocs.Viewer는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 단계별 지침을 사용하여 Outlook 데이터 파일에서 특별히 렌더링되는 항목 수를 제한하는 방법을 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. Visual Studio IDE: 시스템에 Visual Studio가 설치되어 있는지 확인하세요.
2.  .NET용 Groupdocs.Viewer: 다음에서 Groupdocs.Viewer 라이브러리를 다운로드하고 설치합니다.[다운로드 페이지](https://releases.groupdocs.com/viewer/net/).
3. C#의 기본 이해: C# 프로그래밍 언어 기본 사항을 숙지하세요.

## 네임스페이스 가져오기
필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작하세요. 이 단계에서는 Groupdocs.Viewer 라이브러리에서 필요한 클래스와 메서드에 액세스할 수 있는지 확인합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 정의
먼저 렌더링된 HTML 페이지를 저장할 디렉터리를 지정합니다. 이 디렉터리에는 Outlook 데이터 파일의 렌더링된 각 페이지에 대한 개별 HTML 파일이 포함됩니다.
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 렌더링된 HTML 페이지를 저장하려는 디렉토리의 경로를 사용합니다.
## 2단계: 페이지 파일 경로 형식 정의
 다음으로 렌더링된 HTML 페이지의 파일 경로 형식을 정의합니다. 각 HTML 페이지는 다음 형식을 따르는 파일 이름으로 저장됩니다.`{0}` 페이지 번호로 대체됩니다.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
이 단계에서는 렌더링된 각 페이지가 페이지 번호에 따라 고유한 파일 이름으로 저장되도록 합니다.
## 3단계: Outlook 데이터 파일의 항목 제한
 이제`Viewer` 클래스를 지정하고 Outlook 데이터 파일의 경로를 지정합니다(`*.ost`) 렌더링하려는 항목입니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST))
```
 바꾸다`TestFiles.SAMPLE_OST` Outlook 데이터 파일의 경로를 사용하세요.
## 4단계: HTML 보기 옵션 구성
Outlook 데이터 파일의 각 폴더에서 렌더링할 최대 항목 수 지정을 포함하여 HTML 보기 옵션을 구성합니다.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.MaxItemsInFolder = 3;
```
 이 예에서는`MaxItemsInFolder` 재산`3`, Outlook 데이터 파일의 각 폴더 내에서 렌더링할 항목(예: 이메일 또는 폴더) 수를 제한합니다.
## 5단계: 문서 렌더링
 마지막으로`View` 의 방법`Viewer` 예를 들어 HTML 보기 옵션을 전달합니다.
```csharp
viewer.View(options);
```
이 방법은 지정된 옵션에 따라 Outlook 데이터 파일을 렌더링하여 각 항목에 대한 HTML 페이지를 생성합니다.
## 6단계: 출력 디렉터리 경로 표시
선택적으로 렌더링된 HTML 페이지가 저장되는 출력 디렉터리의 경로를 인쇄할 수 있습니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 Groupdocs.Viewer를 사용하여 Outlook 데이터 파일에서 렌더링되는 항목 수를 제한하는 방법을 살펴보았습니다. 단계별 가이드를 따르면 이 기능을 .NET 애플리케이션에 쉽게 통합하여 사용자에게 효율적인 문서 보기 환경을 제공할 수 있습니다.
## FAQ
### HTML 렌더링 옵션을 추가로 사용자 정의할 수 있나요?
예, Groupdocs.Viewer는 렌더링 프로세스를 사용자 정의하기 위한 광범위한 옵션을 제공하므로 페이지 크기, 글꼴 설정 등과 같은 다양한 측면을 제어할 수 있습니다.
### Groupdocs.Viewer는 Outlook 데이터 파일 외에 다른 문서 형식과 호환됩니까?
물론, Groupdocs.Viewer는 PDF, Microsoft Office 파일, 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### Groupdocs.Viewer는 플랫폼 간 호환성을 제공합니까?
예, Groupdocs.Viewer는 Windows, Linux 및 macOS 환경에서 실행되는 .NET 응용 프로그램과 호환됩니다.
### Groupdocs.Viewer를 웹 응용 프로그램에 통합할 수 있습니까?
확실히 Groupdocs.Viewer는 데스크톱과 웹 응용 프로그램 모두에 원활하게 통합되어 유연성과 다양성을 제공할 수 있습니다.
### Groupdocs.Viewer에 대한 기술 지원이 제공됩니까?
 예, Groupdocs를 통해 기술 지원을 받을 수 있습니다.[법정](https://forum.groupdocs.com/c/viewer/9)에서 도움을 구하고, 질문하고, 개발자 커뮤니티에 참여할 수 있습니다.