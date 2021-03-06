---
title: Poprawa dyscypliny linii bazowej tożsamości
description: Poznaj potencjalne zadania wykonywane przez firmę w celu opracowania i poznawania dyscypliny linii bazowej tożsamości w każdej fazie wdrażania chmury.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: f1e991a83c79be3e829bce618a50243b74c2c90f
ms.sourcegitcommit: 5d6a7610e556f7b8ca69960ba76a3adfa9203ded
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/14/2020
ms.locfileid: "83400725"
---
<!-- cSpell:ignore offboarding preintegration -->

# <a name="identity-baseline-discipline-improvement"></a>Poprawa dyscypliny linii bazowej tożsamości

Dyscyplina bazowa tożsamości koncentruje się na sposobach ustanawiania zasad zapewniających spójność i ciągłość tożsamości użytkowników niezależnie od dostawcy chmury, który obsługuje aplikację lub obciążenie. W ramach pięciu dyscyplin nadzoru chmurowego dyscyplina podstawowa tożsamości obejmuje decyzje dotyczące [strategii tożsamości hybrydowej](../../decision-guides/identity/index.md), oceny i rozszerzenia repozytoriów tożsamości, implementacji logowania jednokrotnego (tego samego logowania), inspekcji i monitorowania w celu nieautoryzowanego użycia lub złośliwych podmiotów. W niektórych przypadkach może być również zaangażowana decyzja o modernizację, konsolidację lub integrację wielu dostawców tożsamości.

