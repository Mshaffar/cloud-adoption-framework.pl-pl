---
title: Racjonalizacja chmury
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Zapoznaj się z opcjami, które są dostępne w celu racjonalizacji cyfrowego podpisywania.
author: BrianBlanchard
ms.author: brblanch
ms.date: 12/10/2018
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: plan
ms.custom: governance
ms.openlocfilehash: 40962b8c658c40e4a27e3c025bc42b3aa5acd0f3
ms.sourcegitcommit: 443c28f3afeedfbfe8b9980875a54afdbebd83a8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2019
ms.locfileid: "71023616"
---
# <a name="cloud-rationalization"></a>Racjonalizacja chmury

Racjonalizacja chmury to proces oceniania zasobów w celu ustalenia najlepszego sposobu migracji lub modernizacji każdego elementu zawartości w chmurze. Aby uzyskać więcej informacji na temat procesu racjonalizacji, zobacz [co to jest znak cyfrowy?](./index.md).

## <a name="rationalization-context"></a>Kontekst racjonalizacji

"Pięć RS racjonalizacji" wymienione w tym artykule jest świetnym sposobem na oznaczenie potencjalnego przyszłego stanu wszelkich obciążeń, które są uważane za kandydata w chmurze. Jednak ten proces etykietowania powinien być umieszczony w odpowiednim kontekście przed podjęciem próby racjonalizacji środowiska. Aby zapewnić ten kontekst, przejrzyj następujący mitów:

