---
"description": "Dowiedz się, jak renderować wybrane strony z dokumentów za pomocą Groupdocs.Viewer dla .NET. Samouczek krok po kroku z dołączonymi przykładami kodu."
"linktitle": "Renderuj wybrane strony"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj wybrane strony"
"url": "/pl/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Renderuj wybrane strony

## Wstęp

W tym samouczku zagłębimy się w sposób wykorzystania Groupdocs.Viewer dla .NET do renderowania wybranych stron z dokumentu. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku przeprowadzi Cię przez ten proces z łatwością.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

### 1. Instalacja

Upewnij się, że masz zainstalowany Groupdocs.Viewer dla .NET w swoim środowisku programistycznym. Jeśli nie, możesz go pobrać ze strony [Link do pobrania](https://releases.groupdocs.com/viewer/net/).

## Importowanie przestrzeni nazw

W pliku kodu C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do wymaganych klas i metod. Możesz to zrobić za pomocą `using` dyrektywa:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz rozłóżmy przykładowy kod na kilka kroków:

## Krok 1: Ustaw katalog wyjściowy

Zdefiniuj katalog, w którym chcesz zapisać renderowane strony. Zastąp `"Your Document Directory"` z żądaną ścieżką katalogu.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Zdefiniuj format ścieżki pliku stronicowania

Określ format ścieżek plików renderowanych stron. Będzie on używany do zapisywania każdej strony jako pliku HTML w katalogu wyjściowym.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Utwórz obiekt Viewer

Utwórz instancję klasy Viewer, przekazując jako argument ścieżkę do dokumentu, który chcesz renderować.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Krok 4: Skonfiguruj opcje widoku HTML

Skonfiguruj opcje widoku HTML do renderowania. W tym przykładzie konfigurujemy opcje osadzania zasobów w wyjściu HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Krok 5: Renderuj wybrane strony

Określ numery stron, które chcesz renderować. W tym przypadku renderujemy strony od 1 do 3. Następnie wywołaj metodę View na obiekcie Viewer, przekazując opcje i numery stron jako argumenty.

```csharp
viewer.View(options, 1, 3);
```

## Krok 6: Wynik wyjściowy

Na koniec wyświetl komunikat informujący o pomyślnym wyrenderowaniu dokumentu i miejscu, w którym zapisane zostały pliki wyjściowe.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak renderować wybrane strony z dokumentu za pomocą Groupdocs.Viewer dla .NET. Dzięki tej wiedzy możesz teraz z łatwością zintegrować możliwości renderowania dokumentów z aplikacjami .NET.

## Najczęściej zadawane pytania

### P: Czy mogę renderować strony z różnych typów dokumentów, np. plików PDF lub obrazów?

O: Tak, Groupdocs.Viewer dla platformy .NET obsługuje renderowanie stron z różnych formatów dokumentów, w tym plików PDF, dokumentów pakietu Microsoft Office i plików graficznych.

### P: Czy jest dostępna wersja próbna do przetestowania przed zakupem?

O: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Groupdocs.Viewer dla .NET z [strona internetowa](https://releases.groupdocs.com/).

### P: Czy mogę dostosować format wyjściowy inaczej niż HTML?

O: Oczywiście, Groupdocs.Viewer dla platformy .NET oprócz formatu HTML oferuje również opcje renderowania stron jako obrazów, plików PDF i innych.

### P: W jaki sposób mogę uzyskać tymczasową licencję do celów testowych?

A: Licencje tymczasowe można nabyć w [tymczasowa strona licencji](https://purchase.groupdocs.com/temporary-license/) na stronie internetowej Groupdocs.

### P: Gdzie mogę szukać pomocy lub otrzymać pomoc w rozwiązaniu problemów, z którymi się spotkam?

A: Możesz odwiedzić [Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) aby uzyskać wsparcie i wskazówki od społeczności i deweloperów.