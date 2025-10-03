---
"description": "Odkryj magię GroupDocs.Viewer dla .NET – bezproblemowo integruj przeglądanie dokumentów ze swoimi aplikacjami. Wypróbuj bezpłatną wersję próbną już teraz!"
"linktitle": "Pobierz nazwy arkuszy roboczych"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Pobierz nazwy arkuszy roboczych"
"url": "/pl/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# Pobierz nazwy arkuszy roboczych

## Wstęp
Witamy w fascynującym świecie GroupDocs.Viewer dla .NET! Jeśli jesteś programistą lub entuzjastą, który chce odkrywać potężne możliwości przeglądania dokumentów w swoich aplikacjach .NET, czeka cię gratka. W tym kompleksowym przewodniku zagłębimy się w zawiłości pobierania nazw arkuszy kalkulacyjnych za pomocą GroupDocs.Viewer. Więc zapnij pasy i wyruszmy w tę ekscytującą podróż!
## Wymagania wstępne
Zanim zagłębimy się w magię kodowania, upewnijmy się, że wszystko masz skonfigurowane:
1. Zainstaluj GroupDocs.Viewer dla .NET: Przejdź do [link do pobrania](https://releases.groupdocs.com/viewer/net/) aby pobrać najnowszą wersję GroupDocs.Viewer dla .NET. Postępuj zgodnie z instrukcjami instalacji, aby bezproblemowo zintegrować ją ze środowiskiem programistycznym.
2. Przygotuj dokument: Upewnij się, że w wyznaczonym katalogu dokumentów masz dokument docelowy, powiedzmy plik programu Excel o nazwie „file.xlsx”.
## Importuj przestrzenie nazw
Teraz, gdy masz już wszystkie wymagania wstępne, zacznijmy od zaimportowania niezbędnych przestrzeni nazw. Dzięki temu Twoja aplikacja rozpoznaje i może wykorzystywać funkcjonalności udostępniane przez GroupDocs.Viewer dla .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Konfigurowanie katalogu dokumentów
```csharp
string outputDirectory = "Your Document Directory";
```
Zastąp „Katalog dokumentów” ścieżką do katalogu, w którym znajduje się dokument docelowy.
## 2. Inicjalizacja przeglądarki
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
W tym kroku utworzymy instancję klasy Viewer, podając ścieżkę do pliku Excel.
## 3. Konfigurowanie opcji wyświetlania informacji
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Tutaj konfigurujemy ViewInfoOptions, aby generować widoki HTML i ustawić dodatkowe opcje renderowania arkusza kalkulacyjnego.
## 4. Pobieranie informacji o widoku
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Użyj instancji Viewer do pobrania informacji o widoku na podstawie skonfigurowanych opcji.
## 5. Wyświetlanie nazw arkuszy kalkulacyjnych
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Przejrzyj pobrane strony i wydrukuj nazwę każdego arkusza na konsoli.
## Wniosek
Gratulacje! Udało Ci się pomyślnie przejść przez proces pobierania nazw arkuszy roboczych przy użyciu GroupDocs.Viewer dla .NET. Otwiera to niezliczone możliwości udoskonalenia funkcjonalności przeglądania dokumentów w Twoich aplikacjach.
## Często zadawane pytania
### Czy mogę używać GroupDocs.Viewer dla .NET z innymi formatami dokumentów?
Oczywiście! GroupDocs.Viewer obsługuje szeroki zakres formatów dokumentów, w tym PDF, Microsoft Office i inne.
### Czy jest dostępna bezpłatna wersja próbna?
Tak, możesz zapoznać się z GroupDocs.Viewer dla .NET za pomocą naszego [bezpłatny okres próbny](https://releases.groupdocs.com/).
### Gdzie mogę znaleźć dodatkową pomoc?
Udaj się do [Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) celu uzyskania wsparcia społeczności i dyskusji.
### Czy mogę uzyskać tymczasową licencję?
Oczywiście! Odwiedź [ten link](https://purchase.groupdocs.com/temporary-license/) aby otrzymać tymczasowe prawo jazdy.
### Czy są dostępne szczegółowe źródła dokumentacji?
Oczywiście! Sprawdź [oficjalna dokumentacja](https://tutorials.groupdocs.com/viewer/net/) aby uzyskać szczegółowe informacje i przewodniki.