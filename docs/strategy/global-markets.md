---
title: Wpływ na globalne decyzje dotyczące rynku
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby zrozumieć, w jaki sposób globalne decyzje rynkowe mogą wpłynąć na podróż transformację do chmury.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: strategy
ms.openlocfilehash: 8dba91bf7bd87395d3b5c55cf99480f8c6a54bd4
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83221454"
---
<!-- markdownlint-disable MD026 -->

# <a name="how-will-global-market-decisions-affect-the-transformation-journey"></a>W jaki sposób globalne decyzje rynkowe wpłyną na podróż transformację?

Chmura otwiera nowe możliwości do wykonania w skali globalnej. Bariery związane z operacjami globalnymi są znacznie ograniczone, przez umożliwienie firmom wdrażania zasobów na rynku, bez konieczności inwestowania w nowe centra danych. Niestety, zwiększa to również dużą liczbę złożoności od perspektyw technicznych i prawnych.

## <a name="data-sovereignty"></a>Niezależność danych

Wiele regionów geopolitycznych ustanowiło przepisy dotyczące suwerenności danych. Przepisy te ograniczają miejsce przechowywania danych, jakie dane mogą opuścić kraj pochodzenia i jakie dane mogą być zbierane dla obywateli tego regionu. Przed rozpoczęciem korzystania z rozwiązań chmurowych w obcych lokalizacjach, należy zrozumieć, w jaki sposób dostawca chmury obsługuje suwerenność danych. Aby uzyskać więcej informacji na temat podejścia platformy Azure dla każdej lokalizacji geograficznej, zobacz [Azure lokalizacje geograficzne](https://azure.microsoft.com/global-infrastructure/geographies). Aby uzyskać więcej informacji na temat zgodności na platformie Azure, zobacz [prywatność w firmie Microsoft](https://www.microsoft.com/trust-center/privacy) w centrum zaufania firmy Microsoft.

W pozostałej części tego artykułu przyjęto, że legalne osoby przejrzały i zatwierdzili operacje w obcym kraju.

## <a name="business-units"></a>Jednostki biznesowe

Ważne jest, aby zrozumieć, które jednostki biznesowe działają w krajach obcych i jakie kraje podlegają usterce. Te informacje będą używane do projektowania rozwiązań hostingu, rozliczeń i wdrożeń dla dostawcy chmury.

## <a name="employee-usage-patterns"></a>Wzorce użycia pracownika

Ważne jest, aby zrozumieć, w jaki sposób użytkownicy globalni uzyskują dostęp do aplikacji, które nie są hostowane w tym samym kraju co użytkownik. Globalne sieci rozległe (WAN) kierują użytkowników w oparciu o istniejące umowy sieciowe. W tradycyjnym lokalnym świecie niektóre ograniczenia ograniczają projektowanie sieci WAN. Te ograniczenia mogą prowadzić do słabych środowisk użytkownika, jeśli nie są właściwie zrozumiałe przed wdrożeniem chmury.

W modelu chmury internetowy asortyment otwiera również wiele nowych opcji. Komunikowanie się z rozmieszczeniem pracowników wielu lokalizacje geograficzne może ułatwić zespołowi wdrożenia chmury projektowanie rozwiązań sieci WAN, które tworzą pozytywne środowisko użytkownika **i** potencjalne obniżenie kosztów sieciowych.

## <a name="external-user-usage-patterns"></a>Wzorce użycia użytkownika zewnętrznego

Równie ważne jest zrozumienie wzorców użytkowania użytkowników zewnętrznych, takich jak klienci lub partnerzy. Podobnie jak wzorce użycia pracowników, wzorce użycia zewnętrznego użytkownika mogą negatywnie wpłynąć na wydajność wdrożeń w chmurze. W przypadku dużej lub krytycznej bazy użytkowników, która znajduje się w obcym kraju, może być konieczne dołączenie strategii wdrażania globalnego do ogólnego projektu rozwiązania.

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej o [umiejętnościach potrzebnych podczas fazy strategii](./suggested-skills.md) przejazdu w chmurze.

> [!div class="nextstepaction"]
> [Umiejętności wymagane w fazie strategii](./suggested-skills.md)
