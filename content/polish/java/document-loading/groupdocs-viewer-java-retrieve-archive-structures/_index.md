---
date: '2026-02-05'
description: Dowiedz się, jak uzyskać viewinfo i pobrać struktury plików typu Java
  Archive przy użyciu GroupDocs.Viewer. Ten przewodnik obejmuje konfigurację, przykłady
  kodu oraz rzeczywiste przypadki użycia.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Jak uzyskać ViewInfo i pobrać struktury archiwum w Javie
type: docs
url: /pl/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Jak uzyskać ViewInfo i pobrać struktury archiwów w Javie

Efektywne zarządzanie plikami archiwów wymaga jasnego zrozumienia ich struktury. W tym samouczku dowiesz się **jak uzyskać viewinfo** dla dowolnego archiwum i zobaczysz, jak pomaga to w pracy z **typem pliku archiwum Java**. Przejdziemy przez konfigurację GroupDocs.Viewer, wyodrębnianie informacji o widoku oraz rekurencyjne odczytywanie hierarchii folderów, abyś mógł zintegrować rozwiązanie w rzeczywistych projektach.

![Struktury archiwów z GroupDocs.Viewer dla Javy](/viewer/document-loading/archive-structures-java.png)

**Co się nauczysz**
- Konfiguracja i ustawienie GroupDocs.Viewer dla Javy.  
- Metody **uzyskiwania viewinfo** z archiwów.  
- Techniki odczytywania i wyświetlania struktury folderów pliku archiwum.  
- Praktyczne zastosowania i kwestie wydajności przy użyciu GroupDocs.Viewer w projektach Java.

## Szybkie odpowiedzi
- **Co dostarcza „viewinfo”?** Zwraca typ pliku, liczbę stron oraz listę folderów w archiwum.  
- **Jakie archiwa są obsługiwane?** ZIP, RAR, TAR i inne popularne formaty.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do oceny; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę przetwarzać duże archiwa?** Tak – użyj strumieniowania i odpowiedniego zarządzania pamięcią, jak pokazano później.  
- **Czy Maven jest wymagany?** Maven jest zalecaną metodą zarządzania zależnością GroupDocs.Viewer.

## Co to jest „how to get viewinfo”?
`getViewInfo` to metoda w API GroupDocs.Viewer, która wyodrębnia metadane dokumentu lub archiwum bez renderowania pełnej zawartości. Dla archiwów ujawnia wewnętrzne drzewo folderów, umożliwiając decyzję, które części renderować lub przetwarzać dalej.

## Dlaczego pobierać struktury typów plików archiwów Java?
Zrozumienie wewnętrznego układu **java archive file type** (np. ZIP, RAR) pozwala Ci:
- Szybko zlokalizować potrzebne pliki bez rozpakowywania wszystkiego.  
- Budować zautomatyzowane pipeline’y przetwarzające tylko istotne podfoldery.  
- Zintegrować nawigację po archiwum z systemami zarządzania treścią lub pobierania danych.

## Wymagania wstępne

- **Java Development Kit (JDK):** Wersja 8 lub nowsza.  
- **Maven:** Do zarządzania zależnościami i budowania.  
- **Podstawowa znajomość Javy:** Znajomość koncepcji OOP pomaga, ale nie jest wymagana.

Musisz również mieć dostęp do biblioteki GroupDocs.Viewer, którą możesz dodać do swojego projektu Maven, jak pokazano poniżej.

## Konfiguracja GroupDocs.Viewer dla Javy

### Konfiguracja Maven

Dodaj repozytorium i zależność do swojego `pom.xml`.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Uzyskiwanie licencji

- **Darmowa wersja próbna:** Pobierz wersję próbną ze strony GroupDocs.  
- **Licencja tymczasowa:** Poproś o tymczasowy klucz do krótkoterminowej oceny.  
- **Pełna licencja:** Kup licencję komercyjną do nieograniczonego użycia w produkcji.

Gdy biblioteka znajdzie się na Twojej ścieżce klas, możesz rozpocząć kodowanie.

## Przewodnik implementacji

