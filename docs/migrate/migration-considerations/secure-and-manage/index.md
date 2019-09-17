---
title: Zabezpieczenia i zarządzanie
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Bezpieczne narzędzia do monitorowania i zarządzania
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 652637905f9de09972eed199f85245e99fb60e29
ms.sourcegitcommit: 443c28f3afeedfbfe8b9980875a54afdbebd83a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2019
ms.locfileid: "71022585"
---
# <a name="secure-monitoring-and-management-tools"></a>Bezpieczne narzędzia do monitorowania i zarządzania

Po zakończeniu migracji zmigrowane zasoby powinny być zarządzane przez kontrolowane operacje działu IT. Ten artykuł nie ma na celu sugerowania odchyleń od najlepszych rozwiązań dotyczących operacji. Zamiast tego poniższe zalecenia należy uznać za produkt o minimalnej wymaganej funkcjonalności umożliwiający zabezpieczenie zmigrowanych zasobów i zarządzanie nimi przez operacje działu IT lub niezależnie, gdy operacje działu IT przechodzą w tryb online.

## <a name="monitoring"></a>Monitorowanie

*Monitorowanie* polega na zbieraniu i analizowaniu danych w celu określenia wydajności, kondycji i dostępności obciążenia biznesowego i zasobów, od których jest ono zależne. Platforma Azure obejmuje wiele usług, które indywidualnie wykonują określoną rolę lub zadanie w obszarze monitorowania. Razem usługi te zapewniają kompleksowe rozwiązanie umożliwiające zbieranie, analizowanie oraz działanie na podstawie danych telemetrycznych z aplikacji obciążeń oraz zasobów platformy Azure, które je obsługują. Uzyskaj wgląd w kondycję i wydajność aplikacji, infrastruktury i danych na platformie Azure za pomocą narzędzi do monitorowania w chmurze, takich jak Azure Monitor, Log Analytics i Application Insights. Za pomocą następujących narzędzi do monitorowania w chmurze możesz podejmować działania i zapewniać integrację z Twoimi rozwiązaniami do zarządzania usługami:

- **Monitorowanie podstawowe** Monitorowanie podstawowe zapewnia niezbędne, wymagane monitorowanie w zasobach platformy Azure. Te usługi wymagają minimalnej konfiguracji i zbierają podstawowe dane telemetryczne, z których korzystają usługi monitorowania Premium.
- **Zaawansowane monitorowanie aplikacji i infrastruktury** Usługi platformy Azure zapewniają bogate możliwości bardziej szczegółowego zbierania i analizowania danych monitorowania. Te usługi opierają się na monitorowaniu podstawowym i wykorzystują wspólną funkcjonalność platformy Azure. Umożliwiają zaawansowaną analizę z użyciem zebranych danych, dostarczając unikatowe szczegółowe informacje dotyczące aplikacji i infrastruktury.

Dowiedz się więcej o usłudze [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) służącej do monitorowania zmigrowanych zasobów.

## <a name="security-monitoring"></a>Monitorowanie zabezpieczeń

Usługa Azure Security Center zapewnia ujednolicone monitorowanie zabezpieczeń i zaawansowane powiadomienia o zagrożeniach dotyczące różnych obciążeń chmury hybrydowej. Usługa Security Center zapewnia pełny wgląd w zabezpieczenia aplikacji w chmurze na platformie Azure i kontrolę nad nimi. Szybko wykrywaj zagrożenia i podejmuj odpowiednie akcje, a także zmniejsz narażenie na ataki, włączając adaptacyjną ochronę przed zagrożeniami. Wbudowany pulpit nawigacyjny zapewnia błyskawiczny wgląd w alerty zabezpieczeń i luki w zabezpieczeniach, które wymagają uwagi. Usługa Azure Security Center może zapewnić pomoc dotyczącą wielu funkcji, takich jak:

- **Scentralizowane monitorowanie zasad** Zapewnij zgodność z firmowymi lub prawnymi wymaganiami dotyczącymi zabezpieczeń przez centralne zarządzanie zasadami zabezpieczeń we wszystkich obciążeniach chmury hybrydowej.
- **Ciągła ocena zabezpieczeń** Monitoruj zabezpieczenia maszyn, sieci, magazynu i usług danych oraz aplikacji pod kątem potencjalnych problemów z zabezpieczeniami.
- **Rekomendacje z możliwością wykonywania akcji** Koryguj luki w zabezpieczeniach zanim zostaną wykorzystane przez atakujących. Otrzymuj praktyczne rekomendacje uszeregowane według priorytetów.
- **Zaawansowana ochrona w chmurze** Ogranicz zagrożenia dzięki dostępowi typu just in time do portów zarządzania i list dozwolonych na potrzeby kontrolowania aplikacji działających na maszynach wirtualnych.
- **Alerty i zdarzenia uszeregowane według priorytetów** Zdarzenia i alerty zabezpieczeń uszeregowane według priorytetów pozwalają koncentrować się najpierw na krytycznych zagrożeniach.
- **Zintegrowane rozwiązania zabezpieczeń** Zbieranie, wyszukiwanie i analizowanie danych zabezpieczeń z różnych źródeł, w tym połączonych rozwiązań partnerskich.

Dowiedz się więcej o usłudze [Azure Security Center](https://docs.microsoft.com/azure/security-center) do zabezpieczania zmigrowanych zasobów.

## <a name="protect-assets-and-data"></a>Ochrona zasobów i danych

Usługa Azure Backup umożliwia ochronę maszyn wirtualnych, plików i danych. Usługa Azure Backup może zapewnić pomoc dotyczącą wielu funkcji, takich jak:

- Tworzenie kopii zapasowych maszyn wirtualnych
- Tworzenie kopii zapasowych plików
- Tworzenie kopii zapasowych baz danych programu SQL Server
- Odzyskiwanie chronionych zasobów

Dowiedz się więcej o usłudze [Azure Backup](https://docs.microsoft.com/azure/backup) do ochrony zmigrowanych zasobów.