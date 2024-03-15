---
title: Dostosuj rozmiar i jakość obrazu (JPG)
linktitle: Dostosuj rozmiar i jakość obrazu (JPG)
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak zoptymalizować rozmiar i jakość obrazu w formacie JPEG przy użyciu programu Groupdocs.Viewer dla platformy .NET. Popraw swoje wrażenia z przeglądania dokumentów.
type: docs
weight: 11
url: /pl/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Wstęp
Groupdocs.Viewer dla .NET to potężna biblioteka, która umożliwia programistom bezproblemową integrację funkcji przeglądania dokumentów z aplikacjami .NET. Jednym z powszechnych wymagań w aplikacjach do przeglądania dokumentów jest możliwość dostosowania rozmiaru i jakości obrazów, szczególnie w przypadku obrazów JPEG (JPG). W tym samouczku przeprowadzimy Cię przez proces dostosowywania rozmiaru i jakości obrazu za pomocą programu Groupdocs.Viewer dla platformy .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Podstawowa znajomość języka programowania C#.
2. Program Visual Studio zainstalowany w systemie.
3.  Zainstalowana biblioteka Groupdocs.Viewer dla .NET. Można go pobrać z[Tutaj](https://releases.groupdocs.com/viewer/net/).

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#. Te przestrzenie nazw zapewniają dostęp do klas i metod wymaganych do pracy z Groupdocs.Viewer.
## Krok 1: Importuj przestrzenie nazw
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz dostarczony przykładowy kod na wiele kroków, aby lepiej zrozumieć.
## Krok 2: Ustaw katalog wyjściowy i format ścieżki pliku strony
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
W tym kroku określamy katalog wyjściowy, w którym będą zapisywane wyrenderowane obrazy i definiujemy format ścieżki pliku każdego obrazu strony.
## Krok 3: Zainicjuj przeglądarkę i skonfiguruj opcje widoku JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Tutaj inicjujemy obiekt Viewer ścieżką do dokumentu, który ma być przeglądany. Następnie tworzymy instancję JpgViewOptions i ustawiamy żądaną szerokość i wysokość obrazów JPEG.
## Krok 4: Renderuj dokument źródłowy
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na koniec drukujemy komunikat wskazujący pomyślne wyrenderowanie dokumentu źródłowego i lokalizację, w której zapisywane są obrazy wyjściowe.

## Wniosek
tym samouczku dowiedzieliśmy się, jak dostosować rozmiar i jakość obrazów JPEG za pomocą programu Groupdocs.Viewer dla platformy .NET. Wykonując kroki opisane powyżej, możesz łatwo włączyć tę funkcjonalność do aplikacji .NET, zapewniając użytkownikom zoptymalizowane wrażenia z oglądania obrazów.
## Często zadawane pytania
### Czy mogę także dostosować jakość obrazu?
Tak, możesz dostosować jakość obrazu, ustawiając właściwość Quality w JpgViewOptions.
### Jakie formaty dokumentów są obsługiwane przez Groupdocs.Viewer dla .NET?
Groupdocs.Viewer dla .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, PPTX, XLSX i inne.
### Czy Groupdocs.Viewer dla .NET jest kompatybilny z .NET Core?
Tak, Groupdocs.Viewer dla .NET jest kompatybilny z .NET Core wraz z tradycyjnym .NET Framework.
### Czy mogę dostosować format nazewnictwa plików wyjściowych?
Tak, możesz dostosować format nazewnictwa plików wyjściowych, modyfikując zmienną pageFilePathFormat w kodzie.
### Czy Groupdocs.Viewer dla .NET obsługuje adnotacje w dokumentach?
Tak, Groupdocs.Viewer dla .NET zapewnia kompleksową obsługę adnotacji w dokumentach, w tym wyróżnianie, podkreślanie i komentowanie tekstu.