---
title: Procesy zgodności zasad przyspieszenia wdrożenia
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby poznać podejście do tworzenia procesów, które obsługują dyscyplinę zarządzania wdrożeniem.
author: alexbuckgit
ms.author: abuck
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 4850fe8377c642ae7af2c763ee28c13d90f25b61
ms.sourcegitcommit: 9a84c2dfa4c3859fd7d5b1e06bbb8549ff6967fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "83754982"
---
# <a name="deployment-acceleration-policy-compliance-processes"></a>Procesy zgodności zasad przyspieszenia wdrożenia

W tym artykule omówiono podejście do procesów związanych z podwyższeniem poziomu zasad, które regulują [dyscyplinę wdrażania](./index.md). Skuteczne zarządzanie konfiguracją chmury rozpoczyna się od cyklicznych procesów ręcznych zaprojektowanych w celu wykrywania problemów i nakładania zasad w celu skorygowania ryzyka. Można zautomatyzować te procesy i uzupełnienie, aby zmniejszyć koszty zarządzania i umożliwić szybsze reagowanie na odchylenia.

## <a name="planning-review-and-reporting-processes"></a>Planowanie, przeglądanie i raportowanie procesów

Najlepsze narzędzia do przyspieszania wdrażania w chmurze są takie same jak w przypadku procesów i zasad, które są przez nie obsługiwane. Poniżej znajduje się zestaw przykładowych procesów często używanych jako część przyspieszenia wdrożenia. Użyj tych przykładów jako punktu wyjścia podczas planowania procesów, które umożliwią dalszą aktualizację wdrożenia i zasad konfiguracji na podstawie zmian w firmie i informacji zwrotnych z rozwoju i zespołów IT odpowiedzialnych za włączenie wytycznych ładu do działania.

**Wstępna ocena ryzyka i planowanie:** W ramach początkowego wdrażania dyscypliny wdrożenia należy określić podstawowe zagrożenia biznesowe i tolerancję związaną z wdrażaniem aplikacji firmowych. Te informacje służą do omówienia określonych zagrożeń technicznych związanych z członkami zespołu ds. operacji IT i opracowania bazowego zestawu zasad wdrażania i konfiguracji korygowaniem te zagrożenia w celu ustalenia wstępnej strategii zarządzania.

**Planowanie wdrożenia:** Przed wdrożeniem dowolnego elementu zawartości należy wykonać Przegląd zabezpieczeń i operacji w celu zidentyfikowania nowych zagrożeń i upewnienia się, że spełniono wszystkie wymagania dotyczące zasad związanych z wdrażaniem.

**Testowanie wdrożenia:** W ramach procesu wdrażania dowolnego elementu zawartości zespół nadzorujący chmury, we współpracy z zespołami ds. operacji IT, jest odpowiedzialny za przeglądanie zgodności zasad wdrażania.

**Planowanie roczne:** Przeprowadzenie rocznego przeglądu strategii przyspieszenia wdrożenia. Zapoznaj się z przyszłymi priorytetami firmowymi i zaktualizowanymi strategiami wdrażania chmury, aby zidentyfikować potencjalne zwiększenie ryzyka oraz inne nowe potrzeby i możliwości konfiguracji. Użyj tego czasu, aby zapoznać się z najnowszymi najlepszymi rozwiązaniami DevOps i zintegrować je z zasadami i przeglądać procesy.

**Kwartalne przeglądy i planowanie:** Przeprowadź kwartalną przegląd danych i raportów o zdarzeniach audytu operacyjnego, aby zidentyfikować zmiany wymagane w zasadach przyspieszenia wdrożenia. W ramach tego procesu zapoznaj się z bieżącymi najlepszymi rozwiązaniami DevOps i devtechops i zaktualizuj zasady zgodnie z potrzebami. Po zakończeniu przeglądu Dopasuj wskazówki dotyczące projektowania aplikacji i systemów ze zaktualizowanymi zasadami.

Ten proces planowania jest również dobrym terminem do oszacowania bieżącego członkostwa zespołu nadzoru w chmurze w celu uzyskania luk w wiedzy dotyczącej nowych lub zmienionych zasad i zagrożeń związanych z przyspieszeniem DevOps i wdrożeniem. Zaproś odpowiednich pracowników działu IT o uczestnictwo w recenzjach i planowaniu jako tymczasowych doradców technicznych lub stałych członków zespołu.

**Edukacja i szkolenia:** Co miesiąc, oferuj sesje szkoleniowe, aby upewnić się, że personel IT i deweloperzy są aktualne, zgodnie z najnowszą strategią i wymaganiami dotyczącymi przyspieszenia wdrażania. W ramach tego procesu zapoznaj się z dokumentacją, wskazówkami lub innymi aktywami szkoleniowymi, aby upewnić się, że są one zsynchronizowane z najnowszymi instrukcjami zasad obowiązującymi w firmie.

