---
"date": "2025-04-25"
"description": "GroupDocs.Viewer for .NET을 사용하여 아카이브 정보를 효율적으로 추출하는 방법을 알아보세요. 이 가이드에서는 설정, 코드 예제, 그리고 실제 적용 사례를 다룹니다."
"title": "GroupDocs.Viewer for .NET을 사용하여 아카이브 정보를 검색하는 방법&#58; 종합 가이드"
"url": "/ko/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
---

# .NET용 GroupDocs.Viewer를 사용하여 보관 정보를 검색하는 방법: 포괄적인 가이드

## 소개

ZIP 파일과 같은 아카이브 파일에서 자세한 정보를 효율적으로 추출하고 싶으신가요? 문서 관리에 있어 구조를 이해하는 것은 매우 중요합니다. 이 가이드에서는 **.NET용 GroupDocs.Viewer** 보관 파일에 대한 포괄적인 세부 정보를 검색하고 표시합니다.

![.NET용 GroupDocs.Viewer를 사용하여 보관 정보 검색](/viewer/metadata-properties/retrieve-archive-information.png)

이 튜토리얼에서는 다음 내용을 다룹니다.
- .NET 애플리케이션에서 GroupDocs.Viewer 설정
- 아카이브 파일에서 뷰 정보 검색
- 아카이브 내 폴더 구조 표시

이 가이드를 마치면 이러한 기능 구현에 대한 탄탄한 이해를 갖추게 될 것입니다. 코드로 들어가기 전에 필요한 것부터 시작해 보겠습니다.

### 필수 조건

다음 사항을 준비하세요.

- **라이브러리 및 버전**: .NET용 GroupDocs.Viewer(버전 25.3.0)를 설치합니다.
- **환경 설정**: Visual Studio와 같은 적합한 .NET 개발 환경을 사용하세요.
- **지식 전제 조건**: C#과 .NET 애플리케이션에서의 파일 처리에 대한 기본적인 이해.

## .NET용 GroupDocs.Viewer 설정

.NET용 GroupDocs.Viewer를 사용하려면 NuGet 패키지 관리자를 통해 설치하세요.

### 설치 지침

**NuGet 패키지 관리자 콘솔**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 면허 취득

GroupDocs.Viewer는 다양한 라이선스 옵션을 제공합니다.
- **무료 체험**기본 기능을 살펴보세요.
- **임시 면허**: 평가 기간 동안 모든 기능에 액세스할 수 있습니다.
- **구입**: 장기간 사용하려면 라이선스 구매를 고려하세요.

설치 및 라이선스 설정 후 애플리케이션에서 GroupDocs.Viewer를 초기화하세요. 설정 예시는 다음과 같습니다.

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // 여기에서 뷰어 기능을 사용하세요.
}
```

## 구현 가이드

구조화된 접근 방식을 위해 구현을 주요 기능으로 나누어 보겠습니다.

### 보관 파일에 대한 보기 정보 검색

아카이브의 구조를 이해하는 것은 매우 중요합니다. 이를 달성하는 방법은 다음과 같습니다.

#### 뷰어 객체 초기화

인스턴스를 생성합니다 `Viewer` 아카이브 파일 경로를 사용한 클래스:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // 처리에 필요한 코드는 여기에 입력하세요.
}
```

#### 보기 정보 얻기

JPG 이미지로 포맷된 뷰 정보를 검색합니다.

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### 루트 폴더 정보 표시

전체적인 개요를 보려면 루트 폴더 세부 정보를 인쇄하세요.

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### 재귀적으로 하위 폴더 이름을 읽고 인쇄

보관함 내의 하위 폴더를 탐색하려면 다음 재귀적 방법을 사용하세요.

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### 실제 응용 프로그램

GroupDocs.Viewer for .NET은 다양한 시나리오에서 사용될 수 있습니다.
- **문서 관리 시스템**: 자동으로 보관 구조를 추출하고 표시합니다.
- **콘텐츠 전송 플랫폼**: 사용자에게 보관된 콘텐츠의 미리보기를 제공합니다.
- **데이터 분석 도구**: 비즈니스 통찰력을 얻기 위해 보관소 내의 폴더 계층 구조를 분석합니다.

ASP.NET이나 WPF 등 다른 프레임워크와의 통합이 간단하여 기존 시스템에 원활하게 통합할 수 있습니다.

## 성능 고려 사항

최적의 성능을 위해:
- **리소스 사용 최적화**: 메모리를 효율적으로 관리하고 대용량 파일을 처리합니다.
- **메모리 관리 모범 사례**: 폐기하다 `Viewer` 객체를 적절하게 배치하여 리소스를 신속하게 확보합니다.

## 결론

이 튜토리얼에서는 GroupDocs.Viewer for .NET을 활용하여 보관 파일에서 자세한 정보를 가져오는 방법을 알아보았습니다. 이러한 기능을 구현하면 문서 관리 역량을 크게 향상시킬 수 있습니다.

### 다음 단계

GroupDocs.Viewer가 제공하는 고급 기능을 살펴보거나 애플리케이션의 다른 구성 요소와 통합해 보세요. 다양한 파일 형식과 복잡한 폴더 구조를 실험하여 이해를 심화하세요.

## FAQ 섹션

1. **의 목적은 무엇입니까? `ViewInfoOptions`?**
   - JPG와 같은 특정 형식을 렌더링하는 등 문서를 보는 방법을 구성합니다.

2. **대규모 아카이브를 효율적으로 처리하려면 어떻게 해야 하나요?**
   - 메모리 관리 기술을 사용하고 리소스를 적절하게 처리합니다.

3. **GroupDocs.Viewer는 암호로 보호된 파일을 처리할 수 있나요?**
   - 네, 올바른 라이선스와 구성을 사용하면 암호화된 문서를 처리할 수 있습니다.

4. **처리할 수 있는 보관 파일 크기에 제한이 있습니까?**
   - 제한은 시스템의 메모리 용량에 따라 다르며, 파일이 클수록 더 많은 리소스가 필요합니다.

5. **GroupDocs.Viewer를 ASP.NET 애플리케이션과 통합하려면 어떻게 해야 하나요?**
   - 콘솔 애플리케이션에서와 비슷하게 컨트롤러 작업이나 서비스 내에서 Viewer 클래스를 사용합니다.

## 자원

- [선적 서류 비치](https://docs.groupdocs.com/viewer/net/)
- [API 참조](https://reference.groupdocs.com/viewer/net/)
- [.NET용 GroupDocs.Viewer 다운로드](https://releases.groupdocs.com/viewer/net/)
- [라이센스 구매](https://purchase.groupdocs.com/buy)
- [무료 체험판](https://releases.groupdocs.com/viewer/net/)
- [임시 면허 신청](https://purchase.groupdocs.com/temporary-license/)
- [지원 포럼](https://forum.groupdocs.com/c/viewer/9)