W tym artykule przedstawiono niektóre potencjalne zadania, w których firma może uczestniczyć w ulepszaniu dyscypliny linii bazowej tożsamości. Te zadania mogą być podzielone na planowanie, kompilowanie, przyjmowanie i eksploatację etapów wdrażania rozwiązania w chmurze, które są następnie powtarzane na umożliwieniu rozwoju [przyrostowego podejścia do zarządzania chmurą](../guides/index.md#an-incremental-approach-to-cloud-governance).

![Cztery etapy wdrażania](../../_images/govern/adoption-phases.png)

_Rysunek 1: etapy wdrażania stopniowego podejścia do ładu w chmurze._

Nie jest możliwe, aby żaden z dokumentów mógł uwzględnić wymagania wszystkich firm. W tym artykule opisano sugerowane minimalne i potencjalne przykładowe działania dla każdej fazy procesu ładu. Początkowym celem tych działań jest ułatwienie tworzenia programu MVP dla [zasad](../guides/index.md#an-incremental-approach-to-cloud-governance) i ustanowienie platformy do ulepszania zasad. Zespół ds. zarządzania chmurą będzie musiał zdecydować, jak dużo inwestować w te działania, aby ulepszyć dyscyplinę bazową tożsamości.

> [!CAUTION]
> Nie są one wyrównane do określonych zasad firmy lub wymagań dotyczących zgodności innych firm. Te wskazówki mają na celu ułatwienie obsługi konwersacji, które będą prowadzić do wyrównania obu wymagań przy użyciu modelu ładu chmurowego.

## <a name="planning-and-readiness"></a>Planowanie i gotowość

W tej fazie działania ładu mostkuje podział między wynikami biznesowymi i strategiami, które mogą być funkcjonalne. W trakcie tego procesu zespół lidera definiuje określone metryki, mapuje te metryki na cyfrę elektroniczną i rozpoczyna planowanie ogólnego wysiłku migracji.

**Minimalna sugerowane działania:**

- Oceń opcje [łańcucha narzędzi linii bazowej tożsamości](./toolchain.md) i Implementuj strategię hybrydową, która jest odpowiednia dla Twojej organizacji.
- Opracowywanie dokumentów z instrukcjami dotyczącymi architektury i dystrybucji do kluczowych uczestników projektu.
- Zaangażuj i powiąż osoby i zespoły, których dotyczy rozwój wytycznych dotyczących architektury.

**Potencjalne działania:**

- Zdefiniuj role i przydziały, które będą zarządzać zarządzaniem tożsamościami i dostępem w chmurze.
- Zdefiniuj grupy lokalne i Mapuj je na odpowiednie role oparte na chmurze.
- Dostawcy tożsamości spisu (w tym tożsamości oparte na bazie danych używane przez aplikacje niestandardowe).
- Konsolidowanie i integrowanie dostawców tożsamości, w których istnieje duplikacja, w celu uproszczenia ogólnego rozwiązania do tworzenia tożsamości i zmniejszania ryzyka.
- Oceń zgodność hybrydową istniejących dostawców tożsamości.
- W przypadku dostawców tożsamości, które nie są zgodne ze standardem hybrydowym, Oceń opcje konsolidacji lub zamiany.

## <a name="build-and-predeployment"></a>Kompilacja i prewdrażanie

Do pomyślnego przeprowadzenia migracji środowiska wymagane są pewne wymagania techniczne i nietechniczne. Ten proces koncentruje się na decyzjach, gotowości i infrastrukturze podstawowej, która przejdzie do migracji.

**Minimalna sugerowane działania:**

- Rozważmy test pilotażowy przed wdrożeniem [linii bazowej tożsamości łańcucha narzędzi](./toolchain.md), aby upewnić się, że środowisko użytkownika jest tak dużo jak to możliwe.
- Zastosuj opinię z testów pilotażowych do wdrożenia prewdrożeniowego. Powtarzaj, dopóki wyniki nie zostaną akceptowalne.
- Aktualizacja dokumentu z instrukcjami dotyczącymi architektury w celu uwzględnienia planów wdrażania i wdrożenia użytkowników oraz dystrybucji do kluczowych udziałowców.
- Rozważ utworzenie programu wczesnego oprogramowania do wdrażania i przeprowadzenie wdrożenia w ograniczonej liczbie użytkowników.
- Kontynuuj, aby wypróbować ludzi i zespoły, których dotyczą wskazówki dotyczące architektury.

<!-- docsTest:ignore "seamless SSO" -->

**Potencjalne działania:**

- Oceń architekturę logiczną i fizyczną oraz określ [strategię tożsamości hybrydowej](../../decision-guides/identity/index.md).
- Mapowanie zasad zarządzania dostępem do tożsamości, takich jak przypisania identyfikatorów logowania, i Wybieranie odpowiedniej metody uwierzytelniania dla usługi Azure AD.
  - W przypadku federacyjnego Włącz ograniczenia dzierżawy dla kont administracyjnych.
- Integruj katalogi lokalne i w chmurze.
- Rozważ użycie następujących modeli dostępu:
  - Model dostępu [administracyjnego o najniższych uprawnieniach](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models) .
  - Model dostępu [Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure) .
- Zakończ wszystkie szczegóły dotyczące preintegracji oraz zapoznaj się z [najlepszymi rozwiązaniami dotyczącymi zabezpieczeń zarządzania tożsamościami i kontroli dostępu](https://docs.microsoft.com/azure/security/fundamentals/identity-management-best-practices).
  - Włącz pojedyncze tożsamości, logowanie jednokrotne (SSO), nazywane również bezproblemową logowaniem jednokrotnym.
  - Skonfiguruj uwierzytelnianie wieloskładnikowe dla administratorów.
  - W razie potrzeby można skonsolidować lub zintegrować dostawców tożsamości.
  - Zaimplementuj narzędzia niezbędne do scentralizowanego zarządzania tożsamościami.
  - Włącz dostęp just-in-Time (JIT) i alerty zmian ról.
  - Przeprowadź analizę ryzyka dla kluczowych działań administratorów do przypisywania do wbudowanych ról.
  - Zapoznaj się z zaktualizowanym wdrożeniem silniejszego uwierzytelniania dla wszystkich użytkowników.
  - Włącz usługę Privileged Identity Management (PIM) dla JIT (przy użyciu aktywacji ograniczonej czasowo) dla dodatkowych ról administracyjnych.
  - Oddziel konta użytkowników od kont administratora globalnego, aby upewnić się, że administratorzy nie mogą przypadkowo otwierać wiadomości e-mail ani uruchamiać programów skojarzonych z kontami administratora globalnego).

## <a name="adopt-and-migrate"></a>Zastosuj i Migruj

Migracja to proces przyrostowy, który koncentruje się na przeniesieniu, testowaniu i wdrażaniu aplikacji lub obciążeń w istniejącym obszarze cyfrowym.

**Minimalna sugerowane działania:**

- Migruj swoją [linię bazową tożsamości łańcucha narzędzi](./toolchain.md) z programowania do produkcji.
- Aktualizacja dokumentu z instrukcjami dotyczącymi architektury i dystrybucja do kluczowych uczestników projektu.
- Opracowywanie materiałów edukacyjnych i dokumentacji, świadomości, zachęt i innych programów w celu ułatwienia wdrażania użytkowników.

**Potencjalne działania:**

- Sprawdź, czy najlepsze rozwiązania zdefiniowane w fazie wdrożenia wstępnego są prawidłowo wykonywane.
- Weryfikuj i udoskonalaj [strategię tożsamości hybrydowej](../../decision-guides/identity/index.md).
- Upewnij się, że każda aplikacja lub obciążenie nadal są wyrównane z strategią tożsamości przed wydaniem.
- Sprawdź, czy logowanie jednokrotne (SSO) i bezproblemowe logowanie jednokrotne działają zgodnie z oczekiwaniami dla aplikacji.
- Zmniejsz lub Usuń liczbę alternatywnych magazynów tożsamości.
- Scrutinize potrzebę dla wszystkich magazynów tożsamości w aplikacji lub w bazie danych. Tożsamości, które znajdują się poza właściwym dostawcą tożsamości (podmiot pierwszej lub innej firmy), mogą reprezentować ryzyko dla aplikacji i użytkowników.
- Włącz dostęp warunkowy dla [lokalnych aplikacji federacyjnych](https://docs.microsoft.com/azure/active-directory/devices/overview).
- Dystrybuuj tożsamość między regionami globalnymi w wielu centrach z synchronizacją między regionami.
- Ustanawianie Federacji kontroli dostępu opartej na rolach (RBAC).

## <a name="operate-and-post-implementation"></a>Działanie i po wdrożeniu

Po zakończeniu transformacji zarządzanie i działania muszą być aktywne w przypadku naturalnego cyklu życia aplikacji lub obciążenia. Ta faza zarządzania terminem spłaty koncentruje się na działaniach, które często są stosowane po wdrożeniu rozwiązania, a cykl transformacji zaczyna się ustabilizować.

**Minimalna sugerowane działania:**

- Dostosuj swoją [linię bazową tożsamości łańcucha narzędzi](./toolchain.md) w zależności od zmieniających się potrzeb organizacji.
- Automatyzuj powiadomienia i raporty, aby otrzymywać alerty o potencjalnych złośliwych zagrożeniach.
- Monitoruj i zgłaszaj postępy dotyczące użycia systemu i postępu wdrażania użytkownika.
- Zgłoś metryki po wdrożeniu i Dystrybuuj je do zainteresowanych stron.
- Zawęzić wskazówki dotyczące architektury w celu zaplanowania przyszłych procesów wdrażania.
- Należy okresowo komunikować się i stale przekazywać odpowiednie zespoły, aby zapewnić ciągłe przestrzeganie wytycznych dotyczących architektury.

**Potencjalne działania:**

- Przeprowadzaj okresowe inspekcje zasad tożsamości i praktyk przestrzegania.
- Upewnij się, że poufne konta użytkowników (takie jak konta kierownictwa firmy) są zawsze włączone na potrzeby uwierzytelniania wieloskładnikowego i wykrywania nietypowego logowania.
- Skanuj w poszukiwaniu złośliwych podmiotów i naruszeń danych regularnie, szczególnie tych związanych z oszustwem tożsamości, takimi jak potencjalne przejęcie kont administratorów.
- Skonfiguruj narzędzie do monitorowania i raportowania.
- Rozważ ścisłą integrację z systemami zabezpieczeń i zapobiegania oszustwom.
- Regularnie Przeglądaj prawa dostępu dla podniesionych użytkowników lub ról.
  - Zidentyfikuj każdego użytkownika, który kwalifikuje się do aktywowania uprawnień administratora.
- Zapoznaj się z procesem dołączania, odłączania i aktualizacji poświadczeń.
- Zbadaj rosnące poziomy automatyzacji i komunikacji między modułami zarządzania dostępem do tożsamości (IAM).
- Rozważ zaimplementowanie podejścia do operacji związanych z zabezpieczeniami programistycznymi (DevSecOps).
- Przeprowadź analizę wpływu, aby ocenić wyniki dotyczące kosztów, zabezpieczeń i adopcji użytkowników.
- Należy okresowo generować raport dotyczący wpływów, który pokazuje zmiany w metrykach utworzonych przez system i ocenia wpływ [strategii tożsamości hybrydowej](../../decision-guides/identity/index.md)na działalność biznesową.
- Ustanów zintegrowane monitorowanie zalecane przez [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro).

## <a name="next-steps"></a>Następne kroki

Teraz, gdy rozumiesz koncepcję zarządzania tożsamościami w chmurze, zapoznaj się z [łańcucha narzędziem linii bazowej tożsamości](./toolchain.md) , aby zidentyfikować narzędzia i funkcje platformy Azure, które będą potrzebne podczas tworzenia dyscypliny linii bazowej tożsamości na platformie Azure.

> [!div class="nextstepaction"]
> [Łańcucha narzędzi linii bazowej tożsamości dla platformy Azure](./toolchain.md)
