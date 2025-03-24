---
title: Dodaj znak wodny w dokumencie
linktitle: Dodaj znak wodny w dokumencie
second_title: GroupDocs.Viewer API .NET
description: Dowiedz się, jak bezproblemowo dodawać znaki wodne do dokumentów za pomocą programu GroupDocs.Viewer dla platformy .NET. Zwiększ bezpieczeństwo dokumentów i budowanie marki dzięki temu łatwemu do zrozumienia samouczkowi.
weight: 10
url: /pl/net/rendering-options/add-watermark/
---
## Wstęp
W dzisiejszej erze cyfrowej płynne zarządzanie różnymi formatami dokumentów i przeglądanie ich jest koniecznością zarówno dla wielu firm, jak i osób prywatnych. Na szczęście dzięki narzędziom takim jak GroupDocs.Viewer dla .NET obsługa dokumentów staje się dziecinnie prosta. Ta potężna biblioteka .NET umożliwia programistom bezproblemową integrację funkcji przeglądania dokumentów z ich aplikacjami, umożliwiając użytkownikom przeglądanie dokumentów bez konieczności korzystania z oryginalnego oprogramowania, które je utworzyło.
## Warunki wstępne
Zanim zaczniesz używać GroupDocs.Viewer dla .NET do dodawania znaków wodnych do dokumentów, upewnij się, że posiadasz następujące elementy:
1. Konfiguracja środowiska: skonfiguruj środowisko programistyczne z zainstalowaną platformą .NET Framework lub .NET Core.
2.  GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla .NET z[strona pobierania](https://releases.groupdocs.com/viewer/net/).
3. Pliki dokumentów: Przygotuj pliki dokumentów, z którymi chcesz pracować, takie jak DOCX, PDF lub inne.
4. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna do implementacji przykładowego kodu.

## Importuj przestrzenie nazw
Przed rozpoczęciem dodawania znaków wodnych do dokumentów przy użyciu programu GroupDocs.Viewer dla platformy .NET pamiętaj o zaimportowaniu wymaganych przestrzeni nazw do kodu C#. Ten krok umożliwia bezproblemowy dostęp do klas i metod udostępnianych przez bibliotekę.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Przeanalizujmy teraz proces dodawania znaku wodnego do dokumentu za pomocą programu GroupDocs.Viewer dla platformy .NET. Wykonaj poniższe kroki, aby bezproblemowo zintegrować funkcję znaku wodnego ze swoją aplikacją.
## Krok 1: Ustaw katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Określ katalog, w którym chcesz zapisać pliki wyjściowe po zastosowaniu znaku wodnego.
## Krok 2: Zdefiniuj format ścieżki pliku strony
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ustaw format ścieżek plików renderowanych stron. W tym przykładzie zostaną wygenerowane pliki HTML z numerami stron.
## Krok 3: Utwórz instancję obiektu przeglądarki
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kod jest kontynuowany w następnym kroku...
}
```
Utwórz instancję klasy Viewer, przekazując jako parametr ścieżkę do pliku dokumentu. W tym przykładzie używamy przykładowego pliku DOCX.
## Krok 4: Skonfiguruj opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Skonfiguruj opcje widoku HTML, w tym tekst znaku wodnego, który chcesz dodać do dokumentu.
## Krok 5: Wyświetl dokument ze znakiem wodnym
```csharp
viewer.View(options);
```
Wywołaj metodę View obiektu Viewer, przekazując skonfigurowane opcje. Spowoduje to wyrenderowanie dokumentu z określonym znakiem wodnym.
## Krok 6: Wyświetl ścieżkę do katalogu wyjściowego
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Poinformuj użytkownika o pomyślnym wygenerowaniu dokumentu i wskaż katalog, w którym zapisywane są pliki wyjściowe.

## Wniosek
GroupDocs.Viewer dla .NET zapewnia wygodny sposób programowego dodawania znaków wodnych do dokumentów. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować funkcję znaku wodnego z aplikacjami .NET, zwiększając bezpieczeństwo dokumentów i budowanie marki.
## Często zadawane pytania
### Czy mogę dostosować wygląd znaku wodnego?
Tak, możesz dostosować różne właściwości znaku wodnego, takie jak tekst, czcionka, kolor, rozmiar i położenie.
### Czy GroupDocs.Viewer obsługuje przeglądanie dokumentów ze zdalnych źródeł?
Tak, GroupDocs.Viewer obsługuje przeglądanie dokumentów z magazynu lokalnego, a także zdalnych adresów URL.
### Czy dostępna jest wersja próbna programu GroupDocs.Viewer dla platformy .NET?
Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.groupdocs.com/).
### Czy mogę dodać znaki wodne do wielu stron dokumentu?
Oczywiście GroupDocs.Viewer umożliwia dodawanie znaków wodnych do poszczególnych stron lub wszystkich stron dokumentu.
### Jak mogę uzyskać wsparcie lub pomoc, jeśli napotkam jakiekolwiek problemy?
 Możesz szukać pomocy i wsparcia na forach społeczności GroupDocs[Tutaj](https://forum.groupdocs.com/c/viewer/9).