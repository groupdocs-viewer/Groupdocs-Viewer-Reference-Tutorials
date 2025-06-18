---
"description": "Dowiedz się, jak renderować pliki PDF z oryginalnymi rozmiarami stron za pomocą GroupDocs.Viewer dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku i płynnie zintegruj tę funkcjonalność."
"linktitle": "Renderuj PDF z oryginalnym rozmiarem strony"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj PDF z oryginalnym rozmiarem strony"
"url": "/pl/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# Renderuj PDF z oryginalnym rozmiarem strony

## Wstęp
dziedzinie rozwoju .NET GroupDocs.Viewer wyróżnia się jako potężne narzędzie do renderowania różnych formatów dokumentów, w tym PDF-ów. Jednym z powszechnych wymagań w obsłudze dokumentów jest renderowanie plików PDF przy zachowaniu ich oryginalnych rozmiarów stron. Bezproblemowe wykonanie tego zadania wymaga wszechstronnego zrozumienia GroupDocs.Viewer dla .NET i jego funkcjonalności.

![Renderuj PDF z oryginalnym rozmiarem strony za pomocą GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Wymagania wstępne
Zanim zaczniesz renderować pliki PDF z zachowaniem oryginalnych rozmiarów stron za pomocą GroupDocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Zainstaluj GroupDocs.Viewer dla .NET
Zacznij od pobrania biblioteki GroupDocs.Viewer ze strony internetowej. Możesz uzyskać bibliotekę z dostarczonego [link do pobrania](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji, aby skutecznie zintegrować ją z projektem .NET.
### 2. Skonfiguruj środowisko programistyczne
Upewnij się, że masz środowisko programistyczne skonfigurowane do programowania .NET. Obejmuje to zainstalowanie zgodnego środowiska IDE, takiego jak Visual Studio, oraz podstawową znajomość programowania w języku C#.
### 3. Uzyskaj dokument PDF
Będziesz potrzebować przykładowego dokumentu PDF do renderowania za pomocą GroupDocs.Viewer. Możesz użyć dowolnego dokumentu PDF do celów testowych. Jeśli nie masz takiego dokumentu, możesz pobrać przykładowy plik PDF z różnych źródeł online.

## Importuj przestrzenie nazw
Przed przystąpieniem do renderowania plików PDF konieczne jest zaimportowanie niezbędnych przestrzeni nazw do projektu C#. Ten krok umożliwia dostęp do wymaganych klas i metod z biblioteki GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz, gdy spełniłeś już wymagania wstępne i zaimportowałeś niezbędne przestrzenie nazw, możemy podzielić proces renderowania plików PDF z zachowaniem oryginalnych rozmiarów stron za pomocą GroupDocs.Viewer dla platformy .NET na kilka prostych kroków:
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Upewnij się, że określiłeś katalog, w którym chcesz zapisać renderowane strony. Zastąp `"Your Document Directory"` ze ścieżką do wybranego katalogu.
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Ustaw format nazywania renderowanych plików stron. W tym przykładzie strony zostaną zapisane jako obrazy PNG z nazwami plików w formacie `"page_1.png"`, `"page_2.png"`i tak dalej.
## Krok 3: Renderuj PDF z oryginalnym rozmiarem strony
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Utwórz instancję `Viewer` obiekt ze ścieżką do pliku PDF. Następnie utwórz `PngViewOptions` z określonym formatem ścieżki pliku stronicowania. Ustaw `RenderOriginalPageSize` nieruchomość do `true` aby zachować oryginalne rozmiary stron podczas renderowania.
## Krok 4: Wyświetl lokalizację renderowanego dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Wyświetl komunikat informujący o pomyślnym renderowaniu i podaj katalog, w którym zapisywane są wyrenderowane strony.

## Wniosek
Renderowanie plików PDF z oryginalnymi rozmiarami stron za pomocą GroupDocs.Viewer dla .NET to prosty proces, jeśli wykonasz kroki opisane w tym samouczku. Importując niezbędne przestrzenie nazw i postępując zgodnie z przewodnikiem krok po kroku, możesz bezproblemowo zintegrować tę funkcjonalność ze swoimi aplikacjami .NET.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer może renderować inne formaty dokumentów niż PDF?
Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów dokumentów, w tym Word, Excel, PowerPoint i innych.
### Czy GroupDocs.Viewer jest kompatybilny z .NET Core?
Tak, GroupDocs.Viewer jest kompatybilny zarówno ze środowiskami .NET Framework, jak i .NET Core.
### Czy mogę dostosować format wyjściowy renderowanych stron?
Tak, możesz dostosować format wyjściowy, modyfikując opcje udostępniane przez GroupDocs.Viewer, np. ustawiając różne formaty obrazu lub określając niestandardowe opcje renderowania.
### Czy GroupDocs.Viewer obsługuje renderowanie dokumentów w chmurze?
Tak, GroupDocs.Viewer udostępnia interfejsy API do renderowania dokumentów w chmurze, umożliwiając renderowanie dokumentów bezpośrednio od dostawców pamięci masowej w chmurze.
### Czy jest dostępna bezpłatna wersja próbna GroupDocs.Viewer?
Tak, możesz wypróbować GroupDocs.Viewer za darmo, odwiedzając podaną stronę [połączyć](https://releases.groupdocs.com/).