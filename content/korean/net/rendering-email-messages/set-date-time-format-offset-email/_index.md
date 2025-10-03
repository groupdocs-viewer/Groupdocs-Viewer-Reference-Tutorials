---
"description": "GroupDocs.Viewer for .NET을 애플리케이션에 완벽하게 통합하여 강력한 문서 보기 기능을 활용하세요. 사용자 지정 가능한 옵션으로 사용자 경험을 향상시키세요."
"linktitle": "DateTime 형식 및 시간대 오프셋 설정(이메일)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "DateTime 형식 및 시간대 오프셋 설정(이메일)"
"url": "/ko/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# DateTime 형식 및 시간대 오프셋 설정(이메일)


## 소개
GroupDocs.Viewer for .NET은 개발자가 문서 보기 기능을 .NET 애플리케이션에 완벽하게 통합할 수 있도록 지원하는 강력한 도구입니다. GroupDocs.Viewer를 사용하면 외부 플러그인이나 뷰어 없이도 PDF, Microsoft Office 문서, 이미지 등 다양한 문서 형식을 애플리케이션 내에서 직접 표시할 수 있습니다. 이 포괄적인 튜토리얼에서는 GroupDocs.Viewer for .NET을 설정하는 과정을 안내하고, 기능을 살펴보고, 애플리케이션의 문서 보기 기능을 향상시키기 위해 효과적으로 활용하는 방법을 보여줍니다.
## 필수 조건
이 튜토리얼을 시작하기 전에 다음과 같은 필수 구성 요소가 설정되어 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요. GroupDocs.Viewer for .NET은 Visual Studio와 완벽하게 호환되므로 .NET 프로젝트에 원활하게 통합할 수 있습니다.
2. .NET용 GroupDocs.Viewer: .NET용 GroupDocs.Viewer를 다운로드하여 설치하세요. [다운로드 링크](https://releases.groupdocs.com/viewer/net/)제공된 설치 지침에 따라 개발 환경 내에서 라이브러리를 설정하세요.
3. .NET Framework: 적절한 버전의 .NET Framework가 설치되어 있는지 확인하세요. GroupDocs.Viewer for .NET은 .NET Core 및 .NET Standard를 포함한 다양한 버전의 .NET Framework를 지원합니다.

## 네임스페이스 가져오기
GroupDocs.Viewer for .NET을 효과적으로 활용하려면 필요한 네임스페이스를 프로젝트에 가져와야 합니다. 다음 단계에 따라 필요한 네임스페이스를 가져오세요.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


제공된 예를 여러 단계로 나누어 각 구성 요소와 기능을 이해해 보겠습니다.
## 1단계: 출력 디렉토리 및 파일 경로 설정
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
이 단계에서는 렌더링된 문서가 저장될 출력 디렉토리를 정의하고 출력 HTML 파일의 파일 경로를 지정합니다.
## 2단계: 뷰어 객체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
여기서 우리는 새로운 인스턴스를 생성합니다. `Viewer` 클래스는 보려는 문서의 경로(이 경우 샘플 EML 파일)를 매개변수로 전달합니다.
## 3단계: HTML 보기 옵션 정의
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
이 단계에서는 문서 렌더링을 위한 HTML 보기 옵션을 구성하고, 렌더링된 HTML 문서의 출력 파일 경로를 지정합니다.
## 4단계: 날짜/시간 형식 및 시간대 오프셋 설정
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
여기에서는 이메일 메시지의 날짜 및 시간 형식을 사용자 지정하고 원하는 시간대에 따라 시간대 오프셋을 설정합니다.
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
마지막으로 우리는 다음을 호출합니다. `View` 방법 `Viewer` 객체를 사용하여 구성된 HTML 보기 옵션을 전달하여 문서를 HTML 형식으로 렌더링합니다.
## 6단계: 출력 디렉토리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 단계에서는 문서가 성공적으로 렌더링되었다는 메시지를 표시하고 렌더링된 HTML 문서가 있는 출력 디렉터리의 경로를 제공합니다.

## 결론
GroupDocs.Viewer for .NET은 문서 보기 기능을 .NET 애플리케이션에 통합하는 강력한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따라 GroupDocs.Viewer를 쉽게 설정하고, 필요한 네임스페이스를 가져오고, 해당 기능을 활용하여 사용자 지정 가능한 옵션으로 문서를 렌더링할 수 있습니다. PDF, Microsoft Office 문서 또는 기타 형식 등 어떤 형식으로 작업하든 GroupDocs.Viewer는 문서 보기 프로세스를 간소화하여 애플리케이션의 사용자 경험을 향상시킵니다.
## 자주 묻는 질문
### GroupDocs.Viewer는 .NET Core와 호환됩니까?
네, GroupDocs.Viewer for .NET은 .NET Core를 지원하여 애플리케이션 간 플랫폼 호환성을 확보할 수 있습니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있나요?
물론입니다! GroupDocs.Viewer는 확대/축소 수준, 페이지 회전 등 다양한 사용자 지정 옵션을 제공하여 튜토리얼에 따라 보기 환경을 맞춤 설정할 수 있습니다.
### 테스트 목적으로 사용할 수 있는 체험판이 있나요?
예, .NET용 GroupDocs.Viewer의 무료 평가판 버전을 다운로드할 수 있습니다. [웹사이트 링크](https://releases.groupdocs.com/viewer/net/) 구매하기 전에 기능을 평가해보세요.
### GroupDocs.Viewer는 암호로 보호된 문서 렌더링을 지원합니까?
네, GroupDocs.Viewer에는 암호로 보호된 문서를 렌더링하는 기능이 내장되어 있어 애플리케이션 내에서 안전하게 문서를 볼 수 있습니다.
### GroupDocs.Viewer에 대한 추가 지원이나 도움말은 어디에서 찾을 수 있나요?
기술적인 질문이나 지원이 필요하면 GroupDocs.Viewer를 방문하세요. [법정](https://forum.groupdocs.com/c/viewer/9) 또는 지원팀에 문의하여 신속한 도움과 안내를 받으세요.