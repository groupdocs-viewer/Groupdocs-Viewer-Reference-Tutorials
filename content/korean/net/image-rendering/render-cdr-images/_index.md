---
"description": "GroupDocs.Viewer for .NET을 사용하여 CDR 이미지를 HTML, JPG, PNG, PDF로 렌더링하는 방법을 알아보세요. 이 튜토리얼을 통해 CorelDRAW 파일을 쉽게 변환할 수 있습니다."
"linktitle": "CDR 이미지 렌더링"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDR 이미지 렌더링"
"url": "/ko/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# CDR 이미지 렌더링

## 소개
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 CDR(CorelDRAW) 이미지를 렌더링하는 과정을 안내합니다. CDR은 벡터 그래픽 편집기인 CorelDRAW와 주로 관련된 파일 형식입니다. GroupDocs.Viewer를 사용하면 CDR 파일을 HTML, JPG, PNG, PDF 등 다양한 형식으로 쉽게 변환할 수 있습니다.

![.NET용 GroupDocs.Viewer를 사용하여 CDR 이미지 렌더링](/viewer/image-rendering/render-cdr-images.png)

## 필수 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. GroupDocs.Viewer for .NET: GroupDocs.Viewer for .NET이 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/viewer/net/).
2. 문서 디렉토리: 렌더링된 이미지를 저장할 디렉토리를 준비합니다.
3. C#에 대한 기본 지식: 코드 예제를 이해하려면 C# 프로그래밍 언어에 대한 지식이 필요합니다.
## 네임스페이스 가져오기
코드 예제를 살펴보기 전에 C# 파일에 필요한 네임스페이스를 가져오세요.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
이제 각 예를 여러 단계로 나누어 보겠습니다.
## HTML로 렌더링
1. 렌더링된 HTML 파일을 저장할 출력 디렉토리를 정의합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML 파일에 대한 파일 경로 형식을 지정하세요.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Viewer 클래스를 사용하여 CDR 파일을 HTML로 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPG로 렌더링
1. JPG 파일의 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Viewer 클래스를 사용하여 CDR 파일을 JPG로 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNG로 렌더링
1. PNG 파일의 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Viewer 클래스를 사용하여 CDR 파일을 PNG로 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PDF로 렌더링
1. PDF에 대한 파일 경로 형식을 정의합니다.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Viewer 클래스를 사용하여 CDR 파일을 PDF로 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. 선택적으로 추가 매개변수를 전달하여 렌더링 옵션을 지정하거나 특정 페이지를 렌더링할 수 있습니다. `viewer.View()` 방법.
## 결론
GroupDocs.Viewer for .NET을 사용하여 CDR 이미지를 HTML, JPG, PNG, PDF 등 다양한 형식으로 렌더링하는 것은 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따르면 요구 사항에 따라 CDR 파일을 다양한 형식으로 효율적으로 변환할 수 있습니다.
## 자주 묻는 질문
### GroupDocs.Viewer for .NET은 모든 버전의 CDR 파일과 호환됩니까?
.NET용 GroupDocs.Viewer는 다양한 버전의 CorelDRAW에서 생성된 CDR 파일의 렌더링을 지원합니다.
### 렌더링된 파일의 출력을 사용자 정의할 수 있나요?
네, GroupDocs.Viewer for .NET은 이미지 품질 조정, 워터마크 설정 등 출력을 사용자 정의하기 위한 다양한 옵션을 제공합니다.
### .NET용 GroupDocs.Viewer에 외부 종속성이 필요합니까?
아니요, .NET용 GroupDocs.Viewer는 독립 실행형 라이브러리이므로 문서 렌더링을 위해 외부 종속성이 필요하지 않습니다.
### GroupDocs.Viewer for .NET의 평가판이 있나요?
예, .NET용 GroupDocs.Viewer의 무료 평가판 버전을 다운로드할 수 있습니다. [여기](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 지원은 어디에서 받을 수 있나요?
GroupDocs.Viewer 커뮤니티 포럼에서 지원을 받을 수 있습니다. [여기](https://forum.groupdocs.com/c/viewer/9).