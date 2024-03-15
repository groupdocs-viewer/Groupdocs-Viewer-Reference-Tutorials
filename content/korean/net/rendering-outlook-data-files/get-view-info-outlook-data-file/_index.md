---
title: Outlook 데이터 파일(PST, OST)에 대한 보기 정보 가져오기
linktitle: Outlook 데이터 파일(PST, OST)에 대한 보기 정보 가져오기
second_title: GroupDocs.Viewer .NET API
description: .NET용 GroupDocs.Viewer를 사용하여 Outlook 데이터 파일(PST, OST)에서 보기 정보를 추출하는 방법을 살펴보세요. 문서 관리 기능을 손쉽게 향상하세요.
type: docs
weight: 10
url: /ko/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---
## 소개
문서 관리 및 보기 영역에서 .NET용 GroupDocs.Viewer는 특히 Outlook 데이터 파일(PST, OST) 처리와 관련하여 강력한 도구입니다. 이 튜토리얼에서는 이러한 파일에 대한 뷰 정보를 추출하는 프로세스를 단계별로 살펴보겠습니다.
## 전제조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### 1. .NET용 GroupDocs.Viewer 설치
 먼저 개발 환경에 .NET용 GroupDocs.Viewer가 설치되어 있어야 합니다. 다음에서 필요한 패키지를 다운로드할 수 있습니다.[.NET 웹사이트용 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/).
### 2. C# 프로그래밍 언어에 대한 지식
제공된 코드 예제를 이해하고 구현하려면 C# 프로그래밍 언어에 대한 기본 지식이 필수적입니다.
### 3. 아웃룩 데이터 파일(PST, OST)
테스트 목적으로 사용할 수 있는 Outlook 데이터 파일(PST, OST)이 있는지 확인하세요. 다양한 소스에서 샘플 파일을 얻거나 자체 데이터 파일을 사용할 수 있습니다.

## 네임스페이스 가져오기
코드를 살펴보기 전에 필요한 네임스페이스를 가져왔는지 확인하세요.
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 뷰어 개체 인스턴스화
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
여기서는 인수로 지정된 Outlook 데이터 파일(OST) 경로를 사용하여 뷰어 개체를 초기화합니다.
## 2단계: 정보 보기 옵션 구성
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
보기 정보를 검색하기 위한 옵션을 설정하는 중입니다. 이 경우 HTML 보기를 선택합니다.
## 3단계: Outlook 보기 정보 검색
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
이 줄은 Outlook 데이터 파일에 대한 보기 정보를 가져옵니다.
## 4단계: 파일 형식 및 페이지 수 표시
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Outlook 데이터 파일의 파일 형식과 페이지 수를 인쇄하고 있습니다.
## 5단계: 폴더 반복
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
이 루프는 Outlook 데이터 파일 내에 포함된 폴더를 반복하여 해당 이름을 인쇄합니다.
## 6단계: 검색 마무리
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
보기 정보가 성공적으로 검색되었음을 나타내는 메시지가 표시됩니다.

## 결론
.NET용 GroupDocs.Viewer는 Outlook 데이터 파일(PST, OST)에서 보기 정보를 추출하기 위한 완벽한 솔루션을 제공합니다. 이 튜토리얼에 설명된 단계를 따르면 향상된 문서 관리를 위해 이러한 파일에 대한 귀중한 통찰력을 손쉽게 얻을 수 있습니다.
## FAQ
### .NET용 GroupDocs.Viewer는 다른 버전의 Outlook 데이터 파일과 호환됩니까?
예, .NET용 GroupDocs.Viewer는 다양한 버전의 Outlook 데이터 파일을 지원하여 다양한 환경 간의 호환성을 보장합니다.
### .NET용 GroupDocs.Viewer를 사용하여 Outlook 데이터 파일의 보기 옵션을 사용자 정의할 수 있습니까?
전적으로! .NET용 GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 요구 사항에 따라 보기 환경을 맞춤화할 수 있습니다.
### .NET용 GroupDocs.Viewer는 Outlook 데이터 파일 외에 다른 파일 형식을 지원합니까?
예, .NET용 GroupDocs.Viewer는 PDF, DOCX, XLSX 등을 포함하되 이에 국한되지 않는 광범위한 파일 형식을 지원합니다.
### .NET용 GroupDocs.Viewer에 대한 무료 평가판이 있습니까?
 예, 다음 웹사이트에서 .NET용 GroupDocs.Viewer 무료 평가판에 액세스할 수 있습니다.[무료 시험판](https://releases.groupdocs.com/).
### .NET용 GroupDocs.Viewer에 대한 추가 지원은 어디서 찾을 수 있나요?
 문의사항이나 도움이 필요한 경우 .NET용 GroupDocs.Viewer 지원 포럼을 방문하세요.[지원하다](https://forum.groupdocs.com/c/viewer/9).