---
title: Uzyskaj informacje o wyświetleniu dokumentu PDF
linktitle: Uzyskaj informacje o wyświetleniu dokumentu PDF
second_title: GroupDocs.Viewer API .NET
description: Z tego obszernego samouczka dowiesz się, jak wyodrębnić informacje o widoku z dokumentów PDF za pomocą programu GroupDocs.Viewer dla platformy .NET.
type: docs
weight: 16
url: /pl/net/pdf-rendering-options/get-view-info-pdf-document/
---
## Wstęp
GroupDocs.Viewer dla .NET to potężne narzędzie zaprojektowane w celu usprawnienia przeglądania dokumentów w aplikacjach .NET. Niezależnie od tego, czy masz do czynienia z plikami PDF, dokumentami programu Word, arkuszami kalkulacyjnymi programu Excel czy prezentacjami programu PowerPoint, ta biblioteka upraszcza proces renderowania i interakcji z różnymi formatami plików. W tym samouczku skupimy się na wykorzystaniu możliwości programu GroupDocs.Viewer specjalnie do wyodrębniania informacji o widoku z dokumentów PDF.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1.  Instalacja GroupDocs.Viewer dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę GroupDocs.Viewer. Można go uzyskać od[link do pobrania](https://releases.groupdocs.com/viewer/net/).   
2. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna do zrozumienia i wdrożenia dostarczonych przykładów kodu.
3. Dostęp do dokumentu PDF: przygotuj dokument PDF, którego będziesz używać do wyodrębniania informacji o widoku.

## Importuj przestrzenie nazw
W projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Rozłóżmy teraz proces pobierania informacji o widoku z dokumentu PDF przy użyciu programu GroupDocs.Viewer dla platformy .NET.
## Krok 1: Zainicjuj obiekt przeglądarki
Utwórz obiekt Viewer i podaj ścieżkę do dokumentu PDF jako parametr.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Krok 2: Zdefiniuj ViewInfoOptions
Określ opcje widoku, takie jak widok HTML, aby pobrać informacje o widoku.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Krok 3: Uzyskaj informacje o widoku
Wywołaj metodę GetViewInfo, aby wyodrębnić informacje o widoku z dokumentu PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Krok 4: Informacje o widoku wyjściowym
Wyświetl wyodrębnione informacje o widoku, takie jak typ dokumentu, liczba stron i uprawnienia do drukowania.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Wniosek
W tym samouczku omówiliśmy, jak używać programu GroupDocs.Viewer dla platformy .NET do wyodrębniania informacji o widoku z dokumentów PDF. Wykonując podane kroki, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami .NET, usprawniając zarządzanie dokumentami i możliwości przeglądania.
## Często zadawane pytania
### Czy GroupDocs.Viewer jest kompatybilny z innymi formatami plików oprócz PDF?
Tak, GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym Word, Excel, PowerPoint i inne.
### Czy mogę dostosować opcje widoku do wymagań mojej aplikacji?
Oczywiście GroupDocs.Viewer oferuje różne opcje dostosowania sposobu oglądania do Twoich konkretnych potrzeb.
### Czy GroupDocs.Viewer nadaje się zarówno do aplikacji komputerowych, jak i internetowych?
Tak, GroupDocs.Viewer jest wszechstronny i można go bezproblemowo zintegrować zarówno z aplikacjami stacjonarnymi, jak i internetowymi .NET.
### Czy GroupDocs.Viewer zapewnia wsparcie i pomoc w przypadku napotkania jakichkolwiek problemów podczas wdrażania?
Oczywiście możesz zwrócić się o pomoc na forum społeczności GroupDocs.Viewer lub uzyskać dostęp do profesjonalnych usług wsparcia w celu szybkiego rozwiązania wszelkich problemów.
### Czy mogę wypróbować GroupDocs.Viewer przed dokonaniem zakupu?
 Tak, możesz poznać funkcje GroupDocs.Viewer, korzystając z bezpłatnej wersji próbnej dostępnej na stronie[strona internetowa](https://purchase.groupdocs.com/buy).