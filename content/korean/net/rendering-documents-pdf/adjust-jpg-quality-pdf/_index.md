---
title: 렌더링된 PDF에서 JPG 이미지 품질 조정
linktitle: 렌더링된 PDF에서 JPG 이미지 품질 조정
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 렌더링된 PDF 문서에서 JPG 이미지 품질을 조정하는 방법을 알아보세요. 문서 보기 경험을 향상시키세요.
weight: 11
url: /ko/net/rendering-documents-pdf/adjust-jpg-quality-pdf/
---

# 렌더링된 PDF에서 JPG 이미지 품질 조정

## 소개
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 PDF를 렌더링할 때 JPG 이미지의 품질을 조정하는 방법을 알아봅니다. 이 강력한 라이브러리를 사용하면 .NET 애플리케이션에서 다양한 문서 형식을 원활하게 보고 조작할 수 있습니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 GroupDocs.Viewer: .NET 라이브러리용 GroupDocs.Viewer를 다운로드하여 설치했는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET Framework가 설치된 작업 개발 환경을 설정합니다.

## 네임스페이스 가져오기
먼저, 필요한 네임스페이스를 C# 코드로 가져와야 합니다. 이를 통해 응용 프로그램은 GroupDocs.Viewer for .NET에서 제공하는 기능에 액세스할 수 있습니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 및 파일 경로 정의
렌더링된 PDF가 저장될 출력 디렉터리를 설정하고 출력 PDF 파일의 파일 경로를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2단계: 조정된 JPG 이미지 품질로 PDF 렌더링
Viewer 클래스를 인스턴스화하고 JPG 이미지가 포함된 문서의 경로를 전달합니다. 그런 다음 PDF 렌더링 옵션을 구성하여 JPG 이미지 품질을 조정합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
{               
    PdfViewOptions options = new PdfViewOptions(filePath);
    viewer.View(options);
}
```
## 3단계: 성공 메시지 표시
PDF를 성공적으로 렌더링한 후 사용자에게 완료 및 출력 파일의 위치를 알리는 메시지를 표시합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 PDF를 렌더링할 때 JPG 이미지 품질을 조정하는 방법을 살펴보았습니다. 다음 단계를 수행하면 렌더링된 PDF 문서의 이미지 품질을 효과적으로 제어하여 최적의 시각적 표현을 보장할 수 있습니다.
## FAQ
### JPG 외에 다른 형식의 이미지 품질을 조정할 수 있나요?
예, .NET용 GroupDocs.Viewer는 다양한 이미지 형식을 지원하며 PNG, TIFF 및 기타 형식의 품질도 조정할 수 있습니다.
### .NET용 GroupDocs.Viewer는 모든 버전의 .NET Framework와 호환됩니까?
.NET용 GroupDocs.Viewer는 .NET Core 및 .NET Standard를 포함한 여러 버전의 .NET 프레임워크와 호환됩니다.
### .NET용 GroupDocs.Viewer를 사용하여 문서를 비동기적으로 렌더링할 수 있습니까?
예, .NET용 GroupDocs.Viewer는 비동기 렌더링 기능을 제공하므로 응용 프로그램의 성능을 향상시킬 수 있습니다.
### .NET용 GroupDocs.Viewer에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 .NET용 GroupDocs.Viewer의 무료 평가판 버전에 액세스할 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원을 받으려면 어떻게 해야 합니까?
 .NET용 GroupDocs.Viewer 포럼을 방문할 수 있습니다.[여기](https://forum.groupdocs.com/c/viewer/9) 도움을 받고, 질문하고, 다른 사용자 및 개발자와 상호 작용할 수 있습니다.