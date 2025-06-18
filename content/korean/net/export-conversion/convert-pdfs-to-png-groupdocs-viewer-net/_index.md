---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET을 사용하여 PDF 페이지를 원본 크기를 유지하면서 PNG 이미지로 변환하는 방법을 알아보세요. 이 가이드에서는 설정, 구성 및 모범 사례를 다룹니다."
"title": "GroupDocs.Viewer for .NET을 사용하여 PDF를 원본 크기의 PNG로 변환"
"url": "/ko/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# GroupDocs.Viewer for .NET을 사용하여 PDF를 원본 크기의 PNG로 변환

## 소개

PDF 파일을 원본 페이지 크기를 유지하면서 PNG 이미지로 변환하는 것은 고품질 문서 디지털화 또는 웹 콘텐츠 제작에 필수적입니다. 이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 PDF 페이지를 원본 크기를 유지하면서 PNG 파일로 렌더링하는 방법을 안내합니다.

![GroupDocs.Viewer for .NET을 사용하여 PDF를 원래 크기로 PNG로 변환](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**배울 내용:**
- 프로젝트에서 .NET용 GroupDocs.Viewer를 설정하고 구성하는 방법
- 페이지 크기를 유지하면서 PDF를 PNG 이미지로 렌더링하는 단계별 프로세스
- 최적의 성능을 위한 주요 구성 옵션 및 모범 사례

이 튜토리얼을 마치면 이 기능을 애플리케이션에 완벽하게 통합할 수 있을 것입니다. 시작하는 데 필요한 전제 조건부터 살펴보겠습니다.

## 필수 조건

프로젝트에 GroupDocs.Viewer for .NET을 구현하기 전에 다음 요구 사항이 있는지 확인하세요.

### 필수 라이브러리 및 버전
- **.NET용 GroupDocs.Viewer**: 버전 25.3.0 이상.

### 환경 설정 요구 사항
- Visual Studio와 같은 호환 가능한 개발 환경.
- C# 프로그래밍에 대한 기본적인 이해.

### 지식 전제 조건
- NuGet 패키지 관리에 대한 지식이 필요합니다.
- .NET 애플리케이션에서 PDF 작업과 이미지 처리에 대한 경험이 있습니다.

이러한 필수 구성 요소를 갖추면 .NET용 GroupDocs.Viewer를 설정할 수 있습니다.

## .NET용 GroupDocs.Viewer 설정

.NET용 GroupDocs.Viewer를 사용하려면 아래 설치 단계를 따르세요.

### NuGet 패키지 관리자 콘솔을 통한 설치
Visual Studio에서 프로젝트를 열고 다음 명령을 사용하세요.
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### .NET CLI를 통한 설치
또는 다음 명령을 사용하여 .NET CLI를 사용하여 설치할 수 있습니다.
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 라이센스 취득 단계
1. **무료 체험**: 평가판을 다운로드하세요 [GroupDocs 다운로드](https://releases.groupdocs.com/viewer/net/).
2. **임시 면허**: 전체 기능을 탐색하기 위한 임시 라이센스를 얻으세요. [임시 면허 페이지](https://purchase.groupdocs.com/temporary-license/).
3. **구입**: 장기 사용을 위해서는 라이센스를 구매하세요. [구매 페이지](https://purchase.groupdocs.com/buy).

### 기본 초기화 및 설정
C# 프로젝트에서 .NET용 GroupDocs.Viewer를 초기화하려면 다음 단계를 따르세요.
1. 필요한 네임스페이스 가져오기:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. 입력 PDF와 출력 디렉토리에 대한 경로를 설정합니다.
3. 초기화 `Viewer` 이 스니펫에 표시된 것처럼 소스 문서에 대한 경로를 사용합니다.
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## 구현 가이드
이 섹션에서는 PDF 페이지를 원래 크기를 유지하면서 PNG 이미지로 렌더링하는 구현 방법을 다룹니다.

### 원본 페이지 크기를 사용하여 PDF 페이지를 PNG로 렌더링
#### 개요
이 기능을 사용하면 PDF 문서의 각 페이지를 원본 크기를 유지하면서 PNG 이미지로 렌더링할 수 있습니다. 이 기능은 문서의 정확한 시각적 표현이 필요한 애플리케이션에 특히 유용합니다.

##### 1단계: 경로 설정 및 뷰어 초기화
입력 PDF 경로와 출력 디렉토리에 대한 변수를 생성합니다.
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
초기화 `Viewer` 소스 문서 경로를 사용한 클래스:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // 코드 블록은 다음 단계에서 계속됩니다.
}
```
##### 2단계: PngViewOptions 구성
인스턴스를 생성합니다 `PngViewOptions`출력 이미지에 대한 파일 명명 패턴을 지정합니다.
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
각 페이지를 원래 크기로 렌더링하도록 뷰어 옵션을 구성하세요.
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### 3단계: 문서 페이지 렌더링
전화하다 `View` 당신의 방법 `Viewer` 예를 들어 구성된 뷰 옵션을 전달합니다.
```csharp
viewer.View(viewOptions);
```
### 문제 해결 팁
- 경로가 올바른지, 디렉토리가 있는지 확인하세요.
- 입력 디렉토리에서 읽고 출력 디렉토리에 쓸 수 있는 권한이 있는지 확인하세요.

## 실제 응용 프로그램
1. **문서 디지털화**: 보관된 PDF 문서를 디지털 이미지로 변환하여 더 쉽게 접근하고 배포할 수 있습니다.
2. **웹 포털**: PDF 리더가 없어도 웹사이트에 문서 미리보기를 표시합니다.
3. **콘텐츠 관리 시스템(CMS)**: CMS 플랫폼과 통합하여 대용량 PDF 콘텐츠를 효율적으로 관리하고 표시합니다.

## 성능 고려 사항
GroupDocs.Viewer for .NET을 사용하여 애플리케이션의 성능을 최적화하려면:
- 대용량 파일을 다루는 경우 문서를 청크로 처리하여 메모리 사용량을 제한하세요.
- 렌더링 중에 스레드가 차단되는 것을 방지하려면 가능하면 비동기 메서드를 사용하세요.
- 폐기하다 `Viewer` 사용 후 즉시 인스턴스를 종료하여 리소스를 확보합니다.

## 결론
이 튜토리얼에서는 GroupDocs.Viewer for .NET을 사용하여 PDF 페이지를 원래 크기를 유지하면서 PNG 이미지로 렌더링하는 방법을 알아보았습니다. 환경 설정, 최적의 결과를 위한 필수 옵션 구성, 그리고 이 기능의 실제 활용 방법을 살펴보았습니다.

다음 단계로는 GroupDocs.Viewer에서 제공하는 다른 렌더링 옵션을 실험하거나 대규모 프로젝트에 통합하여 문서 관리 기능을 강화하는 것이 포함됩니다.

## FAQ 섹션
1. **GroupDocs.Viewer를 사용하여 대용량 PDF 파일을 처리하는 가장 좋은 방법은 무엇입니까?**
   - 더 작은 단위로 문서를 처리하고 비동기 방식을 사용하여 성능을 유지합니다.
2. **PNG 파일 이름을 사용자 정의할 수 있나요?**
   - 예, 명명 패턴을 지정하여 `PngViewOptions`.
3. **특정 페이지만 렌더링하는 것이 가능합니까?**
   - 물론입니다. 구성할 수 있습니다. `PageNumbers` ~에 `PngViewOptions` 어떤 페이지를 렌더링할지 지정합니다.
4. **GroupDocs.Viewer에 대한 라이선스를 어떻게 처리하나요?**
   - 옵션으로는 무료 체험판, 임시 라이선스, 전체 라이선스 구매 등이 있습니다.
5. **이 설정을 웹 애플리케이션에 사용할 수 있나요?**
   - 네, ASP.NET Core 및 기타 .NET 기반 웹 프레임워크에서 PDF의 서버 측 렌더링에 적합합니다.

## 자원
- [선적 서류 비치](https://docs.groupdocs.com/viewer/net/)
- [API 참조](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/net/)
- [라이센스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험](https://releases.groupdocs.com/viewer/net/)
- [임시 면허](https://purchase.groupdocs.com/temporary-license/)
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)