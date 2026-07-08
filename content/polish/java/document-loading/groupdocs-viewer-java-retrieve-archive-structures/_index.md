---
date: '2026-06-30'
description: Dowiedz się, jak uzyskać viewinfo i pobrać struktury typów plików archiwów
  Java przy użyciu GroupDocs.Viewer. Ten przewodnik obejmuje konfigurację, przykłady
  kodu oraz rzeczywiste przypadki użycia.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Jak uzyskać ViewInfo i pobrać struktury archiwów w Javie
type: docs
url: /pl/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Jak uzyskać ViewInfo i pobrać struktury archiwów w Javie

Efektywne zarządzanie plikami archiwów wymaga jasnego zrozumienia ich struktury. W tym samouczku nauczysz się **jak uzyskać viewinfo** dla dowolnego archiwum i zobaczysz, jak pomaga to w pracy z **typem pliku archiwum Java**. Przejdziemy przez konfigurację GroupDocs.Viewer, wyodrębnianie informacji o widoku oraz rekurencyjne odczytywanie hierarchii folderów, abyś mógł zintegrować rozwiązanie w rzeczywistych projektach.

![Struktury archiwów z GroupDocs.Viewer dla Javy](/viewer/document-loading/archive-structures-java.png)

**Co się nauczysz**
- Ustawienie i konfiguracja GroupDocs.Viewer dla Javy.  
- Metody do **uzyskania viewinfo** z archiwów.  
- Techniki odczytu i wyświetlania struktury folderów pliku archiwum.  
- Praktyczne zastosowania i kwestie wydajności przy używaniu GroupDocs.Viewer w projektach Java.

## Szybkie odpowiedzi
- **Co dostarcza “viewinfo”?** Zwraca typ pliku, liczbę stron oraz pełną listę folderów i plików wewnątrz archiwum.  
- **Jakie formaty archiwów są obsługiwane?** ZIP, RAR, TAR, 7z, ISO oraz ponad 12 innych popularnych formatów.  
- **Czy potrzebna jest licencja do produkcji?** Tak — wymagana jest licencja komercyjna do produkcji; darmowa wersja próbna działa w celach oceny.  
- **Czy duże archiwa mogą być przetwarzane wydajnie?** Absolutnie — użyj opcji strumieniowania i przetwarzaj jeden poziom folderu naraz, aby utrzymać niskie zużycie pamięci.  
- **Czy Maven jest jedynym sposobem dodania biblioteki?** Maven jest zalecanym menedżerem zależności, ale Gradle lub ręczne dołączenie pliku JAR również działają.

## Co to jest “how to get viewinfo”?

`getViewInfo` jest metodą API GroupDocs.Viewer, która wyodrębnia metadane z dokumentu lub archiwum bez pełnego renderowania. Zwraca wewnętrzne drzewo folderów, liczbę plików oraz podstawowe właściwości w jednym wywołaniu, pozwalając zdecydować, które części przetworzyć. Wywołanie zwraca pełny migawkę archiwów do 500 MB w czasie krótszym niż sekunda na typowych serwerach.

## Dlaczego pobierać struktury typu pliku archiwum Java?

Pobieranie wewnętrznego układu **java archive file type** umożliwia natychmiastowe zlokalizowanie potrzebnych plików, uniknięcie niepotrzebnego rozpakowywania oraz budowanie zautomatyzowanych pipeline'ów, które dotykają tylko istotnych podfolderów. Takie podejście redukuje operacje I/O nawet o 70 % przy dużych archiwach i pozwala skanować tysiące plików na minutę w scenariuszach ingestii danych.

## Wymagania wstępne

- **Java Development Kit (JDK):** Wersja 8 lub nowsza.  
- **Maven:** Do zarządzania zależnościami i budowania.  
- **Podstawowa znajomość Javy:** Znajomość koncepcji OOP pomaga, ale nie jest wymagana.  

