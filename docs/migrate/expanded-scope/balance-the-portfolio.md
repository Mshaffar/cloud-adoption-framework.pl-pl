---
title: Równoważenie portfela
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Równoważenie portfela
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 1227b798972ce7e139181c9267a1a1e860390029
ms.sourcegitcommit: a26c27ed72ac89198231ec4b11917a20d03bd222
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2019
ms.locfileid: "70825759"
---
# <a name="balance-the-portfolio"></a>Równoważenie portfela

Wdrażanie chmury to nakład pracy związany z zarządzaniem portfelem, zręcznie ukryty pod maską implementacji technicznej. Podobnie jak w przypadku wszystkich zadań związanych z zarządzaniem portfelem, równowaga portfela jest elementem krytycznym dla sukcesu. Na poziomie strategicznym oznacza to zrównoważenie migracji, innowacji i eksperymentów w celu maksymalnego wykorzystania chmury. Gdy nakłady pracy związane z wdrażaniem chmury posuwają się zbyt daleko w jedną lub drugą stronę, wysiłek związany z migracją staje się nazbyt złożony. W tym artykule przedstawimy Czytelnikowi podejścia do osiągnięcia równowagi portfela.

## <a name="general-scope-expansion"></a>Rozszerzenie zakresu ogólnego

Ten temat ma charakter strategiczny. W związku z tym zaprezentowane w nim podejście jest równie strategiczne. W celu umocowania strategii podejmowania decyzji opartych na danych w tym artykule przyjęto, że Czytelnik ocenił istniejący [majątek cyfrowy](../../digital-estate/index.md) (lub jest w trakcie tego procesu). Celem tego podejścia jest pomoc w ocenie obciążeń, aby zapewnić odpowiednią równowagę portfela przez pytania jakościowe i udoskonalanie portfela.

### <a name="documenting-business-outcomes"></a>Dokumentowanie wyników biznesowych

Przed przeprowadzeniem równoważenia portfela ważne jest, aby udokumentować i udostępnić wyniki biznesowe związane z nakładem pracy w zakresie migracji do chmury. Kilka przykładów ogólnych wyników biznesowych związanych z migracjami do chmury znajduje się w artykule [Cloud migration executive summary](../../getting-started/migrate.md) (Podsumowanie ogólne migracji do chmury).

Poniższa tabela ułatwia dokumentowanie i udostępnianie żądanych wyników biznesowych. Należy pamiętać, że większość firm dąży do osiągnięcia wielu wyników jednocześnie. Celem tego ćwiczenia jest wyjaśnienie rezultatów, które są najbardziej bezpośrednio związane z nakładem pracy w zakresie migracji do chmury:

|Wynik  |Mierzony przez  |Cel  |Horyzont czasowy  |Priorytet tego nakładu pracy  |
|---------|---------|---------|---------|---------|
|Zmniejszenie kosztów IT     |Budżet centrum danych         |Zmniejszenie o 2 mln dolarów         |12 miesięcy         |1\.         |
|Wyjście z centrum danych     |Wyjście z centrów danych         |2 centra danych         |6 miesięcy         |2\.         |
|Zwiększenie sprawności biznesowej     |Szybsze wejście na rynek  |Skrócenie czasu wdrożenia o sześć miesięcy         |2 lata         |3\.        |
|Ulepszenie środowiska klienta     |Zadowolenie klienta (CSAT)         |Poprawa o 10%         |12 miesięcy         |4\.         |

> [!IMPORTANT]
> Powyższa tabela jest przykładem fikcyjnym i nie powinna być używana do określania priorytetów. W wielu przypadkach ta tabela może być traktowana jako antywzorzec, ponieważ oszczędnościom kosztów nadano wyższy priorytet niż zadowoleniu klienta.

Powyższa tabela może precyzyjnie reprezentować priorytety zespołu strategicznego ds. chmury i zespołu wdrożeniowego ds. chmury nadzorującego migrację do chmury. Ze względu na znaczne ograniczenia czasowe ten zespół kładzie większy nacisk na redukcję kosztów IT i traktuje priorytetowo wyjście z centrum danych jako środek do osiągnięcia żądanego obniżenia kosztów IT. Jednak dzięki udokumentowaniu konkurencyjnych priorytetów w tej tabeli zespół wdrożeniowy ds. chmury może ułatwiać zespołowi strategicznemu ds. chmury identyfikowanie możliwości lepszego dopasowania implementacji nadrzędnej strategii portfela.

### <a name="move-fast-while-maintaining-balance"></a>Szybkość zmian przy zachowaniu równowagi

