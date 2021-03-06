---
title: Krytyczne znaczenie biznesowe w zarządzaniu chmurą
description: Użyj struktury wdrażania w chmurze dla platformy Azure, aby zrozumieć istotność obciążeń i zapobiec niekorzystnemu wpływowi na dochody i zyskowność.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 68bfe3b1acfb6a48fdda7e4d9583adcadac29893
ms.sourcegitcommit: 070e6a60f05519705828fcc9c5770c3f9f986de5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2020
ms.locfileid: "83815212"
---
# <a name="business-criticality-in-cloud-management"></a>Krytyczne znaczenie biznesowe w zarządzaniu chmurą

Dla każdej firmy istnieje niewielka liczba obciążeń, które są zbyt ważne, aby zakończyć się niepowodzeniem. Te obciążenia są uznawane za krytyczne. Gdy te obciążenia są w stanie awarii lub obniżeniu wydajności, niekorzystny wpływ na dochody i zyskowność można uzyskać w całej firmie.

Z drugiej strony, niektóre obciążenia mogą zaczynać miesiące w danym momencie bez użycia. Niska wydajność lub przerwy w obciążeniu nie są pożądane, ale wpływ jest odizolowany i ograniczony.

Zrozumienie stopnia zagrożenia każdego obciążenia w portfolio IT to pierwszy krok w kierunku ustanowienia wzajemnych zobowiązań związanych z zarządzaniem chmurą. Na poniższym diagramie przedstawiono typowe wyrównanie między skalą o krytycznym znaczeniu i standardowe zobowiązania podejmowane przez firmę.

![Wyrównanie poziomu krytycznego i zarządzania](../../_images/manage/cloud-criticality-alignment.png)

## <a name="criticality-scale"></a>Skalowanie krytyczne

Pierwszym krokiem w celu wyrównania znaczenia dla działania firmy jest utworzenie skali krytycznej. W poniższej tabeli przedstawiono przykładową skalę, która ma być używana jako odwołanie lub szablon w celu utworzenia własnej skali.

| Zagrożenia | Widok biznesowy |
| --------- | --------- |
| Operacje krytyczne dla działalności firmy |  Wpływa na misja firmy i może w zauważalny sposób mieć wpływ na firmowe zestawienie zysków i strat. |
| Jednostka — krytyczne | Ma wpływ na misja określonej jednostki biznesowej i jej zestawień zysków i strat. |
| Wysoki | Może nie utrudniać misja, ale ma wpływ na procesy o wysokiej ważności. Wymierne straty mogą być wymierne w przypadku awarii. |
| Średniaa | Prawdopodobnie ma to wpływ na procesy. Straty są niskie lub wymierne, ale przyczyną mogą być uszkodzenia marki lub straty w strumieniu. |
| Małe | Wpływ na procesy biznesowe nie jest wymierny. Nie ma to żadnego uszkodzenia marki ani utraty strumienia. Prawdopodobnie zlokalizowany wpływ na pojedynczy zespół. |
| Nieobsługiwane | Żaden właściciel firmy, zespół lub proces, który jest skojarzony z tym obciążeniem, może uzasadniać wszelką inwestycję w ciągłe zarządzanie obciążeniem. |

Jest to typowy w przypadku firm, które uwzględniają dodatkowe klasyfikacje krytyczne, które są specyficzne dla branżowych, pionowych lub określonych procesów biznesowych. Przykłady dodatkowych klasyfikacji obejmują:

- **Zgodność — krytyczne:** W silnie regulowanej branży niektóre obciążenia mogą być krytyczne w ramach wysiłków związanych z zachowaniem zgodności.
- **Krytyczne dla zabezpieczeń:** Niektóre obciążenia mogą nie być krytyczne dla działalności, ale może to spowodować utratę danych lub niezamierzony dostęp do chronionych informacji.
- **Krytyczne dla bezpieczeństwa:** W przypadku życia lub fizycznego bezpieczeństwa pracowników i klientów w trakcie awarii może być konieczne klasyfikowanie obciążeń jako krytycznych dla bezpieczeństwa.

## <a name="importance-of-accurate-criticality"></a>Znaczenie dokładnej krytycznej ważności

W dalszej części procesu wdrażania w chmurze zespół zarządzający chmurą będzie używać tej klasyfikacji do określenia wielkości nakładu pracy wymaganej do spełnienia poziomów stopnia krytycznego zagrożenia. W środowiskach lokalnych, zarządzanie operacjami jest często kupowane centralnie i traktowane jako niezbędne obciążenia biznesowe, z małym lub bez dodatkowych kosztów operacyjnych. Podobnie jak w przypadku wszystkich usług w chmurze, zarządzanie operacjami jest kupowane na podstawie zasobów jako miesięczne koszty operacyjne.

Ze względu na to, że istnieje jasne i bezpośrednie koszty zarządzania operacjami w chmurze, ważne jest, aby odpowiednio dostosować koszty i skalować pożądaną skalowalność.

## <a name="select-a-default-criticality"></a>Wybierz domyślną wartość krytyczną

Początkowy przegląd wszystkich obciążeń w portfolio może być czasochłonny. Aby zapewnić, że to wysiłki nie zablokuje szerszej strategii chmurowej, zalecamy, aby Twoje zespoły zgadzali się z domyślną wartością krytyczną, która ma zastosowanie do wszystkich obciążeń.

Zgodnie z poprzednią tabelą skalowania w poziomie o krytycznym znaczeniu zaleca się przyjęcie _średniego poziomu_ krytycznego jako domyślnego. Dzięki temu zespół strategii chmury będzie mógł szybko identyfikować obciążenia, które wymagają wyższego poziomu zagrożenia.

## <a name="use-the-template"></a>Korzystanie z szablonu

Poniższe kroki są stosowane, jeśli używasz [skoroszytu zarządzania operacjami](https://raw.githubusercontent.com/Microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) do planowania zarządzania chmurą.

1. Zapisz skalę krytyczności w `Scale` arkuszu.
2. Zaktualizuj każde obciążenie w `Example` arkuszu lub w arkuszu, `Clean Template` aby odzwierciedlić domyślną wartość krytyczną w `Criticality` kolumnie.
3. Firma powinna wprowadzić poprawne wartości, aby odzwierciedlić wszelkie odchylenia od domyślnej krytycznej.

## <a name="next-steps"></a>Następne kroki

Gdy zespół ma zdefiniowaną istotność biznesową, możesz [obliczyć i zarejestrować wpływ na działalność biznesową](./impact.md).

> [!div class="nextstepaction"]
> [Oblicz i zarejestruj wpływ na firmę](./impact.md)