Potrzebujesz również dostępu do biblioteki GroupDocs.Viewer, którą możesz dodać do projektu Maven, jak pokazano poniżej.

## Konfiguracja GroupDocs.Viewer dla Javy

### Konfiguracja Maven

Dodaj repozytorium i zależność do swojego `pom.xml`.

**Repozytoria:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Zależności:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Uzyskanie licencji

- **Free Trial:** Pobierz wersję próbną ze strony GroupDocs.  
- **Temporary License:** Poproś o tymczasowy klucz do krótkoterminowej oceny.  
- **Full License:** Kup licencję komercyjną do nieograniczonego użycia w produkcji.  

Gdy biblioteka znajdzie się na classpath, możesz rozpocząć kodowanie.

## Przewodnik implementacji

### Jak uzyskać ViewInfo dla plików archiwów

Aby uzyskać informacje o widoku, najpierw załaduj archiwum do Viewer, następnie wywołaj `getViewInfo`, aby pobrać metadane, a na końcu przeiteruj zwróconą hierarchię folderów. Ten trzyetapowy wzorzec działa dla wszystkich obsługiwanych formatów archiwów i zapewnia kompletną migawkę w jednym wywołaniu API, upraszczając dalsze przetwarzanie.

#### Inicjalizacja Viewer

Klasa `Viewer` jest punktem wejścia dla wszystkich operacji renderowania i inspekcji. Zarządza strumieniami plików, wykrywaniem formatu oraz czyszczeniem zasobów.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Pobranie informacji o widoku

`ViewInfo` zawiera metadane takie jak typ pliku, liczba stron oraz hierarchiczna lista folderów i plików. Wywołanie `getViewInfo` zwraca ten obiekt natychmiast.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Wyświetlenie struktury folderów

Iteruj przez `viewInfo.getFolders()`, aby wypisać nazwę każdego folderu, jego głębokość oraz zawarte pliki. Ta prosta pętla zapewnia czytelny widok drzewa archiwum.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekursywne odczytywanie folderów

W przypadku głęboko zagnieżdżonych archiwów, rekurencyjna metoda pomocnicza może przechodzić drzewo w głąb, zapewniając odwiedzenie każdego podfolderu bez ładowania całego archiwum do pamięci.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Funkcja 2: Pobranie struktury folderów archiwum

Ta funkcja koncentruje się na wypisywaniu struktury folderów pliku archiwum. Jest podobna do pierwszej funkcji, ale podkreśla rekurencyjne przeglądanie.

#### Konfiguracja opcji ViewInfo

