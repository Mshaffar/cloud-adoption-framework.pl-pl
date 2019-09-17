---
title: 'Migracja komputera mainframe: Przełączenie z komputerów mainframe na platformę Azure'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Migruj aplikacje ze środowisk mainframe na platformę Azure dla systemów, które są aktualnie uruchomione na komputerach mainframe.
author: njray
ms.author: v-nanra
ms.date: 12/26/2018
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 00b2ee80709c36658a58f23b2848fdf1b64d856d
ms.sourcegitcommit: 443c28f3afeedfbfe8b9980875a54afdbebd83a8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2019
ms.locfileid: "71024379"
---
# <a name="make-the-switch-from-mainframes-to-azure"></a>Przełączenie z komputerów mainframe na platformę Azure

Jako alternatywną platformę do uruchamiania tradycyjnych aplikacji typu mainframe platforma Azure oferuje duże możliwości skalowania i magazynowania w środowisku o wysokiej dostępności. Uzyskasz wartość i elastyczność nowoczesnej platformy opartej na chmurze bez kosztów związanych ze środowiskiem mainframe.

Ta sekcja zawiera wskazówki techniczne dotyczące tworzenia przełącznika z platformy mainframe na platformie Azure.

![Mainframe i Azure](../../_images/mainframe-migration/make-the-switch.png)

## <a name="mips-vs-vcpus"></a>MIPS a procesorów wirtualnych vCPU

Nie istnieje żadna formuła mapowania uniwersalnego, która pozwala określić liczbę wirtualnych jednostek przetwarzania (procesorów wirtualnych vCPU), które są konieczne do uruchamiania obciążeń mainframe. Jednak Metryka miliona instrukcji na sekundę (MIPS) jest często mapowana na procesorów wirtualnych vCPU na platformie Azure. MIPS mierzy ogólną moc obliczeniową komputera mainframe, dostarczając stałą wartość liczby cykli na sekundę dla danej maszyny.

