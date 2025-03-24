---
title: Ustaw licencję taryfową
linktitle: Ustaw licencję taryfową
second_title: GroupDocs.Viewer API .NET
description: Ulepsz swoje aplikacje .NET za pomocą GroupDocs.Viewer, aby zapewnić płynne przeglądanie dokumentów. Z łatwością integruj funkcje renderowania dokumentów ze swoimi projektami.
weight: 12
url: /pl/net/getting-started/set-metered-license/
---

# Ustaw licencję taryfową

## Wstęp
świecie programowania .NET włączenie do aplikacji zaawansowanych funkcji przeglądania dokumentów jest niezbędne, aby zwiększyć wygodę użytkownika i funkcjonalność. GroupDocs.Viewer dla .NET oferuje solidne rozwiązanie umożliwiające bezproblemową integrację funkcji przeglądania dokumentów z projektami .NET. Niezależnie od tego, czy pracujesz z plikami PDF, dokumentami Microsoft Office, czy różnymi formatami obrazów, GroupDocs.Viewer upraszcza proces renderowania i wyświetlania tych dokumentów w aplikacjach.
## Warunki wstępne
Przed przystąpieniem do implementacji GroupDocs.Viewer dla .NET upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Zainstaluj GroupDocs.Viewer dla .NET
 Aby rozpocząć, musisz pobrać i zainstalować GroupDocs.Viewer dla .NET. Możesz znaleźć link do pobrania[Tutaj](https://releases.groupdocs.com/viewer/net/). Postępuj zgodnie z dostarczonymi instrukcjami instalacji, aby skonfigurować bibliotekę w środowisku programistycznym.
### 2. Uzyskaj licencję licznikową
Aby korzystać z GroupDocs.Viewer dla .NET, musisz uzyskać licencję taryfową. Licencja ta pozwala kontrolować i monitorować wykorzystanie API w oparciu o predefiniowane limity. Wykonaj poniższe czynności, aby skonfigurować licencję taryfową:

## Importuj przestrzenie nazw
Najpierw upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcji udostępnianych przez GroupDocs.Viewer dla .NET:
```csharp
using System;
```

Podzielmy teraz dostarczony przykładowy kod na kilka kroków:
## Krok 1: Zadeklaruj klucze publiczne i prywatne
Zadeklaruj zmienne do przechowywania kluczy publicznych i prywatnych:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Pamiętaj o wymianie`"YOUR_PUBLIC_KEY"` I`"YOUR_PRIVATE_KEY"` z twoimi prawdziwymi kluczami.
## Krok 2: Ustaw licencję taryfową
Sprawdź, czy podano klucz publiczny. Jeśli nie, poproś użytkownika o ustawienie kluczy:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://zakup.groupdocs.com/faqs/licensing/metered.”);
    return;
}
```
## Krok 3: Zainicjuj obiekt mierzony i ustaw licencję
Zainicjuj obiekt Metered i ustaw licencję taryfową przy użyciu kluczy publicznych i prywatnych:
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
Podsumowując, GroupDocs.Viewer dla .NET zapewnia kompleksowe rozwiązanie umożliwiające włączenie funkcji przeglądania dokumentów do aplikacji .NET. Wykonując opisane kroki, możesz łatwo skonfigurować licencję licznikową i zacząć wykorzystywać możliwości GroupDocs.Viewer w swoich projektach.
## Często zadawane pytania
### P: Gdzie mogę znaleźć dokumentację GroupDocs.Viewer dla .NET?
 Można znaleźć dokumentację[Tutaj](https://tutorials.groupdocs.com/viewer/net/).
### P: Czy dostępna jest bezpłatna wersja próbna programu GroupDocs.Viewer dla platformy .NET?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.groupdocs.com/).
### P: Jak mogę uzyskać licencje tymczasowe do celów testowych?
 Można uzyskać licencje tymczasowe[Tutaj](https://purchase.groupdocs.com/temporary-license/).
### P: Gdzie mogę uzyskać pomoc lub zadać pytania dotyczące GroupDocs.Viewer dla .NET?
 Możesz szukać pomocy i zadawać pytania na forum GroupDocs.Viewer[Tutaj](https://forum.groupdocs.com/c/viewer/9).
### P: Gdzie mogę kupić licencję na GroupDocs.Viewer dla .NET?
 Możesz kupić licencję[Tutaj](https://purchase.groupdocs.com/buy).