---
title: Ulepszanie zabezpieczeń strefy docelowej
description: Ulepszanie zabezpieczeń strefy docelowej
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/15/2020
ms.topic: overview
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 116c628d31267fafe50d8a870f9e6c83d3c51f3c
ms.sourcegitcommit: 9a84c2dfa4c3859fd7d5b1e06bbb8549ff6967fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "83756502"
---
<!-- cSpell:ignore SIEM -->

# <a name="improve-landing-zone-security"></a>Ulepszanie zabezpieczeń strefy docelowej

W przypadku obciążeń lub strefy docelowej, w której znajdują się hosty, wymagane jest uzyskanie dostępu do dowolnych poufnych danych lub systemów krytycznych, dlatego należy chronić dane i zasoby. Udoskonalenie zabezpieczeń strefy wyładunkowej w ramach [podejścia do projektowania opartego na testach w celu](./test-driven-development.md) wystawiania stref, rozszerzając lub refaktoryzację strefy docelowej pod kątem podwyższonych wymagań w zakresie zabezpieczeń.

## <a name="landing-zone-security-best-practices"></a>Najlepsze rozwiązania w zakresie zabezpieczeń strefy wyładunkowej

Poniższa lista architektury referencyjnych i najlepszych rozwiązań zawiera przykłady sposobów ulepszania zabezpieczeń spocznika:

- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-get-started?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json): dołączanie subskrypcji do usługi Security Center.
- [Azure — wskaźnik](https://docs.microsoft.com/azure/sentinel/quickstart-onboard?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json): dołączanie do platformy Azure — wskaźnik kontrolny, który zapewnia **zarządzanie zdarzeniami zabezpieczeń (Siem)** i rozwiązanie do **automatycznej reakcji aranżacji (o)** .
- [Zabezpieczenia granic sieci](../../reference/networking-vdc.md): kilka wzorców referencyjnych na potrzeby tworzenia sieci, podobnie jak w przypadku zabezpieczenia granicy sieci w centrum danych.
- [Bezpieczna architektura sieci](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json): architektura referencyjna do implementowania strefy zdemilitaryzowana i bezpiecznej architektury sieci.
- [Zarządzanie tożsamościami i kontrola dostępu](https://docs.microsoft.com/azure/security/fundamentals/identity-management-best-practices?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json): szereg najlepszych rozwiązań dotyczących implementowania tożsamości i dostępu w celu zabezpieczenia strefy wyładunkowej na platformie Azure.
- [Praktyki dotyczące zabezpieczeń sieci](https://docs.microsoft.com/azure/security/fundamentals/network-best-practices?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json): zapewniają dodatkowe najlepsze rozwiązania w zakresie zabezpieczania sieci.
- [Zabezpieczenia operacyjne](https://docs.microsoft.com/azure/security/fundamentals/operational-best-practices?toc=/azure/cloud-adoption-framework/toc.json&bc=/azure/cloud-adoption-framework/_bread/toc.json) zapewniają najlepsze rozwiązania w zakresie zwiększania bezpieczeństwa operacyjnego na platformie Azure.
- [Dyscyplina linii bazowej zabezpieczeń](../../govern/guides/complex/security-baseline-improvement.md#incremental-improvement-of-the-best-practices): przykład tworzenia linii bazowej zabezpieczeń opartej na ładu w celu wymuszenia wymagań dotyczących zabezpieczeń.

## <a name="test-driven-development-cycle"></a>Cykl programowania oparty na testach

Przed rozpoczęciem wszelkich ulepszeń zabezpieczeń należy zrozumieć "definicję gotowe" i wszystkie "kryteria akceptacji". Aby uzyskać więcej informacji, zapoznaj się z artykułami dotyczącymi [opracowywania testów w strefach lądowania](./test-driven-development.md) i [opracowywanie testów na platformie Azure](./azure-test-driven-development.md).

![Proces projektowania oparty na testach dla stref wyładunku w chmurze](../../_images/ready/test-driven-development-process.png)

## <a name="next-steps"></a>Następne kroki

Dowiedz się, jak [ulepszyć operacje strefy wyładunkowej](./landing-zone-operations.md) w celu obsługi kluczowych aplikacji.

> [!div class="nextstepaction"]
> [Ulepszanie operacji strefy docelowej](./landing-zone-operations.md)
