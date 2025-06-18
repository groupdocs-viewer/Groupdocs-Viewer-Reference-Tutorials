---
"description": "Dowiedz się, jak optymalizować rozmiar i jakość obrazu w formacie JPEG przy użyciu Groupdocs.Viewer dla platformy .NET. Ulepsz swoje doświadczenie przeglądania dokumentów."
"linktitle": "Dostosuj rozmiar i jakość obrazu (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dostosuj rozmiar i jakość obrazu (JPG)"
"url": "/pl/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Dostosuj rozmiar i jakość obrazu (JPG)

## Wstęp
Groupdocs.Viewer for .NET to potężna biblioteka, która umożliwia deweloperom bezproblemową integrację funkcji przeglądania dokumentów z aplikacjami .NET. Jednym z powszechnych wymagań w aplikacjach do przeglądania dokumentów jest możliwość dostosowania rozmiaru i jakości obrazów, szczególnie w przypadku obrazów JPEG (JPG). W tym samouczku przeprowadzimy Cię przez proces dostosowywania rozmiaru i jakości obrazu za pomocą Groupdocs.Viewer for .NET.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
1. Podstawowa znajomość języka programowania C#.
2. Program Visual Studio zainstalowany w systemie.
3. Zainstalowano bibliotekę Groupdocs.Viewer dla .NET. Można ją pobrać z [Tutaj](https://releases.groupdocs.com/viewer/net/).

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#. Te przestrzenie nazw zapewniają dostęp do klas i metod wymaganych do pracy z Groupdocs.Viewer.
## Krok 1: Importuj przestrzenie nazw
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz rozbijemy przykładowy kod na kilka kroków, aby lepiej go zrozumieć.
## Krok 2: Ustaw format katalogu wyjściowego i ścieżki pliku stronicowania
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
W tym kroku określamy katalog wyjściowy, w którym zostaną zapisane wyrenderowane obrazy i definiujemy format ścieżki pliku każdego obrazu strony.
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
Tutaj inicjujemy obiekt Viewer ścieżką do dokumentu, który ma zostać wyświetlony. Następnie tworzymy wystąpienie JpgViewOptions i ustawiamy żądaną szerokość i wysokość dla obrazów JPEG.
## Krok 4: Renderuj dokument źródłowy
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na koniec drukujemy komunikat informujący o pomyślnym wyrenderowaniu dokumentu źródłowego i miejscu, w którym zapisane zostały obrazy wyjściowe.

## Wniosek
tym samouczku nauczyliśmy się, jak dostosować rozmiar i jakość obrazów JPEG za pomocą Groupdocs.Viewer dla .NET. Postępując zgodnie z powyższymi krokami, możesz łatwo włączyć tę funkcjonalność do swoich aplikacji .NET, zapewniając użytkownikom zoptymalizowane wrażenia podczas przeglądania obrazów.
## Najczęściej zadawane pytania
### Czy mogę również dostosować jakość obrazu?
Tak, możesz dostosować jakość obrazu, ustawiając właściwość Jakość w JpgViewOptions.
### Jakie formaty dokumentów są obsługiwane przez Groupdocs.Viewer dla platformy .NET?
Groupdocs.Viewer dla platformy .NET obsługuje szeroką gamę formatów dokumentów, w tym DOCX, PDF, PPTX, XLSX i inne.
### Czy Groupdocs.Viewer dla .NET jest zgodny z .NET Core?
Tak, Groupdocs.Viewer dla .NET jest kompatybilny zarówno z platformą .NET Core, jak i tradycyjnym środowiskiem .NET Framework.
### Czy mogę dostosować format nazewnictwa plików wyjściowych?
Tak, możesz dostosować format nazewnictwa plików wyjściowych, modyfikując zmienną pageFilePathFormat w kodzie.
### Czy Groupdocs.Viewer dla platformy .NET obsługuje adnotacje dokumentów?
Tak, Groupdocs.Viewer dla platformy .NET zapewnia wszechstronną obsługę adnotacji dokumentów, obejmującą wyróżnianie tekstu, podkreślanie go i komentowanie.