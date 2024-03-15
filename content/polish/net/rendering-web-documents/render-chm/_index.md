---
title: Renderuj pliki CHM
linktitle: Renderuj pliki CHM
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak renderować pliki CHM w .NET przy użyciu GroupDocs.Viewer. Bez wysiłku konwertuj CHM na formaty HTML, JPG, PNG i PDF.
type: docs
weight: 10
url: /pl/net/rendering-web-documents/render-chm/
---
## Wstęp
tym samouczku omówimy sposób renderowania plików CHM (skompilowanej pomocy HTML) przy użyciu programu GroupDocs.Viewer dla platformy .NET. GroupDocs.Viewer dla .NET to potężny interfejs API do renderowania dokumentów, który umożliwia programistom wyświetlanie ponad 170 typów dokumentów w aplikacjach .NET bez konieczności instalowania zewnętrznego oprogramowania.

## Warunki wstępne

Zanim zajmiemy się renderowaniem plików CHM, upewnij się, że spełniasz następujące wymagania wstępne:

### Instalowanie GroupDocs.Viewer dla .NET

 Aby rozpocząć, musisz zainstalować GroupDocs.Viewer dla .NET. Bibliotekę można pobrać ze strony[Witryna GroupDocs](https://releases.groupdocs.com/viewer/net/) lub zainstaluj go za pomocą Menedżera pakietów NuGet, uruchamiając następujące polecenie w konsoli Menedżera pakietów:

```bash
Install-Package GroupDocs.Viewer
```

## Importowanie przestrzeni nazw

Pamiętaj, aby zaimportować niezbędne przestrzenie nazw do swojego projektu:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz proces renderowania na kilka etapów:

## Krok 1: Zdefiniuj katalog wyjściowy

Zdefiniuj katalog, w którym chcesz zapisywać renderowane pliki:

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Renderuj do HTML

Aby wyrenderować pliki CHM do formatu HTML, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Ustaw na true, aby przekonwertować całą zawartość CHM na jedną stronę

    viewer.View(options); //Konwertuj wszystkie strony
}
```

## Krok 3: Renderuj do JPG

Aby renderować pliki CHM do obrazów JPG, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konwertuj tylko strony 1, 2, 3
}
```

## Krok 4: Renderuj do PNG

Aby renderować pliki CHM do obrazów PNG, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Konwertuj tylko strony 1, 2, 3
}
```

## Krok 5: Renderuj do formatu PDF

Aby wyrenderować pliki CHM do dokumentu PDF, użyj następującego fragmentu kodu:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Konwertuj wszystkie strony
}
```

## Krok 6: Sprawdź dane wyjściowe

Po zakończeniu procesu renderowania sprawdź określony katalog wyjściowy dla renderowanych plików:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek

Renderowanie plików CHM przy użyciu programu GroupDocs.Viewer dla platformy .NET jest prostym procesem. Wykonując kroki opisane w tym samouczku, możesz efektywnie konwertować dokumenty CHM do różnych formatów, takich jak HTML, obrazy (JPG, PNG) i PDF w aplikacjach .NET.

## Często zadawane pytania

### P1: Czy GroupDocs.Viewer może renderować dokumenty w innych formatach niż CHM?

O1: Tak, GroupDocs.Viewer obsługuje renderowanie ponad 170 formatów dokumentów, w tym PDF, DOCX, XLSX, PPTX i innych.

### P2: Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?

O2: Tak, GroupDocs.Viewer oprócz tradycyjnego .NET Framework obsługuje platformę .NET Core.

### P3: Czy mogę dostosować opcje renderowania dla różnych formatów wyjściowych?

O3: Tak, GroupDocs.Viewer udostępnia różne opcje dostosowywania procesu renderowania, takie jak określanie numerów stron, ustawianie jakości obrazu i konfigurowanie ścieżek wyjściowych.

### P4: Czy GroupDocs.Viewer wymaga jakichkolwiek zewnętrznych zależności do renderowania dokumentów?

O4: Nie, GroupDocs.Viewer jest samodzielną biblioteką i nie wymaga żadnych zewnętrznych zależności ani instalacji oprogramowania innych firm.

### P5: Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer?

 O5: Tak, możesz skorzystać z bezpłatnej wersji próbnej GroupDocs.Viewer, odwiedzając stronę[strona internetowa](https://releases.groupdocs.com/).