---
"description": "Dowiedz się, jak renderować pliki CHM w .NET za pomocą GroupDocs.Viewer. Konwertuj pliki CHM do formatów HTML, JPG, PNG i PDF bez wysiłku."
"linktitle": "Renderuj pliki CHM"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderuj pliki CHM"
"url": "/pl/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Renderuj pliki CHM

## Wstęp
W tym samouczku pokażemy, jak renderować pliki CHM (skompilowana pomoc HTML) przy użyciu GroupDocs.Viewer dla platformy .NET. GroupDocs.Viewer dla platformy .NET to zaawansowany interfejs API do renderowania dokumentów, który umożliwia programistom wyświetlanie ponad 170 typów dokumentów w aplikacjach .NET bez konieczności instalowania zewnętrznego oprogramowania.

## Wymagania wstępne

Zanim przejdziemy do renderowania plików CHM, upewnij się, że spełnione są następujące wymagania wstępne:

### Instalowanie GroupDocs.Viewer dla .NET

Aby rozpocząć, musisz zainstalować GroupDocs.Viewer dla .NET. Możesz pobrać bibliotekę ze strony [Strona internetowa GroupDocs](https://releases.groupdocs.com/viewer/net/) lub zainstaluj go za pomocą Menedżera pakietów NuGet, uruchamiając następujące polecenie w konsoli Menedżera pakietów:

```bash
Install-Package GroupDocs.Viewer
```

## Importowanie przestrzeni nazw

Pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw do swojego projektu:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz proces renderowania na kilka kroków:

## Krok 1: Zdefiniuj katalog wyjściowy

Zdefiniuj katalog, w którym mają zostać zapisane wyrenderowane pliki:

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Renderowanie do HTML

Aby przekształcić pliki CHM do formatu HTML, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Ustaw na true, aby przekonwertować całą zawartość CHM na pojedynczą stronę

    viewer.View(options); // Konwertuj wszystkie strony
}
```

## Krok 3: Renderowanie do JPG

Aby przekształcić pliki CHM w obrazy JPG, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konwertuj tylko strony 1, 2, 3
}
```

## Krok 4: Renderowanie do PNG

Aby przekształcić pliki CHM w obrazy PNG, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konwertuj tylko strony 1, 2, 3
}
```

## Krok 5: Renderowanie do PDF

Aby przekształcić pliki CHM w dokument PDF, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Konwertuj wszystkie strony
}
```

## Krok 6: Sprawdź wynik

Po zakończeniu procesu renderowania należy sprawdzić określony katalog wyjściowy pod kątem wyrenderowanych plików:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek

Renderowanie plików CHM za pomocą GroupDocs.Viewer dla .NET to prosty proces. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz skutecznie konwertować dokumenty CHM do różnych formatów, takich jak HTML, obrazy (JPG, PNG) i PDF w swoich aplikacjach .NET.

## Najczęściej zadawane pytania

### P1: Czy GroupDocs.Viewer może renderować inne formaty dokumentów niż CHM?

A1: Tak, GroupDocs.Viewer obsługuje renderowanie ponad 170 formatów dokumentów, w tym PDF, DOCX, XLSX, PPTX i inne.

### P2: Czy GroupDocs.Viewer jest kompatybilny z .NET Core?

A2: Tak, GroupDocs.Viewer obsługuje platformę .NET Core oprócz tradycyjnej platformy .NET Framework.

### P3: Czy mogę dostosować opcje renderowania do różnych formatów wyjściowych?

A3: Tak, GroupDocs.Viewer oferuje różne opcje umożliwiające dostosowanie procesu renderowania, takie jak określanie numerów stron, ustawianie jakości obrazu i konfigurowanie ścieżek wyjściowych.

### P4: Czy GroupDocs.Viewer wymaga jakichkolwiek zewnętrznych zależności do renderowania dokumentów?

A4: Nie, GroupDocs.Viewer jest samodzielną biblioteką i nie wymaga żadnych zewnętrznych zależności ani instalacji oprogramowania innych firm.

### P5: Czy jest dostępna bezpłatna wersja próbna GroupDocs.Viewer?

A5: Tak, możesz skorzystać z bezpłatnej wersji próbnej GroupDocs.Viewer, odwiedzając stronę [strona internetowa](https://releases.groupdocs.com/).