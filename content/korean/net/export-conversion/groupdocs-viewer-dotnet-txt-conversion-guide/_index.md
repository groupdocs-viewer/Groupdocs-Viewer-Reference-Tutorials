---
"date": "2025-04-25"
"description": "이 포괄적인 가이드를 통해 GroupDocs.Viewer for .NET을 사용하여 TXT 파일을 HTML, JPG, PNG, PDF 등 여러 형식으로 변환하는 방법을 알아보세요."
"title": "GroupDocs.Viewer .NET을 사용하여 TXT를 HTML, JPG, PNG, PDF로 변환하는 완벽한 가이드"
"url": "/ko/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# GroupDocs.Viewer .NET을 사용하여 TXT를 여러 형식으로 변환

## 소개

텍스트 문서를 HTML, JPG, PNG, PDF 등 다양한 형식으로 손쉽게 변환하고 싶으신가요? 특히 여러 페이지나 특정 형식이 필요한 경우 문서 변환 관리가 어려울 수 있습니다. **.NET용 GroupDocs.Viewer** TXT 파일을 다양한 출력 형식으로 렌더링하는 과정을 간소화하여 데이터에 쉽게 접근하고 시각적으로 매력적으로 보이도록 보장합니다.

![GroupDocs.Viewer for .NET을 사용하여 TXT를 HTML, JPG, PNG, PDF로 변환](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

이 가이드에서는 GroupDocs.Viewer for .NET을 사용하여 TXT 문서를 여러 페이지 HTML, 단일 페이지 HTML, JPG, PNG, PDF로 변환하는 방법을 살펴보겠습니다. 이 가이드를 마치면 다음 기능을 완벽하게 익힐 수 있습니다.
- GroupDocs.Viewer를 사용하여 C#을 사용하여 TXT 파일 변환
- 귀하의 요구 사항에 맞는 다양한 렌더링 옵션 구현
- 전환 중 성능 최적화

문서 변환 과제를 해결하는 방법을 알아보겠습니다.

## 필수 조건

시작하기에 앞서 다음 사항을 준비하세요.
- **개발 환경**: Visual Studio 2019 이상.
- **.NET 프레임워크**: 버전 4.6.1 이상.
- **.NET 라이브러리용 GroupDocs.Viewer**:
  - NuGet 패키지 관리자 콘솔을 통해: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - .NET CLI 사용: `dotnet add package GroupDocs.Viewer --version 25.3.0`

쉽게 따라가려면 C# 프로그래밍과 .NET의 기본 파일 작업에 익숙해야 합니다.

## .NET용 GroupDocs.Viewer 설정

### 설치

시작하려면 다음을 설치하세요. **그룹 문서 뷰어** 선호하는 패키지 관리자를 사용하여 라이브러리를 설치합니다.

#### NuGet 패키지 관리자 콘솔
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 라이센스

당신은 ~로 시작할 수 있습니다 **무료 체험** 또는 얻다 **임시 면허** 평가 제한 없이 .NET용 GroupDocs.Viewer의 모든 기능을 살펴보려면 다음을 수행합니다.
- 무료 체험: [여기에서 다운로드하세요](https://releases.groupdocs.com/viewer/net/)
- 임시 면허: [여기서 요청하세요](https://purchase.groupdocs.com/temporary-license/)

지속적으로 사용하려면 라이선스를 직접 구매하는 것을 고려하세요. [그룹닥스](https://purchase.groupdocs.com/buy).

### 기본 초기화

프로젝트에 GroupDocs.Viewer를 설정하려면:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// TXT 파일 경로로 Viewer 객체를 초기화합니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 렌더링 코드는 여기에 입력하세요.
}
```

## 구현 가이드

이제 각 기능을 자세히 살펴보고 이를 어떻게 구현할 수 있는지 살펴보겠습니다.

### TXT 문서를 다중 페이지 HTML로 렌더링

#### 개요
이 기능은 TXT 문서를 여러 페이지 HTML 형식으로 변환하는 방법을 보여줍니다. 텍스트 파일의 각 페이지는 내장된 리소스가 있는 개별 HTML 파일로 렌더링됩니다.

#### 1단계: 뷰어 설정

생성하다 `Viewer` 소스 TXT 파일에 대한 개체:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// 샘플 텍스트 파일로 뷰어를 초기화합니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2단계로 계속하세요.
```

#### 2단계: HTML 보기 옵션 구성

설정 `HtmlViewOptions` 각 페이지를 별도로 렌더링하려면:

```csharp
// 다중 페이지 렌더링을 위한 HTML 보기 옵션을 설정합니다.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// 문서를 여러 페이지 HTML로 렌더링합니다.
viewer.View(options);
}
```

**설명**: 그 `ForEmbeddedResources()` 이 방법을 사용하면 이미지와 스타일과 같은 리소스가 HTML 파일에 직접 포함되어 쉽게 공유될 수 있습니다.

### TXT 문서를 단일 페이지 HTML로 렌더링

#### 개요
TXT 문서를 단일 HTML 페이지로 변환합니다. 이는 하나의 연속된 웹 페이지로 표시되어야 하는 문서에 적합합니다.

#### 1단계: 뷰어 설정

초기화 `Viewer` 물체:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// 다른 텍스트 파일에 대한 새로운 Viewer 인스턴스를 초기화합니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // 2단계로 계속하세요.
```

#### 2단계: 단일 페이지 HTML 옵션 구성

구성 `HtmlViewOptions` 단일 페이지 설정이 활성화된 경우:

```csharp
// 단일 HTML 페이지로 렌더링하기 위한 옵션을 설정합니다.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// 단일 HTML 페이지로 렌더링합니다.
viewer.View(options);
}
```

**설명**: 그 `RenderToSinglePage` 속성은 전체 콘텐츠가 한 페이지에 렌더링되도록 보장합니다.

### TXT 문서를 JPG로 렌더링

#### 개요
이 기능을 사용하면 텍스트 문서를 JPEG 이미지로 변환할 수 있어 시각적 프레젠테이션이나 보관 목적으로 유용합니다.

#### 1단계: 뷰어 설정

준비하세요 `Viewer` 물체:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// 샘플 파일로 뷰어를 초기화합니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2단계로 계속하세요.
```

#### 2단계: JPG 보기 옵션 구성

설정 `JpgViewOptions` 이미지 렌더링을 위해:

```csharp
// JPG 이미지로 렌더링하기 위한 옵션을 설정합니다.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// 문서를 JPEG 파일로 렌더링합니다.
viewer.View(options);
}
```

**설명**: 그 `JpgViewOptions` 클래스는 문서의 각 페이지를 JPEG 형식으로 렌더링하고 저장하는 방법을 지정합니다.

### TXT 문서를 PNG로 렌더링

#### 개요
텍스트 문서를 PNG 형식으로 변환하여 투명도 지원과 함께 고품질 이미지 출력을 제공합니다.

#### 1단계: 뷰어 설정

초기화 `Viewer` 물체:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// TXT 파일에 대한 뷰어 인스턴스를 만듭니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2단계로 계속하세요.
```

#### 2단계: PNG 보기 옵션 구성

설정 `PngViewOptions`:

```csharp
// PNG 이미지로 렌더링하기 위한 보기 옵션을 설정합니다.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// PNG 형식으로 문서를 렌더링합니다.
viewer.View(options);
}
```

**설명**: 그 `PngViewOptions` 클래스를 사용하면 각 페이지를 투명하게 렌더링할 수 있으므로 레이어 그래픽에 적합합니다.

### TXT 문서를 PDF로 렌더링

#### 개요
이 기능은 텍스트 문서를 보편적으로 접근 가능한 PDF 형식으로 변환하는 데 적합합니다.

#### 1단계: 뷰어 설정

준비하세요 `Viewer` 물체:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// 샘플 텍스트 파일에 대한 뷰어 인스턴스를 초기화합니다.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // 2단계로 계속하세요.
```

#### 2단계: PDF 보기 옵션 구성

설정 `PdfViewOptions`:

```csharp
// PDF 문서로 렌더링하기 위한 보기 옵션을 설정합니다.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// 문서를 PDF 파일로 변환합니다.
viewer.View(options);
}
```

**설명**: 그 `PdfViewOptions` 클래스는 TXT 파일을 PDF 문서로 변환하고 저장하는 방법을 지정합니다.

## 결론

GroupDocs.Viewer for .NET을 사용하면 텍스트 문서를 다양한 형식으로 간편하게 변환할 수 있습니다. 이 가이드에서는 C#을 사용하여 TXT 파일을 여러 페이지 HTML, 단일 페이지 HTML, JPG, PNG, PDF로 변환하는 방법을 다뤘습니다. 문서 접근성이나 호환성 향상을 원하든, 이러한 방법들은 강력한 솔루션을 제공합니다.

추가 지원이나 보다 고급 기능에 대해서는 다음을 참조하세요. [공식 GroupDocs.Viewer 문서](https://docs.groupdocs.com/viewer/net/)즐거운 코딩 되세요!