---
title: Decyzje, które mają wpływ na migracje
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Ważne decyzje dotyczące procesu migracji
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 4bc84ad8bd2d0a0521399c1762585db6f9a5a6ab
ms.sourcegitcommit: 443c28f3afeedfbfe8b9980875a54afdbebd83a8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2019
ms.locfileid: "71025413"
---
# <a name="decisions-that-affect-migrations"></a>Decyzje, które mają wpływ na migracje

Podczas migracji występuje kilka czynników wpływających na decyzje i działania związane z realizacją. W tym artykule wyjaśniono główną motywację tych decyzji i przedstawiono kilka pytań dotyczących zasad migracji w tej sekcji wskazówek dotyczących struktury wdrażania chmury.

## <a name="business-outcomes"></a>Wyniki biznesowe

Cel każdego procesu wdrożenia może mieć znaczny wpływ na sugerowane podejście do jego wykonania.

- **Migracja** Pilne czynniki biznesowe, szybkość wdrażania lub oszczędności kosztów to przykłady wyników operacyjnych. Te wyniki mają kluczowe znaczenie dla wysiłków, które przekształcają przejściowe zmiany w infrastrukturze IT lub modelach operacyjnych w wartość biznesową. Sekcja Migracja struktury wdrażania chmury skupia się w dużym stopniu na wynikach biznesowych związanych z migracją.
- **Innowacje w zakresie aplikacji** Poprawa jakości obsługi klienta oraz rosnący udział w rynku to przykłady wyników przyrostowych. Te wyniki są skutkiem kolekcji zmian przyrostowych ukierunkowanych na potrzeby i wymagania bieżących klientów.
- **Innowacje oparte na danych** Nowe produkty lub usługi, a w szczególności te, które są oparte na danych, są przykładami wyników zakłócających. Te wyniki są skutkiem eksperymentów i prognoz z wykorzystaniem danych w celu zakłócenia status quo na rynku.

Każda firma chce uzyskiwać wiele takich wyników. Bez działań nie ma klientów i odwrotnie. Wdrażanie chmury nie różni się pod tym względem. Firmy często pracują nad osiągnięciem każdego z tych wyników, ale próbują skupić się na wszystkich jednocześnie, co powoduje zbytnie rozproszenie wysiłków i spowalnia postęp prac, które mogą być najbardziej korzystne dla firmy.

To wymaganie wstępne nie jest zaleceniem, aby wybrać jeden z tych trzech celów, a jedynie ma na celu ułatwienie zespołowi strategicznemu ds. chmury i zespołowi wdrożeniowemu ds. chmury określenie zestawu priorytetów operacyjnych, którymi należy kierować się podczas wykonywania migracji w ciągu następnych trzech do sześciu miesięcy. Te priorytety należy określić przez uporządkowanie tych opcji w kolejności od *najważniejszej* do *najmniej ważnej* w odniesieniu do nakładu pracy, który ten zespół może wykonać w ciągu następnego kwartału lub dwóch.

### <a name="acting-on-migration-outcomes"></a>Działania w kierunku osiągnięcia wyników migracji

Jeśli wyniki operacyjne mają najwyższy priorytet na liście, ta sekcja struktury wdrażania chmury będzie odpowiednia dla Twojego zespołu. W tej sekcji założono, że konieczna jest priorytetyzacja szybkości i oszczędności kosztów jako kluczowych wskaźników wydajności (KPI), co sprawia, że model migracji do wdrożenia jest zgodny z wynikami. Model skoncentrowany na migracji jest w dużym stopniu oparty na migracji metodą „lift-and-shift” zasobów infrastruktury jako usługi (IaaS) w celu usunięcia zasobów z centrum danych i uzyskania oszczędności kosztów. W takim modelu może mieć miejsce modernizacja, ale jest ona drugorzędnym celem, dopóki nie zostanie zrealizowana główna misja migracji.

### <a name="acting-on-application-innovations"></a>Działania w kierunku innowacji dotyczących aplikacji

