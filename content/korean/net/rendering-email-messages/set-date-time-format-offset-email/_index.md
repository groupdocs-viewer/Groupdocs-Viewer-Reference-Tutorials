---
title: 날짜/시간 형식 및 시간대 오프셋 설정(이메일)
linktitle: 날짜/시간 형식 및 시간대 오프셋 설정(이메일)
second_title: GroupDocs.Viewer .NET API
description: 강력한 문서 보기 기능을 위해 .NET용 GroupDocs.Viewer를 응용 프로그램에 완벽하게 통합하세요. 사용자 정의 가능한 옵션으로 사용자 경험을 향상하십시오.
weight: 11
url: /ko/net/rendering-email-messages/set-date-time-format-offset-email/
---

# 날짜/시간 형식 및 시간대 오프셋 설정(이메일)


## 소개
.NET용 GroupDocs.Viewer는 개발자가 문서 보기 기능을 .NET 응용 프로그램에 원활하게 통합할 수 있게 해주는 강력한 도구입니다. GroupDocs.Viewer를 사용하면 외부 플러그인이나 뷰어 없이도 PDF, Microsoft Office 문서, 이미지 등을 포함한 다양한 문서 형식을 응용 프로그램 내에서 직접 표시할 수 있습니다. 이 포괄적인 자습서에서는 .NET용 GroupDocs.Viewer를 설정하고 해당 기능을 탐색하며 이를 효과적으로 활용하여 응용 프로그램의 문서 보기 기능을 향상시키는 과정을 안내합니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. Visual Studio: 시스템에 Visual Studio가 설치되어 있는지 확인하세요. .NET용 GroupDocs.Viewer는 Visual Studio와 완벽하게 호환되므로 .NET 프로젝트에 원활하게 통합할 수 있습니다.
2.  .NET용 GroupDocs.Viewer: 다음에서 .NET용 GroupDocs.Viewer를 다운로드하고 설치합니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/). 개발 환경 내에서 라이브러리를 설정하려면 제공된 설치 지침을 따르십시오.
3. .NET Framework: 적절한 버전의 .NET Framework가 설치되어 있는지 확인하십시오. .NET용 GroupDocs.Viewer는 .NET Core 및 .NET Standard를 포함하여 다양한 버전의 .NET Framework를 지원합니다.

## 네임스페이스 가져오기
.NET용 GroupDocs.Viewer를 효과적으로 활용하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 필수 네임스페이스를 가져오려면 다음 단계를 따르세요.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


제공된 예제를 여러 단계로 나누어 각 구성 요소와 해당 기능을 이해해 보겠습니다.
## 1단계: 출력 디렉터리 및 파일 경로 설정
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
이 단계에서는 렌더링된 문서가 저장될 출력 디렉터리를 정의하고 출력 HTML 파일의 파일 경로를 지정합니다.
## 2단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 여기서는 새로운 인스턴스를 생성합니다.`Viewer` 클래스, 보려는 문서(이 경우 샘플 EML 파일)의 경로를 매개변수로 전달합니다.
## 3단계: HTML 보기 옵션 정의
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
이 단계에서는 렌더링된 HTML 문서의 출력 파일 경로를 지정하여 문서 렌더링을 위한 HTML 보기 옵션을 구성합니다.
## 4단계: 날짜/시간 형식 및 시간대 오프셋 설정
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
여기서는 이메일 메시지의 날짜 및 시간 형식을 사용자 정의하고 원하는 시간대에 따라 시간대 오프셋을 설정합니다.
## 5단계: 문서 렌더링
```csharp
viewer.View(options);
```
 마지막으로 우리는`View` 의 방법`Viewer` 문서를 HTML 형식으로 렌더링하기 위해 구성된 HTML 보기 옵션을 전달합니다.
## 6단계: 출력 디렉터리 표시
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
이 단계에서는 문서가 성공적으로 렌더링되었음을 나타내는 메시지를 표시하고 렌더링된 HTML 문서가 있는 출력 디렉터리에 대한 경로를 제공합니다.

## 결론
.NET용 GroupDocs.Viewer는 문서 보기 기능을 .NET 응용 프로그램에 통합하기 위한 강력한 솔루션을 제공합니다. 이 자습서에 설명된 단계를 따르면 쉽게 GroupDocs.Viewer를 설정하고, 필요한 네임스페이스를 가져오고, 해당 기능을 활용하여 사용자 정의 가능한 옵션으로 문서를 렌더링할 수 있습니다. PDF, Microsoft Office 문서 또는 기타 형식으로 작업하는 경우 GroupDocs.Viewer는 문서 보기 프로세스를 단순화하여 응용 프로그램의 사용자 경험을 향상시킵니다.
## FAQ
### GroupDocs.Viewer는 .NET Core와 호환되나요?
예, .NET용 GroupDocs.Viewer는 .NET Core를 지원하므로 응용 프로그램에 대한 플랫폼 간 호환성이 가능합니다.
### 렌더링된 문서의 모양을 사용자 정의할 수 있습니까?
전적으로! GroupDocs.Viewer는 확대/축소 수준, 페이지 회전 등을 포함한 다양한 사용자 정의 옵션을 제공하여 기본 설정에 따라 보기 환경을 맞춤화합니다.
### 테스트 목적으로 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 GroupDocs.Viewer의 무료 평가판을 다운로드할 수 있습니다.[웹 사이트 링크](https://releases.groupdocs.com/viewer/net/) 구매하기 전에 기능을 평가하십시오.
### GroupDocs.Viewer는 암호로 보호된 문서 렌더링을 지원합니까?
예, GroupDocs.Viewer에는 암호로 보호된 문서 렌더링을 기본적으로 지원하므로 응용 프로그램 내에서 문서를 안전하게 볼 수 있습니다.
### GroupDocs.Viewer에 대한 추가 지원은 어디서 찾을 수 있나요?
 기술적인 질문이나 도움이 필요하면 GroupDocs.Viewer를 방문하세요.[법정](https://forum.groupdocs.com/c/viewer/9) 또는 지원팀에 연락하여 즉각적인 도움과 안내를 받으세요.