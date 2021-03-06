---
title: Przewodnik po gotowości zabezpieczeń w chmurze CISO
description: Przygotuj Urząd ds. bezpieczeństwa informacji (CISO) na potrzeby transformacji w chmurze i zarządzania przyrostowego.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.openlocfilehash: 53549ed01b9656ba4ce365e4707b411bdae2db1f
ms.sourcegitcommit: bd9872320b71245d4e9a359823be685e0f4047c5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/26/2020
ms.locfileid: "83862283"
---
<!-- cSpell:ignore CISO -->

# <a name="ciso-cloud-readiness-guide"></a>Przewodnik po gotowości w chmurze CISO

Wskazówki firmy Microsoft, takie jak struktura wdrażania chmury, nie są umieszczane w celu ustalenia lub zaplanowania unikatowych ograniczeń zabezpieczeń tysięcy przedsiębiorstw obsługiwanych przez tę dokumentację. Podczas przejścia do chmury rola dyrektora ds. zabezpieczeń informacji lub dyrektora ds. bezpieczeństwa informacji (CISO) nie jest supplanted przez technologie chmurowe. Całkiem inaczej, CISO i Biuro CISO stają się bardziej engrained i zintegrowane. W tym przewodniku przyjęto założenie, że czytelnik jest zaznajomiony z procesami CISO i dąży do modernizacji tych procesów, aby umożliwić transformację chmury.

Wdrożenie chmury umożliwia korzystanie z usług, które nie były często brane pod uwagę w tradycyjnych środowiskach IT. Wdrożenia samoobsługowe lub zautomatyzowane są zwykle wykonywane przez projektowanie aplikacji lub innych zespołów IT, które nie są tradycyjnie wyrównane do wdrożenia produkcyjnego. W niektórych organizacjach składniki biznesowe są podobne do funkcji samoobsługowych. Może to spowodować nowe wymagania dotyczące zabezpieczeń, które nie były wymagane w lokalnym świecie. Scentralizowane zabezpieczenia są bardziej trudne, a zabezpieczenia często staną się wspólną odpowiedzialnością dla działalności biznesowej i kultury IT. Ten artykuł może pomóc w CISO przygotowania do tego podejścia i zaangażować się w zarządzanie przyrostowe.

<!-- markdownlint-disable MD026 -->

## <a name="how-can-a-ciso-prepare-for-the-cloud"></a>Jak główny inspektor ds. bezpieczeństwa informacji może przygotować się pod kątem chmury?

Podobnie jak w przypadku większości zasad, zasady zabezpieczeń i zarządzania w organizacji są klasyfikowane w sposób organiczny. Gdy nastąpi incydenty związane z bezpieczeństwem, Przyporządkują zasady, aby poinformować użytkowników i zmniejszyć prawdopodobieństwo powtarzania wystąpień. W naturalny sposób takie podejście tworzy przeładowanie zasad i zależności techniczne. Podróże w chmurze tworzą unikatową okazję do modernizacji i resetowania zasad. Podczas przygotowywania do dowolnych przekształceń transformującej CISO może stworzyć natychmiastową i wymierną wartość dzięki obsłużeniu jako podstawowy uczestnik projektu w [przeglądzie zasad](./cloud-policy-review.md).

W takim przeglądzie rolą CISO jest utworzenie bezpiecznej równowagi między ograniczeniami istniejącej zasady/zgodności a zwiększonymi zabezpieczeniami stan dostawców chmury. Mierzenie tego postępu może potrwać wiele form, często jest to mierzone w liczbie zasad zabezpieczeń, które mogą być bezpiecznie Odciążone dostawcy chmury.

**Transfer zagrożeń bezpieczeństwa:** Gdy usługi są przenoszone do modeli hostowania infrastruktury jako usługi (IaaS), firma zakłada mniej bezpośrednie ryzyko związane z obsługą sprzętu. Ryzyko nie zostanie usunięte, a nie zostanie przesłane do dostawcy chmury. W przypadku, gdy podejście dostawcy chmury do aprowizacji sprzętu zapewnia ten sam poziom łagodzenia ryzyka, w bezpiecznym procesie powtarzania ryzyko wykonania aprowizacji sprzętowej jest usuwane z firmowej obszaru obowiązków i przenoszone do dostawcy chmury. Pozwala to ograniczyć ogólne ryzyko związane z zabezpieczeniami, które jest odpowiedzialne za zarządzanie, chociaż samo ryzyko powinno być nadal śledzone i przeglądane.

