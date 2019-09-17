---
title: 'Standardowa Przewodnik po przedsiębiorstwie: Poprawa chmury'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Standardowa Przewodnik po przedsiębiorstwie: Poprawa chmury'
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/05/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: d1953e190e2581d96db443be00aad74a6b94d5f9
ms.sourcegitcommit: 443c28f3afeedfbfe8b9980875a54afdbebd83a8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2019
ms.locfileid: "71030367"
---
# <a name="small-to-medium-enterprise-guide-multicloud-improvement"></a>Przewodnik po małych i średnich przedsiębiorstwach: Poprawa chmury

W tym artykule naliczą się opisy, dodając formanty do wdrożenia wielochmurowego.

## <a name="advancing-the-narrative"></a>Przesuwanie narracji

Firma Microsoft uznaje, że klienci przyjmują wiele chmur do określonych celów. Fikcyjny klient w tym przewodniku nie ma żadnego wyjątku. Równolegle z podróżą w zakresie wdrażania platformy Azure, sukces biznesowy doprowadził do nabycia małego, ale dodatkowej firmy. Firma pracuje nad wszystkimi swoimi operacjami IT na innym dostawcy chmury.

W tym artykule opisano, jak zmieniają się zmiany podczas integrowania nowej organizacji. Na potrzeby postanowień przyjęto, że firma Microsoft zakończyła wszystkie iteracje ładu opisane w tym przewodniku ładu.

### <a name="changes-in-the-current-state"></a>Zmiany w bieżącym stanie

W poprzedniej fazie tego przykładu firma rozpoczęła aktywnie wypychanie aplikacji produkcyjnych do chmury za pomocą potoków ciągłej integracji/ciągłego wdrażania.

Od tej pory zmieniono pewne zmiany, które wpłyną na nadzór:

- Tożsamość jest kontrolowana przez lokalne wystąpienie Active Directory. Tożsamość hybrydowa jest ułatwiona poprzez replikację do Azure Active Directory.
- Operacje IT lub operacje w chmurze są w dużej mierze zarządzane przez Azure Monitor i powiązane usługi Automation.
- Odzyskiwanie po awarii/ciągłość biznesowa jest kontrolowane przez wystąpienia magazynu Azure.
- Azure Security Center służy do monitorowania naruszeń zabezpieczeń i ataków.
- Azure Security Center i Azure Monitor są używane do monitorowania zarządzania chmurą.
- Plany platformy Azure, Azure Policy i grupy zarządzania platformy Azure są używane do automatyzowania zgodności z zasadami.

### <a name="incrementally-improve-the-future-state"></a>Przyrostowe ulepszanie stanu w przyszłości

Celem jest zintegrowanie firmy pozyskiwania z istniejącymi operacjami wszędzie tam, gdzie to możliwe.

## <a name="changes-in-tangible-risks"></a>Zmiany w materialnym ryzyku

**Koszt pozyskiwania przez firmę:** Nabycie nowej firmy szacuje się na zyskowność w ciągu około pięciu lat. Ze względu na powolnej częstotliwości powrotu tablica chce kontrolować koszty pozyskiwania, tak jak to możliwe. Istnieje ryzyko związane z kontrolą kosztów i integracją techniczną ze sobą.

To ryzyko biznesowe można rozszerzyć na kilka zagrożeń technicznych:

- Migracja w chmurze może spowodować dodatkowe koszty pozyskiwania.
- Nowe środowisko może nie być prawidłowo regulowane, co może spowodować naruszenia zasad.

## <a name="incremental-improvement-of-the-policy-statements"></a>Przyrostowe ulepszanie instrukcji zasad

Następujące zmiany zasad ułatwią skorygowanie nowych zagrożeń i implementacji przewodnika:

- Wszystkie zasoby w chmurze dodatkowej muszą być monitorowane za pomocą istniejących narzędzi do zarządzania operacyjnego i monitorowania zabezpieczeń.
- Wszystkie jednostki organizacyjne muszą być zintegrowane z istniejącym dostawcą tożsamości.
- Podstawowy dostawca tożsamości powinien zarządzać uwierzytelnianiem zasobów w chmurze pomocniczej.

