---
title: 로컬 디스크에서 문서 로드
linktitle: 로컬 디스크에서 문서 로드
second_title: GroupDocs.Viewer .NET API
description: .NET용 Groupdocs.Viewer를 사용하여 로컬 디스크에서 문서를 원활하게 렌더링하는 방법을 알아보세요. 효율적인 문서로 .NET 애플리케이션을 강화하세요.
weight: 10
url: /ko/net/loading-documents/loading-document-local-disk/
---

# 로컬 디스크에서 문서 로드

## 소개
오늘날의 디지털 시대에는 다양한 애플리케이션에 효율적인 문서 렌더링이 필수적입니다. .NET용 Groupdocs.Viewer는 로컬 디스크에서 직접 문서를 렌더링하기 위한 강력한 솔루션을 제공합니다. 이 자습서에서는 .NET용 Groupdocs.Viewer를 사용하여 로컬 디스크에서 문서를 로드하는 과정을 안내합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드는 문서 렌더링을 .NET 애플리케이션에 원활하게 통합하는 데 도움이 될 것입니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1.  .NET용 Groupdocs.Viewer: 다음에서 최신 버전을 다운로드하여 설치하세요.[여기](https://releases.groupdocs.com/viewer/net/).
2. .NET 개발 환경: 시스템에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하십시오.
3. 로컬 문서: 렌더링하려는 문서를 디스크에 로컬로 저장합니다.

## 네임스페이스 가져오기
먼저 .NET용 Groupdocs.Viewer의 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 1단계: 로컬 디스크에서 문서 로드
렌더링된 HTML 페이지가 저장될 출력 디렉터리를 설정하는 것부터 시작합니다.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2단계: 뷰어 초기화 및 문서 렌더링
문서 경로로 뷰어 개체를 초기화하고 HTML 보기 옵션을 사용하여 렌더링합니다.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 3단계: 출력 표시
렌더링이 완료되면 소스 문서의 성공적인 렌더링과 출력 파일의 위치를 나타내는 메시지를 표시합니다.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 결론
축하해요! .NET용 Groupdocs.Viewer를 사용하여 로컬 디스크에서 문서를 로드하는 방법을 성공적으로 배웠습니다. 이 강력한 도구는 .NET 애플리케이션 내에서 문서 렌더링에 대한 가능성의 세계를 열어줍니다.
## FAQ
### .NET용 Groupdocs.Viewer를 사용하여 다양한 형식의 문서를 렌더링할 수 있습니까?
예, .NET용 Groupdocs.Viewer는 DOCX, PDF, XLSX, PPTX 등을 포함한 광범위한 문서 형식을 지원합니다.
### .NET용 Groupdocs.Viewer는 모든 .NET 프레임워크와 호환됩니까?
.NET용 Groupdocs.Viewer는 .NET Core, .NET Framework 및 .NET Standard를 포함한 대부분의 .NET 프레임워크와 호환됩니다.
### 내 문서의 렌더링 옵션을 사용자 정의할 수 있나요?
전적으로! .NET용 Groupdocs.Viewer는 렌더링 프로세스를 특정 요구 사항에 맞게 조정할 수 있는 광범위한 사용자 정의 옵션을 제공합니다.
### .NET용 Groupdocs.Viewer에 사용할 수 있는 평가판이 있습니까?
예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.groupdocs.com/).
### .NET용 Groupdocs.Viewer에 대한 지원이나 추가 리소스는 어디에서 찾을 수 있나요?
 지원 및 추가 리소스를 보려면 .NET용 Groupdocs.Viewer를 방문하세요.[법정](https://forum.groupdocs.com/c/viewer/9).