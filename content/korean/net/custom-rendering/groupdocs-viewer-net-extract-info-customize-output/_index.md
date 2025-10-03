---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET을 사용하여 문서 메타데이터를 추출하고 출력 디렉터리를 사용자 지정하는 방법을 알아보세요. 지금 바로 문서 관리 시스템을 강화하세요."
"title": "GroupDocs.Viewer .NET을 사용하여 문서 정보 추출 및 출력 사용자 정의 - 포괄적인 가이드"
"url": "/ko/net/custom-rendering/groupdocs-viewer-net-extract-info-customize-output/"
"weight": 1
type: docs
---
# GroupDocs.Viewer .NET을 사용하여 문서 정보 추출 및 출력 사용자 지정
## 사용자 정의 렌더링 튜토리얼
### 배울 내용:
- GroupDocs.Viewer를 사용하여 문서에서 기본 정보를 추출하는 방법
- 문서를 렌더링할 때 출력 디렉토리를 사용자 지정하는 단계
- 모범 사례 및 문제 해결 팁

**소개:**
오늘날의 디지털 시대에는 모든 비즈니스 환경에서 문서를 효율적으로 처리하는 것이 매우 중요합니다. 문서 관리 시스템을 구축하는 개발자든 워크플로를 개선하는 IT 전문가든 PDF 및 기타 파일 형식을 관리하는 것은 어려울 수 있습니다. GroupDocs.Viewer for .NET은 문서를 원활하게 보고, 조작하고, 정보를 추출할 수 있는 강력한 기능을 제공하여 이러한 문제를 간소화합니다. 이 튜토리얼에서는 GroupDocs.Viewer를 활용하여 기본 문서 정보를 검색하고 렌더링된 뷰의 출력 디렉터리를 사용자 지정하는 방법을 살펴보겠습니다.

![GroupDocs.Viewer for .NET을 사용하여 문서 정보 추출 및 출력 사용자 지정](/viewer/custom-rendering/extract-document-info-customize-output-img.png)

**필수 조건:**
이 튜토리얼을 따라하려면 다음이 필요합니다.
- **.NET용 GroupDocs.Viewer**: 이 라이브러리는 문서 보기 기능에 액세스하는 데 필수적입니다. 25.3.0 이상 버전을 사용하세요.
- .NET 애플리케이션(예: Visual Studio)을 위한 개발 환경이 설정되었습니다.
- C#에 대한 기본 지식과 코드에서 파일 경로를 처리하는 데 익숙함이 필요합니다.
- C#에서 객체 지향 프로그래밍 개념에 대한 이해.
- .NET에서 파일 I/O 작업을 수행한 경험이 있습니다.

**.NET용 GroupDocs.Viewer 설정:**
NuGet 패키지 관리자 또는 .NET CLI를 통해 GroupDocs.Viewer를 설치하세요.

