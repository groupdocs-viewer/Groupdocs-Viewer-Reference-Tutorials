---
title: 페이지 뒤집기 및 회전
linktitle: 페이지 뒤집기 및 회전
second_title: GroupDocs.Viewer .NET API
description: 원활한 문서 렌더링, 뒤집기 및 회전을 위해 .NET용 Groupdocs.Viewer를 응용 프로그램에 통합하는 방법을 알아보세요.
weight: 12
url: /ko/net/rendering-options/flip-rotate-pages/
---
## 소개
이 자습서에서는 .NET용 Groupdocs.Viewer의 기능, 특히 페이지 넘기기 및 회전에 중점을 두고 자세히 살펴보겠습니다. .NET용 Groupdocs.Viewer는 .NET 응용 프로그램 내에서 다양한 형식의 문서를 렌더링하도록 설계된 강력한 도구입니다. 문서 관리 시스템을 개발 중이거나 문서 보기 기능을 소프트웨어에 통합해야 하는 경우 Groupdocs.Viewer for .NET은 효율적인 솔루션을 제공합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
### .NET용 Groupdocs.Viewer 설치
 .NET용 Groupdocs.Viewer를 사용하려면 NuGet 패키지 관리자를 통해 패키지를 설치해야 합니다. 자세한 설치 지침은 다음에서 확인할 수 있습니다.[선적 서류 비치](https://tutorials.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
.NET용 Groupdocs.Viewer를 효과적으로 활용하려면 프로젝트에 필요한 네임스페이스를 가져왔는지 확인하세요.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

.NET용 Groupdocs.Viewer를 사용하여 페이지를 넘기고 회전하는 과정을 간단한 단계로 나누어 보겠습니다.
## 1단계: 출력 디렉터리 및 파일 경로 설정
출력 파일을 저장할 디렉터리를 정의하고 출력 파일 경로를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2단계: 뷰어 개체 초기화
보려는 문서의 경로를 전달하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## 3단계: 보기 옵션 구성
출력 파일 형식 지정 및 페이지 회전과 같은 추가 설정과 같은 보기 옵션을 설정합니다.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## 4단계: 문서 렌더링
Viewer 개체의 View 메서드를 호출하고 보기 옵션을 전달합니다.
```csharp
viewer.View(viewOptions);
```
## 5단계: 성공 메시지 표시
사용자에게 문서가 성공적으로 렌더링되었음을 알리고 확인을 위해 출력 디렉터리를 지정합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
결론적으로, .NET용 Groupdocs.Viewer는 페이지 뒤집기 및 회전을 포함하여 문서 렌더링을 위한 강력한 기능을 제공합니다. 이 자습서에 설명된 단계를 따르면 이러한 기능을 .NET 애플리케이션에 원활하게 통합하여 사용자의 문서 보기 환경을 향상시킬 수 있습니다.
## FAQ
### .NET용 Groupdocs.Viewer는 모든 문서 형식과 호환됩니까?
예, .NET용 Groupdocs.Viewer는 DOCX, PDF, PPTX 등을 포함한 광범위한 문서 형식을 지원합니다.
### 페이지를 넘기거나 회전하는 것 외에 보기 옵션을 사용자 정의할 수 있나요?
물론, .NET용 Groupdocs.Viewer는 문서 보기를 위한 다양한 사용자 정의 옵션을 제공하므로 요구 사항에 따라 환경을 맞춤화할 수 있습니다.
### .NET용 Groupdocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 다음 사이트를 방문하면 .NET용 Groupdocs.Viewer 무료 평가판을 이용할 수 있습니다.[웹사이트](https://releases.groupdocs.com/).
### .NET용 Groupdocs.Viewer에 대한 지원을 받으려면 어떻게 해야 합니까?
 다음을 통해 도움을 구하고 지역사회에 참여할 수 있습니다.[Groupdocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9).
### .NET용 Groupdocs.Viewer의 임시 라이센스는 어디서 얻을 수 있습니까?
 .NET용 Groupdocs.Viewer의 임시 라이센스는 다음에서 얻을 수 있습니다.[구매 페이지](https://purchase.groupdocs.com/temporary-license/).