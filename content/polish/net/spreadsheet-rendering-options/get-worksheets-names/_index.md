---
title: Pobierz nazwy arkuszy
linktitle: Pobierz nazwy arkuszy
second_title: GroupDocs.Viewer API .NET
description: Odkryj magię GroupDocs.Viewer dla .NET – bezproblemowo zintegruj przeglądanie dokumentów ze swoimi aplikacjami. Wypróbuj bezpłatną wersję próbną już teraz!
weight: 11
url: /pl/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Wstęp
Witamy w fascynującym świecie GroupDocs.Viewer dla .NET! Jeśli jesteś programistą lub entuzjastą chcącym poznać zaawansowane możliwości przeglądania dokumentów w aplikacjach .NET, czeka Cię gratka. W tym obszernym przewodniku zagłębimy się w zawiłości pobierania nazw arkuszy za pomocą GroupDocs.Viewer. Zatem zapnij pasy i wyrusz w tę ekscytującą podróż!
## Warunki wstępne
Zanim zagłębimy się w magię kodowania, upewnijmy się, że wszystko mamy skonfigurowane:
1.  Zainstaluj GroupDocs.Viewer dla .NET: Przejdź do[link do pobrania](https://releases.groupdocs.com/viewer/net/)aby pobrać najnowszą wersję GroupDocs.Viewer dla .NET. Postępuj zgodnie z instrukcjami instalacji, aby bezproblemowo zintegrować go ze środowiskiem programistycznym.
2. Przygotuj dokument: Upewnij się, że masz dokument docelowy, powiedzmy plik Excel o nazwie „plik.xlsx”, w wyznaczonym katalogu dokumentów.
## Importuj przestrzenie nazw
Teraz, gdy masz już wymagania wstępne, zacznijmy od zaimportowania niezbędnych przestrzeni nazw. Dzięki temu Twoja aplikacja rozpoznaje i będzie mogła korzystać z funkcjonalności udostępnianych przez GroupDocs.Viewer dla .NET.
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
Zastąp „Twój katalog dokumentów” ścieżką do katalogu, w którym znajduje się dokument docelowy.
## 2. Inicjowanie przeglądarki
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
W tym kroku tworzymy instancję klasy Viewer, podając ścieżkę do pliku Excel.
## 3. Konfigurowanie opcji wyświetlania informacji
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Tutaj konfigurujemy ViewInfoOptions do generowania widoków HTML i ustawiamy dodatkowe opcje renderowania arkusza kalkulacyjnego.
## 4. Pobieranie informacji o widoku
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Użyj instancji Viewer, aby pobrać informacje o widoku na podstawie skonfigurowanych opcji.
## 5. Wyświetlanie nazw arkuszy
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Przejdź w pętli pobrane strony i wydrukuj nazwę każdego arkusza na konsoli.
## Wniosek
Gratulacje! Pomyślnie przeszedłeś przez proces pobierania nazw arkuszy przy użyciu GroupDocs.Viewer dla .NET. Otwiera to niezliczone możliwości ulepszania funkcjonalności przeglądania dokumentów w aplikacjach.
## Często zadawane pytania
### Czy mogę używać programu GroupDocs.Viewer for .NET z dokumentami w innych formatach?
Absolutnie! GroupDocs.Viewer obsługuje szeroką gamę formatów dokumentów, w tym PDF, Microsoft Office i inne.
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz eksplorować GroupDocs.Viewer dla .NET za pomocą naszego narzędzia[bezpłatna wersja próbna](https://releases.groupdocs.com/).
### Gdzie mogę znaleźć dodatkowe wsparcie?
 Udaj się do[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) za wsparcie społeczności i dyskusje.
### Czy mogę uzyskać licencję tymczasową?
 Z pewnością! Odwiedzać[ten link](https://purchase.groupdocs.com/temporary-license/) aby otrzymać tymczasową licencję.
### Czy dostępne są szczegółowe źródła dokumentacji?
 Absolutnie! Sprawdź[oficjalna dokumentacja](https://tutorials.groupdocs.com/viewer/net/) aby uzyskać szczegółowe informacje i przewodniki.