---
"description": "Dowiedz się, jak bez wysiłku zastąpić brakujące czcionki w dokumentach .NET za pomocą GroupDocs.Viewer. Zapewnij dokładne renderowanie za pomocą prostych kroków."
"linktitle": "Zastąp brakującą czcionkę"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Zastąp brakującą czcionkę"
"url": "/pl/net/rendering-options/replace-missing-font/"
"weight": 20
---

# Zastąp brakującą czcionkę

## Wstęp
świecie rozwoju .NET wydajna obsługa dokumentów jest kluczowa. GroupDocs.Viewer dla .NET zapewnia potężne rozwiązanie do przeglądania różnych formatów dokumentów w aplikacjach .NET. W tym samouczku przyjrzymy się, jak używać GroupDocs.Viewer dla .NET do zastępowania brakujących czcionek w dokumentach. Niezależnie od tego, czy masz do czynienia z plikami PDF, prezentacjami PowerPoint czy dokumentami Word, GroupDocs.Viewer upraszcza proces, zapewniając, że dokumenty są renderowane dokładnie, nawet gdy brakuje czcionek.
## Wymagania wstępne
Zanim przejdziesz do tego samouczka, upewnij się, że posiadasz następujące rzeczy:
1. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer ze strony internetowej](https://releases.groupdocs.com/viewer/net/).
2. Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET, np. Visual Studio.
3. Podstawowa wiedza z zakresu języka C#: Znajomość języka programowania C# i platformy .NET.

## Importuj przestrzenie nazw
kodzie C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz przeanalizujemy proces zastępowania brakujących czcionek w dokumentach za pomocą GroupDocs.Viewer dla platformy .NET.
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Ustaw katalog, w którym zostaną zapisane wyrenderowane strony dokumentu.
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Określ format nazywania plików wyjściowych HTML. W tym przykładzie każda strona zostanie zapisana jako plik HTML z konwencją nazewnictwa „page_{page_number}.html”.
## Krok 3: Zainicjuj obiekt Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Zainicjuj nowe wystąpienie klasy Viewer, przekazując ścieżkę do pliku dokumentu (w tym przypadku prezentacji programu PowerPoint z brakującymi czcionkami) jako parametr.
## Krok 4: Ustaw opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Utwórz instancję HtmlViewOptions i skonfiguruj ją, aby osadzać zasoby w wynikach HTML. Określ domyślną nazwę czcionki, która będzie używana jako zamiennik brakujących czcionek.
## Krok 5: Renderowanie dokumentu
```csharp
viewer.View(options);
```
Wywołaj metodę View obiektu Viewer, przekazując opcje widoku HTML. Spowoduje to wyrenderowanie stron dokumentu przy użyciu określonych opcji.
## Krok 6: Wyświetl ścieżkę wyjściową
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Wyświetl komunikat informujący o pomyślnym wyrenderowaniu dokumentu i podaj ścieżkę, w której zapisane zostaną pliki wyjściowe HTML.

## Wniosek
W tym samouczku nauczyliśmy się, jak używać GroupDocs.Viewer dla .NET, aby zastąpić brakujące czcionki w dokumentach. Wykonując te kroki, możesz mieć pewność, że Twoje dokumenty będą dokładnie renderowane, nawet gdy niektóre czcionki są niedostępne. GroupDocs.Viewer upraszcza ten proces, pozwalając Ci skupić się na budowaniu solidnych aplikacji .NET bez martwienia się o problemy ze zgodnością czcionek.
## Najczęściej zadawane pytania
### Czy GroupDocs.Viewer radzi sobie z innymi typami problemów związanych z czcionkami?
Tak, GroupDocs.Viewer oferuje różne funkcje związane z czcionkami, w tym podstawianie i wykrywanie czcionek.
### Czy GroupDocs.Viewer jest kompatybilny ze wszystkimi platformami .NET?
GroupDocs.Viewer obsługuje szeroką gamę środowisk .NET, w tym .NET Core i .NET Standard.
### Czy mogę dostosować domyślną czcionkę zastępczą w GroupDocs.Viewer?
Oczywiście, możesz wybrać dowolną czcionkę jako domyślną czcionkę zastępującą brakujące czcionki.
### Czy GroupDocs.Viewer obsługuje przetwarzanie wsadowe dokumentów?
Tak, GroupDocs.Viewer pozwala na przetwarzanie wielu dokumentów jednocześnie, co czyni go idealnym rozwiązaniem w przypadku przetwarzania wsadowego.
### Gdzie mogę znaleźć dalszą pomoc lub wsparcie dotyczące GroupDocs.Viewer?
Możesz odwiedzić forum GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9) w celu uzyskania pomocy lub wsparcia.