**Comiesięczne przeglądy audytu i raportowania:** Wykonaj comiesięczne inspekcje we wszystkich wdrożeniach w chmurze, aby zapewnić ciągły sposób wyrównania przy użyciu zasad konfiguracji. Przejrzyj działania związane z wdrażaniem z personelem działu IT i zidentyfikuj wszelkie problemy ze zgodnością, które nie zostały jeszcze obsłużone w ramach trwającego procesu monitorowania i wymuszania. Wynikiem tego przeglądu jest raport dotyczący zespołu strategii chmury i każdego zespołu wdrażania w chmurze w celu komunikowania się ogólnego przestrzegania zasad. Raport jest również przechowywany na potrzeby inspekcji i przepisów prawnych.

## <a name="processes-for-ongoing-monitoring"></a>Procesy do ciągłego monitorowania

Strategia przyspieszania wdrażania została zależała od widoczności do bieżącego i poprzedniego stanu infrastruktury chmurowej. Bez możliwości analizowania odpowiednich metryk i danych dotyczących kondycji i aktywności zasobów w chmurze nie można identyfikować zmian zagrożeń ani wykrywać naruszeń tolerancji ryzyka. Bieżące procesy zarządzania omówione powyżej wymagają danych dotyczących jakości, aby zapewnić możliwość modyfikacji zasad w celu ochrony infrastruktury przed zmianami zagrożeń i zagrożeń spowodowanymi błędami skonfigurowanymi zasobów.

Upewnij się, że zespoły operacyjne IT zaimplementowali zautomatyzowane systemy monitorowania dla infrastruktury chmurowej, które przechwytują odpowiednie dane dzienników potrzebne do oszacowania ryzyka. Można aktywnie monitorować te systemy w celu zapewnienia wykrywania monitów i łagodzenia potencjalnych naruszeń zasad oraz upewnić się, że strategia monitorowania jest zgodne z wymaganiami wdrożenia i konfiguracji.

## <a name="violation-triggers-and-enforcement-actions"></a>Wyzwalacze naruszenia i akcje wymuszania

Ze względu na to, że niezgodność z zasadami konfiguracji może prowadzić do krytycznych zagrożeń w usłudze, zespół nadzorujący chmury powinien mieć wgląd w poważne naruszenia zasad. Upewnij się, że personel działu IT ma jasne ścieżki eskalacji do raportowania problemów ze zgodnością konfiguracji z członkami zespołu nadzoru najlepiej dopasowane do identyfikacji i sprawdzenia, czy problemy z zasadami zostały skorygowane po wykryciu.

W przypadku wykrycia naruszeń należy podjąć akcje, aby szybko dostosować je za pomocą zasad najszybciej, jak to możliwe. Zespół IT może zautomatyzować większość wyzwalaczy naruszenia przy użyciu narzędzi opisanych w temacie [Acceleration Deployment łańcucha narzędzi for Azure](./toolchain.md).

Następujące wyzwalacze i akcje wymuszania zawierają przykłady, których można użyć podczas omawiania sposobu używania danych monitorowania do rozwiązywania naruszeń zasad:

- **Wykryto nieoczekiwane zmiany w konfiguracji.** W przypadku nieoczekiwanej zmiany konfiguracji zasobu należy skontaktować się z pracownikami działu IT i właścicielami obciążeń w celu zidentyfikowania głównej przyczyny i opracowania planu korygowania.
- **Konfiguracja nowych zasobów nie jest zgodna z zasadami.** Współpraca z zespołami DevOps i właścicielami obciążeń w celu sprawdzenia zasad przyspieszenia wdrożenia podczas uruchamiania projektu, dzięki czemu wszyscy użytkownicy będą zrozumieć odpowiednie wymagania dotyczące zasad.
- **Błędy wdrożenia lub problemy z konfiguracją powodują opóźnienia w harmonogramach projektu.** Pracuj z zespołami programistycznymi i właścicielami obciążeń, aby upewnić się, że zespół zrozumie, jak zautomatyzować wdrażanie zasobów opartych na chmurze pod kątem spójności i powtarzalności. W cyklu opracowywania, w pełni zautomatyzowane wdrożenia, powinny być wymagane na wczesnych cyklach programistycznych, &mdash; a w cyklu projektowania zwykle prowadzi do nieoczekiwanych problemów i opóźnień.

## <a name="next-steps"></a>Następne kroki

Użyj [szablonu dyscypliny wdrożenia](./template.md) , aby udokumentować procesy i wyzwalacze, które są wyrównane do bieżącego planu wdrożenia chmury.

Aby uzyskać wskazówki dotyczące wykonywania zasad zarządzania chmurą w wyrównaniu z planami wdrażania, zobacz [udoskonalanie dyscypliny wdrożenia](./discipline-improvement.md).

> [!div class="nextstepaction"]
> [Udoskonalenie ulepszeń wdrożenia](./discipline-improvement.md)
