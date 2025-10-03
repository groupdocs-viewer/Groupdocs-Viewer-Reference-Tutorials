---
"description": "Groupdocs.Viewer for .NET을 애플리케이션에 통합하여 원활한 문서 렌더링, 뒤집기, 회전을 구현하는 방법을 알아보세요."
"linktitle": "페이지 뒤집기 및 회전"
"second_title": "GroupDocs.Viewer .NET API"
"title": "페이지 뒤집기 및 회전"
"url": "/ko/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# 페이지 뒤집기 및 회전

## 소개
이 튜토리얼에서는 Groupdocs.Viewer for .NET의 기능, 특히 페이지 뒤집기와 회전 기능을 자세히 살펴보겠습니다. Groupdocs.Viewer for .NET은 .NET 애플리케이션에서 다양한 형식의 문서를 렌더링하도록 설계된 강력한 도구입니다. 문서 관리 시스템을 개발하거나 소프트웨어에 문서 보기 기능을 통합해야 하는 경우, Groupdocs.Viewer for .NET은 효율적인 솔루션을 제공합니다.
## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 설정되어 있는지 확인하세요.
### .NET용 Groupdocs.Viewer 설치
.NET용 Groupdocs.Viewer를 사용하려면 NuGet 패키지 관리자를 통해 패키지를 설치해야 합니다. 자세한 설치 지침은 다음에서 확인할 수 있습니다. [선적 서류 비치](https://tutorials.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
Groupdocs.Viewer for .NET을 효과적으로 활용하려면 프로젝트에 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Groupdocs.Viewer for .NET을 사용하여 페이지를 뒤집고 회전하는 과정을 간단한 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉토리 및 파일 경로 설정
출력 파일을 저장할 디렉토리를 정의하고 출력 파일 경로를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2단계: 뷰어 객체 초기화
보고 싶은 문서의 경로를 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## 3단계: 보기 옵션 구성
출력 파일 형식이나 페이지 회전과 같은 추가 설정을 지정하는 등 보기 옵션을 설정합니다.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## 4단계: 문서 렌더링
Viewer 객체의 View 메서드를 호출하고 뷰 옵션을 전달합니다.
```csharp
viewer.View(viewOptions);
```
## 5단계: 성공 메시지 표시
문서가 성공적으로 렌더링되었음을 사용자에게 알리고 검증을 위해 출력 디렉터리를 지정합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
결론적으로, Groupdocs.Viewer for .NET은 페이지 뒤집기 및 회전을 포함한 강력한 문서 렌더링 기능을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 이러한 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자의 문서 보기 환경을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Groupdocs.Viewer for .NET은 모든 문서 형식과 호환됩니까?
네, Groupdocs.Viewer for .NET은 DOCX, PDF, PPTX 등 다양한 문서 형식을 지원합니다.
### 페이지 넘기기, 회전 외에 다른 보기 옵션도 사용자 지정할 수 있나요?
물론입니다. Groupdocs.Viewer for .NET은 문서 보기에 대한 다양한 사용자 정의 옵션을 제공하여 요구 사항에 맞게 환경을 맞춤 설정할 수 있습니다.
### Groupdocs.Viewer for .NET에 대한 무료 평가판이 있나요?
예, .NET용 Groupdocs.Viewer의 무료 평가판을 이용하려면 다음을 방문하세요. [웹사이트](https://releases.groupdocs.com/).
### .NET용 Groupdocs.Viewer에 대한 지원은 어떻게 받을 수 있나요?
당신은 다음을 통해 도움을 요청하고 커뮤니티에 참여할 수 있습니다. [Groupdocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9).
### Groupdocs.Viewer for .NET의 임시 라이선스는 어디서 구할 수 있나요?
.NET용 Groupdocs.Viewer의 임시 라이센스는 다음에서 얻을 수 있습니다. [구매 페이지](https://purchase.groupdocs.com/temporary-license/).