---
title: Narzędzia bazowe zabezpieczeń na platformie Azure
description: Zobacz, jak narzędzia natywne platformy Azure mogą pomóc w dojrzałych zasadach i procesach, które obsługują dyscyplinę linii bazowej zabezpieczeń.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 51e0a253a7e66f70ec440dd7be969f324afb795c
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83217680"
---
# <a name="security-baseline-tools-in-azure"></a>Narzędzia bazowe zabezpieczeń na platformie Azure

[Dyscyplina odniesienia zabezpieczeń](./index.md) jest jednym z [pięciu dyscyplin zarządzania chmurą](../governance-disciplines.md). Ta dyscyplina koncentruje się na sposobach ustanawiania zasad chroniących sieć, zasoby i najważniejsze dane, które będą znajdować się w rozwiązaniu dostawcy chmury. W ramach pięciu dyscyplin nadzoru chmurowego dyscyplina odniesienia zabezpieczeń obejmuje klasyfikację cyfrowej i danych. Obejmuje to również dokumentację zagrożeń, tolerancję biznesową i strategie zaradcze związane z bezpieczeństwem danych, zasobów i sieci. Z perspektywy technicznej ta dyscyplina obejmuje również zaangażowanie w decyzje dotyczące [szyfrowania](../../decision-guides/encryption/index.md), [wymagań sieci](../../decision-guides/software-defined-network/index.md), [hybrydowych strategii tożsamości](../../decision-guides/identity/index.md)i narzędzi do [automatyzowania wymuszania](../../decision-guides/policy-enforcement/index.md) zasad zabezpieczeń w [grupach zasobów](../../decision-guides/resource-consistency/index.md).

Poniższa lista narzędzi platformy Azure może pomóc w przedwczesnym wykorzystaniu zasad i procesów, które obsługują tę dyscyplinę.

| Narzędzie | [Azure Portal](https://azure.microsoft.com/features/azure-portal) i [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/management/overview)  | [W usłudze Azure Key Vault](https://docs.microsoft.com/azure/key-vault)  | [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) | [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) |
|------------------------------------------------------------|---------------------------------|-----------------|----------|--------------|-----------------------|---------------|
| Stosowanie kontroli dostępu do zasobów i tworzenie zasobów   | Yes                             | Nie              | Yes      | Nie           | Nie                    | Nie            |
| Bezpieczne sieci wirtualne                                    | Yes                             | Nie              | Nie       | Yes          | Nie                    | Nie            |
| Szyfruj dyski wirtualne                                     | Nie                              | Yes             | Nie       | Nie           | Nie                    | Nie            |
| Szyfruj magazyn PaaS i bazy danych                         | Nie                              | Yes             | Nie       | Nie           | Nie                    | Nie            |
| Zarządzanie hybrydowymi usługami tożsamości                            | Nie                              | Nie              | Yes      | Nie           | Nie                    | Nie            |
| Ogranicz dozwolone typy zasobów                         | Nie                              | Nie              | Nie       | Yes          | Nie                    | Nie            |
| Wymuszaj ograniczenia geograficzne-regionalne                          | Nie                              | Nie              | Nie       | Yes          | Nie                    | Nie            |
| Monitorowanie kondycji zabezpieczeń sieci i zasobów          | Nie                              | Nie              | Nie       | Nie           | Yes                   | Tak           |
| Wykrywanie złośliwego działania                                  | Nie                              | Nie              | Nie       | Nie           | Yes                   | Tak           |
| Zapobiegawczo wykrywaj luki w zabezpieczeniach                        | Nie                              | Nie              | Nie       | Nie           | Yes                   | Nie            |
| Konfigurowanie kopii zapasowej i odzyskiwania po awarii                     | Yes                             | Nie              | Nie       | Nie           | Nie                    | Nie            |

Aby uzyskać pełną listę narzędzi i usług zabezpieczeń platformy Azure, zobacz [usługi i technologie zabezpieczeń dostępne na platformie Azure](https://docs.microsoft.com/azure/security/fundamentals/services-technologies).

Klienci często używają narzędzi innych firm do włączania działań dyscypliny linii bazowej zabezpieczeń. Aby uzyskać więcej informacji, zobacz artykuł [integracja rozwiązań zabezpieczeń w Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration).

Oprócz narzędzi zabezpieczeń [Centrum zaufania Microsoft](https://www.microsoft.com/microsoft-365/business/compliance-solutions#office-KeyMessages-k3j63yo) zawiera obszerne wskazówki, raporty i powiązane dokumenty, które mogą pomóc w wykonywaniu oceny ryzyka w ramach procesu planowania migracji.
