---
title: Zagadnienia dotyczące strefy docelowej na platformie Azure
description: Użyj platformy wdrażania w chmurze dla platformy Azure, aby dowiedzieć się, w jaki sposób strefa docelowa zapewnia podstawowy blok konstrukcyjny dowolnego środowiska wdrażania w chmurze.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/09/2020
ms.topic: overview
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 18b5aefb0498c530313afa63d2f005fd874f8741
ms.sourcegitcommit: 7d3fc1e407cd18c4fc7c4964a77885907a9b85c0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2020
ms.locfileid: "81121820"
---
# <a name="landing-zone-considerations"></a>Zagadnienia dotyczące strefy docelowej

Strefa docelowa to podstawowy blok konstrukcyjny każdego środowiska wdrażania chmury. Termin *strefa docelowa* odnosi się do środowiska, które zostało aprowizowane i przygotowane do hostowania obciążeń w środowisku chmury, takim jak platforma Azure. W pełni funkcjonalna strefa docelowa jest finalnym dostarczanym elementem dowolnej iteracji metodologii gotowości podręcznika Cloud Adoption Framework.

![Zagadnienia dotyczące strefy docelowej](../../_images/ready/landing-zone-considerations.png)

Na tej ilustracji przedstawiono główne kwestie do rozważenia podczas implementowania każdego wdrożenia strefy docelowej. Te kwestie można podzielić na trzy kategorie lub typy zagadnień: hosting, podstawy platformy Azure i ład.

## <a name="hosting-considerations"></a>Zagadnienia dotyczące hostingu

Wszystkie strefy docelowe zapewniają strukturę dla opcji hostingu. Struktura jest tworzona jawnie za pośrednictwem mechanizmów kontroli ładu lub organicznie przez wdrożenie usług w strefie docelowej. Następujące artykuły mogą pomóc w podjęciu decyzji, które zostaną odzwierciedlone w strategii lub innych skryptach automatyzacji tworzących strefę docelową:

- **[Decyzje dotyczące obliczeń](./compute-options.md)**. Dostosuj opcje obliczeniowe do przeznaczenia strefy docelowej, aby zminimalizować złożoność operacyjną. Tę decyzję można wymusić przy użyciu łańcuchów narzędzi automatyzacji, takich jak inicjatywy usługi Azure Policy i strategie strefy docelowej.
- **[Decyzje dotyczące magazynu](./storage-options.md)**. Wybierz odpowiednie rozwiązanie usługi Azure Storage do obsługi wymagań swoich obciążeń.
- **[Decyzje dotyczące sieci](./networking-options.md)**. Wybierz usługi, narzędzia i architektury sieciowe, które spełnią wymagania dotyczące obciążeń, ładu i łączności Twojej organizacji.
- **[Decyzje dotyczące bazy danych](./data-options.md)**. Ustal, która technologia baz danych najlepiej odpowiada wymaganiom Twoich obciążeń.

## <a name="azure-fundamentals"></a>Podstawy platformy Azure

Każda strefa docelowa jest częścią szerszego rozwiązania do organizowania zasobów w środowisku chmury. Podstawy platformy Azure to podstawowe bloki konstrukcyjne dla organizacji.

- **[Podstawowe pojęcia związane z platformą Azure](./fundamental-concepts.md)**. Poznaj podstawowe pojęcia i terminy używane podczas organizowania zasobów na platformie Azure i dowiedz się, jak te pojęcia odnoszą się do siebie nawzajem.
- **[Przewodnik podejmowania decyzji dotyczących spójności zasobów](../../decision-guides/resource-consistency/index.md)**. Gdy zrozumiesz już wszystkie podstawy, przewodnik po decyzjach dotyczących organizacji zasobów pomoże Ci w podjęciu decyzji, które ukształtują strefę docelową.

## <a name="governance-considerations"></a>Zagadnienia związane z nadzorem

Metodologie ładu podręcznika Cloud Adoption Framework ustalają proces zapewniania ładu w całym środowisku. Istnieje jednak wiele przypadków użycia, które mogą wymagać podjęcia decyzji dotyczących ładu dla poszczególnych stref docelowych. W wielu scenariuszach plany bazowe ładu są wymuszane w poszczególnych strefach docelowych, mimo że plany bazowe są ustanawiane holistycznie. Jest to prawdziwe w przypadku pierwszych kilku stref docelowych wdrażanych przez organizację.

Następujące artykuły mogą pomóc w podjęciu decyzji dotyczących ładu dla strefy docelowej. Każdą decyzję można uwzględnić w planach bazowych ładu.

- **Wymagania dotyczące kosztów**. Na podstawie motywacji organizacji do wdrożenia chmury i zobowiązania operacyjne względem jej środowiska, może być konieczne wprowadzenie zmian w różnych konfiguracjach zarządzania kosztami dla strefy docelowej.
- **Decyzje dotyczące monitorowania**. W zależności od wymagań operacyjnych dla strefy docelowej można wdrożyć różne narzędzia do monitorowania. Artykuł na temat decyzji dotyczących monitorowania pomoże określić najbardziej odpowiednie narzędzia do wdrożenia.
- **Przy użyciu kontroli dostępu opartej na rolach**. [Kontrola dostępu na podstawie ról](../considerations/roles.md) na platformie Azure (RBAC) oferuje szczegółowe, oparte na grupach zarządzanie dostępem dla zasobów zorganizowanych wokół ról użytkownika.
- **Decyzje dotyczące zasad**. [Przykłady strategii platformy Azure](https://docs.microsoft.com/azure/governance/blueprints/samples) zawierają wstępnie utworzone strategie zgodności — każdą ze wstępnie zdefiniowanymi inicjatywami zasad. Decyzje dotyczące zasad ułatwiają wybór najlepszego planu lub inicjatywy zasad na podstawie Twoich wymagań i ograniczeń.
- **[Uzyskiwanie zgodności w chmurze hybrydowej](./hybrid-consistency.md)**. Utwórz rozwiązania chmury hybrydowej, które zapewniają organizacji korzyści z innowacji w chmurze przy zachowaniu wielu udogodnień zarządzania w środowisku lokalnym.