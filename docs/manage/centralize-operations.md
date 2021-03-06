---
title: Centralizowanie operacji zarządzania
description: Dowiedz się, jak scentralizować operacje zarządzania przy użyciu jednej dzierżawy Azure Active Directory dla wszystkich użytkowników. Scentralizowane zarządzanie upraszcza operacje zarządzania i zmniejsza koszty konserwacji.
author: JnHs
ms.author: jenhayes
ms.date: 09/27/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 6d777a1c919e72c55d8c6202ef1c32f44d9444d9
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83219482"
---
<!-- cSpell:ignore jenhayes -->

# <a name="centralize-management-operations"></a>Centralizowanie operacji zarządzania

W przypadku większości organizacji przy użyciu jednej dzierżawy usługi Azure Active Directory (Azure AD) dla wszystkich użytkowników upraszczają operacje zarządzania i obniżają koszty konserwacji. Wynika to z faktu, że wszystkie zadania zarządzania mogą być wyznaczonymi użytkownikami, grupami użytkowników lub jednostkami usługi w ramach danej dzierżawy.

Zalecamy używanie tylko jednej dzierżawy usługi Azure AD w organizacji, jeśli jest to możliwe. Jednak niektóre sytuacje mogą wymagać od organizacji utrzymania wielu dzierżawców usługi Azure AD z następujących powodów:

- Są one całkowicie niezależne od podmiotów zależnych.
- Działają one niezależnie w wielu lokalizacje geograficzneach.
- Obowiązują pewne wymagania prawne lub dotyczące zgodności.
- Istnieją nabycie innych organizacji (czasami czas tymczasowy do momentu zdefiniowania długoterminowej strategii konsolidacji dzierżawców).

Gdy wymagana jest architektura z wieloma dzierżawcami, [usługa Azure Lighthouse](https://docs.microsoft.com/azure/lighthouse/overview) zapewnia sposób scentralizowania i usprawniania operacji zarządzania. Subskrypcje z wielu dzierżawców można dołączyć do [zarządzania zasobami delegowanymi przez platformę Azure](https://docs.microsoft.com/azure/lighthouse/concepts/azure-delegated-resource-management). Ta opcja umożliwia określonym użytkownikom w dzierżawie zarządzającej wykonywanie [funkcji zarządzania między dzierżawcami](https://docs.microsoft.com/azure/lighthouse/concepts/cross-tenant-management-experience) w sposób scentralizowany i skalowalny.

Załóżmy na przykład, że organizacja ma jedną dzierżawę `Tenant A` . Organizacja uzyskuje dwie dodatkowe dzierżawy `Tenant B` i `Tenant C` ma powody biznesowe, które wymagają utrzymania ich jako osobnych dzierżawców.

Organizacja chce używać tych samych definicji zasad, metod tworzenia kopii zapasowych i procesów zabezpieczeń we wszystkich dzierżawach. Ponieważ masz już użytkowników (w tym grupy użytkowników i jednostek usługi) odpowiedzialnych za wykonywanie tych zadań w ramach dzierżawy A, możesz dołączyć wszystkie subskrypcje w ramach dzierżawy B i dzierżawy C, aby Ci użytkownicy w dzierżawie mogli wykonywać te zadania. Dzierżawa A następnie będzie dzierżawą zarządzającą dla dzierżawy B i dzierżawy C.

![Użytkownicy w dzierżawie to zarządzanie zasobami w dzierżawie B i w ramach dzierżawy C](../_images/manage/enterprise-azure-lighthouse.jpg)

Aby uzyskać więcej informacji, zobacz [Azure Lighthouse w scenariuszach dla przedsiębiorstw](https://docs.microsoft.com/azure/lighthouse/concepts/enterprise).