### Jak uzyskać ViewInfo dla plików archiwów

Ten rozdział pokazuje dokładne kroki wywołania `getViewInfo` i odczytania hierarchii folderów.

#### Inicjalizacja Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Pobranie informacji o widoku

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Wyświetlenie struktury folderów

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekurencyjne odczytywanie folderów

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

Ta funkcja koncentruje się na wypisaniu struktury folderów pliku archiwum. Jest podobna do pierwszej funkcji, ale podkreśla rekurencyjną eksplorację.

#### Konfiguracja opcji ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekurencyjna eksploracja

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktyczne zastosowania

1. **Zarządzanie danymi:** Szybko organizować duże zestawy danych, rozumiejąc struktury archiwów.  
2. **Automatyczne przetwarzanie plików:** Przetwarzać wsadowo pliki archiwalne bez pełnego ich rozpakowywania.  
3. **Integracja z CMS:** Ulepszyć systemy zarządzania treścią o nawigację po archiwach w locie.

## Rozważania dotyczące wydajności

- **Optymalizacja użycia pamięci:** Przetwarzaj foldery poziom po poziomie i szybko zamykaj instancję `Viewer`.  
- **Bądź na bieżąco:** Używaj najnowszej wersji GroupDocs.Viewer oraz wydań JDK dla zwiększenia wydajności.

## Częste problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| `NullPointerException` podczas odczytywania folderów | `viewInfo.getFolders()` zwraca null dla pustych katalogów | Sprawdź, czy lista nie jest null lub pusta przed iteracją. |
| Wolne przetwarzanie dużych plików ZIP | Całe archiwum jest ładowane do pamięci | Użyj opcji strumieniowania dostępnych w nowszych wersjach GroupDocs. |
| Nie znaleziono licencji | Ścieżka do pliku licencji jest nieprawidłowa | Umieść plik licencji w katalogu głównym aplikacji lub ustaw `License.setLicense("path/to/license.json")`. |

## Najczęściej zadawane pytania

**Q: Czym jest GroupDocs.Viewer?**  
A: To potężna biblioteka Java do renderowania dokumentów, w tym archiwów, do formatów takich jak HTML, obraz oraz PDF.

**Q: Czy mogę używać GroupDocs.Viewer z innymi językami programowania?**  
A: Tak, GroupDocs oferuje SDK dla wielu platform, ale ten samouczek koncentruje się na implementacji w Javie.

**Q: Jak obsługiwać duże pliki archiwów?**  
A: Stosuj efektywne praktyki zarządzania pamięcią i rozważ podział archiwów w razie potrzeby.

**Q: Jakie typy archiwów obsługuje GroupDocs.Viewer?**  
A: Obsługuje różnorodne formaty, w tym ZIP, RAR, TAR i inne.

**Q: Czy istnieje limit rozmiaru archiwów, które mogę przetworzyć?**  
A: Limity zależą od zasobów systemu. Przetestuj w docelowym środowisku, aby określić praktyczne granice.

**Q: Czy „how to get viewinfo” działa z archiwami zabezpieczonymi hasłem?**  
A: Tak, możesz podać hasło za pomocą `ArchiveOptions.setPassword("yourPassword")` przed wywołaniem `getViewInfo`.

## Podsumowanie

Postępując zgodnie z tym przewodnikiem, teraz wiesz **jak uzyskać viewinfo** dla dowolnego obsługiwanego archiwum oraz jak przeglądać jego strukturę folderów przy użyciu GroupDocs.Viewer dla Javy. Te techniki umożliwiają budowanie inteligentniejszych pipeline’ów przetwarzania danych, ulepszanie integracji z CMS oraz pewne radzenie sobie z dużymi zbiorami plików archiwalnych. Następnie możesz zbadać renderowanie pojedynczych plików z archiwum lub konwersję ich do PDF/HTML przy użyciu innych funkcji Viewer.

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Zasoby**
- **Dokumentacja:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencja API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Pobierz GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Kup licencję:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Darmowa wersja próbna i licencja tymczasowa:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)