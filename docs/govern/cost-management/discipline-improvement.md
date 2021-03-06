---
title: Ulepszanie dyscypliny Cost Management
description: Poznaj potencjalne zadania wykonywane przez firmę w celu opracowania i przedwczesnej dyscypliny Cost Management w każdej fazie wdrażania chmury.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 45b750b6d99bf858eaefa635aa6b16464158f412
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83220638"
---
# <a name="cost-management-discipline-improvement"></a>Ulepszanie dyscypliny Cost Management

Dyscyplina Cost Management próbuje rozwiązać podstawowe ryzyko biznesowe związane z kosztami związanymi z obsługą obciążeń opartych na chmurze. W ramach pięciu dyscyplin nadzoru w chmurze Cost Management dyscypliny są związane z kontrolowaniem kosztów i użycia zasobów w chmurze w celu utworzenia i utrzymania planowanego cyklu kosztu.

W tym artykule przedstawiono potencjalne zadania wykonywane przez firmę w celu opracowania i zamontowania dyscypliny Cost Management. Te zadania mogą być podzielone na planowanie, kompilowanie, przyjmowanie i eksploatację faz wdrażania rozwiązania w chmurze. Zadania są następnie wykonywane w sposób umożliwiający opracowywanie [stopniowego podejścia do zarządzania chmurą](../guides/index.md#an-incremental-approach-to-cloud-governance).

![Cztery etapy wdrażania](../../_images/govern/adoption-phases.png)

_Rysunek 1: etapy wdrażania stopniowego podejścia do ładu w chmurze._

Żaden pojedynczy dokument nie może uwzględniać wymagań wszystkich firm. W tym artykule opisano sugerowane minimalne i potencjalne przykładowe działania dla każdej fazy procesu ładu. Początkowym celem tych działań jest ułatwienie tworzenia programu MVP dla [zasad](../guides/index.md#an-incremental-approach-to-cloud-governance) i ustanowienie platformy do ulepszania zasad. Zespół ds. zarządzania chmurą będzie musiał zdecydować, jak dużo inwestować w te działania, aby usprawnić Cost Management możliwości dyscypliny.

> [!CAUTION]
> Nie są one wyrównane do określonych zasad firmy lub wymagań dotyczących zgodności innych firm. Te wskazówki mają na celu ułatwienie obsługi konwersacji, które będą prowadzić do wyrównania obu wymagań przy użyciu modelu ładu chmurowego.

## <a name="planning-and-readiness"></a>Planowanie i gotowość

W tej fazie działania ładu mostkuje podział między wynikami biznesowymi i strategiami, które mogą być funkcjonalne. W trakcie tego procesu zespół lidera definiuje określone metryki, mapuje te metryki na cyfrę elektroniczną i rozpoczyna planowanie ogólnego wysiłku migracji.

**Minimalna sugerowane działania:**

- Oceń [Cost Management opcje łańcucha narzędzi](./toolchain.md) .
- Utwórz wersję roboczą dokumentu pod kątem wytycznych dotyczących architektury i Rozpowszechnij ją na najważniejszych udziałowców.
- Zaangażuj i powiąż osoby i zespoły, których dotyczy rozwój wytycznych dotyczących architektury.

**Potencjalne działania:**

- Zadbaj o podejmowanie decyzji budżetowych, które wspierają uzasadnienie biznesowe dla strategii chmurowej.
- Sprawdź poprawność metryk uczenia, które służą do zgłaszania pomyślnej alokacji finansowania.
- Zapoznaj się z żądanym modelem ewidencjonowania aktywności w chmurze, który ma wpływ na sposób uwzględniania kosztów chmury.
- Zapoznaj się z planem elektronicznej i Sprawdź dokładne koszty.
- Oceń opcje kupowania, aby określić, czy lepiej jest "płatność zgodnie z rzeczywistym użyciem", czy też dokonać zobowiązania przed zakupem Umowa Enterprise.
- Wyrównaj cele biznesowe z planowanymi budżetami i Dostosuj plany budżetowe w miarę potrzeb.
- Opracowuj cele i mechanizm raportowania budżetu, aby powiadomić zainteresowanych uczestników technicznych i firmowych na końcu każdego cyklu kosztu.

## <a name="build-and-predeployment"></a>Kompilacja i prewdrażanie

Do pomyślnego przeprowadzenia migracji środowiska wymagane są pewne wymagania techniczne i nietechniczne. Ten proces koncentruje się na decyzjach, gotowości i infrastrukturze podstawowej, która przejdzie do migracji.

**Minimalna sugerowane działania:**

- Zaimplementuj [Cost Management łańcucha narzędzi](./toolchain.md) , przechodząc do etapu preinstalacji.
- Aktualizacja dokumentu z instrukcjami dotyczącymi architektury i dystrybucja do kluczowych uczestników projektu.
- Opracowywanie materiałów edukacyjnych i dokumentacji, świadomości, zachęt i innych programów w celu ułatwienia wdrażania użytkowników.
- Ustal, czy wymagania zakupu są wyrównane z budżetami i celami.

**Potencjalne działania:**

- Wyrównuje plany budżetowe z [strategią subskrypcji](../../decision-guides/subscriptions/index.md) , która definiuje model własności podstawowej.
- Użyj [strategii dyscypliny spójności zasobów](../../decision-guides/resource-consistency/index.md) , aby wymusić architekturę i wytyczne dotyczące kosztów w miarę upływu czasu.
- Ustal, czy jakiekolwiek anomalie kosztów wpływają na plany wdrażania i migracji.

## <a name="adopt-and-migrate"></a>Zastosuj i Migruj

Migracja to proces przyrostowy, który koncentruje się na przeniesieniu, testowaniu i wdrażaniu aplikacji lub obciążeń w istniejącym obszarze cyfrowym.

**Minimalna sugerowane działania:**

- Migruj [Cost Management łańcucha narzędzi](./toolchain.md) z wstępnego wdrożenia do środowiska produkcyjnego.
- Aktualizacja dokumentu z instrukcjami dotyczącymi architektury i dystrybucja do kluczowych uczestników projektu.
- Opracowywanie materiałów edukacyjnych i dokumentacji, świadomości, zachęt i innych programów w celu ułatwienia wdrażania użytkowników.

**Potencjalne działania:**

- Zaimplementuj model ewidencjonowania aktywności w chmurze.
- Upewnij się, że budżety odzwierciedlają rzeczywiste wydatki w poszczególnych wydaniach i dostosowuje się w razie potrzeby.
- Monitoruj zmiany w planach budżetowych i Weryfikuj je w przypadku konieczności dodatkowych rejestracji.
- Zaktualizuj zmiany w dokumencie wytyczne dotyczące architektury w celu odzwierciedlenia rzeczywistych kosztów.

## <a name="operate-and-post-implementation"></a>Działanie i po wdrożeniu

Po zakończeniu transformacji zarządzanie i działania muszą być aktywne w przypadku naturalnego cyklu życia aplikacji lub obciążenia. Ta faza zarządzania terminem spłaty koncentruje się na działaniach, które często są stosowane po wdrożeniu rozwiązania, a cykl transformacji zaczyna się ustabilizować.

**Minimalna sugerowane działania:**

- Dostosuj [Cost Management łańcucha narzędzi](./toolchain.md) w zależności od zmieniających się potrzeb organizacji.
- Rozważ automatyzację wszelkich powiadomień i raportów, aby odzwierciedlić rzeczywiste wydatki.
- Udoskonalenie wytycznych dotyczących architektury w celu zaplanowania przyszłych procesów wdrażania.
- Przeprowadzaj okresowe przeglądy odnośnych zespołów, aby zapewnić ciągłe przestrzeganie wytycznych dotyczących architektury.

**Potencjalne działania:**

- Wykonaj kwartalne przeglądy biznesowe w chmurze, aby komunikować wartości dostarczane z firmą i powiązanymi kosztami.
- Dostosuj plany kwartalnie, aby odzwierciedlić zmiany w rzeczywistych wydatkach.
- Określ wyrównanie finansowe do&LS dla subskrypcji jednostek biznesowej.
- Co miesiąc Analizuj wartości poszczególnych uczestników i metody raportowania kosztów.
- Skoryguj nieużywane zasoby i ustal, czy są one kontynuowane.
- Wykrywaj niewłaściwe wyrównania i anomalie między planem a rzeczywistymi wydatkami.
- Zapoznaj się z zespołami wdrażania chmury i zespołem strategii chmurowej, aby zrozumieć i rozwiązać te anomalie.

## <a name="next-steps"></a>Następne kroki

Teraz, po zrozumieniu koncepcji ładu kosztów w chmurze, zapoznaj się z [najlepszymi rozwiązaniami dotyczącymi zarządzania kosztami](./best-practices.md) , aby znaleźć sposoby zredukowania ogólnych wydatków.

> [!div class="nextstepaction"]
> [Najlepsze rozwiązania związane z zarządzaniem kosztami](./best-practices.md)