## <a name="incremental-improvement-of-governance-practices"></a>Przyrostowe ulepszanie praktyk w zakresie zapewniania ładu

W tej części artykułu zostanie zmieniony projekt ładu MVP, który obejmuje nowe zasady platformy Azure i implementację Azure Cost Management. Te zmiany w projekcie zostaną spełnione w ramach nowych instrukcji dotyczących zasad firmowych.

1. Połącz sieci. Ten krok jest wykonywany przez zespoły ds. sieci i IT i obsługiwane przez zespół nadzorujący chmurę. Dodanie połączenia z dostawcy MPLS/dzierżawy do nowej chmury spowoduje integrację sieci. Dodanie tabel routingu i konfiguracji zapory umożliwi sterowanie dostępem i ruchem między środowiskami.
1. Konsolidowanie dostawców tożsamości. W zależności od obciążeń obsługiwanych w chmurze dodatkowej istnieje wiele opcji konsolidacji dostawców tożsamości. Poniżej przedstawiono kilka przykładów:
    1. W przypadku aplikacji, które uwierzytelniają się za pomocą protokołu OAuth 2, użytkownicy z Active Directory w chmurze pomocniczej mogą po prostu przeprowadzić replikację do istniejącej dzierżawy usługi Azure AD. Dzięki temu wszyscy użytkownicy mogą być uwierzytelniani w dzierżawie.
    1. W drugiej lokalizacji Federacja umożliwia jednostek organizacyjnych przepływ do Active Directory lokalnego, a następnie do wystąpienia usługi Azure AD.
1. Dodaj zasoby do Azure Site Recovery.
    1. Azure Site Recovery został zaprojektowany od początku jako narzędzie hybrydowe lub wielochmurowe.
    1. Maszyny wirtualne w chmurze pomocniczej mogą być chronione za pomocą tych samych Azure Site Recovery procesów, które są używane do ochrony zasobów lokalnych.
1. Dodaj zasoby do Azure Cost Management.
    1. Azure Cost Management został zaprojektowany od początku jako narzędzie do wielochmurowego.
    1. Maszyny wirtualne w chmurze pomocniczej mogą być zgodne z Azure Cost Managementami dla niektórych dostawców chmury. Mogą obowiązywać dodatkowe koszty.
1. Dodaj zasoby do Azure Monitor.
    1. Azure Monitor został zaprojektowany jako narzędzie chmury hybrydowej.
    1. Maszyny wirtualne w chmurze pomocniczej mogą być zgodne z Azure Monitor agentami, co umożliwia ich uwzględnienie w Azure Monitor monitorowania operacyjnego.
1. Przyjmowanie narzędzi do wymuszania ładu.
    1. Wymuszanie ładu jest specyficzne dla chmury.
    1. Zasady firmowe ustanowione w przewodniku ładu nie są specyficzne dla chmury. Chociaż implementacja może się różnić w zależności od chmury, zasady mogą być stosowane do pomocniczego dostawcy.

Po rozwojem wdrożenia wielochmurowego zmiany projektu powyżej będą nadal dojrzałe.

## <a name="conclusion"></a>Wniosek

W tej serii artykułów opisano przyrostowe opracowywanie najlepszych praktyk nadzoru, które są dostosowane do środowiska tej fikcyjnej firmy. Rozpoczynając od małych, ale z właściwą podstawą, firma może szybko przełączać się i nadal stosować odpowiednią ilość ładu w odpowiednim czasie. Sam SPECJALISTa nie chroni klienta. Zamiast tego tworzy podstawę do zarządzania ryzykiem i dodawania ochrony. Z tego miejsca zostały zastosowane warstwy ładu, które korygują zagrożenia materialne. Dokładna podróż przedstawiona w tym miejscu nie wyrównuje 100% z doświadczeniami każdego czytnika. Zamiast tego służy jako wzorzec dla ładu przyrostowego. Czytelnik jest Doradzany do Mold tych najlepszych rozwiązań, aby dopasować własne ograniczenia i wymagania dotyczące zarządzania.