---
title: Przykładowe instrukcje dotyczące zasad przyspieszania wdrażania
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby uzyskać przykładowe instrukcje dotyczące przyspieszania wdrażania, które ułatwiają Szkicowanie instrukcji zasad.
author: alexbuckgit
ms.author: abuck
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: b92f9593c0d35f4c73dc17733d1ae57dbbe599b4
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83220264"
---
# <a name="deployment-acceleration-sample-policy-statements"></a>Przykładowe instrukcje dotyczące zasad przyspieszania wdrażania

Poszczególne instrukcje dotyczące zasad chmury to wskazówki dotyczące rozwiązywania określonych zagrożeń zidentyfikowanych podczas procesu oceny ryzyka. Te instrukcje powinny dostarczyć zwięzłe podsumowanie zagrożeń i plany postępowania z nimi. Każda definicja instrukcji powinna zawierać następujące informacje:

- **Ryzyko techniczne:** Podsumowanie ryzyka, którego dotyczy ta zasada.
- **Instrukcja zasad:** Jasne wyjaśnienie wymagań zasad.
- **Opcje projektowania:** Zalecenia z możliwością wykonania akcji, specyfikacje lub inne wskazówki, które mogą być używane przez zespoły IT i deweloperów podczas implementowania zasad.

Poniższe przykładowe instrukcje dotyczące zasad dotyczą typowych zagrożeń firmy związanych z konfiguracją. Te instrukcje są przykładami, które można przywołać podczas sporządzania projektów instrukcji zasad w celu rozwiązania potrzeb organizacji. Te przykłady nie są przeznaczone do obsługi skryptów i mogą być dostępne różne opcje dotyczące ponoszenia określonych zagrożeń. Ścisła współpraca z firmowymi i zespołami IT w celu zidentyfikowania najlepszych zasad dla unikatowego zestawu zagrożeń.

## <a name="reliance-on-manual-deployment-or-configuration-of-systems"></a>Zależność od ręcznego wdrożenia lub konfiguracji systemów

**Ryzyko techniczne:** Poleganie na interwencji ludzkiej podczas wdrażania lub konfiguracji zwiększa prawdopodobieństwo wystąpienia błędu ludzkiego i zmniejsza powtarzalność i przewidywalność wdrożeń i konfiguracji systemu. Zwykle prowadzi to do wolniejszego wdrażania zasobów systemowych.

**Instrukcja zasad:** Wszystkie zasoby wdrożone w chmurze powinny być wdrażane za pomocą szablonów lub skryptów automatyzacji wszędzie tam, gdzie to możliwe.

**Potencjalne opcje projektowania:** [Szablony Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/templates/overview) umożliwiają używanie infrastruktury jako kodu do wdrażania zasobów na platformie Azure. Można również użyć [Terraform](https://docs.microsoft.com/azure/terraform/terraform-overview) jako spójnego lokalnego i opartego na chmurze narzędzia do wdrażania.

## <a name="lack-of-visibility-into-system-issues"></a>Brak wglądu w problemy systemowe

**Ryzyko techniczne:** Niewystarczające monitorowanie i Diagnostyka systemów firmowych uniemożliwiają pracownikom operacji identyfikowanie i korygowaniem problemów przed wystąpieniem awarii systemu i znacząco wydłużyć czas wymagany do prawidłowego rozwiązania awarii.

**Instrukcja zasad:** Następujące zasady zostaną zaimplementowane:

- Kluczowe metryki i środki diagnostyki zostaną zidentyfikowane dla wszystkich systemów i składników produkcyjnych, a narzędzia do monitorowania i diagnostyki zostaną zastosowane do tych systemów i monitorowane regularnie przez pracowników operacyjnych.
- Operacje będą brane pod uwagę przy użyciu narzędzi do monitorowania i diagnostyki w środowiskach nieprodukcyjnych, takich jak przygotowanie i kontrola jakości, aby identyfikować problemy systemowe przed ich wystąpieniem w środowisku produkcyjnym.

**Potencjalne opcje projektowania:** [Azure monitor](https://docs.microsoft.com/azure/azure-monitor), w tym log Analytics i Application Insights, udostępnia narzędzia do zbierania i analizowania danych telemetrycznych, które pomagają zrozumieć, jak działają aplikacje i aktywnie identyfikują problemy wpływające na te i zasoby, od których zależą. Ponadto [Dziennik aktywności platformy Azure](https://docs.microsoft.com/azure/azure-monitor/platform/activity-logs-overview) raportuje wszystkie zmiany wprowadzane na poziomie platformy i powinny być monitorowane i poddane inspekcji pod kątem niezgodnych zmian.

## <a name="configuration-security-reviews"></a>Przeglądy zabezpieczeń konfiguracji

**Ryzyko techniczne:** W miarę upływu czasu nowe zagrożenia lub problemy związane z bezpieczeństwem mogą zwiększyć ryzyko nieautoryzowanego dostępu do zabezpieczonych zasobów.

**Instrukcja zasad:** Procesy nadzoru chmur muszą obejmować comiesięczne przeglądy z zespołami zarządzania konfiguracją w celu identyfikowania złośliwych aktorów lub wzorców użytkowania, które powinny być blokowane przez konfigurację zasobów w chmurze.

**Potencjalne opcje projektu:** Ustanów comiesięczne spotkanie przeglądowe dotyczące zabezpieczeń, które obejmuje członków zespołu nadzoru i personel IT odpowiedzialny za konfigurację aplikacji i zasobów w chmurze. Zapoznaj się z istniejącymi danymi i metrykami zabezpieczeń, aby ustalić luki w bieżącym narzędziu do przyspieszania wdrażania i narzędziach, a także zasady aktualizacji w celu skorygowania wszelkich nowych zagrożeń.

## <a name="next-steps"></a>Następne kroki

Skorzystaj z przykładów przedstawionych w tym artykule jako punktu wyjścia do opracowania zasad, które wiążą się z konkretnymi zagrożeniami biznesowymi, które są dostosowane do planów wdrażania w chmurze.

Aby rozpocząć tworzenie własnych niestandardowych instrukcji zasad linii bazowej tożsamości, Pobierz [szablon dyscypliny linii bazowej tożsamości](../identity-baseline/template.md).

Aby przyspieszyć wdrażanie tego dyscypliny, wybierz [Przewodnik dotyczący ładu](../guides/index.md) z możliwością działania, który najlepiej odpowiada Twojemu środowisku. Następnie zmodyfikuj projekt, aby uwzględnić określone decyzje dotyczące zasad firmowych.

Opracowywanie zagrożeń i odporności, ustanawianie procesu do zarządzania zasadami przyspieszenia wdrożenia i ich przekazywania.

> [!div class="nextstepaction"]
> [Ustanawianie procesów zgodności z zasadami](./compliance-processes.md)
