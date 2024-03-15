---
title: 아카이브 파일을 렌더링할 때 파일 이름 지정
linktitle: 아카이브 파일을 렌더링할 때 파일 이름 지정
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer를 사용하여 .NET에서 보관 파일을 렌더링하여 문서 관리 기능을 향상시키는 방법을 알아보세요.
type: docs
weight: 14
url: /ko/net/rendering-archive-files/specify-filename-render-archive/
---
## 소개
.NET 개발 영역에서 GroupDocs.Viewer는 다양한 형식의 문서를 렌더링하기 위한 다목적 도구로 돋보입니다. 강력한 기능과 유연성을 통해 아카이브 파일을 포함한 파일 보기 프로세스를 단순화합니다. 이 튜토리얼에서는 .NET용 GroupDocs.Viewer를 사용하여 아카이브 파일 렌더링의 세부 사항을 살펴보겠습니다. 이러한 단계별 지침을 따르면 아카이브 파일을 렌더링할 때 파일 이름을 지정하여 .NET 애플리케이션 내에서 원활한 문서 관리를 가능하게 하는 방법을 배우게 됩니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  .NET용 GroupDocs.Viewer: 다음에서 GroupDocs.Viewer 라이브러리를 다운로드하고 설치합니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: 필요한 구성을 사용하여 Visual Studio와 같은 .NET 개발 환경을 설정합니다.
3. C#에 대한 기본 지식: 제공된 코드 조각을 이해하고 구현하려면 C# 프로그래밍 언어에 대한 지식이 필수적입니다.

## 네임스페이스 가져오기
C# 프로젝트에서 GroupDocs.Viewer의 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 출력 디렉터리 및 파일 경로 지정
렌더링된 문서가 저장될 출력 디렉터리를 정의하고 출력 파일 경로를 지정합니다.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## 2단계: 뷰어 개체 초기화
아카이브 파일의 경로를 제공하여 Viewer 클래스의 인스턴스를 만듭니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP))
{
    // 렌더링 옵션
}
```
## 3단계: PDF 렌더링 옵션 구성
특히 PDF 출력의 경우 렌더링 옵션을 지정합니다.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```
## 4단계: 보관 파일 이름 지정
렌더링된 아카이브 파일에 대해 원하는 파일 이름을 설정합니다.
```csharp
viewOptions.ArchiveOptions.FileName = new FileName("my filename");
```
## 5단계: 문서 렌더링
구성된 보기 옵션을 사용하여 뷰어 개체의 View 메서드를 호출합니다.
```csharp
viewer.View(viewOptions);
```
## 6단계: 성공 메시지 표시
성공적인 렌더링에 대해 사용자에게 알리고 출력 디렉터리를 제공합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
이 자습서에서는 .NET용 GroupDocs.Viewer를 활용하여 아카이브 파일을 렌더링하고 출력에 대한 사용자 정의 파일 이름을 지정하는 방법을 살펴보았습니다. 설명된 단계를 따르면 이 기능을 .NET 애플리케이션에 원활하게 통합하여 문서 보기 및 관리 기능을 향상시킬 수 있습니다.
## FAQ
### GroupDocs.Viewer는 모든 아카이브 파일 형식과 호환됩니까?
GroupDocs.Viewer는 특히 ZIP, RAR, TAR 및 7z를 포함한 다양한 아카이브 형식을 지원합니다.
### PDF 이외의 출력 형식을 사용자 정의할 수 있나요?
예, GroupDocs.Viewer는 HTML 및 PDF는 물론 JPG 및 PNG와 같은 이미지 형식을 포함하여 출력 형식을 선택할 수 있는 유연성을 제공합니다.
### GroupDocs.Viewer는 대용량 아카이브 파일에 적합합니까?
예, GroupDocs.Viewer는 대용량 아카이브 파일을 효율적으로 처리하고 원활한 렌더링과 성능을 보장하도록 최적화되어 있습니다.
### GroupDocs.Viewer는 보관 파일의 암호화를 지원합니까?
예, 필요한 암호 해독 키가 제공되면 GroupDocs.Viewer는 암호화된 보관 파일을 처리할 수 있습니다.
### GroupDocs.Viewer를 클라우드 저장소 서비스와 통합할 수 있습니까?
예, GroupDocs.Viewer는 널리 사용되는 클라우드 저장소 제공업체와의 원활한 통합을 제공하므로 클라우드에 저장된 파일을 직접 렌더링할 수 있습니다.