- **Omówienia W ten sposób można łatwo podejmować decyzje o racjonalizacji.** Dokładne racjonalizacja wymaga głębokiej znajomości obciążeń i skojarzonych zasobów (aplikacji, maszyn wirtualnych i danych). Najważniejsze decyzje podejmowane są z dokładnością. Zalecamy korzystanie z [procesu racjonalizacji przyrostowej](./rationalize.md#incremental-rationalization).

- **Omówienia Wdrażanie w chmurze musi oczekiwać na uzasadnienie wszystkich obciążeń.** Racjonalizacja całego portfolio IT lub nawet jednego centrum danych może opóźnić realizację wartości biznesowej według miesięcy lub nawet lat. W miarę możliwości należy unikać pełnej racjonalizacji. Zamiast tego należy użyć [mocy 10 podejścia do wydania planowania](./rationalize.md#release-planning) , aby podejmować odpowiednie decyzje dotyczące kolejnych 10 obciążeń, które są styczeń na potrzeby wdrażania w chmurze.

- **Omówienia Uzasadnienie biznesowe musi oczekiwać na uzasadnienie wszystkich obciążeń.** Aby opracować uzasadnienie biznesowe dla wysiłku związanego z wdrażaniem w chmurze, należy wprowadzić kilka podstawowych założeń na poziomie portfela. Gdy motywacje są wyrównane do innowacyjności, założono, że architektura zostanie wdrożona. Gdy motywacje są wyrównane do migracji, założono, że rehosty. Te założenia mogą przyspieszyć proces uzasadnienia biznesowego. Założenia są następnie zakwestionowane i budżety są udoskonalane w fazie oceny poszczególnych cykli wdrażania obciążeń.

Zapoznaj się z poniższą piątą z pięciu usprawnień, aby zaznajomić się z długoterminowym procesem. Podczas opracowywania planu wdrażania w chmurze wybierz opcję, która najlepiej odpowiada Twoim potrzebom, rezultatom biznesowym i bieżącemu środowisku stanu. Celem na potrzeby racjonalizacji cyfrowej jest ustawienie linii bazowej, a nie podniesienia poziomu każdego obciążenia.

## <a name="the-five-rs-of-rationalization"></a>Pięć pięciu usprawnień

Pięć z pięciu usprawnień, które są wymienione w tym miejscu, opisują najbardziej typowe opcje racjonalizacji.

## <a name="rehost"></a>Ponowne hostowanie

Również w przypadku migracji "wind i Shift" przenoszone jest bieżący zasób stanu do wybranego dostawcy chmury z minimalną zmianą ogólnej architektury.

Typowe sterowniki mogą obejmować:

- Redukowanie wydatków inwestycyjnych
- Zwalnianie miejsca w centrum danych
- Osiąganie szybkiego powrotu do inwestycji w chmurze

Czynniki analizy ilościowej:

- Rozmiar maszyny wirtualnej (procesor, pamięć, magazyn)
- Zależności (ruch sieciowy)
- Zgodność zasobów

Czynniki analizy jakościowej:

- Tolerancja zmiany
- Priorytety biznesowe
- Krytyczne zdarzenia biznesowe
- Zależności procesów

## <a name="refactor"></a>Refaktoryzacja

Opcje platforma jako usługa (PaaS) umożliwiają zmniejszenie kosztów operacyjnych skojarzonych z wieloma aplikacjami. Dobrym pomysłem jest nieznacznie Refaktoryzacja aplikacji do modelu opartego na PaaS.

"Refaktoryzacja" odnosi się również do procesu tworzenia aplikacji w kodzie refaktoryzacji, aby umożliwić aplikacji dostarczanie nowych możliwości biznesowych.

Typowe sterowniki mogą obejmować:

- Szybsze i krótsze aktualizacje
- Przenośność kodu
- Większa wydajność chmury (zasoby, szybkość, koszt)

Czynniki analizy ilościowej:

- Rozmiar zasobu aplikacji (procesor CPU, pamięć, magazyn)
- Zależności (ruch sieciowy)
- Ruch użytkownika (wyświetlenia stron, czas na stronie, czas ładowania)
- Platforma programistyczna (Języki, platforma danych, usługi warstwy środkowej)

Czynniki analizy jakościowej:

- Dalsze inwestycje biznesowe
- Opcje i osie czasu
- Zależności procesów firmy

## <a name="rearchitect"></a>Ponowne ustalenie architektury

Niektóre aplikacje przedawniania nie są zgodne z dostawcami chmury ze względu na decyzje dotyczące architektury, które zostały wykonane podczas kompilowania aplikacji. W takich przypadkach może być konieczne ponowne zaprojektowanie aplikacji przed przekształceniem.

W innych przypadkach aplikacje, które są zgodne z chmurą, ale nie są natywne w chmurze, mogą powodować wzrost kosztów i efektywność operacyjną dzięki ponownemu tworzeniu architektury rozwiązania w aplikacji natywnej w chmurze.

Typowe sterowniki mogą obejmować:

- Skalowanie i elastyczność aplikacji
- Łatwiejsze wdrażanie nowych możliwości chmury
- Mieszanie stosów technologicznych

Czynniki analizy ilościowej:

- Rozmiar zasobu aplikacji (procesor CPU, pamięć, magazyn)
- Zależności (ruch sieciowy)
- Ruch użytkownika (wyświetlenia stron, czas na stronie, czas ładowania)
- Platforma programistyczna (Języki, platforma danych, usługi warstwy środkowej)

Czynniki analizy jakościowej:

- Rosnące inwestycje biznesowe
- Koszty operacyjne
- Potencjalni pętle opinii i DevOps inwestycje.

## <a name="rebuild"></a>Kompiluj ponownie

W niektórych scenariuszach różnica, którą należy przezwyciężyć w celu przeniesienia aplikacji, może być zbyt duża, aby uzasadnić dalsze inwestycje. Jest to szczególnie ważne w przypadku aplikacji, które wcześniej spełniały potrzeby biznesowe, ale są teraz nieobsługiwane lub nieprawidłowo wyrównane z bieżącymi procesami biznesowymi. W takim przypadku tworzony jest nowy podstawowy kod, który będzie wyrównany z podejściem natywnym w [chmurze](https://azure.microsoft.com/overview/cloudnative) .

Typowe sterowniki mogą obejmować:

- Przyspieszaj wprowadzanie innowacji
- Szybsze tworzenie aplikacji
- Zmniejsz koszty operacyjne

Czynniki analizy ilościowej:

- Rozmiar zasobu aplikacji (procesor CPU, pamięć, magazyn)
- Zależności (ruch sieciowy)
- Ruch użytkownika (wyświetlenia stron, czas na stronie, czas ładowania)
- Platforma programistyczna (Języki, platforma danych, usługi warstwy środkowej)

Czynniki analizy jakościowej:

- Odrzucanie zadowolenia użytkowników końcowych
- Procesy biznesowe ograniczone przez funkcje
- Potencjalny koszt, doświadczenie lub zyski z przychodów

## <a name="replace"></a>Replace

Rozwiązania są zwykle implementowane przy użyciu najlepszej technologii i metody dostępnej w danym momencie. Czasami aplikacje SaaS (Software as a Service) mogą zapewnić wszystkie niezbędne funkcje aplikacji hostowanej. W tych scenariuszach obciążenie może zostać zaplanowane do przyszłego zastąpienia, co skutecznie eliminuje je z wysiłku transformacji.

Typowe sterowniki mogą obejmować:

- Standaryzacja z najlepszymi praktykami branżowymi
- Przyspieszanie wdrażania podejścia sterowanego procesami biznesowymi
- Zmiana alokacji inwestycji programistycznych na aplikacje, które tworzą zróżnicowane lub zalety konkurencji

Czynniki analizy ilościowej:

- Ogólne redukcje kosztów operacyjnych
- Rozmiar maszyny wirtualnej (procesor, pamięć, magazyn)
- Zależności (ruch sieciowy)
- Zasoby do wycofania

Czynniki analizy jakościowej:

- Analiza kosztów związanych z bieżącą architekturą w porównaniu z rozwiązaniem SaaS
- Mapy procesów firmy
- Schematy danych
- Procesy niestandardowe lub zautomatyzowane

## <a name="next-steps"></a>Następne kroki

Zbiorczo można zastosować te pięć informacji o racjonalizacji do cyfr cyfrowych, aby ułatwić podejmowanie decyzji o racjonalizacji w przyszłości.

> [!div class="nextstepaction"]
> [Co to jest znak cyfrowy?](./index.md)