---
"description": "Ulepsz przeglądanie dokumentów dzięki GroupDocs.Viewer dla .NET. Bezproblemowo renderuj i dostosowuj wiadomości e-mail."
"linktitle": "Zmień nazwy pól e-mail podczas renderowania"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Zmień nazwy pól e-mail podczas renderowania"
"url": "/pl/net/rendering-email-messages/rename-email-fields/"
"weight": 12
type: docs
---
# Zmień nazwy pól e-mail podczas renderowania

## Wstęp

W dzisiejszej erze cyfrowej zarządzanie dokumentami i ich przeglądanie jest niezwykle ważne zarówno dla firm, jak i osób prywatnych. Niezależnie od tego, czy chodzi o umowy, raporty czy wiadomości e-mail, możliwość płynnego poruszania się po tych dokumentach może znacznie zwiększyć produktywność. W tym miejscu wkracza GroupDocs.Viewer dla .NET. Ta potężna biblioteka umożliwia deweloperom integrację możliwości przeglądania dokumentów bezpośrednio z aplikacjami .NET, oferując szeroki zakres funkcji do renderowania różnych formatów dokumentów.

## Wymagania wstępne

Zanim przejdziesz do samouczka dotyczącego zmiany nazw pól wiadomości e-mail podczas renderowania za pomocą GroupDocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:

1. Biblioteka GroupDocs.Viewer dla platformy .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla platformy .NET z [Tutaj](https://releases.groupdocs.com/viewer/net/).

2. Środowisko programistyczne: Upewnij się, że masz odpowiednie środowisko programistyczne przygotowane do programowania w środowisku .NET, np. Visual Studio.

3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#, ponieważ samouczek będzie obejmował fragmenty kodu C#.

4. Katalog dokumentów: Przygotuj katalog, w którym będą przechowywane dokumenty przeznaczone do renderowania.

## Importuj przestrzenie nazw

Aby móc korzystać z funkcjonalności GroupDocs.Viewer w aplikacji .NET, należy zaimportować niezbędne przestrzenie nazw.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz podzielimy proces zmiany nazw pól wiadomości e-mail podczas renderowania przy użyciu GroupDocs.Viewer dla platformy .NET na kilka kroków:

## Krok 1: Zdefiniuj katalog wyjściowy

Najpierw należy określić katalog, w którym zostaną zapisane wyrenderowane strony HTML.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Zdefiniuj format ścieżki pliku stronicowania

Zdefiniuj format ścieżek plików renderowanych stron HTML. Każda strona zostanie zapisana jako oddzielny plik HTML.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Zainicjuj obiekt Viewer

Utwórz instancję klasy Viewer i przekaż ścieżkę do dokumentu, który chcesz wyświetlić, jako parametr.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Krok 4: Skonfiguruj opcje widoku HTML

Skonfiguruj opcje widoku HTML, w tym określ format pliku wyjściowego i skonfiguruj mapowania pól wiadomości e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Krok 5: Renderowanie dokumentu

Wywołaj metodę View obiektu Viewer, przekazując skonfigurowane opcje widoku HTML.

```csharp
viewer.View(options);
```

## Krok 6: Wyświetl komunikat o powodzeniu

Poinformuj użytkownika, że dokument został pomyślnie wyrenderowany.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Wniosek

Podsumowując, GroupDocs.Viewer dla .NET zapewnia bezproblemowe rozwiązanie do renderowania dokumentów w aplikacjach .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz łatwo zmieniać nazwy pól e-mail podczas renderowania, zwiększając czytelność i użyteczność dokumentów e-mail. Dzięki intuicyjnemu API i kompleksowym funkcjom GroupDocs.Viewer umożliwia deweloperom efektywne usprawnianie procesów przeglądania dokumentów.

## Najczęściej zadawane pytania

### P: Czy mogę renderować dokumenty inne niż wiadomości e-mail za pomocą GroupDocs.Viewer dla .NET?

O: Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów dokumentów, w tym PDF, dokumentów Microsoft Office, obrazów i innych.

### P: Czy GroupDocs.Viewer jest kompatybilny z .NET Core?

O: Tak, GroupDocs.Viewer obsługuje platformę .NET Core i tradycyjną platformę .NET Framework.

### P: Czy mogę dostosować wygląd renderowanych dokumentów?

O: Oczywiście, GroupDocs.Viewer oferuje rozbudowane opcje dostosowywania pozwalające kontrolować wygląd i zachowanie renderowanych dokumentów.

### P: Czy GroupDocs.Viewer obsługuje strumieniowe przesyłanie dokumentów?

O: Tak, GroupDocs.Viewer pozwala na strumieniowe przesyłanie dokumentów bezpośrednio do przeglądarki klienta bez konieczności przechowywania ich na serwerze.

### P: Czy GroupDocs.Viewer nadaje się do zastosowań korporacyjnych?

O: Z pewnością GroupDocs.Viewer został zaprojektowany tak, aby sprostać wymaganiom aplikacji klasy korporacyjnej, oferując skalowalność, niezawodność i rozbudowany zestaw funkcji.