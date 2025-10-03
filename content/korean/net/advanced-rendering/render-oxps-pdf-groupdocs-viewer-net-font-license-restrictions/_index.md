---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET을 사용하여 글꼴 라이선스 제한을 우회하면서 PDF 및 OXPS 문서를 렌더링하는 방법을 알아보세요. 설정, 구현 및 실제 적용 사례를 살펴보세요."
"title": "GroupDocs.Viewer .NET을 사용하여 글꼴 제한이 있는 PDF/OXPS 렌더링하기&#58; 종합 가이드"
"url": "/ko/net/advanced-rendering/render-oxps-pdf-groupdocs-viewer-net-font-license-restrictions/"
"weight": 1
type: docs
---
# GroupDocs.Viewer .NET을 사용하여 글꼴 제한이 있는 PDF/OXPS 렌더링: 포괄적인 가이드

## 소개

XPS 또는 OXPS 문서는 글꼴 라이선스 제한으로 인해 렌더링이 어려울 수 있습니다. 이 튜토리얼에서는 이러한 문서를 효과적으로 렌더링하는 방법을 안내합니다. **.NET용 GroupDocs.Viewer**문서 관리 시스템, 콘텐츠 게시 플랫폼, 원활한 문서 변환이 필요한 애플리케이션에 이상적인 이 솔루션은 매우 귀중합니다.

![GroupDocs.Viewer for .NET에서 글꼴 제한을 적용하여 PDF/OXPS 렌더링](/viewer/advanced-rendering/render-pdf-oxps-font-restrictions-img.png)

이 가이드에서는 다음 내용을 알아봅니다.
- .NET용 GroupDocs.Viewer 설정
- 내장된 글꼴을 사용하여 XPS/OXPS 문서 렌더링
- 렌더링 중 글꼴 라이선스 제한 비활성화

## 필수 조건

시작하기 전에 다음 사항을 확인하세요.

### 필수 라이브러리 및 버전
- **.NET용 GroupDocs.Viewer**: 버전 25.3.0 이상.
- **개발 환경**: Visual Studio(2017 이상) 또는 .NET 개발을 지원하는 호환 IDE.

### 환경 설정 요구 사항
- 선택한 IDE에서 AC# 프로젝트를 실행합니다.
- 라이브러리 설치를 위해 NuGet 패키지 관리자에 액세스합니다.

### 지식 전제 조건
- C# 및 .NET 프레임워크 개념에 대한 기본적인 이해.
- .NET 환경에서 파일 경로와 디렉토리를 처리하는 데 익숙합니다.

필수 구성 요소를 고려했으므로 .NET용 GroupDocs.Viewer를 설정해 보겠습니다.

## .NET용 GroupDocs.Viewer 설정

### 설치 정보

NuGet 패키지 관리자 콘솔이나 .NET CLI를 사용하여 GroupDocs.Viewer를 설치하세요.

**NuGet 패키지 관리자 콘솔**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 라이센스 취득 단계
- **무료 체험**: 무료 체험판을 통해 기능을 살펴보세요.
- **임시 면허**: 장기 평가를 위해 임시 라이센스를 얻으세요.
- **구입**: 전체 액세스 및 지원을 받으려면 구매를 고려하세요.

### 기본 초기화 및 설정

설치 후 C# 프로젝트에서 GroupDocs.Viewer를 초기화합니다.

```csharp
using System;
using GroupDocs.Viewer;

namespace DocumentRendering
{
    class Program
    {
        static void Main(string[] args)
        {
            // 문서 경로로 Viewer 객체를 초기화합니다.
            using (Viewer viewer = new Viewer("path/to/your/document.oxps"))
            {
                Console.WriteLine("GroupDocs.Viewer is set up and ready!");
            }
        }
    }
}
```

GroupDocs.Viewer가 구성된 상태에서 글꼴 라이선스 제한이 비활성화된 OXPS 문서 렌더링을 구현해 보겠습니다.

## 구현 가이드

### 글꼴 라이선스 제한이 비활성화된 XPS/OXPS 문서 렌더링

#### 개요
이 기능을 사용하면 내장된 글꼴 라이선스 검증을 우회하여 XPS 또는 OXPS 문서를 렌더링할 수 있습니다. 라이선스 제약이 있는 독점 글꼴을 처리할 때 유용합니다.

#### 단계별 구현
**출력 디렉토리 및 페이지 파일 경로 형식 정의**
출력 디렉토리를 설정하세요:

```csharp
string outputDirectory = "YOUR_OUTPUT_DIRECTORY"; // 원하는 출력 디렉토리 경로를 사용하세요
string pageFilePathFormat = System.IO.Path.Combine(outputDirectory, "page_{0}.png");
```
이 스니펫은 렌더링된 페이지가 저장될 위치를 지정합니다.