Ponieważ rozwiązania przechodzą dalsze "stos" w celu uwzględnienia modeli platformy jako usługi (PaaS) lub oprogramowania jako usługi (SaaS), można uniknąć lub przenieść dodatkowych zagrożeń. Gdy ryzyko jest bezpiecznie przenoszone do dostawcy chmury, koszt wykonywania, monitorowania i wymuszania zasad zabezpieczeń lub innych zasad zgodności może być również bezpiecznie zmniejszony.

**Sposób myślenia wzrostu:** Zmiana może być Scary zarówno dla realizatorów firmowych, jak i technicznych. Gdy CISO prowadzi do wzrostu sposób myślenia w organizacji, firma Microsoft stwierdziła, że te naturalne obawy zostały zastąpione przez podwyższenie poziomu bezpieczeństwa i zgodności z zasadami. Zbliża się [Przegląd zasad](./cloud-policy-review.md), podróż transformację lub proste przeglądy implementacji z sposób myślenia wzrostem, dzięki czemu zespół może szybko przejść, ale nie kosztem uczciwego i możliwego do zarządzania profilu ryzyka.

## <a name="resources-for-the-chief-information-security-officer"></a>Zasoby dla dyrektora ds. bezpieczeństwa informacji

Wiedza o chmurze jest podstawą podejścia do [przeglądu zasad](./cloud-policy-review.md) z sposób myśleniaem wzrostu. Następujące zasoby mogą pomóc CISO lepiej zrozumieć stan zabezpieczeń platformy Microsoft Azure.

<!-- docsTest:ignore "Security Response in the Cloud" -->

**Zasoby platformy zabezpieczeń:**

- [Cykl rozwoju zabezpieczeń, audyty wewnętrzne](https://www.microsoft.com/sdl)
- [Obowiązkowe szkolenia w zakresie zabezpieczeń, kontrole w tle](https://downloads.cloudsecurityalliance.org/star/self-assessment/StandardResponsetoRequestforInformationWindowsAzureSecurityPrivacy.docx)
- [Testowanie penetracji, Wykrywanie intruzów, DDoS, inspekcje i rejestrowanie](https://www.microsoft.com/security/business/operations)
- [Najnowocześniejsze centrum danych](https://www.microsoft.com/cloud-platform/global-datacenters), zabezpieczenia fizyczne, [bezpieczna sieć](https://docs.microsoft.com/azure/security/security-network-overview)
- [Microsoft Azure odpowiedź zabezpieczeń w chmurze (PDF)](https://aka.ms/securityresponsepaper)

**Prywatność i kontrola:**

- [Zarządzaj danymi przez cały czas](https://www.microsoft.com/trust-center/privacy/data-management)
- [Kontrola lokalizacji danych](https://www.microsoft.com/trust-center/privacy/data-location)
- [Zapewnianie dostępu do danych na Twoich warunkach](https://www.microsoft.com/trust-center/privacy/data-access)
- [Reagowanie na egzekwowanie prawa](https://www.microsoft.com/trust-center/privacy)
- [Rygorystyczne standardy ochrony prywatności](https://www.microsoft.com/trust-center/privacy)

<!-- docsTest:ignore "Cloud Services Due Diligence Checklist" -->

**Przepisów**

- [Centrum zaufania firmy Microsoft](https://www.microsoft.com/trust-center)
- [Centrum formantów wspólnych](https://www.microsoft.com/trust-center/compliance/compliance-overview)
- [Lista kontrolna z zaCloud Servicesmi](https://www.microsoft.com/trust-center/compliance/due-diligence-checklist)
- [Zgodność regionalna i Krajowa](https://www.microsoft.com/trust-center/compliance/regional-country-compliance)

**Przeźroczyst**

- [Jak firma Microsoft zabezpiecza dane klientów w usługach platformy Azure](https://www.microsoft.com/trust-center)
- [Jak firma Microsoft zarządza lokalizacją danych w usługach platformy Azure](https://azuredatacentermap.azurewebsites.net)
- [Kto w firmie Microsoft może uzyskiwać dostęp do Twoich danych, na jakich warunkach](https://www.microsoft.com/trust-center/privacy/data-access)
- [Przejrzyj certyfikaty dla usług platformy Azure, centrum przezroczystości](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="next-steps"></a>Następne kroki

Pierwszym krokiem podjęcia działania w ramach strategii ładu jest [Przegląd zasad](./cloud-policy-review.md). [Zasady i zgodność](./index.md) mogą być przydatne podczas przeglądania zasad.

> [!div class="nextstepaction"]
> [Przygotowanie do przeglądu zasad](./cloud-policy-review.md)
