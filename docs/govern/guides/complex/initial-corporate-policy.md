---
title: 'Kompleksowe zarządzanie przedsiębiorstwami: wstępne zasady firmowe'
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby zdefiniować początkową sytuację ładu, ryzyko wczesnego etapu, wstępne instrukcje zasad i procesy wczesnego wymuszania.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/05/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 9dbbf67fcd303803a110b49b803698eea2c37687
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83220145"
---
# <a name="governance-guide-for-complex-enterprises-initial-corporate-policy-behind-the-governance-strategy"></a>Przewodnik dotyczący zarządzania złożonymi przedsiębiorstwami: wstępne zasady firmowe związane z strategią ładu

Poniższe zasady korporacyjne określają początkową pozycję ładu, która jest punktem początkowym tego przewodnika. Ten artykuł definiuje wczesne zagrożenia, wstępne instrukcje zasad i wczesne procesy w celu wymuszenia instrukcji zasad.

> [!NOTE]
>Zasady firmowe nie są dokumentem technicznym, ale obejmują wiele decyzji technicznych. SPECJALISTa z ładu, opisany w [przeglądzie](./index.md) , ostatecznie pochodzi z tych zasad. Przed wdrożeniem programu MVP (ładu) organizacja powinna opracować zasady firmowe na podstawie własnych celów i ryzyka biznesowego.

## <a name="cloud-governance-team"></a>Zespół nadzorujący chmury

CIO ostatnio posiadała spotkanie z zespołem nadzoru IT, aby zrozumieć historię danych osobowych i zasad o znaczeniu krytycznym, a następnie zapoznać się ze skutkem zmiany tych zasad. CIO również omawiać ogólny potencjał chmury dla IT i firmy.

Po spotkaniu dwóch członków zespołu nadzoru IT zażądało uprawnień do badania i wspierania wysiłków związanych z planowaniem chmury. Rozpoznanie potrzeby zarządzania i możliwości jego ograniczenia w tle, dyrektor ds. zarządzania IT obsługuje ten pomysł. Dzięki temu zespół ds. zarządzania chmurą został urodzony. W ciągu następnych kilku miesięcy dziedziczą one czyszczenie wielu błędów wykonanych podczas eksploracji w chmurze z perspektywy ładu. Spowoduje to zdobycie monikera _powierników w chmurze_. W kolejnych iteracjach ten przewodnik pokazuje, jak ich role zmieniają się wraz z upływem czasu.

[!INCLUDE [business-risk](../../../../includes/business-risks.md)]

## <a name="tolerance-indicators"></a>Wskaźniki tolerancji

Aktualna tolerancja ryzyka jest wysoka i akceptowalnego poziomu do inwestowania w zarządzanie chmurą jest niska. W związku z tym wskaźniki tolerancji działają jako system wczesnego ostrzegania, aby wyzwolić inwestycje czasu i energii. W przypadku przestrzegania następujących wskaźników warto postępować zgodnie z strategią ładu.

- **Zarządzanie kosztami:** Skalowanie wdrożenia przekracza 1 000 zasobów do chmury, a miesięczne wydatki przekraczają $10 000 USD miesięcznie.
- **Linia bazowa tożsamości:** Dołączanie aplikacji ze starszymi lub wieloskładnikowymi wymaganiami usługi uwierzytelnianie wieloskładnikowe.
- **Linia bazowa zabezpieczeń:** Uwzględnianie chronionych danych w zdefiniowanych planach wdrożenia chmury.
- **Spójność zasobów:** Uwzględnianie wszystkich aplikacji o znaczeniu krytycznym w określonych planach wdrożenia chmury.

[!INCLUDE [policy-statements](../../../../includes/policy-statements.md)]

## <a name="next-steps"></a>Następne kroki

Te zasady firmowe przygotowuje zespół nadzorujący chmurę do wdrożenia programu ładu MVP jako podstawy do przyjęcia. Następnym krokiem jest zaimplementowanie tego programu MVP.

> [!div class="nextstepaction"]
> [Objaśniono najlepsze rozwiązania](./prescriptive-guidance.md)
