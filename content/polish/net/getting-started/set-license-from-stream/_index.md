---
"description": "Ulepsz swoje aplikacje .NET dzięki GroupDocs.Viewer, aby bezproblemowo przeglądać dokumenty. Postępuj zgodnie z naszym przewodnikiem krok po kroku i bez wysiłku integruj potężne możliwości przeglądania dokumentów."
"linktitle": "Ustaw licencję ze strumienia"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ustaw licencję ze strumienia"
"url": "/pl/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Ustaw licencję ze strumienia

## Wstęp
Czy chcesz wyposażyć swoje aplikacje .NET w zaawansowane możliwości przeglądania dokumentów? GroupDocs.Viewer dla .NET oferuje kompleksowe rozwiązanie do bezproblemowej integracji funkcji przeglądania dokumentów z projektami. W tym samouczku zagłębimy się w proces wykorzystania GroupDocs.Viewer dla .NET w celu wzbogacenia aplikacji o potężne możliwości przeglądania dokumentów. 

![Ustaw licencję ze strumienia za pomocą GroupDocs.Viewer dla .NET](/viewer/getting-started/set-license-from-stream.png)

## Wymagania wstępne
Zanim rozpoczniemy proces integracji, upewnij się, że spełnione są następujące wymagania wstępne:
1. Podstawowa wiedza na temat programowania w środowisku .NET: Znajomość języka C# i środowiska .NET jest niezbędna, aby móc uczestniczyć w tym samouczku.
   
2. Pakiet GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś pakiet GroupDocs.Viewer dla .NET. Możesz go uzyskać ze strony [link do pobrania](https://releases.groupdocs.com/viewer/net/).
3. Dostęp do dokumentacji GroupDocs: Zachowaj [dokumentacja](https://tutorials.groupdocs.com/viewer/net/) przydatne w samouczkach podczas procesu integracji.

## Importuj przestrzenie nazw
Na początek zaimportuj niezbędne przestrzenie nazw do swojej aplikacji .NET. Wykonaj następujące kroki:
### Krok 1: Otwórz projekt .NET.
Upewnij się, że projekt .NET jest otwarty w preferowanym środowisku programistycznym.
### Krok 2: Dodaj przestrzeń nazw GroupDocs.Viewer.
W pliku kodu dodaj następującą przestrzeń nazw, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Ustaw licencję ze strumienia
Następny krok obejmuje ustawienie licencji ze strumienia. Wykonaj następujące szczegółowe kroki:
### Krok 1: Zdefiniuj katalog wyjściowy.
Ustaw katalog, w którym będą przechowywane Twoje dokumenty, definiując katalog wyjściowy:
```csharp
string outputDirectory = "Your Document Directory";
```
### Krok 2: Sprawdź, czy plik licencji istnieje.
Sprawdź, czy plik licencji znajduje się w katalogu Twojego projektu:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Krok 3: Ustaw licencję.
Jeżeli plik licencji istnieje, ustaw licencję za pomocą dostarczonego strumienia:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Krok 4: Postępowanie w przypadku braku licencji.
Jeżeli plik licencji nie zostanie znaleziony, podaj instrukcje dotyczące uzyskania licencji:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak zintegrować GroupDocs.Viewer dla .NET ze swoimi aplikacjami. Dzięki temu potężnemu narzędziu możesz teraz bez wysiłku przeglądać różne formaty dokumentów w swoich projektach .NET, zwiększając doświadczenie użytkownika i produktywność.
## Najczęściej zadawane pytania
### Czy potrzebuję licencji, aby korzystać z GroupDocs.Viewer dla .NET?
Tak, potrzebujesz licencji, aby używać GroupDocs.Viewer dla .NET. Możesz uzyskać tymczasową lub stałą licencję na stronie internetowej GroupDocs.
### Czy mogę zintegrować GroupDocs.Viewer z moją aplikacją ASP.NET?
Oczywiście! GroupDocs.Viewer dla .NET bezproblemowo integruje się z aplikacjami desktopowymi i internetowymi, w tym ASP.NET.
### Jakie formaty dokumentów są obsługiwane przez GroupDocs.Viewer?
GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, pliki pakietu Microsoft Office (Word, Excel, PowerPoint), obrazy i inne.
### Czy GroupDocs.Viewer jest kompatybilny z .NET Core?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny zarówno z .NET Framework, jak i .NET Core.
### Czy mogę dostosować interfejs przeglądarki do motywu mojej aplikacji?
Tak, GroupDocs.Viewer oferuje rozbudowane opcje personalizacji, pozwalające na idealne dopasowanie interfejsu przeglądarki do motywu Twojej aplikacji.