---
title: Zastąp brakującą czcionkę
linktitle: Zastąp brakującą czcionkę
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak łatwo zastąpić brakujące czcionki w dokumentach .NET za pomocą GroupDocs.Viewer. Zapewnij dokładne renderowanie za pomocą prostych kroków.
weight: 20
url: /pl/net/rendering-options/replace-missing-font/
---
## Wstęp
W świecie programowania .NET wydajna obsługa dokumentów ma kluczowe znaczenie. GroupDocs.Viewer dla .NET zapewnia zaawansowane rozwiązanie do przeglądania różnych formatów dokumentów w aplikacjach .NET. W tym samouczku omówimy, jak używać programu GroupDocs.Viewer dla platformy .NET do zastępowania brakujących czcionek w dokumentach. Niezależnie od tego, czy masz do czynienia z plikami PDF, prezentacjami programu PowerPoint czy dokumentami programu Word, GroupDocs.Viewer upraszcza ten proces, zapewniając dokładne renderowanie dokumentów, nawet jeśli brakuje czcionek.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że posiadasz następujące elementy:
1. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer z witryny internetowej](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio.
3. Podstawowa znajomość C#: Znajomość języka programowania C# i frameworku .NET.

## Importuj przestrzenie nazw
W kodzie C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcji GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Przeanalizujmy teraz proces zastępowania brakujących czcionek w dokumentach za pomocą programu GroupDocs.Viewer dla .NET.
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Ustaw katalog, w którym zostaną zapisane wyrenderowane strony dokumentu.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Określ format nazewnictwa wyjściowych plików HTML. W tym przykładzie każda strona zostanie zapisana jako plik HTML z konwencją nazewnictwa „page_{page_number}.html”.
## Krok 3: Zainicjuj obiekt przeglądarki
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Zainicjuj nową instancję klasy Viewer, przekazując jako parametr ścieżkę do pliku dokumentu (w tym przypadku prezentacji PowerPoint z brakującymi czcionkami).
## Krok 4: Ustaw opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Utwórz instancję HtmlViewOptions i skonfiguruj ją tak, aby osadzała zasoby w wynikach HTML. Określ domyślną nazwę czcionki, która będzie używana jako zamiennik brakujących czcionek.
## Krok 5: Renderuj dokument
```csharp
viewer.View(options);
```
Wywołaj metodę View obiektu Viewer, przekazując opcje widoku HTML. Spowoduje to wyrenderowanie stron dokumentu przy użyciu określonych opcji.
## Krok 6: Wyświetl ścieżkę wyjściową
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Wydrukuj komunikat wskazujący pomyślne wyrenderowanie dokumentu i podaj ścieżkę, w której zapisywane są wyjściowe pliki HTML.

## Wniosek
W tym samouczku dowiedzieliśmy się, jak używać programu GroupDocs.Viewer dla platformy .NET do zastępowania brakujących czcionek w dokumentach. Wykonując poniższe kroki, możesz mieć pewność, że Twoje dokumenty zostaną poprawnie wyrenderowane, nawet jeśli niektóre czcionki są niedostępne. GroupDocs.Viewer upraszcza ten proces, umożliwiając skupienie się na tworzeniu solidnych aplikacji .NET bez martwienia się o problemy ze zgodnością czcionek.
## Często zadawane pytania
### Czy GroupDocs.Viewer może poradzić sobie z innymi typami problemów związanych z czcionkami?
Tak, GroupDocs.Viewer udostępnia różne funkcje związane z czcionkami, w tym podstawianie czcionek i wykrywanie czcionek.
### Czy GroupDocs.Viewer jest kompatybilny ze wszystkimi frameworkami .NET?
GroupDocs.Viewer obsługuje szeroką gamę platform .NET, w tym .NET Core i .NET Standard.
### Czy mogę dostosować domyślną zamianę czcionek w GroupDocs.Viewer?
Oczywiście możesz określić dowolną wybraną czcionkę jako domyślny zamiennik brakujących czcionek.
### Czy GroupDocs.Viewer obsługuje wsadowe przetwarzanie dokumentów?
Tak, GroupDocs.Viewer umożliwia jednoczesne przetwarzanie wielu dokumentów, dzięki czemu idealnie nadaje się do scenariuszy przetwarzania wsadowego.
### Gdzie mogę znaleźć dalszą pomoc lub wsparcie dotyczące GroupDocs.Viewer?
 Możesz odwiedzić forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9) w przypadku jakichkolwiek pytań dotyczących pomocy lub wsparcia.