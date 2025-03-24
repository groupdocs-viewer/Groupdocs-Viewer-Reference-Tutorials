---
title: Renderuj plik PDF z oryginalnym rozmiarem strony
linktitle: Renderuj plik PDF z oryginalnym rozmiarem strony
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować pliki PDF z oryginalnymi rozmiarami stron przy użyciu programu GroupDocs.Viewer dla platformy .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku i bezproblemowo zintegruj tę funkcjonalność.
weight: 17
url: /pl/net/pdf-rendering-options/render-pdf-original-page-size/
---

# Renderuj plik PDF z oryginalnym rozmiarem strony

## Wstęp
W dziedzinie programowania .NET GroupDocs.Viewer wyróżnia się jako potężne narzędzie do renderowania różnych formatów dokumentów, w tym plików PDF. Jednym z powszechnych wymagań w obsłudze dokumentów jest renderowanie plików PDF przy zachowaniu ich oryginalnych rozmiarów stron. Bezproblemowe wykonanie tego zadania wymaga wszechstronnego zrozumienia GroupDocs.Viewer dla .NET i jego funkcjonalności.
## Warunki wstępne
Zanim zaczniesz renderować pliki PDF z oryginalnymi rozmiarami stron za pomocą GroupDocs.Viewer dla .NET, upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Zainstaluj GroupDocs.Viewer dla .NET
 Rozpocznij od pobrania biblioteki GroupDocs.Viewer ze strony internetowej. Bibliotekę można uzyskać z dostarczonej biblioteki[link do pobrania](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji, aby skutecznie zintegrować go z projektem .NET.
### 2. Skonfiguruj środowisko programistyczne
Upewnij się, że masz środowisko programistyczne skonfigurowane do programowania w platformie .NET. Obejmuje to zainstalowanie zgodnego środowiska IDE, takiego jak Visual Studio, i podstawową wiedzę na temat programowania w języku C#.
### 3. Uzyskaj dokument PDF
Będziesz potrzebować przykładowego dokumentu PDF do renderowania za pomocą GroupDocs.Viewer. Do celów testowych możesz użyć dowolnego dokumentu PDF. Jeśli go nie masz, możesz pobrać przykładowy plik PDF z różnych źródeł internetowych.

## Importuj przestrzenie nazw
Przed przystąpieniem do renderowania plików PDF konieczne jest zaimportowanie niezbędnych przestrzeni nazw do projektu C#. Ten krok umożliwia dostęp do wymaganych klas i metod z biblioteki GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz, gdy masz już wymagania wstępne i zaimportowano niezbędne przestrzenie nazw, podzielmy proces renderowania plików PDF z oryginalnymi rozmiarami stron za pomocą programu GroupDocs.Viewer dla .NET na proste kroki:
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
 Upewnij się, że określiłeś katalog, w którym mają być zapisywane renderowane strony. Zastępować`"Your Document Directory"` ze ścieżką żądanego katalogu.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Skonfiguruj format nazewnictwa renderowanych plików stron. W tym przykładzie strony zostaną zapisane jako obrazy PNG z nazwami plików w formacie`"page_1.png"`, `"page_2.png"`, i tak dalej.
## Krok 3: Renderuj plik PDF z oryginalnym rozmiarem strony
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Utwórz instancję a`Viewer` obiekt ścieżką do pliku PDF. Następnie utwórz`PngViewOptions` z określonym formatem ścieżki pliku strony. Ustawić`RenderOriginalPageSize` własność do`true` aby zachować oryginalne rozmiary strony podczas renderowania.
## Krok 4: Wyświetl lokalizację wyrenderowanego dokumentu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Wydrukuj komunikat informujący o pomyślnym renderowaniu i podaj katalog, w którym zapisywane są wyrenderowane strony.

## Wniosek
Renderowanie plików PDF o oryginalnych rozmiarach stron przy użyciu programu GroupDocs.Viewer dla platformy .NET jest prostym procesem, jeśli wykonasz kroki opisane w tym samouczku. Importując niezbędne przestrzenie nazw i postępując zgodnie ze szczegółowym przewodnikiem, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami .NET.
## Często zadawane pytania
### Czy GroupDocs.Viewer może renderować dokumenty w innych formatach niż PDF?
Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów dokumentów, w tym Word, Excel, PowerPoint i innych.
### Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?
Tak, GroupDocs.Viewer jest kompatybilny zarówno ze środowiskami .NET Framework, jak i .NET Core.
### Czy mogę dostosować format wyjściowy renderowanych stron?
Tak, możesz dostosować format wyjściowy, dostosowując opcje udostępniane przez GroupDocs.Viewer, takie jak ustawienie różnych formatów obrazu lub określenie niestandardowych opcji renderowania.
### Czy GroupDocs.Viewer oferuje obsługę renderowania dokumentów w chmurze?
Tak, GroupDocs.Viewer udostępnia interfejsy API do renderowania dokumentów w chmurze, umożliwiając renderowanie dokumentów bezpośrednio od dostawców usług przechowywania w chmurze.
### Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer?
 Tak, możesz korzystać z GroupDocs.Viewer w ramach bezpłatnej wersji próbnej, odwiedzając udostępnioną stronę[połączyć](https://releases.groupdocs.com/).