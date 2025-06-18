---
"description": "Ulepsz swoje aplikacje .NET dzięki GroupDocs.Viewer, aby zapewnić bezproblemowe przeglądanie dokumentów. Łatwo integruj funkcjonalności renderowania dokumentów ze swoimi projektami."
"linktitle": "Ustaw licencję licznikową"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ustaw licencję licznikową"
"url": "/pl/net/getting-started/set-metered-license/"
"weight": 12
---

# Ustaw licencję licznikową

## Wstęp
świecie rozwoju .NET, włączanie potężnych możliwości przeglądania dokumentów do aplikacji jest niezbędne do poprawy doświadczenia użytkownika i funkcjonalności. GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie do bezproblemowej integracji funkcji przeglądania dokumentów z projektami .NET. Niezależnie od tego, czy pracujesz z plikami PDF, dokumentami Microsoft Office czy różnymi formatami obrazów, GroupDocs.Viewer upraszcza proces renderowania i wyświetlania tych dokumentów w aplikacjach.

![Ustaw licencję licznikową z GroupDocs.Viewer dla .NET](/viewer/getting-started/set-metered-license.png)

## Wymagania wstępne
Zanim rozpoczniesz implementację GroupDocs.Viewer dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Zainstaluj GroupDocs.Viewer dla .NET
Na początek musisz pobrać i zainstalować GroupDocs.Viewer dla .NET. Link do pobrania znajdziesz tutaj [Tutaj](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z instrukcjami instalacji, aby skonfigurować bibliotekę w środowisku programistycznym.
### 2. Uzyskaj licencję licznikową
Aby korzystać z GroupDocs.Viewer dla .NET, musisz uzyskać licencję mierzoną. Ta licencja umożliwia kontrolowanie i monitorowanie wykorzystania interfejsu API na podstawie wstępnie zdefiniowanych limitów. Wykonaj poniższe kroki, aby skonfigurować licencję mierzoną:

## Importuj przestrzenie nazw
Najpierw upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności zapewnianej przez GroupDocs.Viewer dla .NET:
```csharp
using System;
```

Teraz rozłóżmy przykładowy kod na kilka kroków:
## Krok 1: Zadeklaruj klucze publiczne i prywatne
Zadeklaruj zmienne, w których będziesz przechowywać swoje klucze publiczne i prywatne:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Upewnij się, że wymienisz `"YOUR_PUBLIC_KEY"` I `"YOUR_PRIVATE_KEY"` z twoimi prawdziwymi kluczami.
## Krok 2: Ustaw licencję licznikową
Sprawdź, czy klucz publiczny jest podany. Jeśli nie, poproś użytkownika o ustawienie kluczy:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Krok 3: Zainicjuj obiekt licznikowy i ustaw licencję
Zainicjuj obiekt Metered i ustaw licencję Metered przy użyciu kluczy publicznych i prywatnych:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Krok 4: Wiadomość potwierdzająca
Wyświetl komunikat potwierdzający, że licencja została pomyślnie ustawiona:
```csharp
Console.WriteLine("License set successfully.");
```

## Wniosek
Podsumowując, GroupDocs.Viewer dla .NET zapewnia kompleksowe rozwiązanie do włączania funkcji przeglądania dokumentów do aplikacji .NET. Postępując zgodnie z opisanymi krokami, możesz łatwo skonfigurować licencję mierzoną i zacząć korzystać z możliwości GroupDocs.Viewer w swoich projektach.
## Najczęściej zadawane pytania
### P: Gdzie mogę znaleźć dokumentację dla GroupDocs.Viewer dla .NET?
Dokumentację można znaleźć [Tutaj](https://tutorials.groupdocs.com/viewer/net/).
### P: Czy jest dostępna bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej [Tutaj](https://releases.groupdocs.com/).
### P: W jaki sposób mogę uzyskać tymczasową licencję do celów testowych?
Można uzyskać licencje tymczasowe [Tutaj](https://purchase.groupdocs.com/temporary-license/).
### P: Gdzie mogę uzyskać pomoc lub zadać pytania dotyczące GroupDocs.Viewer dla platformy .NET?
Możesz szukać wsparcia i zadawać pytania na forum GroupDocs.Viewer [Tutaj](https://forum.groupdocs.com/c/viewer/9).
### P: Gdzie mogę nabyć licencję na GroupDocs.Viewer dla platformy .NET?
Możesz kupić licencję [Tutaj](https://purchase.groupdocs.com/buy).