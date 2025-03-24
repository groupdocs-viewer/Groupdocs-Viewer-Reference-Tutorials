---
title: Ustaw limit czasu ładowania zasobów (zaawansowane)
linktitle: Ustaw limit czasu ładowania zasobów (zaawansowane)
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak efektywnie konfigurować limity czasu ładowania zasobów w programie GroupDocs.Viewer dla platformy .NET. Opanuj renderowanie dokumentów z precyzją i stabilnością.
weight: 13
url: /pl/net/advanced-loading/set-resource-loading-timeout/
---
## Wstęp
dziedzinie programowania .NET GroupDocs.Viewer zapewnia potężny zestaw narzędzi do renderowania dokumentów i obrazów z precyzją i wydajnością. Wykorzystanie jego możliwości wymaga zrozumienia jego zawiłości, w tym ustawiania limitów czasu ładowania zasobów. W tym samouczku omówimy proces konfigurowania limitów czasu ładowania zasobów w programie GroupDocs.Viewer dla platformy .NET.
## Warunki wstępne
Przed rozpoczęciem korzystania z tego samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Podstawowa wiedza na temat programowania .NET: Znajomość programowania w C# i podstaw .NET Framework jest niezbędna.
2.  Instalacja GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla .NET z[strona pobierania](https://releases.groupdocs.com/viewer/net/).
3. Zintegrowane środowisko programistyczne (IDE): Zainstaluj w swoim systemie środowisko IDE, takie jak Visual Studio.

## Importuj przestrzenie nazw
Zanim zagłębisz się w proces kodowania, zaimportuj niezbędne przestrzenie nazw:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Krok 1: Zdefiniuj katalog wyjściowy
Najpierw zdefiniuj katalog, w którym będą zapisywane wyrenderowane dokumenty:
```csharp
string outputDirectory = "Your Document Directory";
```
 Zastępować`"Your Document Directory"`ze ścieżką, w której chcesz zapisać wyrenderowane dokumenty.
## Krok 2: Zdefiniuj format ścieżki pliku strony
Zdefiniuj format ścieżek plików poszczególnych stron:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ten format wygeneruje nazwy plików, takie jak`page_1.html`, `page_2.html`itp. w określonym katalogu wyjściowym.
## Krok 3: Skonfiguruj opcje ładowania
Skonfiguruj opcje ładowania, w tym limit czasu ładowania zasobów:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
W tym przykładzie dla ładowania zasobów ustawiono limit czasu wynoszący 5 sekund.
## Krok 4: Zainicjuj obiekt przeglądarki
 Zainicjuj`Viewer` obiekt z dokumentem do renderowania i zdefiniowanymi opcjami ładowania:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Zastępować`TestFiles.WITH_EXTERNAL_IMAGE_DOC` ze ścieżką do dokumentu, który chcesz renderować.
## Krok 5: Skonfiguruj opcje widoku HTML
Skonfiguruj opcje widoku HTML dla osadzonych zasobów:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Ta konfiguracja zapewnia, że osadzone zasoby, takie jak obrazy, zostaną uwzględnione w renderowanym kodzie HTML.
## Krok 6: Renderuj dokument
Renderuj dokument, korzystając ze skonfigurowanych opcji:
```csharp
viewer.View(options);
```
Ten krok inicjuje proces renderowania.
## Krok 7: Wyświetl katalog wyjściowy
Wyświetl komunikat wskazujący pomyślne renderowanie i lokalizację katalogu wyjściowego:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek
Opanowanie limitów czasu ładowania zasobów w programie GroupDocs.Viewer dla .NET ma kluczowe znaczenie dla zapewnienia płynnego procesu renderowania dokumentów. Wykonując ten samouczek, zyskałeś wiedzę na temat skutecznego konfigurowania limitów czasu, zwiększając swoją biegłość w programowaniu .NET.
## Często zadawane pytania
### Jakie jest znaczenie ustawiania limitów czasu ładowania zasobów?
Ustawienie limitów czasu ładowania zasobów gwarantuje, że procesy renderowania nie będą zawieszane na czas nieokreślony, co zwiększa stabilność aplikacji.
### Czy limity czasu ładowania zasobów można dostosować na podstawie typów dokumentów?
Tak, limity czasu ładowania zasobów można dostosować w zależności od złożoności i rozmiaru renderowanych dokumentów.
### Czy ustawienie krótszych limitów czasu ma wpływ na wydajność?
Krótsze limity czasu mogą prowadzić do niekompletnego renderowania złożonych dokumentów, jeśli nie można załadować zasobów w określonym czasie.
### Czy GroupDocs.Viewer nadaje się do renderowania różnych formatów dokumentów?
Tak, GroupDocs.Viewer obsługuje renderowanie szerokiej gamy formatów dokumentów, w tym PDF, DOCX, XLSX i innych.
### Czy można wyłączyć limity czasu ładowania zasobów?
Chociaż nie jest to zalecane, limity czasu ładowania zasobów można ustawić na dużą wartość lub całkowicie wyłączyć, w zależności od konkretnych wymagań.