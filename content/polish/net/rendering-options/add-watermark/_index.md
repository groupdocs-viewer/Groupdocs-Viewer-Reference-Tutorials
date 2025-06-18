---
"description": "Dowiedz się, jak bezproblemowo dodawać znaki wodne do dokumentów za pomocą GroupDocs.Viewer dla .NET. Zwiększ bezpieczeństwo dokumentów i markę dzięki temu łatwemu w użyciu samouczkowi."
"linktitle": "Dodaj znak wodny w dokumencie"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dodaj znak wodny w dokumencie"
"url": "/pl/net/rendering-options/add-watermark/"
"weight": 10
---

# Dodaj znak wodny w dokumencie

## Wstęp
W dzisiejszej erze cyfrowej zarządzanie i przeglądanie różnych formatów dokumentów bezproblemowo jest koniecznością dla wielu firm i osób. Na szczęście dzięki narzędziom takim jak GroupDocs.Viewer dla .NET obsługa dokumentów staje się dziecinnie prosta. Ta potężna biblioteka .NET umożliwia deweloperom bezproblemową integrację funkcji przeglądania dokumentów z ich aplikacjami, umożliwiając użytkownikom przeglądanie dokumentów bez potrzeby korzystania z oryginalnego oprogramowania, które je utworzyło.
## Wymagania wstępne
Zanim zaczniesz używać GroupDocs.Viewer dla platformy .NET do dodawania znaków wodnych do dokumentów, upewnij się, że masz następujące elementy:
1. Konfiguracja środowiska: Skonfiguruj środowisko programistyczne z zainstalowanym .NET Framework lub .NET Core.
2. GroupDocs.Viewer dla .NET: Pobierz i zainstaluj bibliotekę GroupDocs.Viewer dla .NET z [strona do pobrania](https://releases.groupdocs.com/viewer/net/).
3. Pliki dokumentów: Przygotuj pliki dokumentów, z którymi chcesz pracować, np. DOCX, PDF lub inne.
4. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna do zaimplementowania przykładów kodu.

## Importuj przestrzenie nazw
Zanim zaczniesz dodawać znaki wodne do dokumentów za pomocą GroupDocs.Viewer dla .NET, upewnij się, że zaimportowałeś wymagane przestrzenie nazw do swojego kodu C#. Ten krok umożliwia bezproblemowy dostęp do klas i metod udostępnianych przez bibliotekę.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Teraz przejdźmy przez proces dodawania znaku wodnego do dokumentu za pomocą GroupDocs.Viewer dla .NET. Wykonaj poniższe kroki, aby płynnie zintegrować funkcjonalność znaku wodnego z aplikacją.
## Krok 1: Ustaw katalog wyjściowy
```csharp
string outputDirectory = "Your Document Directory";
```
Określ katalog, w którym mają zostać zapisane pliki wyjściowe po zastosowaniu znaku wodnego.
## Krok 2: Zdefiniuj format ścieżki pliku stronicowania
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ustaw format ścieżek plików renderowanych stron. W tym przykładzie zostaną wygenerowane pliki HTML z numerami stron.
## Krok 3: Utwórz obiekt Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Kontynuacja kodu znajduje się w następnym kroku...
}
```
Utwórz instancję klasy Viewer, przekazując ścieżkę do pliku dokumentu jako parametr. W tym przykładzie używamy przykładowego pliku DOCX.
## Krok 4: Skonfiguruj opcje widoku HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Skonfiguruj opcje widoku HTML, obejmujące również tekst znaku wodnego, który chcesz dodać do dokumentu.
## Krok 5: Wyświetl dokument ze znakiem wodnym
```csharp
viewer.View(options);
```
Wywołaj metodę View obiektu Viewer, przekazując skonfigurowane opcje. Spowoduje to wyrenderowanie dokumentu ze wskazanym znakiem wodnym.
## Krok 6: Wyświetl ścieżkę katalogu wyjściowego
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Poinformuj użytkownika o pomyślnym wyrenderowaniu dokumentu i wskaż katalog, w którym zapisywane są pliki wyjściowe.

## Wniosek
GroupDocs.Viewer dla .NET zapewnia wygodny sposób dodawania znaków wodnych do dokumentów programowo. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz bezproblemowo zintegrować funkcjonalność znaków wodnych z aplikacjami .NET, zwiększając bezpieczeństwo dokumentów i branding.
## Najczęściej zadawane pytania
### Czy mogę dostosować wygląd znaku wodnego?
Tak, możesz dostosować różne właściwości znaku wodnego, takie jak tekst, czcionkę, kolor, rozmiar i położenie.
### Czy GroupDocs.Viewer obsługuje przeglądanie dokumentów ze źródeł zdalnych?
Tak, GroupDocs.Viewer obsługuje przeglądanie dokumentów z pamięci lokalnej, jak i zdalnych adresów URL.
### Czy jest dostępna wersja próbna GroupDocs.Viewer dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną ze strony [Tutaj](https://releases.groupdocs.com/).
### Czy mogę dodać znaki wodne do wielu stron dokumentu?
Oczywiście, GroupDocs.Viewer pozwala na dodawanie znaków wodnych na poszczególnych stronach lub na wszystkich stronach dokumentu.
### Jak mogę uzyskać wsparcie i pomoc, jeśli napotkam jakiekolwiek problemy?
Pomocy i wsparcia możesz szukać na forach społeczności GroupDocs [Tutaj](https://forum.groupdocs.com/c/viewer/9).