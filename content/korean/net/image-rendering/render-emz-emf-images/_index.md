---
title: EMZ 및 EMF 이미지 렌더링
linktitle: EMZ 및 EMF 이미지 렌더링
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 EMZ 및 EMF 이미지를 다양한 형식으로 렌더링하는 방법을 알아보세요. 개발자를 위한 따라하기 쉬운 튜토리얼입니다.
weight: 14
url: /ko/net/image-rendering/render-emz-emf-images/
---

# EMZ 및 EMF 이미지 렌더링

## 소개

.NET용 GroupDocs.Viewer는 개발자가 EMZ(향상된 Windows 메타파일) 및 EMF(향상된 메타파일) 이미지를 비롯한 다양한 문서 유형을 .NET 응용 프로그램에 표시할 수 있는 강력한 문서 렌더링 API입니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 사용하여 EMZ 및 EMF 이미지를 HTML, JPG, PNG 및 PDF와 같은 다양한 형식으로 렌더링하는 방법을 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.

1.  .NET용 GroupDocs.Viewer: 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 개발을 위해 호환 가능한 개발 환경이 설정되어 있는지 확인하세요.
3. 샘플 EMZ/EMF 이미지: 렌더링에 사용할 수 있는 샘플 EMZ 및 EMF 이미지가 있습니다.

## 네임스페이스 가져오기

코드를 살펴보기 전에 필요한 네임스페이스를 가져오겠습니다.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

이제 단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.

## EMZ/EMF 이미지를 HTML로 렌더링

### 1단계: 출력 디렉터리 설정:
```csharp
string outputDirectory = "Your Document Directory";
```
 바꾸다`"Your Document Directory"`렌더링된 HTML 파일을 저장하려는 경로를 사용하세요.

### 2단계: 페이지 파일 경로 형식 정의:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
이는 렌더링된 HTML 파일의 파일 경로 형식을 지정합니다.

### 3단계: HTML로 렌더링:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 이 코드는`Viewer` 샘플 EMZ 이미지로 개체를 생성하고 지정된 옵션을 사용하여 HTML 형식으로 렌더링합니다.

## EMZ/EMF 이미지를 JPG, PNG 및 PDF로 렌더링

JPG, PNG 및 PDF 형식으로 렌더링하려면 다음 단계를 반복하십시오.

### 1단계: 페이지 파일 경로 형식 정의:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
원하는 출력 형식에 따라 파일 이름과 확장자를 조정합니다(`jpg`, `png` , 또는`pdf`).

### 2단계: 각 형식으로 렌더링:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // 출력 형식(Jpg, Png, Pdf)에 따라 옵션 조정
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 바꾸다`JpgViewOptions` ~와 함께`PngViewOptions` 또는`PdfViewOptions` 원하는 출력 형식을 기반으로 합니다.

## 결론

결론적으로 .NET용 GroupDocs.Viewer는 EMZ 및 EMF 이미지를 .NET 응용 프로그램의 다양한 형식으로 렌더링하기 위한 완벽한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 개발자는 문서 렌더링 기능을 애플리케이션에 쉽게 통합할 수 있습니다.

## FAQ

### Q: GroupDocs.Viewer는 EMZ 및 EMF 이미지 외에 다른 문서 형식을 렌더링할 수 있습니까?
A: 예, GroupDocs.Viewer는 PDF, DOCX, PPTX, XLSX 등을 포함한 광범위한 문서 형식을 지원합니다.

### 질문: .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 A: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.groupdocs.com/).

### Q: GroupDocs.Viewer는 개발자를 지원합니까?
 A: 예, GroupDocs는 다음을 통해 지원을 제공합니다.[법정](https://forum.groupdocs.com/c/viewer/9) 개발자가 질문하고 도움을 구할 수 있는 곳입니다.

### 질문: .NET용 GroupDocs.Viewer의 임시 라이센스를 구입할 수 있습니까?
 A: 예, 임시 라이센스를 구매할 수 있습니다.[여기](https://purchase.groupdocs.com/temporary-license/).

### 질문: .NET용 GroupDocs.Viewer에 대한 자세한 설명서는 어디에서 찾을 수 있습니까?
 A: 문서를 참조할 수 있습니다.[여기](https://tutorials.groupdocs.com/viewer/net/)API 사용에 대한 포괄적인 지침을 확인하세요.