---
title: 'Wprowadzenie: Tworzenie zespołu danych w chmurze'
description: Ten przewodnik ułatwia zespołowi danych zrozumienie zakresu, elementów dostarczanych i możliwości, dla których są odpowiedzialni.
author: JanetCThomas
ms.author: janet
ms.service: cloud-adoption-framework
ms.subservice: overview
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: c6d5350b98433044b877bd726871e94a0061474c
ms.sourcegitcommit: 60d8b863d431b5d7c005f2f14488620b6c4c49be
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2020
ms.locfileid: "83229173"
---
<!-- docsTest:disable -->
<!-- TODO: Finish this article. -->

<!---Recommended: Remove all the comments in this template before you sign-off or merge to master.--->
<!---quickstarts are fundamental day-1 instructions for helping new customers use a subscription to quickly try out a specific product/service.
The entire activity is a short set of steps that provides an initial experience.
You only use quickstarts when you can get the service, technology, or functionality into the hands of new customers in less than 10 minutes.
--->

# <a name="get-started-build-a-cloud-data-team"></a>Wprowadzenie: Tworzenie zespołu danych w chmurze

<!---Required:
Starts with "Get started: " and is ideally two lines or less when rendered on a 1920x1080 screen. Make the first word following "Get started:" a verb, which is to say, an action. The "X" part should identify both the technology or service involved (such as App Service, Cosmos DB, etc.) and the language or framework, if applicable (.NET Core, Python, JavaScript, Java, etc.) The language or framework shouldn't appear in parentheses.

This quickstart helps you understand the goals and objectives of a data team working on cloud adoption.

<!-- In the opening sentence, focus on the job or task to be completed, emphasizing. General industry terms (such as "serverless," which are better for SEO) more than Microsoft-branded terms or acronyms (such as "Azure Functions" or "AKS"). That is, try to include terms people typically search for and avoid using _only_ Microsoft terms. -->

<!--After the opening sentence, provide a light introduction that describes, again in customer-friendly language, what the customer will learn in the process of accomplishing the stated goal. Answer the fundamental "why would I want to do this?" question.

Avoid the following elements whenever possible:
- Avoid callouts (note, important, tip, etc.) because readers tend to skip over them.
Important callouts like preview status or version caveats can be included under prerequisites.

- Avoid links, which are generally invitations for the reader to leave the article and not complete the experience of the quickstart. The exception are links to alternate versions of the same content (such as when you have a VSCode-oriented article and a CLI-oriented article). Those links help get the reader to the right article, rather than being a distraction. If you feel that there are other important concepts needing links, make reviewing a particular article a prerequisite. Otherwise, rely on the line of standard links (see below).

- Avoid any indication of the time it takes to complete the quickstart, because there's already the "x minutes to read" at the top and making a second suggestion can be contradictory.

- Avoid a bullet list of steps or other details in the quickstart: the H2's shown on the right of the docs page already fulfill this purpose.

- Avoid screenshots or diagrams: the opening sentence should be sufficient to explain the result, and other diagrams count as conceptual material that is best in a linked overview.
--->

<!-- Optional standard links: if there are suitable links, you can include a single line of applicable links for companion content at the end of the introduction. Don't use the line if there's only a single link. -->

<!-- NOTE: the Azure subscription line is moved to Prerequisites. -->

## <a name="prerequisites"></a>Wymagania wstępne

<!-- Make Prerequisites the first H2 after the H1. Omit any preliminary text to the list.-->

