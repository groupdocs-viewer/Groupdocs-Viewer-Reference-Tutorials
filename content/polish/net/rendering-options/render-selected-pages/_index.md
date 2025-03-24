---
title: Renderuj wybrane strony
linktitle: Renderuj wybrane strony
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować wybrane strony z dokumentów za pomocą Groupdocs.Viewer dla .NET. Samouczek krok po kroku z dołączonymi przykładami kodu.
weight: 17
url: /pl/net/rendering-options/render-selected-pages/
---

# Renderuj wybrane strony

## Wstęp

W tym samouczku omówimy, jak wykorzystać Groupdocs.Viewer dla .NET do renderowania wybranych stron z dokumentu. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku z łatwością przeprowadzi Cię przez ten proces.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

### 1. Instalacja

 Upewnij się, że w środowisku programistycznym zainstalowano Groupdocs.Viewer for .NET. Jeśli nie, możesz pobrać go ze strony[Link do pobrania](https://releases.groupdocs.com/viewer/net/).

## Importowanie przestrzeni nazw

 pliku kodu C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do wymaganych klas i metod. Można to zrobić za pomocą`using` dyrektywa:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz dostarczony przykładowy kod na kilka kroków:

## Krok 1: Ustaw katalog wyjściowy

 Zdefiniuj katalog, w którym mają być zapisywane renderowane strony. Zastępować`"Your Document Directory"` z żądaną ścieżką katalogu.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Zdefiniuj format ścieżki pliku strony

Określ format ścieżek plików renderowanych stron. Będzie to użyte do zapisania każdej strony jako pliku HTML w katalogu wyjściowym.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Utwórz instancję obiektu przeglądarki

Utwórz instancję klasy Viewer, podając jako argument ścieżkę dokumentu, który chcesz wyświetlić.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Krok 4: Skonfiguruj opcje widoku HTML

Skonfiguruj opcje widoku HTML do renderowania. W tym przykładzie konfigurujemy opcje osadzania zasobów w wynikach HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Krok 5: Renderuj wybrane strony

Określ numery stron, które chcesz renderować. W tym przypadku renderujemy strony od 1 do 3. Następnie wywołaj metodę View na obiekcie Viewer, przekazując opcje i numery stron jako argumenty.

```csharp
viewer.View(options, 1, 3);
```

## Krok 6: Wynik wyjściowy

Na koniec wyświetl komunikat wskazujący pomyślne wyrenderowanie dokumentu i lokalizację, w której zapisywane są pliki wyjściowe.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek

Gratulacje! Pomyślnie nauczyłeś się renderować wybrane strony z dokumentu za pomocą Groupdocs.Viewer dla .NET. Dzięki tej wiedzy możesz teraz z łatwością zintegrować możliwości renderowania dokumentów z aplikacjami .NET.

## Często zadawane pytania

### P: Czy mogę renderować strony z różnych typów dokumentów, takich jak pliki PDF lub obrazy?

O: Tak, Groupdocs.Viewer dla .NET obsługuje renderowanie stron z różnych formatów dokumentów, w tym plików PDF, dokumentów Microsoft Office i plików obrazów.

### P: Czy dostępna jest wersja próbna do przetestowania przed zakupem?

 O: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Groupdocs.Viewer dla .NET z poziomu[strona internetowa](https://releases.groupdocs.com/).

### P: Czy mogę dostosować format wyjściowy inny niż HTML?

O: Oczywiście Groupdocs.Viewer dla .NET oprócz HTML zapewnia opcje renderowania stron w postaci obrazów, plików PDF i innych.

### P: Jak mogę uzyskać licencje tymczasowe do celów testowych?

Odp.: Licencje tymczasowe można nabyć w witrynie[strona licencji tymczasowej](https://purchase.groupdocs.com/temporary-license/) na stronie Groupdocs.

### P: Gdzie mogę szukać pomocy lub uzyskać pomoc w przypadku napotkanych problemów?

 O: Możesz odwiedzić[Forum Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) aby uzyskać wsparcie i wskazówki od społeczności i programistów.