Mała organizacja może wymagać mniej niż 500 MIPS, podczas gdy duża organizacja zazwyczaj używa ponad 5 000 MIPS. W $1 000 na pojedynczy MIPS, Duża organizacja poświęca około $5 000 000 rocznie na wdrożenie infrastruktury 5 000-MIPS. Szacowany koszt roczny dla typowego wdrożenia platformy Azure w tej skali to około 1 dziesiąty kosztu infrastruktury MIPS. Aby uzyskać szczegółowe informacje, zobacz tabela 4 [w sztuczna mainframe na platformie Azure. Oficjalny](https://azure.microsoft.com/resources/demystifying-mainframe-to-azure-migration) dokument dotyczący migracji.

Dokładne Obliczanie MIPS procesorów wirtualnych vCPU z platformą Azure zależy od typu vCPU i dokładnego obciążenia, które jest uruchomione. Jednak badania porównawcze zapewniają dobrą podstawę do oszacowania liczby i typu procesorów wirtualnych vCPU. Ostatni wzorzec HPE zREF zapewnia następujące oszacowania:

- 288 MIPS dla procesorów opartych na procesorze Intel, działających na serwerach HP ProLiant na potrzeby zadań online (CICS).

- 170 MIPS na procesor Intel Core dla zadań wsadowych COBOL.

Ten przewodnik szacuje 200 MIPS na vCPU do przetwarzania online i 100 MIPS na vCPU na potrzeby przetwarzania wsadowego.

> [!NOTE]
> Te oszacowania mogą ulec zmianie, ponieważ nowa seria maszyn wirtualnych staje się dostępna na platformie Azure.

## <a name="high-availability-and-failover"></a>Wysoka dostępność i tryb failover

Systemy mainframe często oferują pięć 9 dostępności (99,999 procent), gdy są używane sprzężenia mainframe i równoległe Sysplex. Jeszcze operatory systemu nadal muszą zaplanować przestoje w zakresie konserwacji i początkowych obciążeń programu (IPLs). Rzeczywista dostępność podejścia do dwóch lub trzech 9ów jest porównywalna z serwerami opartymi na architekturze Intel.

Dzięki porównaniu z tym, platforma Azure oferuje umowy dotyczące poziomu usług (umowy SLA) oparte na zobowiązaniach, które są domyślne, zoptymalizowane z użyciem lokalnej lub geograficznie replikacji usług.

Platforma Azure zapewnia dodatkową dostępność poprzez replikowanie danych z wielu urządzeń magazynujących lokalnie lub w innych regionach geograficznych. W przypadku awarii opartych na platformie Azure zasoby obliczeniowe mogą uzyskać dostęp do replikowanych danych na poziomie lokalnym lub regionalnym.

W przypadku używania zasobów platformy Azure jako usługi (PaaS), takich jak [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) i [Azure Cosmos Database](https://docs.microsoft.com/azure/cosmos-db/introduction), platforma Azure może automatycznie obsłużyć tryb failover. Gdy korzystasz z usługi Azure Infrastructure as (IaaS), tryb failover zależy od określonych funkcji systemu, takich jak SQL Server zawsze włączona funkcja, wystąpienia klastra trybu failover i grupy dostępności.

## <a name="scalability"></a>Skalowalność

Komputery mainframe zazwyczaj skalują w górę, a środowiska chmury skalują w poziomie. Komputery mainframe można skalować w poziomie przy użyciu funkcji sprzęgania (CF), ale wysokie koszty sprzętu i magazynu sprawia, że Komputery mainframe są kosztowne do skalowania w poziomie.

CF również oferuje ściśle sprzężone obliczenia, podczas gdy funkcje skalowania w poziomie platformy Azure są luźno powiązane. Chmurę można skalować w górę lub w dół, aby dopasować dokładne specyfikacje użytkownika, przy użyciu możliwości obliczeniowych, magazynu i usług skalowania na żądanie w ramach modelu rozliczania opartego na użyciu.

## <a name="backup-and-recovery"></a>Tworzenie i przywracanie kopii zapasowych

Komputery mainframe zwykle utrzymują Lokacje odzyskiwania po awarii lub wykorzystują lub niezależnym dostawcą systemu mainframe w przypadku awarii awaryjnych. Synchronizacja z lokacją odzyskiwania po awarii zazwyczaj odbywa się za pomocą kopii danych w trybie offline. Obie opcje ponoszą wysokie koszty.

Zautomatyzowana nadmiarowość geograficzna jest również dostępna za pomocą funkcji sprzęgu komputera mainframe, chociaż z dużym obciążeniem i jest zazwyczaj zarezerwowana dla systemów o znaczeniu krytycznym. W przeciwieństwie do systemu Azure dostępne są łatwe w implementacji i ekonomiczne opcje [tworzenia kopii zapasowych](https://docs.microsoft.com/azure/backup/backup-introduction-to-azure-backup), [odzyskiwania](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)i [nadmiarowości](https://docs.microsoft.com/azure/storage/common/storage-redundancy) na poziomach lokalnym lub regionalnym lub za pośrednictwem nadmiarowości geograficznej.

## <a name="storage"></a>Magazyn

Część opisująca, jak działa mainframe, polega na dekodowania różnych nakładających się warunków. Na przykład Magazyn centralny, pamięć rzeczywista, rzeczywiste magazyn i główny magazyn ogólnie odnoszą się do magazynu dołączonego bezpośrednio do procesora mainframe.

Sprzęt mainframe obejmuje procesory i wiele innych urządzeń, takich jak urządzenia magazynujące bezpośredniego dostępu (DASDs), stacje taśm magnetycznych i kilka typów konsol użytkownika. Taśmy i DASDs są używane na potrzeby funkcji systemowych i programów użytkownika.

Typy magazynów fizycznych dla komputerów mainframe obejmują:

- **Magazyn centralny:** Zlokalizowane bezpośrednio na procesorze mainframe, jest to również nazywane procesorem lub rzeczywistym magazynem.
- **Magazyn pomocniczy:** W odróżnieniu od komputera mainframe ten typ obejmuje magazyn w systemie DASDs i jest nazywany magazynem stronicowania.

Chmura oferuje szereg elastycznych, skalowalnych opcji i płacisz tylko za te opcje, które są potrzebne. Usługa [Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction) oferuje wysoce skalowalny magazyn obiektów dla obiektów danych, usługę systemu plików dla chmury, niezawodny magazyn komunikatów i Magazyn NoSQL. W przypadku maszyn wirtualnych dyski zarządzane i niezarządzane zapewniają trwały, bezpieczny magazyn dyskowy.

## <a name="mainframe-development-and-testing"></a>Tworzenie i testowanie komputerów mainframe

Głównym sterownikiem w projektach migracji mainframe jest zmiana sposobu tworzenia aplikacji. Organizacje chcą, aby środowisko programistyczne było bardziej elastyczne i odpowiadać wymaganiom biznesowym.

Komputery mainframe zazwyczaj mają oddzielne partycje logiczne (LPARs) do tworzenia i testowania, takie jak pytań i odpowiedzi LPARs. Rozwiązania deweloperskie obejmują kompilatory (COBOL, PL/I, asembler) i edytorów. Najbardziej typowym jest funkcja interaktywnej produktywności systemu (ISPF) dla systemu operacyjnego z/OS, który działa na mainframe firmy IBM. Inne obejmują narzędzia programistyczne ROSCOE (RPF) i Computer Associates Tools, takie jak bibliotekarza CA i CA-Panvalet.

Środowiska emulacji i kompilatory są dostępne na platformach x86, dlatego projektowanie i testowanie mogą być zazwyczaj między pierwszymi obciążeniami do migracji z komputera mainframe na platformę Azure. Dostępność i szerokie użycie [narzędzi DevOps na platformie Azure](https://azure.microsoft.com/solutions/devops) przyspiesza migrację środowisk deweloperskich i testowych.

Gdy rozwiązania są opracowywane i testowane na platformie Azure i są gotowe do wdrożenia na komputerze mainframe, należy skopiować kod do komputera mainframe i skompilować go w tym miejscu.

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Migracja aplikacji mainframe](./application-strategies.md)