**NuGet 패키지 관리자 콘솔:**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 라이센스 취득:
- **무료 체험**: 무료 체험판을 통해 기본 기능을 탐색해 보세요.
- **임시 면허**: 장기 테스트를 위해서는 임시 라이센스를 취득하는 것을 고려하세요. [GroupDocs 웹사이트](https://purchase.groupdocs.com/temporary-license/).
- **구입**: 전체 프로덕션에 사용하려면 구독을 구매하세요.

### 기본 초기화 및 설정:
C# 프로젝트에서 GroupDocs.Viewer를 초기화하는 방법은 다음과 같습니다.
```csharp
using System;
using GroupDocs.Viewer;

namespace DocumentViewerApp
{
class Program
{
    static void Main(string[] args)
    {
        string filePath = @"C:\Path\To\Your\Document.pdf";
        
        using (Viewer viewer = new Viewer(filePath))
        {
            // 문서와 상호작용하는 코드는 여기에 입력하세요.
        }
    }
}
```

**구현 가이드:**
### 기능 1: 문서에 대한 기본 정보 가져오기
#### 개요:
작업을 수행하기 전에 문서의 구조를 파악하기 위해서는 문서에 대한 필수 정보를 검색하는 것이 중요합니다. GroupDocs.Viewer를 사용하면 페이지 수, 파일 유형 등의 메타데이터를 추출할 수 있습니다.

**단계별 구현:**
##### 1단계: 문서로 뷰어 초기화
문서 경로를 지정하여 바꾸세요 `'YOUR_DOCUMENT_DIRECTORY'` 파일이 저장된 실제 디렉토리:
```csharp
string filePath = @"YOUR_DOCUMENT_DIRECTORY\SamplePDF.pdf";
```
##### 2단계: HTML 렌더링을 위한 뷰 정보 검색
인스턴스를 생성합니다 `ViewInfoOptions` 문서의 뷰 정보에 효율적으로 접근하기 위해 HTML 형식으로 렌더링하도록 특별히 설계되었습니다.
```csharp
using (Viewer viewer = new Viewer(filePath))
{
    ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
    ViewInfo info = viewer.GetViewInfo(options);
    
    // 페이지 수와 같은 기본 문서 정보를 출력합니다.
    Console.WriteLine($"Document type: {info.FileType}");
    Console.WriteLine($"Page count: {info.Pages.Count}");
}
```
**설명:** 
- `ForHtmlView()` HTML 렌더링에 적합한 뷰 세부 정보를 검색하기 위한 옵션을 구성합니다.
- `GetViewInfo(options)` 문서에 대한 메타데이터를 추출합니다.

##### 문제 해결 팁:
- 파일 경로가 올바르게 지정되었고 애플리케이션에서 액세스할 수 있는지 확인하세요.
- 오류가 발생하는 경우 GroupDocs.Viewer에서 문서 형식이 지원되는지 확인하십시오. `GetViewInfo`.

### 기능 2: 문서 보기에 대한 출력 디렉토리 사용자 지정
#### 개요:
문서를 다양한 형식으로 렌더링할 때 사용자 지정 출력 디렉터리는 필수적입니다. 이 기능을 사용하면 렌더링된 파일의 저장 위치를 지정하여 파일 시스템 구성을 더욱 효율적으로 제어할 수 있습니다.

**단계별 구현:**
##### 1단계: 입력 및 출력 경로 정의
입력(소스 문서)과 출력 경로 모두에 대한 변수를 설정합니다.
```csharp
string filePath = @"YOUR_DOCUMENT_DIRECTORY\SamplePDF.pdf";
string outputPath = @"@YOUR_OUTPUT_DIRECTORY";
```
##### 2단계: 뷰어 초기화 및 HTML 보기 옵션 구성
구성 `HtmlViewOptions` 렌더링된 HTML 파일을 저장할 위치를 지정하려면 다음을 사용합니다. `{page}.html` 동적 명명을 위한 플레이스홀더로:
```csharp
using (Viewer viewer = new Viewer(filePath))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(outputPath + "\{page}.html");
    viewer.View(options);
}
```
**설명:** 
- `ForEmbeddedResources()` 이미지 등의 리소스가 HTML에 내장되어 배포가 간소화됩니다.
- 지정된 경로 `outputPath` 출력 파일을 효과적으로 구성하는 데 중요합니다.

##### 문제 해결 팁:
- 출력 디렉토리에 대한 권한을 확인하여 해당 디렉토리에 파일을 쓸 수 있는지 확인하세요.
- 페이지 이름 지정에 사용되는 형식 문자열을 검증합니다(예: `{page}.html`) 런타임 오류를 방지합니다.

**실제 적용 분야:**
GroupDocs.Viewer는 다양한 실제 응용 프로그램을 제공합니다.
1. **문서 관리 시스템**: 자동으로 메타데이터를 추출하고 웹 기반 접근을 위해 문서를 렌더링합니다.
2. **디지털 서명**: 추출된 정보를 활용하여 서명된 문서를 효율적으로 관리합니다.
3. **콘텐츠 전송 네트워크(CDN)**: 글로벌 서버에 콘텐츠를 배포하기 위해 출력 디렉토리를 사용자 정의합니다.
4. **통합 CRM 플랫폼**: 문서 보기를 고객 대시보드에 직접 내장하여 고객 관계 관리를 강화합니다.
5. **교육 포털**: 맞춤형 렌더링을 통해 학생들이 강의 자료에 쉽게 접근할 수 있도록 합니다.

**성능 고려 사항:**
GroupDocs.Viewer를 사용할 때 성능을 최적화하는 것은 특히 대규모 애플리케이션의 경우 매우 중요합니다.
- **자원 관리**: 항상 닫아주세요 `Viewer` 인스턴스화하여 메모리 리소스를 확보합니다.
- **일괄 처리**: 여러 파일을 동시에 처리하는 경우 로드 시간을 줄이기 위해 문서를 일괄적으로 처리합니다.
- **캐싱 전략**: 자주 액세스하는 문서 뷰에 대한 캐싱 메커니즘을 구현하여 성능을 개선합니다.

**결론:**
GroupDocs.Viewer for .NET을 사용하여 문서에서 기본 정보를 추출하고 출력 디렉터리를 사용자 지정하는 방법을 살펴보았습니다. 이 단계를 따라 하면 문서 관리 기능을 향상시키고, 워크플로를 간소화하며, 더 나은 사용자 경험을 제공할 수 있습니다.

**다음 단계:**
- GroupDocs.Viewer의 추가 기능을 시험해 보세요.
- 기능을 확대하기 위해 다른 프레임워크와의 통합 가능성을 탐색합니다.

**FAQ 섹션:**
1. **GroupDocs.Viewer는 어떤 파일 형식을 지원합니까?**
   - PDF, Word 문서, Excel 스프레드시트 등 다양한 문서 유형을 지원합니다.