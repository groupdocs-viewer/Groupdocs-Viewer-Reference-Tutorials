---
"description": "GroupDocs.Viewer for .NET을 사용하여 EMZ 및 EMF 이미지를 다양한 형식으로 렌더링하는 방법을 알아보세요. 개발자를 위한 따라하기 쉬운 튜토리얼입니다."
"linktitle": "EMZ 및 EMF 이미지 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "EMZ 및 EMF 이미지 렌더링"
"url": "/ko/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# EMZ 및 EMF 이미지 렌더링

## 소개

GroupDocs.Viewer for .NET은 개발자가 .NET 애플리케이션에서 EMZ(Enhanced Windows Metafile) 및 EMF(Enhanced Metafile) 이미지를 포함한 다양한 문서 유형을 표시할 수 있도록 지원하는 강력한 문서 렌더링 API입니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 EMZ 및 EMF 이미지를 HTML, JPG, PNG, PDF 등 다양한 형식으로 렌더링하는 방법을 살펴보겠습니다.

![.NET용 GroupDocs.Viewer를 사용하여 EMZ 및 EMF 이미지 렌더링](/viewer/image-rendering/render-emz-and-emf-images.png)

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

1. .NET용 GroupDocs.Viewer: 라이브러리를 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
2. 개발 환경: .NET 개발에 적합한 호환 개발 환경이 설정되어 있는지 확인하세요.
3. 샘플 EMZ/EMF 이미지: 렌더링에 사용할 수 있는 샘플 EMZ 및 EMF 이미지를 제공합니다.

## 네임스페이스 가져오기

코드를 살펴보기 전에 필요한 네임스페이스를 가져와 보겠습니다.

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

이제 각 예를 단계별 가이드 형식으로 여러 단계로 나누어 살펴보겠습니다.

## EMZ/EMF 이미지를 HTML로 렌더링

### 1단계: 출력 디렉토리 설정:
```csharp
string outputDirectory = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 렌더링된 HTML 파일을 저장할 경로를 입력합니다.

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
이 코드는 다음을 초기화합니다. `Viewer` 샘플 EMZ 이미지가 있는 객체를 지정 옵션을 사용하여 HTML 형식으로 렌더링합니다.

## EMZ/EMF 이미지를 JPG, PNG 및 PDF로 렌더링

JPG, PNG, PDF 형식으로 렌더링하려면 다음 단계를 반복하세요.

### 1단계: 페이지 파일 경로 형식 정의:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
원하는 출력 형식에 따라 파일 이름과 확장자를 조정합니다.`jpg`, `png`, 또는 `pdf`).

### 2단계: 해당 형식으로 렌더링:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // 출력 형식(Jpg, Png, Pdf)에 따라 옵션을 조정하세요.
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
바꾸다 `JpgViewOptions` ~와 함께 `PngViewOptions` 또는 `PdfViewOptions` 원하는 출력 형식을 기준으로 합니다.

## 결론

결론적으로, GroupDocs.Viewer for .NET은 .NET 애플리케이션에서 EMZ 및 EMF 이미지를 다양한 형식으로 렌더링하는 완벽한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 개발자는 문서 렌더링 기능을 애플리케이션에 손쉽게 통합할 수 있습니다.

## 자주 묻는 질문

### 질문: GroupDocs.Viewer는 EMZ 및 EMF 이미지 외에 다른 문서 형식을 렌더링할 수 있나요?
답변: 네, GroupDocs.Viewer는 PDF, DOCX, PPTX, XLSX 등 다양한 문서 형식을 지원합니다.

### 질문: GroupDocs.Viewer for .NET에 대한 무료 평가판이 있나요?
A: 네, 무료 체험판을 이용하실 수 있습니다. [여기](https://releases.groupdocs.com/).

### 질문: GroupDocs.Viewer는 개발자에게 지원을 제공합니까?
A: 예, GroupDocs는 다음을 통해 지원을 제공합니다. [법정](https://forum.groupdocs.com/c/viewer/9) 개발자가 질문을 하고 도움을 구할 수 있는 곳입니다.

### 질문: GroupDocs.Viewer for .NET에 대한 임시 라이선스를 구매할 수 있나요?
A: 예, 임시 라이센스를 구매할 수 있습니다. [여기](https://purchase.groupdocs.com/temporary-license/).

### 질문: GroupDocs.Viewer for .NET에 대한 자세한 설명서는 어디에서 찾을 수 있나요?
A: 문서를 참조할 수 있습니다. [여기](https://tutorials.groupdocs.com/viewer/net/) API 사용에 대한 포괄적인 지침을 확인하세요.