---
title: Wprowadzenie do zarządzania operacyjnego
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby poznać różne przejścia, które należy wykonać, aby umożliwić zarządzanie operacyjną w chmurze.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 3e1134d6ea4538a6b0f4c26418c0009d3810a25a
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83216660"
---
# <a name="establish-operational-management-practices-in-the-cloud"></a>Ustanawianie praktyk zarządzania operacyjnego w chmurze

Wdrożenie chmury pozwala szybciej zwiększyć wartość biznesową. Jednak rzeczywista wartość biznesowa jest uzyskiwana za pośrednictwem ciągłych, stabilnych operacji dotyczących zasobów technologicznych wdrożonych w chmurze. Ta sekcja struktury wdrażania w chmurze prowadzi użytkownika przez różne przejścia do zarządzania operacyjnego w chmurze.

## <a name="actionable-best-practices"></a>Najlepsze rozwiązania dotyczące zasobów z możliwością działania

Nowoczesne rozwiązania do zarządzania operacjami tworzą wielochmurowy widok operacji. Zasoby zarządzane przez następujące najlepsze rozwiązania mogą być aktywne w chmurze, w istniejącym centrum danych, a nawet w konkurencyjnym dostawcy chmury. Obecnie platforma obejmuje dwie informacje o najlepszych rozwiązaniach, które umożliwiają Przewodnik zarządzania operacjami w chmurze:

- [Zarządzanie serwerem Azure](./azure-server-management/index.md): Przewodnik dołączania umożliwiający dołączenie natywnych narzędzi i usług w chmurze wymaganych do zarządzania operacjami.
- [Monitorowanie hybrydowe](./monitor/index.md): wielu klientów wprowadziło już znaczną inwestycję w System Center Operations Manager. W przypadku tych klientów ten przewodnik dotyczący monitorowania hybrydowego może pomóc im w porównywaniu i rozróżnieniu natywnych narzędzi do raportowania w chmurze za pomocą narzędzi Operations Manager. To porównanie ułatwia podjęcie decyzji o narzędziach, które mają być używane do zarządzania operacyjnego.

## <a name="cloud-operations"></a>Operacje w chmurze

Obydwie te najlepsze rozwiązania zostały skompilowane w ramach metodologii w przyszłości w zakresie zarządzania operacjami, jak pokazano na poniższym diagramie:

<!-- cSpell:ignore caf -->

![Zarządzanie metodologią wdrożenia chmury](../_images/manage/caf-manage.png)

**Wyrównanie biznesowe:** W metodzie zarządzania wszystkie obciążenia są klasyfikowane według stopnia ważności i wartości biznesowej. Tę klasyfikację można zmierzyć w ramach analizy wpływu, która polega na obliczeniu utraconej wartości związanej z obniżeniem wydajności lub przerwami w działalności. Dzięki tym wymiernym danym wpływu na przychody zespoły ds. operacji w chmurze mogą wspólnie z firmą może ustalić zobowiązanie, które równoważy koszty i wydajność.

**Dyscypliny operacji w chmurze:** Po wyrównaniu firmy jest znacznie łatwiejsze śledzenie i raportowanie właściwych dyscyplin operacji w chmurze dla każdego obciążenia. Podejmowanie decyzji dotyczących poszczególnych dyscyplin można następnie przekonwertować na warunki zobowiązania, które mogą być łatwo zrozumiałe dla firmy. Dzięki rozwiązaniu opartemu na współpracy biorący udział w projekcie stają się partnerami w znajdowaniu równowagi między kosztami i wydajnością.

- **Spis i widoczność:** Program Operations Management wymaga co najmniej środków tworzenia spisu zasobów i zapewnienia widoczności w stanie uruchomienia każdego elementu zawartości.
- **Zgodność operacyjna:** Regularne zarządzanie konfiguracją, rozmiarem, kosztem i wydajnością zasobów jest kluczem do obsługi oczekiwań wydajności.
- **Ochrona i odzyskiwanie:** Minimalizacja przerw w działaniu i przyspieszanie odzyskiwania pomaga uniknąć ubytków wydajności i niekorzystnych wpływów na dochody. Kluczowymi aspektami tej dyscypliny są wykrywanie i odzyskiwanie.
- **Operacje na platformie:** Wszystkie środowiska IT zawierają zestaw często używanych platform. Te platformy mogą obejmować magazyny danych, takie jak SQL Server lub Azure HDInsight. Inne popularne platformy mogą obejmować rozwiązania kontenerów, takie jak Azure Kubernetes Service (AKS). Niezależnie od platformy, data_spłaty operacji platformy koncentrują się na dostosowywaniu operacji w oparciu o sposób wdrażania, konfigurowania i używania typowych platform przez obciążenia.
- **Operacje związane z obciążeniem:** W przypadku najwyższego poziomu zapadalności operacyjnego zespoły operacji w chmurze mogą dostosowywać operacje dla obciążeń krytycznych. W przypadku tych obciążeń dostępne dane mogą pomóc w automatyzowaniu korygowania, ustalaniu wielkości lub ochronie obciążeń w zależności od ich użycia.

Dodatkowe wskazówki, takie jak [Struktura przeglądu projektu (nazwa kodu: zasady projektowania w chmurze)](https://docs.microsoft.com/azure/architecture/framework/resiliency/overview), mogą pomóc w podejmowaniu szczegółowych decyzji architektonicznych dotyczących poszczególnych obciążeń w ramach wcześniej opisanych dyscyplin.

Ta sekcja platformy wdrażania w chmurze zostanie utworzona w ramach każdego z powyższych tematów, aby ułatwić promowanie operacji w chmurze w Twojej organizacji.
