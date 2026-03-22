---
date: '2026-03-22'
description: Dowiedz się, jak generować HTML z pliku PDF i wyłączyć grupowanie znaków
  przy użyciu GroupDocs Viewer dla Javy, aby uzyskać precyzyjną reprezentację tekstu.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Generowanie HTML z PDF i wyłączenie grupowania – GroupDocs Java
type: docs
url: /pl/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Generowanie HTML z PDF i wyłączenie grupowania w GroupDocs Viewer dla Javy

W wielu projektach trzeba **generować HTML z PDF**, zachowując każdy glif dokładnie tam, gdzie powinien. Dotyczy to szczególnie złożonych skryptów, starożytnych języków lub dokumentów prawnych, gdzie pojedynczy nieprawidłowo umieszczony znak może zmienić znaczenie. W tym samouczku przeprowadzimy Cię przez cały proces renderowania PDF‑ów do HTML przy użyciu GroupDocs Viewer dla Javy i pokażemy **jak wyłączyć grupowanie**, aby każdy znak był traktowany jako niezależny element.

![Precyzyjne techniki renderowania z GroupDocs.Viewer dla Javy](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Szybkie odpowiedzi
- **Co robi „wyłączenie grupowania”?** Wymusza, aby renderer traktował każdy znak jako niezależny element, zachowując dokładny układ.  
- **Która opcja API kontroluje to?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Czy potrzebna jest licencja?** Wersja próbna działa do testów, ale pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę jednocześnie generować HTML z PDF?** Tak — użyj `HtmlViewOptions`, aby utworzyć wyjście HTML przy wyłączonym grupowaniu.  
- **Czy ta funkcja jest ograniczona do PDF‑ów?** Przede wszystkim dotyczy PDF‑ów, ale przeglądarka obsługuje wiele innych formatów.

## Wprowadzenie

Podczas pracy z dokumentami PDF precyzja renderowania jest kluczowa — szczególnie przy obsłudze złożonych struktur tekstowych, takich jak hieroglify czy języki wymagające dokładnej reprezentacji znaków. Funkcja „Grupowanie znaków” często powoduje problemy, grupując znaki nieprawidłowo, co prowadzi do błędnej interpretacji treści dokumentu. Może to być szczególnie problematyczne dla użytkowników potrzebujących dokładnej reprodukcji układu tekstu w swoich dokumentach.

### Wymagania wstępne
- **Biblioteki i zależności**: Potrzebujesz GroupDocs.Viewer dla Javy w wersji 25.2 lub nowszej.  
- **Konfiguracja środowiska**: Upewnij się, że masz zainstalowany Java Development Kit (JDK) oraz że Twoje IDE jest skonfigurowane do pracy z projektami Maven.  
- **Wymagania wiedzy**: Podstawowa znajomość programowania w Javie, szczególnie obsługi ścieżek plików i używania zewnętrznych bibliotek.

## Jak generować HTML z PDF przy użyciu GroupDocs Viewer

Generowanie HTML z PDF to dwustopniowy proces: skonfigurowanie przeglądarki, a następnie renderowanie dokumentu. Kluczowe jest wyłączenie grupowania znaków przed renderowaniem, aby wyjście HTML odzwierciedlało oryginalny układ PDF znak po znaku.

### Konfiguracja GroupDocs.Viewer dla Javy

#### Instalacja za pomocą Maven

Najpierw zintegrować niezbędną bibliotekę z projektem. Dodaj następującą konfigurację do swojego pliku `pom.xml`:

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

#### Uzyskanie licencji

Aby w pełni wykorzystać GroupDocs.Viewer, rozważ uzyskanie licencji:
- **Bezpłatna wersja próbna**: Rozpocznij od wersji próbnej, aby przetestować funkcje.  
- **Licencja tymczasowa**: Złóż wniosek o licencję tymczasową, jeśli potrzebujesz więcej czasu.  
- **Zakup**: Dla długoterminowych projektów zaleca się zakup licencji.

#### Podstawowa inicjalizacja i konfiguracja

Poniżej znajduje się gotowy do uruchomienia fragment kodu, który pokazuje pełny przepływ pracy — od ustawienia folderu wyjściowego po renderowanie PDF jako HTML przy wyłączonym grupowaniu znaków:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Przewodnik implementacji

#### Funkcja: Wyłączenie grupowania znaków

Poniżej rozbijamy każdy wiersz przykładu, abyś mógł zrozumieć **dlaczego** to robimy i **jak** przyczynia się to do generowania HTML z PDF bez niepożądanego łączenia znaków.

##### Krok 1: Zdefiniuj katalog wyjściowy  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Dlaczego?** Zapewnia to, że wygenerowane pliki HTML są przechowywane w dedykowanym folderze, co ułatwia ich późniejsze odnalezienie i zarządzanie.

##### Krok 2: Skonfiguruj format ścieżki pliku  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Dlaczego?** Użycie symbolu zastępczego (`{0}`) pozwala przeglądarce utworzyć osobny plik HTML dla każdej strony PDF, utrzymując porządek w wynikach.

##### Krok 3: Zainicjuj opcje widoku HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Dlaczego?** Osadzone zasoby łączą obrazy, czcionki i CSS bezpośrednio z każdą stroną HTML, co jest idealne dla przeglądarek internetowych lub platform e‑learningowych.

##### Krok 4: Wyłącz grupowanie znaków  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Dlaczego?** To kluczowa linia, która instruuje silnik renderujący, aby **nie** łączył sąsiadujących znaków, zapewniając, że wygenerowany HTML odzwierciedla dokładne rozmieszczenie glifów z oryginalnego PDF.

##### Krok 5: Renderuj dokument  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Dlaczego?** Umieszczenie `Viewer` w bloku try‑with‑resources zapewnia automatyczne zwolnienie wszystkich zasobów natywnych, zapobiegając wyciekom pamięci w długotrwale działających aplikacjach.

### Generowanie HTML w Javie z PDF bez grupowania

Klasa `HtmlViewOptions` umożliwia **generowanie HTML z PDF**, zachowując każdy znak oddzielnie. Jest to szczególnie przydatne, gdy trzeba osadzić wyrenderowane strony w portalu internetowym lub platformie e‑learningowej, gdzie dokładne rozmieszczenie glifów ma znaczenie.

### Typowe problemy i rozwiązania

- **FileNotFoundException** – Sprawdź dokładnie ścieżkę przekazywaną do `new Viewer(...)`. Użyj ścieżek bezwzględnych lub `Path.of(...)` dla jasności.  
- **Uprawnienia zapisu** – Upewnij się, że katalog wyjściowy jest zapisywalny przez proces Java; w systemie Linux może być konieczne dostosowanie uprawnień folderu (`chmod 775`).  
- **Niezgodność wersji** – Opcja `setDisableCharsGrouping` jest dostępna od wersji 25.2. Zweryfikuj, czy Twój `pom.xml` odzwierciedla właściwą wersję.

### Praktyczne zastosowania

1. **Zachowanie języka** – Idealne do renderowania dokumentów w chińskim, japońskim, arabskim lub starożytnych skryptach, gdzie odstępy między znakami niosą znaczenie.  
2. **Dokumenty prawne i finansowe** – Gwarantuje dokładną replikację tekstu w dokumentach wymagających wysokiej zgodności.  
3. **Zasoby edukacyjne** – Idealne dla podręczników zawierających złożone diagramy, adnotacje lub treści wielojęzyczne.

### Względy wydajnościowe

- **Optymalizacja zużycia zasobów** – Duże pliki PDF mogą zużywać znaczną ilość pamięci. Rozważ przetwarzanie stron w partiach i szybkie zwalnianie instancji `Viewer`.  
- **Zarządzanie pamięcią w Javie** – Dostosuj rozmiar sterty JVM (`-Xmx2g` lub większy), jeśli planujesz przetwarzać PDF‑y o setkach stron.  
- **Równoległe renderowanie** – Przy masowych konwersjach uruchom osobne wątki, każdy z własną instancją `Viewer`, aby wykorzystać wielordzeniowe procesory.

## Najczęściej zadawane pytania

**Q:** *Dlaczego miałbym w ogóle wyłączać grupowanie znaków?*  
**A:** Wyłączenie grupowania zapobiega łączeniu znaków, które należą do odrębnych glifów, co jest niezbędne w skryptach, w których odstępy i kolejność niosą znaczenie.

**Q:** *Czy ustawienie `setDisableCharsGrouping` dotyczy wyłącznie wyjścia HTML?*  
**A:** Nie, wpływa na podstawowy silnik renderujący PDF, więc każdy format wyjściowy (HTML, PNG, JPEG itp.) odzwierciedli tę zmianę.

**Q:** *Czy mogę połączyć to ustawienie z własnymi czcionkami?*  
**A:** Tak — załaduj własne czcionki przed inicjalizacją `Viewer`, a zasada grupowania nadal będzie obowiązywać.

**Q:** *Czy wyłączenie grupowania wpływa na wydajność?*  
**A:** Nieznacznie, ponieważ silnik przetwarza każdy znak osobno, ale wpływ jest minimalny dla większości dokumentów.

**Q:** *Czy istnieje możliwość przełączania grupowania na poziomie poszczególnych stron?*  
**A:** Obecnie opcja jest globalna dla jednej instancji `PdfOptions`; aby uzyskać mieszane zachowanie, trzeba używać oddzielnych instancji `Viewer` dla różnych stron.

## Zasoby

- [Dokumentacja GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Referencja API](https://reference.groupdocs.com/viewer/java/)
- [Pobierz GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Kup licencję](https://purchase.groupdocs.com/buy)
- [Wersja próbna](https://releases.groupdocs.com/viewer/java/)
- [Wniosek o licencję tymczasową](https://purchase.groupdocs.com/temporary-license/)
- [Forum wsparcia GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Ostatnia aktualizacja:** 2026-03-22  
**Testowano z:** GroupDocs.Viewer 25.2 dla Javy  
**Autor:** GroupDocs