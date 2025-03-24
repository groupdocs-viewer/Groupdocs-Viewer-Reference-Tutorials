---
title: Zmień nazwę pól e-mail podczas renderowania
linktitle: Zmień nazwę pól e-mail podczas renderowania
second_title: GroupDocs.Viewer API .NET
description: Zwiększ komfort przeglądania dokumentów dzięki GroupDocs.Viewer dla platformy .NET. Bezproblemowo renderuj i dostosowuj wiadomości e-mail.
weight: 12
url: /pl/net/rendering-email-messages/rename-email-fields/
---
## Wstęp

dzisiejszej epoce cyfrowej wydajne zarządzanie dokumentami i przeglądanie ich ma ogromne znaczenie zarówno dla firm, jak i osób prywatnych. Niezależnie od tego, czy są to umowy, raporty czy wiadomości e-mail, możliwość płynnego poruszania się po tych dokumentach może znacznie zwiększyć produktywność. W tym miejscu do gry wchodzi GroupDocs.Viewer dla .NET. Ta potężna biblioteka umożliwia programistom integrowanie możliwości przeglądania dokumentów bezpośrednio z aplikacjami .NET, oferując szeroką gamę funkcji do renderowania różnych formatów dokumentów.

## Warunki wstępne

Przed zapoznaniem się z samouczkiem dotyczącym zmiany nazw pól e-mail podczas renderowania przy użyciu programu GroupDocs.Viewer dla platformy .NET upewnij się, że spełnione są następujące wymagania wstępne:

1.  Biblioteka GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla .NET ze strony[Tutaj](https://releases.groupdocs.com/viewer/net/).

2. Środowisko programistyczne: upewnij się, że masz skonfigurowane odpowiednie środowisko programistyczne do programowania w .NET, takie jak Visual Studio.

3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#, ponieważ samouczek będzie zawierał fragmenty kodu C#.

4. Katalog dokumentów: Przygotuj katalog, w którym przechowywane są dokumenty do renderowania.

## Importuj przestrzenie nazw

Aby móc korzystać z funkcjonalności GroupDocs.Viewer w aplikacji .NET, należy zaimportować niezbędne przestrzenie nazw.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Podzielmy teraz proces zmiany nazw pól e-mail podczas renderowania przy użyciu programu GroupDocs.Viewer dla platformy .NET na kilka kroków:

## Krok 1: Zdefiniuj katalog wyjściowy

Najpierw określ katalog, w którym zostaną zapisane wyrenderowane strony HTML.

```csharp
string outputDirectory = "Your Document Directory";
```

## Krok 2: Zdefiniuj format ścieżki pliku strony

Zdefiniuj format ścieżek plików renderowanych stron HTML. Każda strona zostanie zapisana jako oddzielny plik HTML.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Krok 3: Zainicjuj obiekt przeglądarki

Utwórz instancję klasy Viewer i podaj ścieżkę dokumentu, który ma być przeglądany, jako parametr.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Krok 4: Skonfiguruj opcje widoku HTML

Skonfiguruj opcje widoku HTML, w tym określ format pliku wyjściowego i skonfiguruj mapowania pól e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Krok 5: Renderuj dokument

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

Podsumowując, GroupDocs.Viewer dla .NET zapewnia płynne rozwiązanie do renderowania dokumentów w aplikacjach .NET. Wykonując kroki opisane w tym samouczku, możesz łatwo zmieniać nazwy pól e-mail podczas renderowania, zwiększając czytelność i użyteczność dokumentów e-mail. Dzięki intuicyjnemu interfejsowi API i kompleksowym funkcjom GroupDocs.Viewer umożliwia programistom skuteczne usprawnianie procesów przeglądania dokumentów.

## Często zadawane pytania

### P: Czy mogę renderować dokumenty inne niż wiadomości e-mail przy użyciu programu GroupDocs.Viewer dla platformy .NET?

O: Tak, GroupDocs.Viewer obsługuje renderowanie różnych formatów dokumentów, w tym PDF, dokumentów Microsoft Office, obrazów i innych.

### P: Czy GroupDocs.Viewer jest zgodny z platformą .NET Core?

O: Tak, GroupDocs.Viewer obsługuje platformę .NET Core wraz z tradycyjną platformą .NET Framework.

### P: Czy mogę dostosować wygląd renderowanych dokumentów?

O: Oczywiście GroupDocs.Viewer oferuje szerokie opcje dostosowywania umożliwiające kontrolowanie wyglądu i zachowania renderowanych dokumentów.

### P: Czy GroupDocs.Viewer obsługuje przesyłanie strumieniowe dokumentów?

O: Tak, GroupDocs.Viewer umożliwia przesyłanie strumieniowe dokumentów bezpośrednio do przeglądarki klienta bez konieczności przechowywania ich na serwerze.

### P: Czy GroupDocs.Viewer nadaje się do aplikacji na poziomie przedsiębiorstwa?

O: Z pewnością GroupDocs.Viewer zaprojektowano tak, aby spełniał wymagania aplikacji na poziomie korporacyjnym dzięki swojej skalowalności, niezawodności i solidnemu zestawowi funkcji.
