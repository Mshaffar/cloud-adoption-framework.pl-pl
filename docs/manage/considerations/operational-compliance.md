---
title: Zgodność operacyjna w zarządzaniu chmurą
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby dowiedzieć się, jak zachować zgodność z zobowiązaniami operacyjnymi.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: dc22c00d9470209f4442f1b9c4a194b8b1fdb417
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83223936"
---
# <a name="operational-compliance-in-cloud-management"></a>Zgodność operacyjna w zarządzaniu chmurą

Zgodność operacyjna jest oparta na dyscyplinach [spisu i widoczności](./inventory.md). Jako pierwszy funkcjonalny krok zarządzania chmurą ta dyscyplina koncentruje się na zwykłych przeglądach telemetrii i wysiłkach naprawczych (zarówno w przypadku aktywnego, jak i aktywnego korygowania). Ta dyscyplina jest podstawą do utrzymania równowagi między bezpieczeństwem, zarządzaniem, wydajnością i kosztami.

## <a name="components-of-operations-compliance"></a>Składniki zgodności operacji

Zachowanie zgodności z zobowiązaniami operacyjnymi wymaga analizy, automatyzacji i korygowania przez człowieka. Skuteczna zgodność operacyjna wymaga spójności w kilku krytycznych procesach:

- Spójność zasobów
- Spójność środowiska
- Spójność konfiguracji zasobów
- Spójność aktualizacji
- Automatyzacja korygowania

### <a name="resource-consistency"></a>Spójność zasobów

Najbardziej skutecznym krokiem, jaki zespół zarządzający chmurą może podjąć w celu zapewnienia zgodności działania, ma na celu ustalenie spójności w organizacji i znakowaniu zasobów. Gdy zasoby są stale zorganizowane i znakowane, wszystkie inne zadania operacyjne stają się łatwiejsze. Aby uzyskać bardziej szczegółowe wskazówki dotyczące spójności zasobów, zobacz [metodologia ładu](../../govern/index.md). Zapoznaj się z [artykułem wstępnego ładu](../../govern/initial-foundation.md) , aby dowiedzieć się, jak rozpocząć tworzenie spójności zasobów.

### <a name="environment-consistency"></a>Spójność środowiska

Ustanawianie spójnych środowisk lub stref wypełniania jest kolejnym najważniejszym krokiem w kierunku zgodności operacyjnej. Gdy strefy wyładunkowe są spójne i wymuszane za poorednictwem zautomatyzowanych narzędzi, jest znacznie mniej skomplikowane do diagnozowania i rozwiązywania problemów operacyjnych. Aby uzyskać bardziej szczegółowe wskazówki dotyczące spójności środowiska, zobacz [Faza gotowości](../../ready/index.md) wdrożenia chmury. Ćwiczenia w tej fazie pomagają w tworzeniu powtarzalnego procesu do definiowania i dojrzewania spójnego kodu po raz pierwszy do rozwoju środowisk opartych na chmurze.

### <a name="resource-configuration-consistency"></a>Spójność konfiguracji zasobów

W miarę kompilowania rozwiązań nadzoru i gotowości zarządzanie chmurą powinno obejmować procesy ciągłego monitorowania i oceny przestrzegania wymagań dotyczących spójności zasobów. W miarę wprowadzania zmian obciążeń lub nowych wersji należy koniecznie, aby procesy zarządzania chmurą szacować zmiany konfiguracji, które nie są łatwo regulowane przez automatyzację.

W przypadku wykrycia niespójności niektóre są rozwiązywane przez spójność aktualizacji, a inne mogą być automatycznie korygowane.

### <a name="update-consistency"></a>Spójność aktualizacji

Stabilność w podejściu może prowadzić do bardziej stabilnych operacji. Jednak niektóre zmiany są wymagane w ramach procesów zarządzania chmurą. W szczególności regularne poprawki i zmiany wydajności są niezbędne do zredukowania przerw i kontrolowania kosztów.

Jedną z wielu wartości metody zarządzania chmurą dla dorosłych jest skoncentrowana na stabilizacji i kontroli koniecznych zmian.

Każda linia bazowa zarządzania chmurą powinna zawierać środki planowania, kontrolowania i możliwego automatyzacji niezbędnych aktualizacji. Te aktualizacje powinny zawierać co najmniej poprawki, ale mogą również obejmować wydajność, rozmiar i inne aspekty aktualizacji zasobów.

### <a name="remediation-automation"></a>Automatyzacja korygowania

Jako rozszerzona linia bazowa dla zarządzania chmurą, niektóre obciążenia mogą korzystać z automatycznego korygowania. Gdy obciążenie często napotyka problemy, których nie można rozwiązać za pomocą zmian kodu lub architektury, Automatyzacja korygowania może pomóc w zmniejszeniu obciążenia zarządzania chmurą i zwiększenia zadowolenia użytkowników.

Wiele z nich podnosi, że wszelkie problemy, które są powszechnie wystarczające do automatyzowania, powinny być rozwiązane przez rozwiązanie długu technicznego. Gdy długoterminowe rozwiązanie jest rozsądne, powinna to być opcja domyślna. Niektóre scenariusze biznesowe utrudniają jednak duże inwestycje w Rozwiązywanie długów technicznych. Gdy takie rozwiązanie nie jest uzasadnione, ale korygowanie jest często spotykane i kosztowne, automatyczne korygowanie jest następnym najlepszym rozwiązaniem.

## <a name="next-steps"></a>Następne kroki

[Ochrona i odzyskiwanie](./protect.md) to kolejne obszary, które należy wziąć pod uwagę w linii bazowej zarządzania chmurą.

> [!div class="nextstepaction"]
> [Ochrona i odzyskiwanie](./protect.md)
