---
title: 워크시트 이름 가져오기
linktitle: 워크시트 이름 가져오기
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer의 마법을 탐험해보세요. 문서 보기를 응용 프로그램에 원활하게 통합할 수 있습니다. 지금 무료 평가판을 사용해 보세요!
type: docs
weight: 11
url: /ko/net/spreadsheet-rendering-options/get-worksheets-names/
---
## 소개
.NET용 GroupDocs.Viewer의 매혹적인 세계에 오신 것을 환영합니다! .NET 애플리케이션 내에서 강력한 문서 보기 기능을 탐색하는 데 관심이 있는 개발자이거나 열광적인 사람이라면 큰 도움이 될 것입니다. 이 종합 가이드에서는 GroupDocs.Viewer를 사용하여 워크시트 이름을 검색하는 복잡한 과정을 자세히 살펴보겠습니다. 그러니 안전벨트를 매시고 신나는 여행을 떠나보세요!
## 전제조건
코딩 마법에 대해 알아보기 전에 모든 것이 설정되었는지 확인하세요.
1.  .NET용 GroupDocs.Viewer 설치:[다운로드 링크](https://releases.groupdocs.com/viewer/net/).NET용 GroupDocs.Viewer의 최신 버전을 다운로드하세요. 설치 지침에 따라 개발 환경에 원활하게 통합하세요.
2. 문서 준비: 지정된 문서 디렉터리에 "file.xlsx"라는 Excel 파일과 같은 대상 문서가 있는지 확인하세요.
## 네임스페이스 가져오기
이제 전제 조건이 준비되었으므로 필요한 네임스페이스를 가져와 작업을 시작하겠습니다. 이렇게 하면 응용 프로그램이 .NET용 GroupDocs.Viewer에서 제공하는 기능을 인식하고 활용할 수 있습니다.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. 문서 디렉토리 설정
```csharp
string outputDirectory = "Your Document Directory";
```
"Your Document Directory"를 대상 문서가 있는 디렉터리의 경로로 바꾸십시오.
## 2. 뷰어 초기화
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
이 단계에서는 Excel 파일의 경로를 제공하는 Viewer 클래스의 인스턴스를 만듭니다.
## 3. 정보보기 옵션 구성
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
여기서는 HTML 보기를 생성하고 스프레드시트 렌더링을 위한 추가 옵션을 설정하도록 ViewInfoOptions를 구성합니다.
## 4. 뷰 정보 검색
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
뷰어 인스턴스를 활용하여 구성된 옵션을 기반으로 보기 정보를 검색합니다.
## 5. 워크시트 이름 표시
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
검색된 페이지를 반복하고 각 워크시트의 이름을 콘솔에 인쇄합니다.
## 결론
축하해요! .NET용 GroupDocs.Viewer를 사용하여 워크시트 이름을 가져오는 프로세스를 성공적으로 탐색했습니다. 이를 통해 애플리케이션 내에서 문서 보기 기능을 향상할 수 있는 수많은 가능성이 열립니다.
## 자주 묻는 질문
### .NET용 GroupDocs.Viewer를 다른 문서 형식과 함께 사용할 수 있습니까?
전적으로! GroupDocs.Viewer는 PDF, Microsoft Office 등을 포함한 광범위한 문서 형식을 지원합니다.
### 무료 평가판이 제공되나요?
 예, 다음을 통해 .NET용 GroupDocs.Viewer를 탐색할 수 있습니다.[무료 시험판](https://releases.groupdocs.com/).
### 추가 지원은 어디서 찾을 수 있나요?
 다음으로 향하세요.[GroupDocs.Viewer 포럼](https://forum.groupdocs.com/c/viewer/9) 커뮤니티 지원 및 토론을 위해.
### 임시면허를 취득할 수 있나요?
 틀림없이! 방문하다[이 링크](https://purchase.groupdocs.com/temporary-license/) 임시면허증을 받으러
### 사용 가능한 자세한 문서 리소스가 있습니까?
 전적으로! 확인해 보세요[공식 문서](https://reference.groupdocs.com/viewer/net/) 자세한 정보와 가이드를 확인하세요.