Jeśli udział w rynku i jakość obsługi klienta są głównymi celami, ta sekcja struktury wdrażania chmury może nie być najlepszym przewodnikiem dla wysiłków Twoich zespołów. Innowacje dotyczące aplikacji wymagają planu skoncentrowanego na modernizacji i przeniesieniu obciążeń, niezależnie od podstawowej infrastruktury. W takim przypadku wskazówki zawarte w tej sekcji mogą zawierać istotne informacje, ale mogą nie być najlepszym podejściem do podejmowania kluczowych decyzji.

### <a name="acting-on-data-innovations"></a>Działania w kierunku innowacji dotyczących danych

Jeśli dane, eksperymentowanie, badania i rozwój lub nowe produkty są priorytetem w ciągu następnych sześciu miesięcy, to nie jest to sekcja opisująca najodpowiedniejszą strukturę wdrażania chmury, którą należy się kierować podczas podejmowania wysiłków przez zespoły. W przypadku wszelkich wysiłków związanych z innowacjami dotyczącymi danych warto skorzystać ze wskazówek dotyczących migracji istniejących danych źródłowych. Jednak wysiłki powinny być skupione w szerszym zakresie na ruchu przychodzącym i integracji dodatkowych źródeł danych. Rozszerzenie tych wskazówek o prognozy i nowe środowiska jest znacznie ważniejsze niż migracja zasobów IaaS.

## <a name="balancing-the-portfolio"></a>Równoważenie portfolio

W tej sekcji opisującej strukturę wdrażania chmury przedstawiono teoretyczne rozwiązania, aby pomóc czytelnikom zrozumieć różne podejścia do zmian w ramach zrównoważonego portfolio. Artykuł dotyczący [równoważenia portfolio](../../expanded-scope/balance-the-portfolio.md) jest jednym z przykładów rozszerzonego zakresu w celu ułatwienia realizacji tej teorii.

## <a name="effort"></a>Nakład pracy

