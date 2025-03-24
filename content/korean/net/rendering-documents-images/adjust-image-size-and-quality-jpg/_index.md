---
title: 이미지 크기 및 품질 조정(JPG)
linktitle: 이미지 크기 및 품질 조정(JPG)
second_title: GroupDocs.Viewer .NET API
description: .NET용 Groupdocs.Viewer를 사용하여 JPEG 형식의 이미지 크기와 품질을 최적화하는 방법을 알아보세요. 문서 보기 경험을 향상시키세요.
weight: 11
url: /ko/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## 소개
.NET용 Groupdocs.Viewer는 개발자가 문서 보기 기능을 .NET 응용 프로그램에 원활하게 통합할 수 있게 해주는 강력한 라이브러리입니다. 문서 보기 응용 프로그램의 일반적인 요구 사항 중 하나는 특히 JPEG(JPG) 이미지를 처리할 때 이미지의 크기와 품질을 조정하는 기능입니다. 이 자습서에서는 .NET용 Groupdocs.Viewer를 사용하여 이미지 크기와 품질을 조정하는 과정을 안내합니다.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. C# 프로그래밍 언어에 대한 기본 이해.
2. 시스템에 Visual Studio가 설치되어 있습니다.
3.  .NET 라이브러리용 Groupdocs.Viewer가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 이러한 네임스페이스는 Groupdocs.Viewer 작업에 필요한 클래스와 메서드에 대한 액세스를 제공합니다.
## 1단계: 네임스페이스 가져오기
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

이제 더 나은 이해를 위해 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 2단계: 출력 디렉터리 및 페이지 파일 경로 형식 설정
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
이 단계에서는 렌더링된 이미지가 저장될 출력 디렉터리를 지정하고 각 페이지 이미지의 파일 경로 형식을 정의합니다.
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
여기서는 보려는 문서의 경로로 Viewer 개체를 초기화합니다. 그런 다음 JpgViewOptions 인스턴스를 생성하고 JPEG 이미지에 대해 원하는 너비와 높이를 설정합니다.
## 4단계: 소스 문서 렌더링
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
마지막으로, 소스 문서의 성공적인 렌더링과 출력 이미지가 저장되는 위치를 나타내는 메시지를 인쇄합니다.

## 결론
이 자습서에서는 .NET용 Groupdocs.Viewer를 사용하여 JPEG 이미지의 크기와 품질을 조정하는 방법을 배웠습니다. 위에 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 쉽게 통합하여 사용자에게 최적화된 이미지 보기 환경을 제공할 수 있습니다.
## FAQ
### 화질도 조정할 수 있나요?
예, JpgViewOptions에서 품질 속성을 설정하여 이미지 품질을 조정할 수 있습니다.
### .NET용 Groupdocs.Viewer는 어떤 문서 형식을 지원합니까?
.NET용 Groupdocs.Viewer는 DOCX, PDF, PPTX, XLSX 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 Groupdocs.Viewer는 .NET Core와 호환됩니까?
예, .NET용 Groupdocs.Viewer는 기존 .NET Framework와 함께 .NET Core와 호환됩니다.
### 출력 파일 이름 지정 형식을 사용자 정의할 수 있습니까?
예, 코드에서 pageFilePathFormat 변수를 수정하여 출력 파일 명명 형식을 사용자 정의할 수 있습니다.
### .NET용 Groupdocs.Viewer는 문서 주석을 지원합니까?
예, .NET용 Groupdocs.Viewer는 텍스트 강조 표시, 밑줄 및 주석 달기를 포함하여 문서 주석에 대한 포괄적인 지원을 제공합니다.