---
"description": "Zintegruj GroupDocs.Viewer dla .NET bezproblemowo ze swoimi aplikacjami, aby uzyskać potężne możliwości przeglądania dokumentów. Ulepsz doświadczenie użytkownika dzięki konfigurowalnym opcjom."
"linktitle": "Ustaw format daty i godziny oraz przesunięcie strefy czasowej (e-mail)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ustaw format daty i godziny oraz przesunięcie strefy czasowej (e-mail)"
"url": "/pl/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# Ustaw format daty i godziny oraz przesunięcie strefy czasowej (e-mail)


## Wstęp
GroupDocs.Viewer dla .NET to potężne narzędzie, które umożliwia deweloperom bezproblemową integrację możliwości przeglądania dokumentów z ich aplikacjami .NET. Dzięki GroupDocs.Viewer możesz wyświetlać szeroką gamę formatów dokumentów, w tym pliki PDF, dokumenty Microsoft Office, obrazy i wiele innych, bezpośrednio w swojej aplikacji, bez potrzeby korzystania z zewnętrznych wtyczek lub przeglądarek. W tym kompleksowym samouczku przeprowadzimy Cię przez proces konfigurowania GroupDocs.Viewer dla .NET, poznamy jego funkcje i pokażemy, jak skutecznie go wykorzystać, aby ulepszyć możliwości przeglądania dokumentów w swojej aplikacji.
## Wymagania wstępne
Zanim przejdziesz do tego samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie. GroupDocs.Viewer dla .NET jest w pełni kompatybilny z programem Visual Studio, umożliwiając bezproblemową integrację z projektami .NET.
2. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj GroupDocs.Viewer dla .NET z [link do pobrania](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z instrukcjami instalacji, aby skonfigurować bibliotekę w środowisku programistycznym.
3. .NET Framework: Upewnij się, że masz zainstalowaną odpowiednią wersję .NET Framework. GroupDocs.Viewer dla .NET obsługuje różne wersje .NET Framework, w tym .NET Core i .NET Standard.

## Importuj przestrzenie nazw
Aby skutecznie wykorzystać GroupDocs.Viewer dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Wykonaj następujące kroki, aby zaimportować wymagane przestrzenie nazw:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Podzielmy podany przykład na kilka kroków, aby zrozumieć każdy komponent i jego funkcjonalność.
## Krok 1: Ustaw katalog wyjściowy i ścieżkę pliku
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
W tym kroku zdefiniujemy katalog wyjściowy, w którym zostanie zapisany wyrenderowany dokument, i podamy ścieżkę do pliku wyjściowego HTML.
## Krok 2: Utwórz obiekt Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Tutaj tworzymy nową instancję `Viewer` klasę, przekazując ścieżkę do dokumentu, który ma zostać wyświetlony (w tym przypadku przykładowego pliku EML) jako parametr.
## Krok 3: Zdefiniuj opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
W tym kroku konfigurujemy opcje widoku HTML dla renderowania dokumentu, określając ścieżkę pliku wyjściowego dla renderowanego dokumentu HTML.
## Krok 4: Ustaw format daty i godziny oraz przesunięcie strefy czasowej
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Tutaj dostosowujemy format daty i godziny dla wiadomości e-mail i ustawiamy przesunięcie strefy czasowej zgodnie z żądaną strefą czasową.
## Krok 5: Renderowanie dokumentu
```csharp
viewer.View(options);
```
Na koniec nazywamy `View` metoda `Viewer` obiekt, przekazując skonfigurowane opcje widoku HTML w celu renderowania dokumentu do formatu HTML.
## Krok 6: Wyświetl katalog wyjściowy
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
W tym kroku wyświetlany jest komunikat informujący o pomyślnym wyrenderowaniu dokumentu i podana jest ścieżka do katalogu wyjściowego, w którym znajduje się wyrenderowany dokument HTML.

## Wniosek
GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie do integrowania możliwości przeglądania dokumentów w aplikacjach .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz łatwo skonfigurować GroupDocs.Viewer, zaimportować niezbędne przestrzenie nazw i wykorzystać jego funkcje do renderowania dokumentów z opcjami dostosowywania. Niezależnie od tego, czy pracujesz z plikami PDF, dokumentami Microsoft Office czy innymi formatami, GroupDocs.Viewer upraszcza proces przeglądania dokumentów, ulepszając wrażenia użytkownika w aplikacjach.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer jest kompatybilny z .NET Core?
Tak, GroupDocs.Viewer dla .NET obsługuje platformę .NET Core, co zapewnia zgodność aplikacji z różnymi platformami.
### Czy mogę dostosować wygląd renderowanych dokumentów?
Oczywiście! GroupDocs.Viewer oferuje różne opcje dostosowywania, w tym poziomy powiększenia, obrót strony i więcej, aby dostosować wrażenia wizualne do Twoich ptutorialss.
### Czy jest dostępna wersja próbna do celów testowych?
Tak, możesz pobrać bezpłatną wersję próbną GroupDocs.Viewer dla .NET ze strony [link do strony internetowej](https://releases.groupdocs.com/viewer/net/) aby ocenić jego cechy przed dokonaniem zakupu.
### Czy GroupDocs.Viewer obsługuje renderowanie dokumentów chronionych hasłem?
Tak, GroupDocs.Viewer ma wbudowaną obsługę renderowania dokumentów chronionych hasłem, co gwarantuje bezpieczne przeglądanie dokumentów w aplikacjach.
### Gdzie mogę znaleźć dodatkową pomoc lub wsparcie dotyczące GroupDocs.Viewer?
W przypadku pytań technicznych lub potrzeby pomocy możesz odwiedzić witrynę GroupDocs.Viewer [forum](https://forum.groupdocs.com/c/viewer/9) lub skontaktuj się z naszym zespołem wsparcia, aby uzyskać szybką pomoc i wskazówki.