Nakład pracy związany z migracją może się znacznie różnić w zależności od rozmiaru i złożoności obciążeń. Migracja mniejszych obciążeń obejmująca kilkaset maszyn wirtualnych jest procesem taktycznym, który można zaimplementować przy użyciu zautomatyzowanych narzędzi, takich jak usługa [Azure Migrate](https://docs.microsoft.com/azure/migrate/migrate-overview). Z kolei migracja dużego przedsiębiorstwa obejmująca setki tysięcy obciążeń wymaga wysoce strategicznego procesu i może być związana z szeroko zakrojoną refaktoryzacją, przebudową i zastępowaniem istniejących aplikacji integrujących możliwości platformy jako usługi (PaaS) oraz oprogramowania jako usługi (SaaS). [Identyfikacja i zrównoważenie zakresu](../../expanded-scope/balance-the-portfolio.md) planowanych migracji ma krytyczne znaczenie.

Przed podjęciem jakichkolwiek decyzji, które mogą mieć długoterminowy wpływ na bieżący program migracji, należy koniecznie osiągnąć porozumienie dotyczące następujących decyzji.

### <a name="effort-type"></a>Typ nakładu pracy

W przypadku migracji o dużej skali (> 250 maszyn wirtualnych) zasoby są migrowane przy użyciu różnych opcji przenoszenia, które omówiono w pięciu zasadach racjonalizacji: *ponowne hostowanie*, *refaktoryzacja*, *zmiana architektury*, *przebudowa* i *zastąpienie*.

Niektóre obciążenia są modernizowane w ramach procesu *przebudowy* lub *zmiany architektury*, co umożliwia utworzenie nowocześniejszych aplikacji z nowymi funkcjami i możliwościami technicznymi. Inne zasoby podlegają procesowi *refaktoryzacji*, na przykład są przenoszone do kontenerów lub innych nowocześniejszych rozwiązań hostingu i operacji, które nie muszą mieć wpływu na bazę kodu rozwiązania. Często maszyny wirtualne i inne lepiej ugruntowane zasoby podlegają procesowi *ponownego hostowania*, który polega na przeniesieniu tych zasobów z centrum danych do chmury. Niektóre obciążenia mogą być potencjalnie migrowane do chmury, ale zamiast tego należy je *zastąpić* przy użyciu usług w chmurze opartych na usługach (SaaS), które spełniają te same potrzeby biznesowe, na przykład korzystając z pakietu Office 365 jako alternatywy dla migrowania wystąpień programu Exchange Server.

W większości scenariuszy pewne zdarzenie biznesowe wymusza tymczasową migrację zasobów w ramach procesu *ponownego hostowania*, po którym następuje bardziej istotne dodatkowe przejście z zastosowaniem jednej z innych strategii migracji po przeniesieniu do chmury. Ten proces jest często nazywany *przeniesieniem do chmury*.

Podczas procesu [racjonalizacji majątku cyfrowego](../../../digital-estate/calculate.md) te typy decyzji są stosowane do każdego zasobu przeznaczonego do migracji. Jednak wymaganiem wstępnym na tym etapie jest przyjęcie założenia bazowego. Która z tych pięciu strategii migracji jest najbardziej zgodna z celami biznesowymi lub wynikam biznesowymi tego wysiłku związanego z migracją? Ta decyzja stanowi założenie przewodnie podczas całej migracji.

### <a name="effort-scale"></a>Skala nakładu pracy

Skala migracji to kolejna ważna decyzja należąca do wymagań wstępnych. Procesy wymagane do migrowania 1000 zasobów różnią się od procesu wymaganego do przeniesienia 10 000 zasobów. Przed rozpoczęciem jakiejkolwiek migracji należy odpowiedzieć na następujące pytania:

- **Ile zasobów obsługują obecnie migrowane obciążenia?** Zasoby obejmują struktury danych, aplikacje, maszyny wirtualne i niezbędne urządzenia IT. Zalecamy wybranie stosunkowo małego obciążenia jako pierwszego kandydata do migracji.
- **Ile z tych zasobów obejmuje plan migracji?** Często działanie pewnej części zasobów zostaje zakończone w ramach procesu migracji, z powodu braku stałej zależności użytkowników końcowych.
- **Jaka jest szacowana z góry skala zasobów do zmigrowania?** W przypadku obciążeń przeznaczonych do migracji należy oszacować liczbę zasobów pomocniczych, takich jak aplikacje, maszyny wirtualne, źródła danych i urządzenia IT. Zapoznaj się z sekcją dotyczącą [majątku cyfrowego](../../../digital-estate/index.md) w strukturze wdrażania chmury, aby uzyskać wskazówki dotyczące identyfikowania odpowiednich zasobów.

### <a name="effort-timing"></a>Harmonogram prac

Często migracje są spowodowane ważnym zdarzeniem biznesowym, które jest zależne od czasu. Na przykład częstą motywacją jest zakończenie lub odnowienie kontraktu hostingu innej firmy. Mimo że wiele potencjalnych zdarzeń biznesowych wymaga migracji, mają one jedną wspólną cechę: datę zakończenia. Ważne jest zrozumienie harmonogramu zdarzeń biznesowych, aby móc prawidłowo planować i weryfikować działania.

## <a name="recap"></a>Podsumowanie

Przed kontynuowaniem należy udokumentować następujące założenia i udostępnić je zespołowi strategicznemu ds. chmury i zespołom wdrożeniowym ds. chmury:

- wyniki biznesowe,
- role. Zostaną one udokumentowane i ulepszone w ramach procesów *oceny*, *migracji*, *optymalizacji* oraz *zabezpieczenia i zarządzania*.
- Definicja gotowości Zostanie ona udokumentowana i ulepszona oddzielnie dla procesów *oceny*, *migracji*, *optymalizacji* oraz *zabezpieczenia i zarządzania* w ramach migracji.
- Typ nakładu pracy
- Skala nakładu pracy
- Harmonogram prac

## <a name="next-steps"></a>Następne kroki

Po zrozumieniu tego procesu przez zespół należy zapoznać się z wstępnymi wymaganiami technicznymi. [Lista kontrolna planowania migracji](./planning-checklist.md) pomaga zapewnić gotowość podstawowych elementów technicznych do migracji.

Po zrozumieniu tego procesu przez zespół należy zapoznać się z wstępnymi wymaganiami technicznymi. [Lista kontrolna planowania migracji] pomaga zapewnić gotowość podstawowej infrastruktury technicznej do migracji.

> [!div class="nextstepaction"]
> [Zapoznaj się z listą kontrolną planowania migracji](./planning-checklist.md)