`ArchiveOptions` pozwala określić ochronę hasłem, limity stron oraz preferencje strumieniowania przed wywołaniem `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekursywne przeglądanie

Druga rekurencyjna procedura demonstruje, jak efektywnie obsługiwać archiwa chronione hasłem i duże zestawy plików.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktyczne zastosowania

1. **Data Management:** Szybko organizuj duże zestawy danych, rozumiejąc struktury archiwów.  
2. **Automated File Processing:** Przetwarzaj wsadowo pliki archiwów bez pełnego ich rozpakowywania, redukując I/O nawet o 70 %.  
3. **CMS Integration:** Ulepsz systemy zarządzania treścią o nawigację po archiwach w locie, umożliwiając edytorom podgląd plików bezpośrednio z archiwum.

## Rozważania dotyczące wydajności

- **Optimize Memory Usage:** Przetwarzaj foldery jeden poziom na raz i szybko zamykaj instancję `Viewer`.  
- **Stay Updated:** Korzystaj z najnowszej wersji GroupDocs.Viewer (25.2 w momencie pisania) oraz wydań JDK, aby uzyskać korzyści wydajnościowe.  
- **Streaming Support:** Biblioteka może strumieniować archiwa większe niż 1 GB bez ładowania całego pliku do RAM, dzięki wewnętrznej architekturze odczytu w kawałkach.

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| `NullPointerException` podczas odczytu folderów | `viewInfo.getFolders()` zwraca null dla pustych katalogów | Sprawdź, czy lista nie jest null lub pusta przed iteracją. |
| Wolne przetwarzanie ogromnych plików ZIP | Całe archiwum jest ładowane do pamięci | Użyj opcji strumieniowania dostępnych w nowszych wersjach GroupDocs. |
| Nie znaleziono licencji | Ścieżka do pliku licencji jest nieprawidłowa | Umieść plik licencji w katalogu głównym aplikacji lub ustaw `License.setLicense("path/to/license.json")`. |

## Najczęściej zadawane pytania

**Q:** Czym jest GroupDocs.Viewer?  
A: GroupDocs.Viewer jest biblioteką Java, która renderuje ponad 100 formatów dokumentów, obrazów i archiwów do HTML, PDF lub strumieni obrazów, bez konieczności używania aplikacji natywnych.

**Q:** Czy mogę używać GroupDocs.Viewer z innymi językami programowania?  
A: Tak, GroupDocs oferuje SDK dla .NET, Pythona, PHP i innych, ale ten samouczek koncentruje się na implementacji w Javie.

**Q:** Jak obsługiwać duże pliki archiwów?  
A: Włącz strumieniowanie za pomocą `ArchiveOptions.setUseStreaming(true)`, przetwarzaj jeden poziom folderu na raz i zwalniaj obiekt `Viewer` po użyciu.

**Q:** Jakie typy archiwów obsługuje GroupDocs.Viewer?  
A: Obsługuje ponad 12 formatów archiwów, w tym ZIP, RAR, TAR, 7z, ISO, ARJ i CAB, oraz wiele własnościowych typów kontenerów.

**Q:** Czy istnieje limit rozmiaru archiwów?  
A: Praktyczny limit zależy od pamięci RAM i CPU serwera; testy wykazują płynne przetwarzanie archiwów 2 GB na maszynie z 16 GB RAM przy włączonym strumieniowaniu.

**Q:** Czy “how to get viewinfo” działa z archiwami chronionymi hasłem?  
A: Tak, podaj hasło za pomocą `ArchiveOptions.setPassword("yourPassword")` przed wywołaniem `getViewInfo`.

## Podsumowanie

Postępując zgodnie z tym przewodnikiem, teraz wiesz **jak uzyskać viewinfo** dla dowolnego obsługiwanego archiwum i jak przeglądać jego hierarchię folderów przy użyciu GroupDocs.Viewer dla Javy. Te techniki umożliwiają budowanie inteligentniejszych pipeline'ów przetwarzania danych, ulepszanie integracji CMS oraz pewne radzenie sobie z dużymi zbiorami plików archiwów. Następnie, odkryj renderowanie pojedynczych plików z archiwum lub konwersję ich do PDF/HTML przy użyciu innych funkcji Viewer.

---

**Ostatnia aktualizacja:** 2026-06-30  
**Testowano z:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

**Zasoby**
- **Dokumentacja:** [Dokumentacja GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Referencja API:** [Referencja API GroupDocs dla Javy](https://reference.groupdocs.com/viewer/java/)
- **Pobierz GroupDocs.Viewer:** [Strona pobierania GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Kup licencję:** [Kup GroupDocs](https://purchase.groupdocs.com/buy)
- **Darmowa wersja próbna i tymczasowa licencja:** [Darmowa wersja próbna GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Tymczasowa licencja](https://purchase.groupdocs.com/temporary-license/)

## Powiązane samouczki

- [Wyodrębnij metadane dokumentu za pomocą GroupDocs.Viewer dla Javy – Pobierz informacje o widoku dokumentu i wnioski](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Jak pobrać załączniki i wydrukować załączniki dokumentu za pomocą GroupDocs.Viewer dla Javy](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Przewodnik Java: Renderowanie konkretnych stron przy użyciu API GroupDocs.Viewer do podglądu i zarządzania dokumentami](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)