---
title: Wprowadzenie do zgodności z przepisami
description: Dowiedz się więcej na temat zasad zgodności w różnych branżach i lokalizacje geograficzne, które mogą mieć wpływ na zarządzanie chmurą.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 927c42b216ff22aa3b721c5f741e49fe089e2923
ms.sourcegitcommit: 9a84c2dfa4c3859fd7d5b1e06bbb8549ff6967fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/21/2020
ms.locfileid: "83755975"
---
# <a name="introduction-to-regulatory-compliance"></a>Wprowadzenie do zgodności z przepisami

Jest to artykuł wprowadzający dotyczący zgodności z przepisami, dlatego nie jest on przeznaczony do wdrażania strategii zgodności. Bardziej szczegółowe informacje na temat [ofert zgodności platformy Azure](https://aka.ms/allcompliance) są dostępne w [Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center). Ponadto cała dokumentacja do pobrania jest dostępna dla niektórych klientów platformy Azure w [portalu zaufania usługi firmy Microsoft](https://servicetrust.microsoft.com).

Zgodność z przepisami dotyczy dyscypliny i procesu zapewnienia, że firma przestrzega obowiązujących przepisów przez zarządzanie organami w ich geograficznym lub regułach wymaganych przez dobrowolne normy branżowe. W celu zapewnienia zgodności z przepisami IT osoby i procesy monitorują systemy firmowe w celu wykrywania i zapobiegania naruszeniom zasad i procedur ustanowionych przez przepisy prawne, regulacje i standardy. To z kolei dotyczy szerokiej gamy procesów monitorowania i wymuszania. W zależności od branży i geografii procesy te mogą stać się długie i złożone.

Zgodność jest wyzwaniem dla organizacji wielonarodowych, szczególnie w silnie regulowanej branży, takiej jak opieka zdrowotna i usługi finansowe. Standardy i regulacje Abound, a w niektórych przypadkach mogą być często zmieniane, utrudniając tym firmom zmianę międzynarodowych przepisów elektronicznych dotyczących obsługi danych.

Podobnie jak w przypadku kontroli zabezpieczeń, organizacje powinny zrozumieć podział obowiązków dotyczących zgodności z przepisami w chmurze. Dostawcy chmury dążą do zapewnienia zgodności ich platform i usług. Organizacje muszą również upewnić się, że ich aplikacje, infrastruktura, od których zależą te aplikacje, i usług świadczonych przez strony trzecie są również certyfikowane jako zgodne.

Poniżej znajdują się opisy rozporządzeń dotyczących zgodności w różnych branżach i lokalizacje geograficzne:

<!-- docsTest:ignore PHI "Health Information Portability and Accountability Act" -->

## <a name="hipaa"></a>HIPAA

Aplikacja do opieki zdrowotnej, która przetwarza chronione informacje o zdrowiu (Fi), podlega zasadom zachowania poufności informacji i regule zabezpieczeń podanym w ramach przenośności i odpowiedzialności za informacje o kondycji (HIPAA). Co więcej, HIPAA może wymagać, aby firma opieki zdrowotnej musiała uzyskać zagwarantowane gwarancje od dostawcy usług w chmurze, które będą chronić wszelkie odebrane lub utworzone przeze mnie Fi.

<!-- cSpell:ignore Visa Mastercard -->
<!-- docsTest:ignore "American Express" Discover JCB QSA ISA ROC SAQ DPO GRC -->

## <a name="pci"></a>Port

Karta płatnicza Industry Data Security Standard (PCI DSS) jest zastrzeżonym standardem zabezpieczeń informacji dla organizacji, które obsługują marki karty kredytowe z głównych schematów kart, w tym wiz, MasterCard, American Express, Discover i JCB. Standard PCI jest przystosowany przez marki kart i administrowany przez Radę branżowych standardów zabezpieczeń. Standard został utworzony w celu zwiększenia kontroli nad danymi posiadaczy kart kredytowych w celu zredukowania oszustw związanych z kartą kredytową. Weryfikacja zgodności jest przeprowadzana co rok, przez zewnętrzną, kwalifikowaną ocenę zabezpieczeń (QSA) lub przez specyficzną firmę wewnętrzną ocenę zabezpieczeń (ISA), która tworzy raport na temat zgodności (ROC) dla organizacji obsługujących duże ilości transakcji lub przez kwestionariusz samooceny (SAQ) dla firm.

## <a name="personal-data"></a>Dane osobowe

Dane osobowe są informacjami, których można użyć do zidentyfikowania konsumenta, pracownika, partnera lub innej jednostki życiowej lub prawnej. Wiele powstających przepisów, szczególnie tych związanych z ochroną prywatności i danymi osobowymi, wymaga, aby same firmy spełniały wymagania i zgłaszać zgodność oraz wszelkie naruszenia, które mogą wystąpić.

## <a name="gdpr"></a>RODO

Jednym z najważniejszych osiągnięć w tym obszarze jest ogólne rozporządzenie o ochronie danych (Rodo), zaprojektowane w celu wzmocnienia ochrony danych dla osób w Unii Europejskiej. Rodo wymaga, aby dane dotyczące osób indywidualnych (takich jak "nazwa, adres domowy, Zdjęcie, adres e-mail, szczegóły banku, wpisy w witrynach sieci społecznościowych, informacje medyczne lub adresy IP komputera") były przechowywane na serwerach w Unii Europejskiej i nie zostały z nich przesłane. Wymaga również, aby firmy powiadomiły osoby o naruszeniu danych i mieli upoważnienia, że firmy mają oficera ochrony danych (DPO). Inne kraje mają lub rozwijają podobne rodzaje rozporządzeń.

## <a name="compliant-foundation-in-azure"></a>Zgodna podstawa na platformie Azure

Aby pomóc klientom w spełnieniu własnych obowiązków związanych ze zgodnością w ramach regulowanych branż i rynków na całym świecie, platforma Azure utrzymuje największe portfolio zgodności w branży, w wysokości (łącznie z liczbą ofert), a także głębi (liczba usług dostępnych dla klientów w zakresie oceny). Oferty zgodności z platformą Azure są pogrupowane w cztery segmenty:

- Globalny
- Administracja USA
- Branża
- Regionalne

Oferty zgodności z platformą Azure są oparte na różnych typach gwarancji, w tym formalnych certyfikatach, zaświadczeniu, atestacji, autoryzacji i ocenach wyprodukowanych przez niezależne przedsiębiorstwa przeprowadzające inspekcje stron trzecich, a także zmiany umowne, samooceny i dokumenty wskazówki klienta utworzone przez firmę Microsoft. Każdy opis oferty w tym dokumencie zawiera aktualne instrukcje dotyczące zakresu, wskazujące, które usługi platformy Azure są w zasięgu dla oceny, a także linki do zasobów do pobrania, które pomagają klientom z własnymi zobowiązaniami w zakresie zgodności.

Centrum zaufania firmy Microsoft zawiera bardziej szczegółowe informacje na temat [ofert zgodności platformy Azure](https://www.microsoft.com/trust-center/compliance/compliance-overview). Ponadto cała dokumentacja do pobrania jest dostępna dla niektórych klientów platformy Azure z [portalu zaufania usługi firmy Microsoft](https://servicetrust.microsoft.com) w następujących sekcjach:

- **Raporty inspekcji:** Zawiera sekcje dla raportów FedRAMP, GRC oceny, ISO, PCI DSS i SOC.
- **Zasoby ochrony danych:** Obejmuje przewodniki dotyczące zgodności, często zadawane pytania i oficjalne dokumenty oraz sekcje dotyczące testowania i oceny zabezpieczeń pióra.

## <a name="next-steps"></a>Następne kroki

Dowiedz się więcej o gotowości zabezpieczeń w chmurze.

> [!div class="nextstepaction"]
> [Gotowość do bezpieczeństwa chmury](./cloud-security-readiness.md)