Wskazówki dotyczące [przyrostowej racjonalizacji majątku cyfrowego](../../digital-estate/index.md) sugerują podejście, w którym racjonalizacja rozpoczyna się od pozycji niezrównoważonej. Zespół strategiczny ds. chmury powinien oszacować każde obciążenie pod kątem zgodności z podejściem do ponownego hostowania. Takie podejście jest sugerowane, ponieważ pozwala na szybką ocenę złożonego majątku cyfrowego na podstawie danych ilościowych. Takie wstępne założenie umożliwia zespołowi wdrożeniowemu ds. chmury szybkie zaangażowanie i skrócenie czasu oczekiwania na wyniki biznesowe. Jednak, zgodnie z opisem w tym artykule, to pytania jakościowe będą zapewniały niezbędną równowagę portfela. W tym artykule opisano proces tworzenia uzgodnionego salda.

### <a name="importance-of-sunset-and-retire-decisions"></a>Znaczenie decyzji o wycofaniu

W tabeli z powyższej sekcji [Dokumentowanie wyników biznesowych](#documenting-business-outcomes) pominięto kluczowy wynik, który mógłby ułatwić osiągnięcie pierwszorzędnego celu redukcji kosztów IT. W przypadku klasyfikacji obniżenia kosztów w dowolnym miejscu listy wyników biznesowych ważne jest, aby wziąć pod uwagę potencjalną liczbę wycofywanych obciążeń. W niektórych scenariuszach oszczędności kosztów mogą pochodzić z BRAKU migracji obciążeń, które nie uzasadniają krótkoterminowych inwestycji. Niektórzy klienci zgłosili oszczędności kosztów przekraczające 20% łącznego obniżenia kosztów przez wycofanie niewykorzystywanych obciążeń.

Aby zrównoważyć portfel, lepiej odzwierciedlając decyzje o wycofaniu, zespół strategiczny ds. chmury i zespół wdrożeniowy ds. chmury są zachęcane do zadawania następujących pytań dotyczących każdego obciążenia w ramach procesów oceny i migracji:

- Czy obciążenie było używane przez użytkowników końcowych w ciągu ostatnich sześciu miesięcy?
- Czy ruch użytkowników końcowych jest stały lub wzrastający?
- Czy to obciążenie będzie potrzebne firmie w ciągu 12 miesięcy od teraz?

Jeśli odpowiedź na dowolne z tych pytań brzmi „nie”, obciążenie może być kandydatem do wycofania. Jeśli możliwość wycofania zostanie potwierdzona przez właściciela aplikacji, migracja obciążenia może nie mieć sensu. To prowadzi do kilku pytań jakościowych:

- Czy można ustanowić plan wycofania tego obciążenia?
- Czy to obciążenie może zostać wycofane przed wyjściem z centrum danych?

Jeśli odpowiedzi na oba te pytania brzmią „tak”, warto rozważyć _brak_ migracji obciążenia. Takie podejście może pomóc osiągnąć cele zmniejszenia kosztów i wyjścia z centrum danych.

Jeśli odpowiedź na dowolne z tych pytań brzmi „nie”, może być konieczne ustanowienie planu hostowania obciążenia do czasu możliwości jego wycofania. Ten plan może obejmować przeniesienie zasobów do tańszego lub alternatywnego centrum danych, co również umożliwia osiągnięcie celów zmniejszenia kosztów i wyjścia z jednego centrum danych.

## <a name="suggested-prerequisites"></a>Sugerowane wymagania wstępne

Wymagania wstępne określone w podstawowym przewodniku powinny być wystarczające dla tego złożonego tematu. Jednak spis zasobów i majątek cyfrowy powinny zostać szczególnie wyróżnione w wymaganiach wstępnych, ponieważ te dane wpływają na kolejne działania.

## <a name="assess-process-changes"></a>Zmiany procesu oceniania

Równoważenie portfela wymaga dodatkowej analizy jakościowej w trakcie procesu oceny, co pomoże kierować prostą racjonalizacją portfela.

### <a name="suggested-action-during-the-assess-process"></a>Sugerowana akcja w trakcie procesu oceny

Na podstawie danych z tabeli w powyższej sekcji [Dokumentowanie wyników biznesowych](#documenting-business-outcomes) prawdopodobne jest ryzyko, że portfel dąży zbyt daleko do modelu wykonywania skoncentrowanego na migracji. Jeśli obsługa klienta miałaby najwyższy priorytet, bardziej prawdopodobny byłby portfel bardziej nastawiony na innowacje. Żadne z tych podejść nie jest prawidłowe lub złe, ale zbytnie dążenie w jednym kierunku zwykle skutkuje mniejszymi zyskami, niepotrzebnie zwiększa złożoność i wydłuża czas wykonywania nakładów pracy zakresie wdrażania w chmurze.

Aby zmniejszyć złożoność, zaleca się, aby Czytelnik przestrzegał tradycyjnego podejścia do racjonalizacji portfela, ale w modelu iteracyjnym. Poniższe kroki przedstawiają model jakościowy takiego podejścia:

- Zespół strategiczny ds. chmury utrzymuje priorytetową listę prac dotyczącą obciążeń, które mają zostać poddane migracji.
- Zespół strategiczny ds. chmury i zespół wdrożeniowy ds. chmury prowadzą spotkanie dotyczące planowania wydania przed ukończeniem każdego wydania.
- W trakcie spotkania dotyczącego planowania wydania zespoły uzgadniają od 5 do 10 najważniejszych obciążeń na priorytetyzowanej liście prac.
- Poza spotkaniem planowania wydania zespół wdrożeniowy ds. chmury zadaje właścicielom aplikacji i ekspertom dziedzinowym następujące pytania:
  - Czy ta aplikacja może zostać zastąpiona odpowiednikiem platformy jako usługi (PaaS)?
  - Czy ta aplikacja jest aplikacją innej firmy?
  - Czy zatwierdzono budżet inwestycji w ciągłe tworzenie aplikacji w ciągu najbliższych 12 miesięcy?
  - Czy dodatkowy rozwój tej aplikacji poprawi środowisko klienta? Utworzy przewagę konkurencyjną? Wygeneruje dodatkowy przychód firmy?
  - Czy dane w ramach tego obciążenia przyczyniają się do dalszych innowacji związanych z technologiami analizy biznesowej, uczenia maszynowego, Internetu rzeczy lub pokrewnymi?
  - Czy obciążenie jest zgodne z nowoczesnymi platformami aplikacji, takimi jak Azure App Service?
- Odpowiedzi na powyższe pytania i wszelka inna wymagana analiza jakościowa wpływają następnie na korekty priorytetyzowanej listy prac. Te korekty mogą obejmować:
  - Jeśli obciążenie nadawałoby się do zastąpienia przy użyciu rozwiązania PaaS, mogłoby zostać całkowicie usunięte z listy prac migracji. Staranna analiza w celu podjęcia decyzji między ponownym hostowaniem a zastąpieniem zostałaby przynajmniej dodana jako zadanie, tymczasowo zmniejszając priorytet obciążenia na liście prac migracji.
  - Jeśli obciążenie jest w trakcie prac deweloperskich (lub powinno być), wówczas może najlepiej pasować do modelu refaktoryzacji/rekonstrukcji/przebudowy. Ponieważ innowacje i migracja wymagają różnych umiejętności technicznych, często zaleca się, aby aplikacje, które są zgodne z podejściem refaktoryzacji/rekonstrukcji/przebudowy, były zarządzane za pomocą listy prac innowacyjnych, zamiast listy prac migracji.
  - Jeśli obciążenie jest częścią dalszej innowacji, wtedy może mieć sens refaktoryzacja platformy danych, ale z pozostawieniem warstw aplikacji jako kandydata do ponownego hostowania. Niewielka refaktoryzacja platformy danych obciążenia może często być wprowadzona do listy prac migracji lub innowacji. Ten wynik racjonalizacji może skutkować bardziej szczegółowymi elementami roboczymi na liście prac, ale w przeciwnym razie priorytety nie zostałyby zmienione.
  - Jeśli obciążenie nie jest strategiczne, ale jest zgodne z nowoczesnymi, opartymi na chmurze platformami hostingu aplikacji, rozsądne może być przeprowadzenie niewielkiej refaktoryzacji aplikacji w celu wdrożenia jej jako nowoczesnej aplikacji. Może to przyczynić się do ogólnego oszczędności przez zredukowanie ogólnych wymagań licencyjnych IaaS i systemów operacyjnych migracji do chmury.
  - Jeśli obciążenie jest aplikacją innej firmy, a dane obciążenia nie są planowane do użycia w dalszych innowacjach, najlepszym rozwiązaniem może być pozostawienie opcji ponownego hostowania na liście prac.

Te pytania nie powinny ograniczać analizy jakościowej wykonywanej dla każdego obciążenia, ale mogą ułatwić prowadzenie rozmów, które pomogą uporać się ze złożonością niezrównoważonego portfela.

## <a name="migrate-process-changes"></a>Zmiany procesu migracji

Podczas migracji działania podejmowane w celu równoważenia portfela mogą mieć negatywny wpływ na szybkość migracji (prędkość, z jaką są migrowane zasoby). Poniższe wskazówki posłużą do rozwinięcia kwestii, dlaczego i jak należy dostosować pracę, aby uniknąć przerw w wysiłkach związanych z migracją.

### <a name="suggested-action-during-the-migrate-process"></a>Sugerowana akcja w trakcie procesu migracji

Racjonalizacja portfela wymaga różnorodności technicznych nakładów pracy. Zespoły wdrożeniowe ds. chmury mają pokusę dopasowania tej różnorodności portfela w ramach wysiłków związanych z migracją. Biznesowi uczestnicy projektu chcą współpracować z pojedynczym zespołem wdrożeniowym ds. chmury w celu prowadzenia całej listy prac migracji. Rzadko jest to zalecanym podejściem, a w wielu przypadkach może zmniejszać produktywność.

Zaleca się, aby te różnorodne wysiłki były podzielone co najmniej dwa zespoły wdrożeniowe ds. chmury. W przykładowym trybie wykonywania z zastosowaniem modelu dwóch zespołów zespół 1 jest zespołem ds. migracji, a zespół 2 jest zespołem ds. innowacji. W przypadku większych nakładów pracy te zespoły mogą być dodatkowo podzielone na inne podejścia, takie jak wysiłki zastępowania/PaaS lub niewielka refaktoryzacja. Poniżej przedstawiono umiejętności i role wymagane do ponownego hostowania, refaktoryzacji lub niewielkiej refaktoryzacji:

**Ponowne hostowanie:** Ponowne hostowanie wymaga, aby członkowie zespołu implementowali zmiany ukierunkowane na infrastrukturę. Zasadniczo odbywa się to przy użyciu narzędzia, takiego jak Azure Site Recovery, do migrowania maszyn wirtualnych lub innych zasobów na platformę Azure. Ta praca dobrze pasuje do administratorów centrum danych lub realizatorów IT. Zespół ds. migracji do chmury ma odpowiednią strukturę, aby wykonać tę pracę na dużą skalę. Jest to najszybszy sposób migrowania istniejących zasobów w większości scenariuszy.

**Refaktoryzacja:** Refaktoryzacja wymaga, aby członkowie zespołu mogli modyfikować kod źródłowy, zmieniać architekturę aplikacji lub wdrażać nowe usługi w chmurze. Zasadniczo ten w tych nakładach pracy wykorzystuje się narzędzia programistyczne, takie jak program Visual Studio i narzędzia potoku wdrażania, takie jak Azure DevOps, do ponownego wdrożenia zmodernizowanych nowoczesnych aplikacji na platformie Azure. Ta praca jest dopasowana do ról wytwarzania aplikacji lub ról wytwarzania potoku DevOps. Zespół ds. innowacji w chmurze ma najlepszą strukturę do wykonania tej pracy. Zastępowanie istniejących zasobów zasobami w chmurze w tym podejściu może zająć więcej czasu, ale natywne funkcje chmury mogą być korzystne dla aplikacji.

**Niewielka refaktoryzacja:** Niektóre aplikacje można zmodernizować za pomocą niewielkiej refaktoryzacji na poziomie danych lub aplikacji. Ta praca wymaga, aby członkowie zespołu wdrażali dane na platformach danych opartych na chmurze lub wprowadzali niewielkie zmiany konfiguracji w aplikacjach. Może to wymagać ograniczonego wsparcia ekspertów zajmujących się danymi lub rozwojem aplikacji. Jednak ta praca jest podobna do pracy wykonywanej przez realizatorów IT podczas wdrażania aplikacji innych firm. Pracę tę można łatwo dopasować do zespołu ds. migracji do chmury lub zespołu strategicznego ds. chmury. Chociaż ten nakład pracy nie zbliża się do szybkości migracji polegającej na ponownym hostowaniu, jego wykonanie zajmuje mniej czasu niż nakład pracy na refaktoryzację.

Podczas migracji zaleca się, aby nakłady pracy zostały podzielone na trzy sposoby wymienione powyżej, a ponadto, aby te nakłady pracy były wykonywane przez odpowiedni zespół w odpowiedniej iteracji. Chociaż zaleca się, aby portfel był zróżnicowany, zaleca się również, aby nakłady pracy były bardzo skoncentrowane i posegregowane.

## <a name="optimize-and-promote-process-changes"></a>Zmiany procesu optymalizacji i podwyższania poziomu

Nie są wymagane żadne dodatkowe zmiany w trakcie procesów optymalizacji i podwyższania poziomu w ramach nakładu pracy migracji.

## <a name="secure-and-manage-process-changes"></a>Zmiany procesu zabezpieczania i zarządzania

Nie są wymagane żadne dodatkowe zmiany w trakcie procesów zabezpieczania i zarządzania w ramach nakładu pracy migracji.

## <a name="next-steps"></a>Następne kroki

Wróć do [listy kontrolnej dotyczącej zakresu rozszerzonego](./index.md), aby upewnić się, że metoda migracji jest w pełni dopasowana.

> [!div class="nextstepaction"]
> [Lista kontrolna dotycząca zakresu rozszerzonego](./index.md)