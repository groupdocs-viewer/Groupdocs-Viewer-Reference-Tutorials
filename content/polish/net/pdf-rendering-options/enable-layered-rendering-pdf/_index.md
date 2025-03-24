---
title: Włącz renderowanie warstwowe w formacie PDF
linktitle: Włącz renderowanie warstwowe w formacie PDF
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak włączyć renderowanie warstwowe w dokumentach PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET. Zwiększ komfort przeglądania dokumentów bez wysiłku.
weight: 15
url: /pl/net/pdf-rendering-options/enable-layered-rendering-pdf/
---

# Włącz renderowanie warstwowe w formacie PDF

## Wstęp
W tym samouczku zagłębimy się w proces włączania renderowania warstwowego w dokumentach PDF za pomocą GroupDocs.Viewer dla .NET. Renderowanie warstwowe umożliwia ulepszone wyświetlanie i manipulowanie dokumentami, zapewniając użytkownikom bardziej interaktywne wrażenia wizualne.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. GroupDocs.Viewer dla .NET: Upewnij się, że zainstalowałeś pakiet lub bibliotekę niezbędną do korzystania z GroupDocs.Viewer dla .NET w swoim projekcie.
2. Visual Studio: Powinieneś mieć zainstalowany Visual Studio w swoim systemie do kodowania i wykonywania dostarczonych przykładów.
3. Podstawowe zrozumienie języka C#: W tym samouczku założono znajomość składni i pojęć języka programowania C#.

## Importuj przestrzenie nazw
Zacznij od zaimportowania wymaganych przestrzeni nazw do swojego projektu:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Pamiętaj, aby określić ścieżkę katalogu, w którym chcesz zapisać renderowane dane wyjściowe.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Ten krok ustawia format ścieżek plików poszczególnych stron w renderowanym wyniku.`{0}` jest symbolem zastępczym numeru strony.
## Krok 3: Włącz renderowanie warstwowe
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Tutaj tworzymy`Viewer` obiekt i określ dokument PDF, który ma zostać przetworzony. Następnie konfigurujemy`HtmlViewOptions` ze zdefiniowanym formatem ścieżki pliku strony. Przez ustawienie`EnableLayeredRendering` własność do`true` W`PdfOptions`, włączamy renderowanie warstwowe dla dokumentu PDF.
## Krok 4: Wyświetl katalog wyjściowy
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na koniec drukujemy komunikat informujący o pomyślnym renderowaniu dokumentu źródłowego i zachęcamy użytkownika do sprawdzenia danych wyjściowych w określonym katalogu.

## Wniosek
Włączenie renderowania warstwowego w dokumentach PDF za pomocą programu GroupDocs.Viewer dla .NET zwiększa możliwości przeglądania dokumentów, zapewniając użytkownikom bogatsze i bardziej interaktywne doświadczenia. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować tę funkcję z aplikacjami .NET.
## Często zadawane pytania
### Co to jest renderowanie warstwowe w dokumentach PDF?
Renderowanie warstwowe umożliwia oddzielanie i manipulowanie różnymi komponentami w dokumencie PDF, umożliwiając interaktywne przeglądanie i lepsze doświadczenie użytkownika.
### Czy mogę dostosować katalog wyjściowy dla renderowanych dokumentów?
Tak, możesz określić dowolną ścieżkę katalogu dla danych wyjściowych zgodnie ze swoimi wymaganiami.
### Czy GroupDocs.Viewer obsługuje inne formaty plików oprócz PDF?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym Word, Excel, PowerPoint i inne.
### Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?
Tak, GroupDocs.Viewer jest kompatybilny zarówno ze środowiskami .NET Framework, jak i .NET Core.
### Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc?
Możesz odwiedzić forum GroupDocs.Viewer, aby uzyskać odpowiedzi na pytania lub uzyskać pomoc dotyczącą biblioteki przeglądarki.