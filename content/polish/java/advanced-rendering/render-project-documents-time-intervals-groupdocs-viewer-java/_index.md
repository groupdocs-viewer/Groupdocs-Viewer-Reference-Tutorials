---
date: '2026-03-29'
description: Dowiedz się, jak stworzyć widok HTML plików MPP przy użyciu GroupDocs
  Viewer w Javie, renderując dokumenty projektowe w interwałach czasowych krok po
  kroku.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Utwórz widok HTML pliku MPP przy użyciu GroupDocs Viewer (Java)
type: docs
url: /pl/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Jak używać GroupDocs Viewer do renderowania dokumentów projektów w przedziałach czasowych w Javie

W tym samouczku dowiesz się, jak **create html view mpp** z GroupDocs Viewer for Java, umożliwiając renderowanie tylko części pliku Microsoft Project, które mieszczą się w określonym przedziale czasowym. Przejdziemy przez konfigurację Maven, konfigurację kodu oraz scenariusze rzeczywiste, abyś mógł osadzić precyzyjne widoki osi czasu bezpośrednio w swoich aplikacjach.

![Renderowanie dokumentów projektów w przedziałach czasowych za pomocą GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Szybkie odpowiedzi
- **Co robi ta funkcja?** Renderuje tylko część pliku Microsoft Project, która mieści się pomiędzy datą początkową a końcową.  
- **Jaki format wyjściowy jest używany?** HTML z osadzonymi zasobami, idealny do integracji webowej.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w celach oceny; pełna licencja jest wymagana w produkcji.  
- **Czy mogę zmienić zakres dat w czasie działania?** Tak — dostosuj wartości `setStartDate` i `setEndDate` w opcjach renderowania.  
- **Czy jest to obsługiwane we wszystkich wersjach Java?** Działa z Java 8+ pod warunkiem użycia GroupDocs.Viewer 25.2 lub nowszej.

## Jak utworzyć html view mpp dla dokumentów projektów
GroupDocs Viewer może konwertować pliki Microsoft Project (`.mpp`, `.mpt`) na strony HTML. Konfigurując daty początkową i końcową w opcjach renderowania, ograniczasz wynik do interesującego Cię fragmentu czasowego, co zmniejsza rozmiar pliku i przyspiesza ładowanie stron.

## Co oznacza „How to Use GroupDocs” w tym kontekście?
GroupDocs Viewer jest biblioteką Java, która konwertuje ponad 100 formatów plików na reprezentacje przyjazne dla sieci. Gdy **how to use GroupDocs** dla plików projektowych, zyskujesz możliwość wyodrębniania, wizualizacji i udostępniania danych harmonogramu bez konieczności posiadania Microsoft Project po stronie klienta.

## Dlaczego renderować dokumenty projektów w przedziałach czasowych?
- **Analiza ukierunkowana:** Pokaż tylko fazę, która Cię interesuje (np. Q3 2024).  
- **Wydajność:** Mniejszy wynik HTML oznacza szybsze ładowanie stron.  
- **Integracja:** Osadź widoki osi czasu w pulpitach, portalach raportowych lub własnych narzędziach PM.  

## Wymagania wstępne

- **GroupDocs.Viewer for Java** wersja 25.2 lub wyższa.  
- Java Development Kit (JDK) 8 lub nowszy.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Podstawowa znajomość Maven.  

## Konfiguracja GroupDocs.Viewer dla Java

### Zależność Maven

Dodaj repozytorium i zależność do swojego `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Kroki uzyskania licencji

1. **Free Trial** – Pobierz wersję próbną ze [strony pobierania GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Uzyskaj tymczasową licencję do rozszerzonego testowania poprzez [ten link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Aby uzyskać nieograniczone użycie w produkcji, kup licencję na [stronie zakupu GroupDocs](https://purchase.groupdocs.com/buy).

### Podstawowa inicjalizacja Viewer

Poniższy fragment kodu pokazuje, jak utworzyć instancję `Viewer`, która wskazuje na plik Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Przewodnik krok po kroku

### 1. Zdefiniuj katalog wyjściowy

Utwórz folder, w którym zostaną zapisane wygenerowane strony HTML:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Dlaczego?* Utrzymywanie renderowanych plików w porządku ułatwia ich serwowanie z serwera WWW lub osadzanie w interfejsie użytkownika.

### 2. Zainicjalizuj Viewer z plikiem projektu

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Dlaczego?* Załadowanie dokumentu przygotowuje wewnętrzny parser i udostępnia metadane specyficzne dla projektu.

### 3. Pobierz informacje o widoku dla plików projektowych

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Dlaczego?* `ProjectManagementViewInfo` dostarcza daty rozpoczęcia i zakończenia harmonogramu, które później użyjesz do ograniczenia zakresu renderowania.

### 4. Skonfiguruj opcje renderowania HTML (Generowanie HTML z projektu)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Dlaczego?* Ustawienie `StartDate` i `EndDate` informuje GroupDocs, aby **generate html view mpp** dane tylko w tym przedziale.

### 5. Wykonaj proces renderowania

```java
viewer.view(viewOptions);
```

*Dlaczego?* To wywołanie generuje serię samodzielnych stron HTML, które przedstawiają wybrany fragment czasowy harmonogramu projektu.

## Typowe pułapki i rozwiązywanie problemów

- **Nieprawidłowe ścieżki plików** – Sprawdź, czy zarówno plik źródłowy `.mpp`, jak i katalog wyjściowy istnieją.  
- **Nieobsługiwany typ pliku** – Upewnij się, że dokument jest w obsługiwanym formacie Project (np. `.mpp`, `.mpt`).  
- **Błędy licencji** – Licencja próbna może nakładać limity renderowania; przejdź na pełną licencję, aby uzyskać nieograniczone użycie.  

## Praktyczne zastosowania

1. **Analiza osi czasu projektu** – Pokaż interesariuszom tylko bieżącą fazę.  
2. **Automatyczne raportowanie** – Generuj raporty HTML ograniczone w czasie dla cotygodniowych aktualizacji statusu.  
3. **Integracja z pulpitami** – Osadź renderowane strony w narzędziach BI lub własnych portalach.  
4. **Archiwizacja** – Przechowuj przyjazny dla sieci migawkę harmonogramu projektu na przyszłość.  

## Wskazówki dotyczące wydajności

- Użyj opcji *embedded resources*, aby każda strona HTML była samodzielna, co zmniejsza liczbę żądań HTTP.  
- W przypadku bardzo dużych projektów rozważ renderowanie w mniejszych fragmentach dat, aby utrzymać niskie zużycie pamięci.  
- Usuń tymczasowe pliki po ich udostępnieniu, aby uniknąć nadmiernego zużycia dysku.  

## Podsumowanie

Teraz wiesz, **how to use GroupDocs** Viewer do renderowania dokumentów projektów w określonym przedziale czasowym i **generate HTML from project** dane w Javie. Ta funkcja usprawnia wizualizacje osi czasu, poprawia efektywność raportowania i płynnie integruje się z nowoczesnymi aplikacjami webowymi.

### Kolejne kroki
- Zbadaj dodatkowe funkcje Viewer, takie jak znak wodny, ochrona hasłem lub niestandardowe stylowanie CSS.  
- Połącz ten pipeline renderowania z REST API, aby udostępniać widoki osi czasu na żądanie.  

## Najczęściej zadawane pytania

**P:** Jakie formaty plików obsługuje GroupDocs.Viewer?  
**O:** GroupDocs.Viewer obsługuje szeroką gamę formatów, w tym Microsoft Project (MPP), PDF, Word, Excel, PowerPoint i wiele innych.

**P:** Jak rozpocząć korzystanie z darmowej wersji próbnej GroupDocs.Viewer?  
**O:** Możesz pobrać wersję próbną z [tutaj](https://releases.groupdocs.com/viewer/java/).

**P:** Czy mogę renderować dokumenty bez osadzania zasobów?  
**O:** Tak, możesz wybrać inną opcję widoku HTML, która odwołuje się do zewnętrznych zasobów zamiast ich osadzania.

**P:** Co zrobić, jeśli mój dokument jest zbyt duży do renderowania?  
**O:** Rozważ podzielenie dokumentu na mniejsze sekcje lub renderowanie tylko wymaganego zakresu dat, jak pokazano powyżej.

**P:** Jak radzić sobie z błędami renderowania?  
**O:** Sprawdź wszystkie ustawienia konfiguracji, upewnij się, że masz ważną licencję i zapoznaj się z dokumentacją GroupDocs w celu uzyskania szczegółowych kodów błędów.

## Zasoby
- **Dokumentacja**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencja API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Pobieranie**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Zakup**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Darmowa wersja próbna**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Tymczasowa licencja**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Wsparcie**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs