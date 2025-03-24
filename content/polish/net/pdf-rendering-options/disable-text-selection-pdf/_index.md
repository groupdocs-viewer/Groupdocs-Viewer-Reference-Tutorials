---
title: Wyłącz zaznaczanie tekstu w formacie PDF
linktitle: Wyłącz zaznaczanie tekstu w formacie PDF
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak wyłączyć zaznaczanie tekstu w formacie PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
weight: 13
url: /pl/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Wstęp
GroupDocs.Viewer dla .NET to potężny interfejs API do renderowania dokumentów, który umożliwia programistom bezproblemową integrację możliwości przeglądania dokumentów z aplikacjami .NET. Jedną z kluczowych funkcjonalności udostępnianych przez GroupDocs.Viewer jest możliwość wyłączenia zaznaczania tekstu w dokumentach PDF. Ta funkcja jest szczególnie przydatna w scenariuszach, w których trzeba uniemożliwić użytkownikom kopiowanie tekstu z poufnych dokumentów, zapewniając bezpieczeństwo i integralność dokumentów.
## Warunki wstępne
Zanim przejdziemy do szczegółowego przewodnika dotyczącego wyłączania zaznaczania tekstu w formacie PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:
1.  Instalacja GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś GroupDocs.Viewer dla .NET ze strony[link do pobrania](https://releases.groupdocs.com/viewer/net/).
2. Katalog dokumentów: Przygotuj katalog, w którym będą przechowywane Twoje dokumenty. Aby wyrenderować dokument PDF, musisz określić ten katalog we fragmencie kodu.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności udostępnianych przez GroupDocs.Viewer dla .NET. Oto jak możesz to zrobić:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz proces wyłączania zaznaczania tekstu w dokumencie PDF za pomocą programu GroupDocs.Viewer dla .NET na kilka kroków:
## Krok 1: Określ katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
 W tym kroku wymień`"Your Document Directory"` ze ścieżką katalogu, w którym znajduje się dokument PDF.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ten krok definiuje format ścieżek plików renderowanych stron HTML. Każda strona dokumentu PDF zostanie przekonwertowana na plik HTML z kolejnym numerem strony.
## Krok 3: Renderuj dokument PDF z wyłączonym zaznaczaniem tekstu
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Zastępować`"Path to Your PDF Document"` z rzeczywistą ścieżką do pliku PDF. Ten fragment kodu inicjuje plik a`Viewer` obiekt, konfiguruje opcje widoku HTML w celu osadzania zasobów i wyłącza zaznaczanie tekstu przez ustawienie`RenderTextAsImage` własność do`true`.
## Krok 4: Wyświetl komunikat o powodzeniu
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Po wyrenderowaniu dokumentu PDF w tym kroku zostanie wyświetlony komunikat o powodzeniu wraz z katalogiem, w którym przechowywane są wyrenderowane strony HTML.

## Wniosek
W tym samouczku dowiedzieliśmy się, jak wyłączyć zaznaczanie tekstu w dokumentach PDF za pomocą programu GroupDocs.Viewer dla platformy .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz bezproblemowo zintegrować tę funkcję z aplikacjami .NET, zapewniając bezpieczeństwo dokumentów i poprawiając wygodę użytkownika.
## Często zadawane pytania
### Czy mogę dostosować katalog wyjściowy dla renderowanych stron HTML?
Tak, możesz określić dowolną ścieżkę katalogu, w którym mają być przechowywane renderowane strony HTML.
### Czy GroupDocs.Viewer dla .NET jest kompatybilny z różnymi wersjami platformy .NET?
Tak, GroupDocs.Viewer dla .NET jest kompatybilny z różnymi wersjami platformy .NET, w tym z .NET Core i .NET Framework.
### Czy wyłączenie zaznaczania tekstu wpływa na inne funkcjonalności dokumentu PDF?
Nie, wyłączenie zaznaczania tekstu uniemożliwia użytkownikom jedynie wybieranie i kopiowanie tekstu z dokumentu. Pozostałe funkcjonalności pozostają nienaruszone.
### Czy mogę ponownie włączyć zaznaczanie tekstu po wyrenderowaniu dokumentu?
 Tak, możesz włączyć zaznaczanie tekstu, po prostu ustawiając`RenderTextAsImage` własność do`false` w opcjach widoku HTML.
### Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej GroupDocs.Viewer dla .NET z poziomu[strona internetowa](https://releases.groupdocs.com/).