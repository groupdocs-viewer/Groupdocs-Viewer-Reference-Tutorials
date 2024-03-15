---
title: Ustawianie formatu daty i godziny oraz przesunięcia strefy czasowej (e-mail)
linktitle: Ustawianie formatu daty i godziny oraz przesunięcia strefy czasowej (e-mail)
second_title: GroupDocs.Viewer API .NET
description: Bezproblemowo zintegruj GroupDocs.Viewer for .NET ze swoimi aplikacjami, aby uzyskać zaawansowane możliwości przeglądania dokumentów. Zwiększ wygodę użytkownika dzięki konfigurowalnym opcjom.
type: docs
weight: 11
url: /pl/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Wstęp
GroupDocs.Viewer dla .NET to potężne narzędzie, które umożliwia programistom bezproblemową integrację możliwości przeglądania dokumentów z aplikacjami .NET. Dzięki GroupDocs.Viewer możesz wyświetlać szeroką gamę formatów dokumentów, w tym pliki PDF, dokumenty Microsoft Office, obrazy i inne, bezpośrednio w aplikacji, bez potrzeby stosowania jakichkolwiek zewnętrznych wtyczek lub przeglądarek. W tym kompleksowym samouczku przeprowadzimy Cię przez proces konfigurowania programu GroupDocs.Viewer dla platformy .NET, poznajemy jego funkcje i pokażemy, jak efektywnie go wykorzystać w celu zwiększenia możliwości przeglądania dokumentów w aplikacji.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie. GroupDocs.Viewer dla .NET jest w pełni kompatybilny z Visual Studio, umożliwiając bezproblemową integrację z projektami .NET.
2.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z[link do pobrania](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z dostarczonymi instrukcjami instalacji, aby skonfigurować bibliotekę w środowisku programistycznym.
3. .NET Framework: Upewnij się, że masz zainstalowaną odpowiednią wersję .NET Framework. GroupDocs.Viewer dla .NET obsługuje różne wersje .NET Framework, w tym .NET Core i .NET Standard.

## Importuj przestrzenie nazw
Aby efektywnie wykorzystać GroupDocs.Viewer dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Wykonaj poniższe kroki, aby zaimportować wymagane przestrzenie nazw:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Podzielmy podany przykład na wiele kroków, aby zrozumieć każdy komponent i jego funkcjonalność.
## Krok 1: Ustaw katalog wyjściowy i ścieżkę pliku
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
W tym kroku definiujemy katalog wyjściowy, w którym zostanie zapisany wyrenderowany dokument i określamy ścieżkę pliku wyjściowego pliku HTML.
## Krok 2: Utwórz instancję obiektu przeglądarki
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Tutaj tworzymy nową instancję pliku`Viewer` class, przekazując jako parametr ścieżkę dokumentu, który ma zostać wyświetlony (w tym przypadku przykładowy plik EML).
## Krok 3: Zdefiniuj opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
tym kroku konfigurujemy opcje widoku HTML dla renderowania dokumentu, określając ścieżkę pliku wyjściowego dla renderowanego dokumentu HTML.
## Krok 4: Ustaw format daty i godziny oraz przesunięcie strefy czasowej
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Tutaj dostosowujemy format daty i godziny wiadomości e-mail oraz ustawiamy przesunięcie strefy czasowej zgodnie z żądaną strefą czasową.
## Krok 5: Renderuj dokument
```csharp
viewer.View(options);
```
 Na koniec wywołujemy`View` metoda`Viewer` obiekt, przekazując skonfigurowane opcje widoku HTML w celu renderowania dokumentu do formatu HTML.
## Krok 6: Wyświetl katalog wyjściowy
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ten krok po prostu wyświetla komunikat wskazujący pomyślne wyrenderowanie dokumentu i podaje ścieżkę do katalogu wyjściowego, w którym znajduje się wyrenderowany dokument HTML.

## Wniosek
GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie umożliwiające integrację możliwości przeglądania dokumentów z aplikacjami .NET. Wykonując kroki opisane w tym samouczku, możesz łatwo skonfigurować GroupDocs.Viewer, zaimportować niezbędne przestrzenie nazw i wykorzystać jego funkcje do renderowania dokumentów z dostosowywalnymi opcjami. Niezależnie od tego, czy pracujesz z plikami PDF, dokumentami Microsoft Office czy innymi formatami, GroupDocs.Viewer upraszcza proces przeglądania dokumentów, poprawiając komfort korzystania z aplikacji.
## Często zadawane pytania
### Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?
Tak, GroupDocs.Viewer dla .NET obsługuje platformę .NET Core, zapewniając zgodność aplikacji z wieloma platformami.
### Czy mogę dostosować wygląd renderowanych dokumentów?
Absolutnie! GroupDocs.Viewer zapewnia różne opcje dostosowywania, w tym poziomy powiększenia, rotację strony i inne, aby dostosować sposób oglądania zgodnie z własnymi preferencjami.
### Czy dostępna jest wersja próbna do celów testowych?
 Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer dla .NET z witryny[link do strony](https://releases.groupdocs.com/viewer/net/) aby ocenić jego funkcje przed dokonaniem zakupu.
### Czy GroupDocs.Viewer obsługuje renderowanie dokumentów chronionych hasłem?
Tak, GroupDocs.Viewer ma wbudowaną obsługę renderowania dokumentów chronionych hasłem, zapewniając bezpieczne przeglądanie dokumentów w aplikacjach.
### Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dotyczącą GroupDocs.Viewer?
 W przypadku jakichkolwiek pytań technicznych lub pomocy możesz odwiedzić GroupDocs.Viewer[forum](https://forum.groupdocs.com/c/viewer/9) lub skontaktuj się z ich zespołem wsparcia, aby uzyskać szybką pomoc i wskazówki.