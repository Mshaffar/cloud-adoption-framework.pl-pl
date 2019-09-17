---
title: Skuteczne organizowanie zasobów platformy Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Najlepsze rozwiązania umożliwiające efektywne organizowanie zasobów platformy Azure w celu ułatwienia zarządzania.
author: laraaleite
ms.author: kfollis
ms.date: 04/09/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 2951c3049a22036199e2bc73a6d3f9283582e7e1
ms.sourcegitcommit: a26c27ed72ac89198231ec4b11917a20d03bd222
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2019
ms.locfileid: "70818510"
---
# <a name="organize-your-azure-resources"></a>Organizowanie zasobów platformy Azure

Organizowanie zasobów opartych na chmurze ma kluczowe znaczenie dla zabezpieczania i śledzenia kosztów związanych z obciążeniami oraz zarządzania nimi. Aby zorganizować zasoby, użyj hierarchii zarządzania w ramach platformy Azure, zaimplementuj dobrze przemyślane konwencje nazewnictwa i zastosuj tagowanie zasobów.

<!-- markdownlint-disable MD024 MD025 -->

# <a name="azure-management-groups-and-hierarchytabazuremanagmentgroupsandhierarchy"></a>[Grupy zarządzania i hierarchia platformy Azure](#tab/AzureManagmentGroupsAndHierarchy)

Platforma Azure oferuje cztery poziomy zakresu zarządzania: grupy zarządzania, subskrypcje, grupy zasobów i zasoby. Na poniższej ilustracji przedstawiono relacje tych poziomów.

   ![Diagram przedstawiający relację hierarchii zarządzania](./media/organize-resources/scope-levels.png)

- **Grupy zarządzania:** Te grupy to kontenery, które ułatwiają zarządzanie dostępem, zasadami i zgodnością w wielu subskrypcjach. Wszystkie subskrypcje w grupie zarządzania automatycznie dziedziczą warunki zastosowane do tej grupy zarządzania.
- **Subskrypcje:** Subskrypcja grupuje konta użytkowników i zasobów, które zostały utworzone przez te konta użytkowników. Każda subskrypcja ma ograniczenia lub limity przydziału ilości zasobów, które można tworzyć i stosować. Organizacje mogą używać subskrypcji do zarządzania kosztami i zasobami, które są tworzone przez użytkowników, zespoły lub projekty.
- **Grupy zasobów:** Grupa zasobów to logiczny kontener przeznaczony do wdrażania zasobów platformy Azure, takich jak aplikacje internetowe, bazy danych i konta magazynu, oraz zarządzania nimi.
- **Zasoby:** zasoby to tworzone przez Ciebie wystąpienia usług, takie jak maszyny wirtualne, magazyn lub bazy danych SQL.

## <a name="scope-of-management-settings"></a>Zakres ustawień zarządzania

Ustawienia zarządzania, takie jak zasady i kontrola dostępu na podstawie ról, można stosować na dowolnym poziomie zarządzania. Zasięg zastosowania ustawienia jest określany na podstawie wybranego poziomu. Niższe poziomy dziedziczą ustawienia z wyższych poziomów. Na przykład zasady stosowane do subskrypcji są również stosowane do wszystkich grup zasobów i zasobów w ramach tej subskrypcji.

Krytyczne ustawienia zwykle warto stosować na wyższych poziomach, a wymagania specyficzne dla projektu na niższych poziomach. Może na przykład zajść potrzeba upewnienia się, że wszystkie zasoby w organizacji zostaną wdrożone w określonych regionach. W tym celu należy do subskrypcji zastosować zasady, które określą dozwolone lokalizacje. Kiedy inni użytkownicy w organizacji będą dodawać nowe grupy zasobów i zasoby, dozwolone lokalizacje będą automatycznie wymuszane. Dowiedz się więcej na temat zasad w sekcji dotyczącej zarządzania, zabezpieczeń i zgodności tego przewodnika.

Jeśli masz tylko kilka subskrypcji, niezależne zarządzanie nimi jest stosunkowo proste. Jeśli liczba używanych przez Ciebie subskrypcji rośnie, rozważ utworzenie hierarchii grup zarządzania, aby uprościć zarządzanie subskrypcjami i zasobami. Aby uzyskać więcej informacji na temat zarządzania wieloma subskrypcjami, zobacz [skalowanie za pomocą wielu subskrypcji platformy Azure](../considerations/scaling-subscriptions.md).

Podczas planowania strategii zgodności pracuj z osobami, które pełnią w organizacji role związane z następującymi obszarami: bezpieczeństwo i zgodność, administracja IT, architektura przedsiębiorstwa, sieć, finanse i zaopatrzenie.

::: zone target="docs"

## <a name="create-a-management-level"></a>Tworzenie poziomu zarządzania

Możesz utworzyć grupę zarządzania, dodatkowe subskrypcje lub grupy zasobów.

### <a name="create-a-management-group"></a>Tworzenie grupy zarządzania

Utwórz grupę zarządzania, która ułatwia zarządzanie dostępem, zasadami i zgodnością w wielu subskrypcjach.

