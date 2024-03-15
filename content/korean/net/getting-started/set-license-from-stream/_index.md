---
title: 스트림에서 라이선스 설정
linktitle: 스트림에서 라이선스 설정
second_title: GroupDocs.Viewer .NET API
description: 원활한 문서 보기를 위해 GroupDocs.Viewer를 사용하여 .NET 응용 프로그램을 강화하세요. 단계별 가이드를 따라 강력한 문서 보기 기능을 손쉽게 통합하세요.
type: docs
weight: 11
url: /ko/net/getting-started/set-license-from-stream/
---
## 소개
고급 문서 보기 기능으로 .NET 애플리케이션을 강화하고 싶으십니까? .NET용 GroupDocs.Viewer는 문서 보기 기능을 프로젝트에 완벽하게 통합하는 포괄적인 솔루션을 제공합니다. 이 자습서에서는 .NET용 GroupDocs.Viewer를 활용하여 강력한 문서 보기 기능으로 응용 프로그램을 강화하는 프로세스를 자세히 살펴보겠습니다. 
## 전제조건
통합 프로세스를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. .NET 개발에 대한 기본 지식: 이 튜토리얼을 진행하려면 C# 및 .NET 프레임워크에 대한 지식이 필수적입니다.
   
2.  .NET용 GroupDocs.Viewer 패키지: .NET용 GroupDocs.Viewer 패키지를 다운로드하여 설치했는지 확인하세요. 에서 얻으실 수 있습니다.[다운로드 링크](https://releases.groupdocs.com/viewer/net/).
3.  GroupDocs 문서에 대한 액세스:[선적 서류 비치](https://reference.groupdocs.com/viewer/net/) 통합 과정에서 참고할 수 있어 편리합니다.

## 네임스페이스 가져오기
먼저 필요한 네임스페이스를 .NET 애플리케이션으로 가져옵니다. 다음과 같이하세요:
### 1단계: .NET 프로젝트를 엽니다.
원하는 개발 환경에서 .NET 프로젝트가 열려 있는지 확인하세요.
### 2단계: GroupDocs.Viewer 네임스페이스를 추가합니다.
코드 파일에서 다음 네임스페이스를 추가하여 GroupDocs.Viewer 기능에 액세스합니다.
```csharp
using System;
using System.IO;
```
## 스트림에서 라이선스 설정
다음 단계에는 스트림에서 라이선스를 설정하는 작업이 포함됩니다. 다음의 세부 단계를 따르십시오.
### 1단계: 출력 디렉터리를 정의합니다.
출력 디렉터리를 정의하여 문서가 저장될 디렉터리를 설정합니다.
```csharp
string outputDirectory = "Your Document Directory";
```
### 2단계: 라이선스 파일 존재 여부를 확인하세요.
프로젝트 디렉터리에 라이선스 파일이 있는지 확인하세요.
```csharp
if (File.Exists(Utils.LicensePath))
```
### 3단계: 라이선스 설정
라이센스 파일이 존재하는 경우 제공된 스트림을 사용하여 라이센스를 설정하십시오.
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 4단계: 라이선스 부재를 처리합니다.
라이센스 파일을 찾을 수 없는 경우 라이센스를 얻기 위한 지침을 제공하십시오.
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.");
}
```

## 결론
축하해요! .NET용 GroupDocs.Viewer를 응용 프로그램에 통합하는 방법을 성공적으로 배웠습니다. 이 강력한 도구를 사용하면 이제 .NET 프로젝트 내에서 다양한 문서 형식을 쉽게 볼 수 있어 사용자 경험과 생산성이 향상됩니다.
## FAQ
### .NET용 GroupDocs.Viewer를 사용하려면 라이센스가 필요합니까?
예, .NET용 GroupDocs.Viewer를 사용하려면 라이센스가 필요합니다. GroupDocs 웹 사이트에서 임시 또는 영구 라이센스를 얻을 수 있습니다.
### GroupDocs.Viewer를 ASP.NET 응용 프로그램에 통합할 수 있습니까?
전적으로! .NET용 GroupDocs.Viewer는 ASP.NET을 포함한 데스크톱 및 웹 응용 프로그램 모두에 완벽하게 통합됩니다.
### GroupDocs.Viewer는 어떤 문서 형식을 지원합니까?
GroupDocs.Viewer는 PDF, Microsoft Office(Word, Excel, PowerPoint), 이미지 등을 포함한 광범위한 문서 형식을 지원합니다.
### GroupDocs.Viewer는 .NET Core와 호환되나요?
예, .NET용 GroupDocs.Viewer는 .NET Framework 및 .NET Core 모두와 호환됩니다.
### 내 애플리케이션 테마에 따라 뷰어 인터페이스를 사용자 정의할 수 있나요?
예, GroupDocs.Viewer는 광범위한 사용자 정의 옵션을 제공하므로 뷰어 인터페이스를 응용 프로그램의 테마와 완벽하게 일치하도록 조정할 수 있습니다.