- Obowiązkowe Zakończenie wszelkich wymaganych szkoleń. Użyj języka "uzupełnianie _tytułu_", gdzie _tytuł_ jest linkiem do szkolenia.
- Konto platformy Azure z aktywną subskrypcją. [Utwórz konto bezpłatnie](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
- Pierwsze wymaganie wstępne: inne metody, dla których czytelnik powinien mieć wiedzę.
- Drugie wymaganie wstępne.
- Trzecie wymaganie wstępne.

<!-- Include this heading even if there aren't any prerequisites, in which case just use the text: "None" (not bulleted). The reason for this is to maintain consistency across services, which trains readers to always look in the same place. -->

<!-- When there are prerequisites, list each as items, not instructions to minimize the verbiage.
For example, use "Python 3.6" instead of "Install Python 3.6". If the prerequisite is something to install, link to the applicable installer or download. Selecting the item/link is then the action to fulfill the prerequisite. Use an action word only if necessary to make the meaning clear.
Don't use links to conceptual information about a prerequisite; only use links for installers.

List prerequisites in the following order:
- An Azure account with an active subscription. [Create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
- Language runtimes (Python, Node, .NET, etc.)
- Packages (from pip, npm, nuget, etc.)
- Tools (like VSCode IF REQUIRED. Don't include tools like pip if they're automatically installed with another tool or language runtime, like Python. Don't include optional tools like text editors--include them only if the quickstart demonstrates them.)
- Sample code
- Specialized hardware
- Other preparatory work, such as creating a VM (OK to link to another article)
- Azure keys
- Service-specific keys

The reason for placing runtimes and tools first is that it might take time to install them, and it's best to get a user started sooner than later.

If you feel like your quickstart has a lot of prerequisites, the quickstart might be the wrong content type; a tutorial or how-to guide might be the better option. Remember that quickstarts should be something a reader can complete in 10 minutes or less.

--->

## <a name="minimum-scope"></a>Zakres minimalny

<!---Required:
Quickstarts are prescriptive and guide the customer through an end-to-end procedure.
Make sure to use specific naming for setting up accounts and configuring technology.

Avoid linking off to other content; include whatever the customer needs to complete the scenario in the article. For example, if the customer needs to set permissions, include the permissions they need to set, and the specific settings in the quickstart procedure. Don't send the customer to another article to read about it.

In a break from tradition, do not link to reference topics in the procedural part of the quickstart when using cmdlets or code. Provide customers what they need to know in the quickstart to successfully complete the quickstart.

For portal-based procedures, minimize bullets and numbering.

For the CLI or PowerShell based procedures, don't use bullets or numbering.

Be mindful of the number of H2/procedures in the Quickstart. 3-5 procedural steps are about right. Once you've staged the article, look at the right-hand "In this article" section on the docs page; if there are more than 8 total, consider restructuring the article.
--->

Uwzględnij zdanie lub dwa, aby wyjaśnić tylko minimalny zakres dla zespołu.

Użyj punktowanej lub numerowanej listy zadań, które mogą być wymagane w tym zakresie.

1. Krok 1
1. Krok 2
1. Krok 3
1. Krok 4

## <a name="deliverable"></a>Dostarcza

Uwzględnij zdanie lub dwa, aby wyjaśnić element dostarczany, który będzie wynikiem pobytu w minimalnym zakresie.

Użyj punktora lub listy uporządkowanej, zgodnie z potrzebami w celu ułatwienia czytelności.

1. Pierwszy element dostarczany
1. Drugi element dostarczany
1. Trzeci element dostarczany

## <a name="baseline-capability"></a>Możliwość linii bazowej

Dołącz zdanie lub dwa, aby wyjaśnić możliwości odniesienia w tym miejscu.

Użyj punktora lub listy numerowanej, zgodnie z potrzebami, aby ułatwić czytelność.

- Element 1
- Element 2
- Element 3

## <a name="out-of-scope"></a>Poza zakresem

Krótko Wyjaśnij, co znajduje się poza zakresem, i podaj linki do dodatkowych informacji.

- Dodatkowy element informacyjny i link.
- Dodatkowy element informacyjny i link.

## <a name="next-steps"></a>Następne kroki

Przejdź do metodologii lub następnego tematu logicznego.
> [!div class="nextstepaction"]
> [Przycisk Następne kroki](../../index.yml)

<!--- Required:
Quickstarts should always have a Next steps H2 that points to the next logical quickstart in a series, or, if there are no other quickstarts, to some other cool thing the customer can do. A single link in the blue box format should direct the customer to the next article; and you can shorten the title in the boxes if the original one doesn't fit.
Do not use a "more info" section or a "resources" section or "see also" section". --->