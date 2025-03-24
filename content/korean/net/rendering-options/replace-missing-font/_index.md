---
title: 누락된 글꼴 바꾸기
linktitle: 누락된 글꼴 바꾸기
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer를 사용하여 .NET 문서에서 누락된 글꼴을 쉽게 바꾸는 방법을 알아보세요. 간단한 단계를 통해 정확한 렌더링을 보장합니다.
weight: 20
url: /ko/net/rendering-options/replace-missing-font/
---
## 소개
.NET 개발 세계에서는 효율적인 문서 처리가 매우 중요합니다. .NET용 GroupDocs.Viewer는 .NET 응용 프로그램 내에서 다양한 문서 형식을 볼 수 있는 강력한 솔루션을 제공합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 문서에서 누락된 글꼴을 바꾸는 방법을 살펴보겠습니다. PDF, PowerPoint 프리젠테이션 또는 Word 문서를 처리하는 경우 GroupDocs.Viewer는 글꼴이 누락된 경우에도 문서가 정확하게 렌더링되도록 프로세스를 단순화합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1. .NET용 GroupDocs.Viewer: 웹 사이트에서 GroupDocs.Viewer 라이브러리를 다운로드하고 설치합니다.](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: Visual Studio와 같은 .NET 개발 환경을 설정합니다.
3. 기본 C# 지식: C# 프로그래밍 언어 및 .NET 프레임워크에 대한 지식.

## 네임스페이스 가져오기
C# 코드에서 GroupDocs.Viewer 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 .NET용 GroupDocs.Viewer를 사용하여 문서에서 누락된 글꼴을 바꾸는 과정을 살펴보겠습니다.
## 1단계: 출력 디렉터리 정의
```csharp
string outputDirectory = "Your Document Directory";
```
렌더링된 문서 페이지가 저장될 디렉터리를 설정합니다.
## 2단계: 페이지 파일 경로 형식 정의
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
출력 HTML 파일의 이름을 지정하기 위한 형식을 지정합니다. 이 예에서 각 페이지는 "page"라는 명명 규칙을 사용하여 HTML 파일로 저장됩니다._{page_number}.html".
## 3단계: 뷰어 개체 초기화
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
문서 파일(이 경우 누락된 글꼴이 있는 PowerPoint 프레젠테이션)의 경로를 매개 변수로 전달하여 Viewer 클래스의 새 인스턴스를 초기화합니다.
## 4단계: HTML 보기 옵션 설정
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
HtmlViewOptions의 인스턴스를 생성하고 HTML 출력 내에 리소스를 포함하도록 구성합니다. 누락된 글꼴을 대체할 기본 글꼴 이름을 지정합니다.
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
HTML 보기 옵션을 전달하여 Viewer 개체의 View 메서드를 호출합니다. 그러면 지정된 옵션을 사용하여 문서 페이지가 렌더링됩니다.
## 6단계: 출력 경로 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
문서가 성공적으로 렌더링되었음을 나타내는 메시지를 인쇄하고 출력 HTML 파일이 저장되는 경로를 제공합니다.

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 문서에서 누락된 글꼴을 바꾸는 방법을 배웠습니다. 다음 단계를 수행하면 특정 글꼴을 사용할 수 없는 경우에도 문서가 정확하게 렌더링되도록 할 수 있습니다. GroupDocs.Viewer는 프로세스를 단순화하므로 글꼴 호환성 문제에 대한 걱정 없이 강력한 .NET 응용 프로그램을 구축하는 데 집중할 수 있습니다.
## FAQ
### GroupDocs.Viewer는 다른 유형의 글꼴 관련 문제를 처리할 수 있습니까?
예, GroupDocs.Viewer는 글꼴 대체 및 글꼴 감지를 포함한 다양한 글꼴 관련 기능을 제공합니다.
### GroupDocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
GroupDocs.Viewer는 .NET Core 및 .NET Standard를 포함하여 광범위한 .NET 프레임워크를 지원합니다.
### GroupDocs.Viewer에서 기본 글꼴 대체를 사용자 정의할 수 있나요?
물론, 원하는 글꼴을 누락된 글꼴의 기본 대체 글꼴로 지정할 수 있습니다.
### GroupDocs.Viewer는 문서 일괄 처리를 지원합니까?
예, GroupDocs.Viewer를 사용하면 여러 문서를 동시에 처리할 수 있으므로 일괄 처리 시나리오에 이상적입니다.
### GroupDocs.Viewer에 대한 추가 지원은 어디서 찾을 수 있나요?
 GroupDocs.Viewer 포럼을 방문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9) 도움이나 지원 문의가 있는 경우.