1. Przejdź do pozycji [Grupy zarządzania](https://portal.azure.com/#blade/Microsoft_Azure_ManagementGroups/HierarchyBlade).
2. Wybierz pozycję **Dodaj grupę zarządzania**.

### <a name="create-a-subscription"></a>Tworzenie subskrypcji

Subskrypcje umożliwiają zarządzanie kosztami i zasobami, które są tworzone przez użytkowników, zespoły lub projekty.

1. Przejdź do pozycji [Subskrypcje](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade).
1. Wybierz pozycję **Dodaj**.

### <a name="create-a-resource-group"></a>Tworzenie grupy zasobów

Utwórz grupę zasobów do przechowywania zasobów, takich jak aplikacje internetowe, bazy danych i konta magazynu, które współużytkują ten sam cykl życia, uprawnienia i zasady.

1. Przejdź do pozycji [Grupy zasobów](https://portal.azure.com/#create/Microsoft.ResourceGroup).
1. Wybierz pozycję **Dodaj**.
1. Wybierz **subskrypcję**, w ramach której chcesz utworzyć grupę zasobów.
1. Wprowadź nazwę **grupy zasobów**.
1. Wybierz **region** dla lokalizacji grupy zasobów.

## <a name="learn-more"></a>Dowiedz się więcej

Aby dowiedzieć się więcej, zobacz:

- [Podstawy platformy Azure](../considerations/fundamental-concepts.md)
- [Skalowanie za pomocą wielu subskrypcji platformy Azure](../considerations/scaling-subscriptions.md)
- [Informacje o zarządzaniu dostępem do zasobów na platformie Azure](../../governance/resource-consistency/azure-resource-access.md)
- [Organizowanie zasobów przy użyciu grup zarządzania platformy Azure](/azure/azure-resource-manager/management-groups-overview)
- [Limity usług subskrypcji](/azure/azure-subscription-service-limits)

::: zone-end

::: zone target="chromeless"

## <a name="actions"></a>Akcje

**Tworzenie grupy zarządzania:**

Utwórz grupę zarządzania, która ułatwia zarządzanie dostępem, zasadami i zgodnością w wielu subskrypcjach.

1. Przejdź do pozycji **Grupy zarządzania**.
1. Wybierz pozycję **Dodaj grupę zarządzania**.

::: form action="OpenBlade[#blade/Microsoft_Azure_ManagementGroups/HierarchyBlade]" submitText="Go to Management groups" :::

**Tworzenie dodatkowej subskrypcji:**

Subskrypcje umożliwiają zarządzanie kosztami i zasobami, które są tworzone przez użytkowników, zespoły lub projekty.

1. Przejdź do pozycji **Subskrypcje**.
1. Wybierz pozycję **Dodaj**.

::: form action="OpenBlade[#blade/Microsoft_Azure_Billing/SubscriptionsBlade]" submitText="Go to Subscriptions" :::

**Tworzenie grupy zasobów:**

Utwórz grupę zasobów do przechowywania zasobów, takich jak aplikacje internetowe, bazy danych i konta magazynu, które współużytkują ten sam cykl życia, uprawnienia i zasady.

1. Przejdź do pozycji **Grupy zasobów**.
1. Wybierz pozycję **Dodaj**.
1. Wybierz **subskrypcję**, w ramach której chcesz utworzyć grupę zasobów.
1. Wprowadź nazwę **grupy zasobów**.
1. Wybierz **region** dla lokalizacji grupy zasobów.

::: form action="Create[#create/Microsoft.ResourceGroup]" submitText="Create a resource group" :::

::: zone-end

# <a name="naming-standardstabnamingstandards"></a>[Standardy nazewnictwa](#tab/NamingStandards)

Odpowiedni standard nazewnictwa ułatwia identyfikowanie zasobów w witrynie Azure Portal, na rachunku i w ramach skryptów. Strategia nazewnictwa powinna zawierać szczegóły biznesowe i operacyjne jako składniki nazw zasobów:

- Biznesowy aspekt tej strategii powinien zapewniać, że nazwy zasobów obejmują informacje organizacyjne konieczne do zidentyfikowania zespołów. Korzystaj z zasobów wraz z właścicielami biznesowymi, którzy odpowiadają za koszty zasobów.

- Strona operacyjna powinna zapewniać, że nazwy zawierają informacje, których potrzebują zespoły IT. Użyj szczegółów, które identyfikują obciążenie, aplikację, środowisko, informacje krytyczne i inne informacje przydatne do zarządzania zasobami.

Różne typy zasobów mogą mieć różne limity długości i dozwolone znaki, z których wiele zostało wymienionych w artykule na temat najlepszych rozwiązaniach platformy Azure dotyczących [konwencji nazewnictwa](/azure/architecture/best-practices/naming-conventions). Aby uzyskać więcej informacji i zaleceń dotyczących w szczególności obsługi zadań związanych z wdrażaniem chmury w przedsiębiorstwie, zobacz [wskazówki dotyczące nazewnictwa i tagowania](../considerations/name-and-tag.md) w przewodniku Cloud Adoption Framework.

Poniższa tabela zawiera wzorce nazewnictwa dla kilku przykładowych typów zasobów platformy Azure.

::: zone target="docs"

>[!TIP]
>Należy unikać używania znaków specjalnych (`-` lub `_`) jako pierwszego lub ostatniego znaku w dowolnej nazwie. Te znaki sprawiają, że większość reguł walidacji kończy się niepowodzeniem.

::: zone-end

| Jednostka | Zakres | Długość | Wielkość liter | Prawidłowe znaki | Sugerowany wzorzec | Przykład |
| --- | --- | --- | --- | --- | --- | --- |
|Grupa zasobów |Subskrypcja |1-90 |Bez uwzględniania wielkości liter |Alfanumeryczne, podkreślenie, nawiasy, łącznik, kropka (z wyjątkiem znaków na końcu) i znaki Unicode |`<service short name>-<environment>-rg` |`profx-prod-rg` |
|Zestaw dostępności |Grupa zasobów |1-80 |Bez uwzględniania wielkości liter |Alfanumeryczne, podkreślenie i łącznik |`<service-short-name>-<context>-as` |`profx-sql-as` |
|Tag |Skojarzona jednostka |512 (nazwa), 256 (wartość) |Bez uwzględniania wielkości liter |Alfanumeryczne |`"key" : "value"` |`"department" : "Central IT"` |

# <a name="resource-tagstabresourcetags"></a>[Tagi zasobów](#tab/ResourceTags)

Tagi ułatwiają szybkie identyfikowanie zasobów i grup zasobów. Stosowanie tagów do zasobów platformy Azure umożliwia ich logiczne zorganizowanie według kategorii. Każdy tag składa się z nazwy i wartości. Na przykład można zastosować nazwę „Środowisko” i wartość „Produkcyjne” do wszystkich zasobów w środowisku produkcyjnym. Tagi powinny zawierać kontekst dotyczący obciążenia lub aplikacji skojarzonych z zasobem, wymagania operacyjne oraz informacje o własności.

Po zastosowaniu tagów można pobrać wszystkie zasoby w subskrypcji o nazwie i wartości konkretnego tagu. Tagi umożliwiają pobieranie powiązanych zasobów z różnych grup zasobów, które są pomocne w przypadku organizowania zasobów na potrzeby rozliczeń lub zarządzania.

Tagów można używać do wielu innych celów. Najczęstsze zastosowania to:

- **Metadane i dokumentacja:** Administratorzy mogą łatwo wyświetlać szczegółowe informacje o zasobach, z którymi pracują, stosując tag, na przykład „ProjectOwner”.
- **Automatyzacja:** Można używać regularnie uruchamianych skryptów, które mogą wykonywać akcję w oparciu o wartość tagu, taką jak „ShutdownTime” lub „DeprovisionDate”.
- **Rozliczenia:** tagi mogą być wyświetlane na fakturze. Można ich używać, aby ułatwić dzielenie rachunku na segmenty za pomocą tagów, takich jak „CostCenter” lub „BillTo”.

Każdy zasób lub grupa zasobów może mieć co najwyżej 15 par nazwy i wartości tagu. To ograniczenie dotyczy tylko tagów stosowanych bezpośrednio do grupy zasobów lub zasobu.

Aby uzyskać więcej zaleceń i przykładów dotyczących tagowania, zobacz [wskazówki dotyczące tagowania](../considerations/name-and-tag.md) w przewodniku Cloud Adoption Framework.

::: zone target="docs"

## <a name="apply-a-resource-tag"></a>Stosowanie tagu zasobu

Aby zastosować tag do grupy zasobów:

1. Przejdź do pozycji [Grupy zasobów](https://portal.azure.com/#blade/HubsExtension/Resources/resourceType/Microsoft.Resources%2Fsubscriptions%2FresourceGroups).
1. Wybierz grupę zasobów.
1. Wybierz pozycję **Przypisz tagi**.
1. Wprowadź nową nazwę i wartość lub użyj listy rozwijanej, aby wybrać istniejącą nazwę i wartość.

## <a name="learn-more"></a>Dowiedz się więcej

Aby dowiedzieć się więcej, zobacz [Organizowanie zasobów platformy Azure przy użyciu tagów](/azure/azure-resource-manager/resource-group-using-tags).

::: zone-end

::: zone target="chromeless"

## <a name="action"></a>Akcja

**Stosowanie tagu zasobu:**

Aby zastosować tag do grupy zasobów:

1. Przejdź do pozycji **Grupy zasobów**.
1. Wybierz grupę zasobów.
1. Wybierz pozycję **Tagi**.
1. Wprowadź nową nazwę i wartość lub wybierz istniejącą nazwę i wartość.

::: form action="OpenBlade[#blade/HubsExtension/Resources/resourceType/Microsoft.Resources%2Fsubscriptions%2FresourceGroups]" submitText="Go to resource groups" :::

::: zone-end