**뷰어 인스턴스 생성**
초기화 `Viewer` OXPS 문서에 대한 개체:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TestFiles.OXPS_EMBEDDED_FONT")) // 실제 문서 경로로 바꾸세요
{
    // 추가 구성 및 렌더링 단계는 여기에 있습니다.
}
```
이 단계에서는 문서를 렌더링할 준비를 합니다.

**HTML 보기 옵션 설정**
구성 `HtmlViewOptions` 내장된 리소스로 렌더링하려면:

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
이 옵션을 사용하면 모든 필수 리소스가 각 페이지 파일에 포함되어 오프라인 액세스가 용이해집니다.

**글꼴 라이선스 확인 비활성화**
다음 속성을 설정하여 글꼴 라이선스 검증을 비활성화합니다.

```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
이 검증 기능을 비활성화하면 글꼴 라이선스 문제로 인해 방해받지 않고 문서를 렌더링할 수 있습니다.

**문서 렌더링**
마지막으로 다음을 사용합니다. `View` 지정된 옵션으로 문서를 렌더링하는 방법:

```csharp
viewer.View(options);
```
이 명령은 구성에 따라 렌더링 프로세스를 실행합니다.

#### 문제 해결 팁
- **누락된 글꼴**: 문서에 필요한 모든 글꼴이 설치되었거나 포함되어 있는지 확인하세요.
- **파일 경로 문제**: 디렉토리 경로와 파일 이름을 다시 한 번 확인하여 오타가 없는지 확인하세요.
- **라이센스 오류**: 라이센스 문제가 발생하는 경우 유효한 라이센스가 있는지 확인하세요.

## 실제 응용 프로그램

### 실제 사용 사례
1. **콘텐츠 게시 플랫폼**: 법적 제약 없이 독점 글꼴을 사용하여 문서를 렌더링합니다.
2. **문서 관리 시스템**: 다양한 플랫폼에서 원활하게 문서를 볼 수 있습니다.
3. **법률 및 금융 산업**: 특정 글꼴 사용이 필요한 민감한 문서를 처리합니다.
4. **학술 기관**다이어그램과 텍스트를 삽입하여 연구 논문을 공유합니다.
5. **마케팅 대행사**: 시각적으로 일관된 프레젠테이션과 보고서를 만듭니다.

### 통합 가능성
- 동적인 문서 보기를 위해 .NET 웹 애플리케이션과 통합합니다.
- 데스크톱 애플리케이션 내에서 사용하여 렌더링된 문서에 오프라인으로 액세스할 수 있도록 합니다.
- Azure Blob Storage나 AWS S3와 같은 클라우드 스토리지 솔루션과 결합하여 확장 가능한 문서 관리를 실현하세요.

## 성능 고려 사항

### 성능 최적화
- **메모리 관리**: 메모리를 효율적으로 관리하기 위해 폐기합니다. `Viewer` 사용 후의 물건.
- **리소스 사용**: 특히 대량의 문서를 렌더링할 때 리소스 사용량을 모니터링합니다.
- **일괄 처리**: 여러 문서를 효율적으로 처리하기 위해 일괄 처리를 구현합니다.

### GroupDocs.Viewer를 사용한 .NET 메모리 관리 모범 사례
- 항상 포장하세요 `Viewer` 인스턴스 `using` 적절한 폐기를 위한 진술.
- 메모리 누수나 리소스 소모가 많은 영역을 식별하고 해결하기 위해 애플리케이션 프로파일을 작성합니다.

## 결론

이 튜토리얼에서는 글꼴 라이선스 제한을 비활성화하면서 XPS/OXPS 문서를 렌더링하는 방법을 살펴보았습니다. **.NET용 GroupDocs.Viewer**설명된 단계를 따르면 다양한 애플리케이션에서 문서 렌더링을 효과적으로 관리할 수 있습니다.

다음 단계로, GroupDocs.Viewer의 추가 기능을 살펴보고 프로젝트에 통합해 보세요. 이 강력한 라이브러리를 최대한 활용하려면 다양한 문서 유형과 구성을 시험해 보세요.

## FAQ 섹션

1. **.NET용 GroupDocs.Viewer란 무엇인가요?**
   - 이는 개발자가 기본 소프트웨어를 설치하지 않고도 애플리케이션 내에서 다양한 문서 형식을 렌더링할 수 있게 해주는 다용도 라이브러리입니다.

2. **GroupDocs.Viewer에서 글꼴 라이선스 문제를 어떻게 처리할 수 있나요?**
   - 를 사용하여 `DisableFontLicenseVerifications` 속성을 사용하면 렌더링 중에 글꼴 라이선스 제한을 우회할 수 있습니다.

3. **클라우드 환경에서 GroupDocs.Viewer를 사용할 수 있나요?**
   - 네, 클라우드 애플리케이션과 서비스 내에서 원활하게 작동하도록 설계되었습니다.

4. **GroupDocs.Viewer를 통합할 때 흔히 발생하는 문제는 무엇입니까?**
   - 과제에는 종속성 관리, 출력 경로 구성, 대용량 문서의 효율적인 처리 등이 포함될 수 있습니다.

5. **GroupDocs.Viewer에서는 비표준 글꼴을 지원합니까?**
   - 내장된 글꼴을 처리할 수 있지만, 렌더링 문제를 방지하려면 모든 필수 글꼴을 사용할 수 있거나 문서에 내장되어 있는지 확인하세요.