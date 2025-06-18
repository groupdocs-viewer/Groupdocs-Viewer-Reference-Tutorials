---
"description": "Groupdocs.Viewer for .NET을 사용하여 JPEG 형식의 이미지 크기와 품질을 최적화하는 방법을 알아보세요. 문서 보기 환경을 개선해 보세요."
"linktitle": "이미지 크기 및 품질 조정(JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "이미지 크기 및 품질 조정(JPG)"
"url": "/ko/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# 이미지 크기 및 품질 조정(JPG)

## 소개
Groupdocs.Viewer for .NET은 개발자가 문서 보기 기능을 .NET 애플리케이션에 원활하게 통합할 수 있도록 지원하는 강력한 라이브러리입니다. 문서 보기 애플리케이션에서 일반적으로 요구되는 기능 중 하나는 이미지의 크기와 품질을 조정하는 기능이며, 특히 JPEG(JPG) 이미지를 다룰 때 더욱 그렇습니다. 이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 이미지 크기와 품질을 조정하는 과정을 안내합니다.
## 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.
1. C# 프로그래밍 언어에 대한 기본적인 이해.
2. 시스템에 Visual Studio가 설치되어 있어야 합니다.
3. Groupdocs.Viewer for .NET 라이브러리가 설치되었습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 이 네임스페이스는 Groupdocs.Viewer 작업에 필요한 클래스와 메서드에 대한 액세스를 제공합니다.
## 1단계: 네임스페이스 가져오기
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 더 잘 이해하기 위해 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 2단계: 출력 디렉터리 및 페이지 파일 경로 형식 설정
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
이 단계에서는 렌더링된 이미지가 저장될 출력 디렉토리를 지정하고 각 페이지 이미지의 파일 경로에 대한 형식을 정의합니다.
## 3단계: 뷰어 초기화 및 JPG 보기 옵션 구성
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
여기서는 표시할 문서의 경로로 Viewer 객체를 초기화합니다. 그런 다음 JpgViewOptions 인스턴스를 생성하고 JPEG 이미지의 원하는 너비와 높이를 설정합니다.
## 4단계: 소스 문서 렌더링
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로, 소스 문서가 성공적으로 렌더링되었다는 메시지와 출력 이미지가 저장된 위치를 나타내는 메시지를 인쇄합니다.

## 결론
이 튜토리얼에서는 Groupdocs.Viewer for .NET을 사용하여 JPEG 이미지의 크기와 품질을 조정하는 방법을 알아보았습니다. 위에 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 쉽게 통합하여 사용자에게 최적화된 이미지 보기 환경을 제공할 수 있습니다.
## 자주 묻는 질문
### 이미지 품질도 조절할 수 있나요?
네, JpgViewOptions의 Quality 속성을 설정하여 이미지 품질을 조정할 수 있습니다.
### Groupdocs.Viewer for .NET에서는 어떤 문서 형식을 지원합니까?
.NET용 Groupdocs.Viewer는 DOCX, PDF, PPTX, XLSX 등 다양한 문서 형식을 지원합니다.
### Groupdocs.Viewer for .NET은 .NET Core와 호환됩니까?
네, Groupdocs.Viewer for .NET은 기존 .NET Framework와 함께 .NET Core와도 호환됩니다.
### 출력 파일 이름 형식을 사용자 정의할 수 있나요?
네, 코드에서 pageFilePathFormat 변수를 수정하여 출력 파일 이름 형식을 사용자 정의할 수 있습니다.
### .NET용 Groupdocs.Viewer는 문서 주석을 지원합니까?
네, Groupdocs.Viewer for .NET은 텍스트 강조 표시, 밑줄, 주석 달기 등 문서 주석에 대한 포괄적인 지원을 제공합니다.