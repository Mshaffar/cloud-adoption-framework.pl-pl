---
title: Ponowne hostowanie aplikacji lokalnej dla systemu Linux na maszynach wirtualnych platformy Azure
description: Dowiedz się, jak firma Contoso przeprowadza ponowne hostowanie lokalnej aplikacji dla systemu Linux przez migrację na maszyny wirtualne platformy Azure.
author: givenscj
ms.author: abuck
ms.date: 04/02/2020
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: migrate
services: azure-migrate
ms.openlocfilehash: cd92cce8ea9eafc95b5b37e2ba4056c961b29a38
ms.sourcegitcommit: 6fef15cc3a8af725dc743e19f127513bc58dd257
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/27/2020
ms.locfileid: "84023444"
---
<!-- cSpell:ignore givenscj WEBVM SQLVM OSTICKETWEB OSTICKETMYSQL contosohost vcenter contosodc contosoosticket osticket InnoDB binlog systemctl NSGs distros -->

# <a name="rehost-an-on-premises-linux-app-to-azure-vms"></a>Ponowne hostowanie aplikacji lokalnej dla systemu Linux na maszynach wirtualnych platformy Azure

W tym artykule pokazano, jak fikcyjna firma Contoso przeprowadza ponowne hostowanie dwuwarstwowej aplikacji opartej na stosie LAMP (Linux, Apache, MySQL, PHP), korzystając z maszyn wirtualnych platformy Azure w modelu „infrastruktura jako usługa” (IaaS).

Używana w tym przykładzie aplikacja do obsługi pomocy technicznej, osTicket, jest dostępna jako aplikacja open source. Jeśli chcesz użyć jej do własnych celów testowych, możesz pobrać ją z witryny [GitHub](https://github.com/osTicket/osTicket).

## <a name="business-drivers"></a>Biznesowa siła napędowa

Zespół liderów IT w ścisłej współpracy z partnerami biznesowymi firmy ustalił, co firma będzie chciała osiągnąć dzięki migracji:

- **Reagowanie na rosnące potrzeby biznesowe.** Firma Contoso rozwija się, przez co lokalne systemy i infrastruktura stają się przeciążone.
- **Ograniczanie ryzyka.** Aplikacja do obsługi pomocy technicznej ma kluczowe znaczenie dla działalności firmy Contoso. Firma Contoso chce przenieść ją na platformę Azure, eliminując ryzyko.
- **Sunąć.** Firma Contoso nie chce teraz zmieniać używanej aplikacji. Po prostu chce mieć pewność, że aplikacja jest stabilna.

## <a name="migration-goals"></a>Cele migracji

Zespół ds. chmury w firmie Contoso określił cele migracji, zgodnie z którymi należy wybrać najlepszą metodę migracji:

- Po migracji aplikacja na platformie Azure powinna mieć taką samą wydajność jak obecnie, gdy działa w lokalnym środowisku programu VMware. Aplikacja działająca w chmurze będzie miała tak samo krytyczne znaczenie jak w środowisku lokalnym.
- Firma Contoso nie chce inwestować w tę aplikację. Jest ona ważna dla działalności firmy, ale firma Contoso chce po prostu bezpiecznie przenieść ją do chmury w obecnej postaci.
- Firma Contoso nie chce zmieniać modelu operacyjnego dla tej aplikacji. Chce korzystać z aplikacji w chmurze w taki sam sposób, jak korzysta z niej teraz.
- Firma Contoso nie chce zmieniać funkcjonalności aplikacji. Zmieni się tylko jej lokalizacja.
- Firma Contoso przeprowadziła już kilka procesów migracji aplikacji dla systemu Windows, a teraz chce poznać sposób korzystania z infrastruktury platformy Azure z systemem Linux.

## <a name="solution-design"></a>Projekt rozwiązania

Po określeniu celów i wymagań firma Contoso planuje i ocenia rozwiązanie do wdrożenia oraz ustala proces migracji, w tym usługi platformy Azure, które zostaną użyte do tego celu.

### <a name="current-app"></a>Bieżąca aplikacja

- Aplikacja OSTicket działa na dwóch maszynach wirtualnych (**OSTICKETWEB** i **OSTICKETMYSQL**).
- Maszyny wirtualne znajdują się na VMware ESXi hosta **contosohost1.contoso.com** (wersja 6,5).
- Środowisko VMware jest zarządzane przez vCenter Server 6,5 (**vCenter.contoso.com**), uruchomione na maszynie wirtualnej.
- Firma Contoso ma lokalne centrum danych (**contoso-Datacenter**) z lokalnym kontrolerem domeny (**ContosoDC1**).

### <a name="proposed-architecture"></a>Proponowana architektura

- Ponieważ aplikacja jest obciążeniem produkcyjnym, maszyny wirtualne na platformie Azure będą znajdowały się w grupie zasobów produkcyjnych **ContosoRG**.
- Maszyny wirtualne zostaną przeniesione do regionu podstawowego (Wschodnie stany USA 2) i umieszczone w sieci produkcyjnej (VNET-PROD-EUS2):
  - Internetowa maszyna wirtualna zostanie umieszczona w podsieci frontonu (PROD-FE-EUS2).
  - Maszyna wirtualna bazy danych zostanie umieszczona w podsieci bazy danych (PROD-DB-EUS2).
- Lokalne maszyny wirtualne w centrum danych firmy Contoso zostaną zlikwidowane po zakończeniu migracji.

![Architektura scenariusza](./media/contoso-migration-rehost-linux-vm/architecture.png)

### <a name="solution-review"></a>Przegląd rozwiązania

Firma Contoso ocenia proponowany projekt, sporządzając listę zalet i wad.

<!-- markdownlint-disable MD033 -->

**Zagadnienie** | **Szczegóły**
--- | ---
**Zalety** | Obie maszyny wirtualne aplikacji zostaną przeniesione na platformę Azure bez zmian, co oznacza prostą migrację. <br><br> Ponieważ firma Contoso używa metody podnoszenia i przesunięcia dla maszyn wirtualnych aplikacji, nie jest wymagana specjalna konfiguracja ani narzędzia migracji dla bazy danych aplikacji. <br><br> Firma Contoso zachowa pełną kontrolę nad maszynami wirtualnymi aplikacji na platformie Azure. <br><br> Na maszynach wirtualnych aplikacji jest uruchomiony system Ubuntu 16,04-TLS, zatwierdzona dystrybucja systemu Linux. [Dowiedz się więcej](https://docs.microsoft.com/azure/virtual-machines/linux/endorsed-distros).
**Wady** | Warstwa internetowa i warstwa danych aplikacji wciąż będą stanowiły pojedynczy punkt awarii. <br><br> Firma Contoso nadal będzie musiała obsługiwać aplikację na maszynach wirtualnych na platformie Azure, zamiast przenieść ją do usługi zarządzanej, takiej jak Azure App Service czy Azure Database for MySQL. <br><br> Firma Contoso realizuje, że przez utrzymywanie prostej i przesunięcia migracji maszyn wirtualnych nie zajmują się one w pełni zaletą funkcji zapewnianych przez [Azure Database for MySQL](https://docs.microsoft.com/azure/mysql/overview), takich jak wbudowana wysoka dostępność, przewidywalna wydajność, proste skalowanie, automatyczne kopie zapasowe i wbudowane zabezpieczenia.

<!-- markdownlint-enable MD033 -->

### <a name="migration-process"></a>Proces migracji

Firma Contoso przeprowadzi migrację w następujący sposób:

- W pierwszym kroku firma Contoso przygotowuje i konfiguruje składniki platformy Azure dla Azure Migrate: Migracja serwera i przygotowuje lokalną infrastrukturę programu VMware.
- Mają już [infrastrukturę platformy Azure](./contoso-migration-infrastructure.md) , więc firma Contoso musi skonfigurować replikację maszyn wirtualnych za pomocą narzędzia do migracji Azure Migrate: serwer.
- Po przygotowaniu wszystkich elementów firma Contoso może rozpocząć replikację maszyn wirtualnych.
- Po włączeniu i uruchomieniu replikacji firma Contoso przeprowadzi migrację maszyny wirtualnej przez przełączenie jej do trybu failover na platformę Azure.

![Proces migracji](./media/contoso-migration-rehost-linux-vm/migration-process-az-migrate.png)

### <a name="azure-services"></a>Usługi platformy Azure

**Usługa** | **Opis** | **Koszty**
--- | --- | ---
[Azure Migrate: Migracja serwera](https://docs.microsoft.com/azure/migrate/contoso-migration-rehost-linux-vm) | Usługa organizuje migrację lokalnych aplikacji i obciążeń oraz wystąpień maszyn wirtualnych AWS/GCP, a także zarządza tym procesem. | Podczas replikacji na platformę Azure naliczane są opłaty za usługę Azure Storage. Maszyny wirtualne platformy Azure są tworzone i wiążą się z opłatami, gdy odbywa się migracja. [Dowiedz się więcej](https://azure.microsoft.com/pricing/details/azure-migrate) o opłatach i cenach.

## <a name="prerequisites"></a>Wymagania wstępne

W tym scenariuszu firma Contoso potrzebuje następujących elementów.

<!-- markdownlint-disable MD033 -->

**Wymagania** | **Szczegóły**
--- | ---
**Subskrypcja platformy Azure** | Firma Contoso utworzyła subskrypcje na początku tej serii artykułów. Jeśli nie masz subskrypcji platformy Azure, Utwórz [bezpłatne konto](https://azure.microsoft.com/pricing/free-trial). <br><br> Jeśli bezpłatne konto właśnie zostało utworzone, jesteś administratorem subskrypcji i możesz wykonywać wszystkie akcje. <br><br> Jeśli używasz istniejącej subskrypcji i nie jesteś jej administratorem, musisz skontaktować się z administratorem w celu uzyskania uprawnień właściciela lub współautora. <br><br> Jeśli potrzebujesz bardziej szczegółowych uprawnień, zapoznaj się z [tym artykułem](https://docs.microsoft.com/azure/site-recovery/site-recovery-role-based-linked-access-control).
**Infrastruktura platformy Azure** |  [Dowiedz się](./contoso-migration-infrastructure.md), jak firma Contoso skonfigurowała infrastrukturę platformy Azure. <br><br> Dowiedz się więcej na temat wymagań [wstępnych](https://docs.microsoft.com/azure/migrate/contoso-migration-rehost-linux-vm#prerequisites) dotyczących Azure Migrate: Migracja serwera.
**Serwery lokalne** | Lokalny serwer vCenter powinien mieć uruchomioną wersję 5,5, 6,0 lub 6,5. <br><br> Host ESXi z systemem w wersji 5,5, 6,0 lub 6,5. <br><br> Co najmniej jedna maszyna wirtualna programu VMware uruchomiona na hoście ESXi.
**Lokalne maszyny wirtualne** | Zapoznaj się z [systemem Linux dystrybucje](https://docs.microsoft.com/azure/virtual-machines/linux/endorsed-distros) , które są zatwierdzone do uruchamiania na platformie Azure.

<!-- markdownlint-enable MD033 -->

## <a name="scenario-steps"></a>Etapy scenariusza

Firma Contoso przeprowadzi migrację w następujący sposób:

> [!div class="checklist"]
>
> - **Krok 1. Przygotowywanie platformy Azure dla Azure Migrate: Migracja serwera.** Dodają narzędzie migracji serwera do projektu usługi Azure Migrate.
> - **Krok 2: Przygotowanie lokalnego programu VMware dla Azure Migrate: Migracja serwera.** Przygotowuje konta do odnajdywania maszyn wirtualnych i przygotowuje się do łączenia się z maszynami wirtualnymi platformy Azure po migracji.
> - **Krok 3. replikowanie maszyn wirtualnych.** Konfigurują replikację i rozpoczynają replikowanie maszyn wirtualnych w magazynie platformy Azure.
> - **Krok 4. Migrowanie maszyn wirtualnych przy użyciu Azure Migrate: Migracja serwera.** Przeprowadzają migrację testową, aby upewnić się, że wszystko działa, a następnie przeprowadzić migrację, aby przenieść maszyny wirtualne na platformę Azure.

## <a name="step-1-prepare-azure-for-the-azure-migrate-server-migration-tool"></a>Krok 1. Przygotowywanie platformy Azure dla Azure Migrate: Narzędzia migracji serwera

Oto składniki platformy Azure, których firma Contoso potrzebuje do zmigrowania maszyn wirtualnych na platformę Azure:

- Sieć wirtualna, w której będą znajdować się maszyny wirtualne platformy Azure, gdy są one tworzone podczas migracji.
- Azure Migrate: zainicjowano narzędzie do migracji serwera.

Te składniki są ustawiane w następujący sposób:

1. **Skonfiguruj sieć:** Firma Contoso skonfigurował już sieć, która może być dla Azure Migrate: Migracja serwera podczas [wdrażania infrastruktury platformy Azure](./contoso-migration-infrastructure.md)

    - Aplikacja SmartHotel360 jest aplikacją produkcyjną, a maszyny wirtualne zostaną zmigrowane do sieci produkcyjnej platformy Azure (VNET-PROD-EUS2) w regionie głównym Wschodnie stany USA 2.
    - Obie maszyny wirtualne zostaną umieszczone w grupie zasobów ContosoRG, która jest używana na potrzeby zasobów produkcyjnych.
    - Maszyna wirtualna frontonu aplikacji (WEBVM) zostanie zmigrowana do podsieci frontonu (PROD-FE-EUS2) w sieci produkcyjnej.
    - Maszyna wirtualna bazy danych aplikacji (SQLVM) zostanie zmigrowana do podsieci bazy danych (PROD-DB-EUS2) w sieci produkcyjnej.

2. **Inicjowanie obsługi administracyjnej Azure Migrate: Narzędzia migracji serwera:** W przypadku konta sieci i magazynu firma Contoso tworzy teraz magazyn Recovery Services (ContosoMigrationVault) i umieszcza go w grupie zasobów ContosoFailoverRG w regionie głównej Wschodnie stany USA 2.

    ![Azure Migrate: Narzędzie do migracji serwera](./media/contoso-migration-rehost-linux-vm/server-migration-tool.png)

**Potrzebujesz dodatkowej pomocy?**

Dowiedz się więcej na temat konfigurowania [Azure Migrate: Narzędzia migracji serwera](https://docs.microsoft.com/azure/migrate/migrate-services-overview#azure-migrate-server-migration-tool).

## <a name="step-2-prepare-on-premises-vmware-for-azure-migrate-server-migration"></a>Krok 2: Przygotowanie lokalnego programu VMware dla Azure Migrate: Migracja serwera

Po migracji na platformę Azure firma Contoso chce mieć możliwość nawiązania połączenia z replikowanymi maszynami wirtualnymi na platformie Azure. W tym celu administratorzy firmy Contoso muszą wykonać kilka czynności:

- Aby mieć dostęp do maszyn wirtualnych platformy Azure za pośrednictwem Internetu, muszą włączyć protokół SSH na lokalnych maszynach wirtualnych systemu Linux przed migracją. W przypadku Ubuntu można to zrobić za pomocą następującego polecenia: `sudo apt-get ssh install -y` .
- Po uruchomieniu migracji mogą sprawdzić **diagnostykę rozruchu** , aby wyświetlić zrzut ekranu maszyny wirtualnej.
- Jeśli to nie zadziała, muszą upewnić się, że maszyna wirtualna jest uruchomiona, i zapoznać się z tymi [poradami dotyczącymi rozwiązywania problemów](https://social.technet.microsoft.com/wiki/contents/articles/31666.troubleshooting-remote-desktop-connection-after-failover-using-asr.aspx).

**Potrzebujesz dodatkowej pomocy?**

- Dowiedz się więcej o [przygotowywaniu maszyn wirtualnych do migracji](https://docs.microsoft.com/azure/migrate/contoso-migration-rehost-linux-vm#prepare-vms-for-migration).

## <a name="step-3-replicate-the-on-premises-vms"></a>Krok 3. replikowanie lokalnych maszyn wirtualnych

Przed uruchomieniem migracji na platformę Azure administratorzy firmy Contoso muszą skonfigurować i włączyć replikację.

Po ukończeniu odnajdywania można rozpocząć replikację maszyn wirtualnych VMware na platformę Azure.

1. Na **serwerach**Azure Migrate project > **Azure Migrate: Migracja serwera**, wybierz opcję **replikacja**.

    ![Replikowanie maszyn wirtualnych](./media/contoso-migration-rehost-linux-vm/select-replicate.png)

2. W obszarze **Replikacja** > **Ustawienia źródła** > **Czy maszyny są zwirtualizowane** wybierz pozycję **Tak, z funkcją VMware vSphere Hypervisor**.

3. W obszarze **Urządzenie lokalne** wybierz nazwę skonfigurowanego urządzenia usługi Azure Migrate > przycisk **OK**.

    ![Ustawienia źródła](./media/contoso-migration-rehost-linux-vm/source-settings.png)

4. W obszarze **Maszyny wirtualne** wybierz maszyny wirtualne, które mają być replikowane.
    - Jeśli przeprowadzasz ocenę dla maszyn wirtualnych, możesz zastosować rekomendacje dotyczące rozmiarów maszyn wirtualnych i typów dysków (Premium/standardowy) w wynikach oceny. W tym celu w obszarze **Zaimportować ustawienia migracji z oceny usługi Azure Migrate?** wybierz opcję **Tak**.
    - Jeśli nie uruchomiono oceny lub nie chcesz używać ustawień oceny, wybierz opcję **Nie**.
    - W przypadku wybrania opcji korzystania z oceny wybierz grupę maszyn wirtualnych i nazwę oceny.

    ![Wybieranie oceny](./media/contoso-migration-rehost-linux-vm/select-assessment.png)

5. W obszarze **Maszyny wirtualne** wyszukaj potrzebne maszyny wirtualne i sprawdź każdą maszynę wirtualną, którą chcesz migrować. Następnie wybierz kolejno pozycje **Dalej: ustawienia docelowe**.

6. W obszarze **Ustawienia elementu docelowego** wybierz subskrypcję i docelowy region migracji, a następnie określ grupę zasobów, w której będą znajdować się maszyny wirtualne platformy Azure po migracji. W obszarze **Sieć wirtualna** wybierz sieć wirtualną/podsieć platformy Azure, do której zostaną dołączone maszyny wirtualne platformy Azure po migracji.

7. W **korzyść użycia hybrydowego platformy Azure**wybierz następujące opcje:

    - Wybierz pozycję **Nie**, jeśli nie chcesz stosować korzyści użycia hybrydowego platformy Azure. Następnie wybierz pozycję **Dalej**.
    - Wybierz opcję **Tak**, jeśli masz maszyny z systemem Windows Server, które są objęte aktywnym programem Software Assurance lub subskrypcjami systemu Windows Server, i chcesz zastosować korzyść do migrowanych maszyn. Następnie wybierz pozycję **Dalej**.

8. W obszarze **Obliczenia** sprawdź nazwę, rozmiar, typ dysku systemu operacyjnego i zestaw dostępności maszyny wirtualnej. Maszyny wirtualne muszą być zgodne z [wymaganiami platformy Azure](https://docs.microsoft.com/azure/migrate/migrate-support-matrix-vmware#vmware-requirements).

    - **Rozmiar maszyny wirtualnej:** Jeśli używasz zaleceń dotyczących oceny, lista rozwijana rozmiaru maszyny wirtualnej będzie zawierać zalecany rozmiar. W przeciwnym razie usługa Azure Migrate wybierze rozmiar na podstawie najbliższego dopasowania w subskrypcji platformy Azure. Alternatywnie możesz wybrać rozmiar ręczny w obszarze **rozmiaru maszyny wirtualnej platformy Azure**.
    - **Dysk systemu operacyjnego:** Określ dysk systemu operacyjnego (Boot) dla maszyny wirtualnej. Dysk systemu operacyjnego to dysk, na którym jest zainstalowany program ładujący i instalator systemu operacyjnego.
    - **Zestaw dostępności:** Jeśli maszyna wirtualna powinna znajdować się w zestawie dostępności platformy Azure po migracji, określ zestaw. Zestaw musi znajdować się w docelowej grupie zasobów określonej dla migracji.

9. W obszarze **Dyski** określ, czy dyski maszyn wirtualnych mają być replikowane na platformę Azure, a następnie wybierz typ dysku (standardowe dyski SSD/dyski twarde lub dyski zarządzane w warstwie Premium) na platformie Azure. Następnie wybierz pozycję **Dalej**.
    - Dyski można wykluczyć z replikacji.
    - Jeśli wykluczysz dyski, nie będą one znajdować się na maszynie wirtualnej platformy Azure po migracji.

10. W obszarze **Przegląd i uruchamianie replikacji**Sprawdź ustawienia, a następnie wybierz pozycję **Replikuj** , aby rozpocząć replikację początkową dla serwerów.

> [!NOTE]
> Ustawienia replikacji można aktualizować w dowolnym momencie przed rozpoczęciem replikacji w obszarze **Zarządzanie**  >  **maszynami replikowanymi**. Ustawień nie można zmienić po rozpoczęciu replikacji.

## <a name="step-4-migrate-the-vms"></a>Krok 4. Migrowanie maszyn wirtualnych

Administratorzy firmy Contoso uruchamiają szybką migrację testową, a następnie przeprowadzają migrację do przenoszenia maszyn wirtualnych.

### <a name="run-a-test-migration"></a>Uruchamianie migracji testowej

1. W obszarze serwery **celów migracji**  >  **Servers**  >  **Azure Migrate: Migracja serwera**wybierz kolejno pozycje **Testuj zmigrowane serwery**.

     ![Serwery z przeprowadzoną migracją testową](./media/contoso-migration-rehost-linux-vm/test-migrated-servers.png)

2. Kliknij prawym przyciskiem myszy maszynę wirtualną do przetestowania, a następnie wybierz pozycję **Testuj migrację**.

    ![Testowanie migracji](./media/contoso-migration-rehost-linux-vm/test-migrate.png)

3. W obszarze **Testowanie migracji** wybierz sieć wirtualną platformy Azure, w której zostanie umieszczona maszyna wirtualna platformy Azure po migracji. Zalecamy użycie sieci wirtualnej nieprodukcyjnej.
4. Zostanie uruchomione zadanie **Testowanie migracji**. Monitoruj zadanie w powiadomieniach portalu.
5. Po zakończeniu migracji sprawdź zmigrowane maszyny wirtualne platformy Azure w obszarze **Maszyny wirtualne** w witrynie Azure Portal. Nazwa maszyny ma sufiks **-Test**.
6. Po zakończeniu testu kliknij prawym przyciskiem myszy maszynę wirtualną platformy Azure w obszarze **replikowanie maszyn**, a następnie wybierz polecenie **Oczyść test migracja**.

    ![Czyszczenie migracji](./media/contoso-migration-rehost-linux-vm/clean-up.png)

### <a name="migrate-the-vms"></a>Migrowanie maszyn wirtualnych

Teraz Administratorzy firmy Contoso uruchamiają pełną migrację, aby zakończyć przenoszenie.

1. W Azure Migrate serwery > projektu **Servers**  >  **Azure Migrate: Migracja serwera**, wybierz opcję **replikowanie serwerów**.

    ![Replikowanie serwerów](./media/contoso-migration-rehost-linux-vm/replicating-servers.png)

2. W obszarze **Replikowanie maszyn** kliknij prawym przyciskiem myszy maszynę wirtualną > **Migruj**.
3. W obszarze **Migrowanie**  >  **Zamknij maszyny wirtualne i przeprowadź planowaną migrację bez utraty danych**wybierz pozycję **tak**  >  **OK**.
    - Domyślnie usługa Azure Migrate zamyka lokalną maszynę wirtualną i uruchamia replikację na żądanie, aby zsynchronizować wszystkie zmiany maszyny wirtualnej, które wystąpiły od momentu ostatniej replikacji. Gwarantuje to brak utraty danych.
    - Jeśli nie chcesz zamykać maszyny wirtualnej, wybierz pozycję **nie**.
4. Zostanie uruchomione zadanie migracji maszyny wirtualnej. Śledź zadanie w powiadomieniach platformy Azure.
5. Po zakończeniu zadania możesz wyświetlić maszynę wirtualną i zarządzać nią na stronie **Maszyny wirtualne**.

### <a name="connect-the-vm-to-the-database"></a>Łączenie maszyny wirtualnej z bazą danych

W ostatnim kroku procesu migracji Administratorzy firmy Contoso aktualizują parametry połączenia aplikacji w taki sposób, aby wskazywały bazę danych aplikacji działającą na maszynie wirtualnej **OSTICKETMYSQL** .

1. Konfigurują połączenie SSH z maszyną wirtualną **OSTICKETMYSQL** za pomocą programu Putty lub innego klienta SSH. Maszyna wirtualna jest prywatna, a więc nawiązują połączenie przy użyciu prywatnego adresu IP.

    ![Łączenie z bazą danych](./media/contoso-migration-rehost-linux-vm/db-connect.png)

    ![Łączenie z bazą danych](./media/contoso-migration-rehost-linux-vm/db-connect2.png)

2. Muszą upewnić się, że maszyna wirtualna **OSTICKETWEB** może komunikować się z maszyną **OSTICKETMYSQL**. Obecnie w konfiguracji jest na stałe zapisany lokalny adres IP 172.16.0.43.

    **Przed aktualizacją:**

    ![Aktualizowanie adresu IP](./media/contoso-migration-rehost-linux-vm/update-ip1.png)

    **Po aktualizacji:**

    ![Aktualizowanie adresu IP](./media/contoso-migration-rehost-linux-vm/update-ip2.png)

3. Ponownie uruchamiają usługę za pomocą polecenia **systemctl restart apache2**.

    ![Ponowne uruchamianie](./media/contoso-migration-rehost-linux-vm/restart.png)

4. Na koniec aktualizują rekordy DNS dla maszyn wirtualnych **OSTICKETWEB** i **OSTICKETMYSQL** na jednym z kontrolerów domeny firmy Contoso.

    ![Aktualizowanie rekordów DNS](./media/contoso-migration-rehost-linux-vm-mysql/update-dns.png)

    ![Aktualizowanie rekordów DNS](./media/contoso-migration-rehost-linux-vm-mysql/update-dns.png)

**Potrzebujesz dodatkowej pomocy?**

- Dowiedz się więcej o [uruchamianiu migracji testowej](https://docs.microsoft.com/azure/migrate/tutorial-migrate-vmware#run-a-test-migration).
- Dowiedz się więcej o [migrowaniu maszyn wirtualnych na platformę Azure](https://docs.microsoft.com/azure/migrate/tutorial-migrate-vmware#migrate-vms).

## <a name="clean-up-after-migration"></a>Czyszczenie zasobów po migracji

Po zakończeniu migracji warstwy aplikacji osTicket działają na maszynach wirtualnych platformy Azure.

Teraz firma Contoso musi wykonać następujące czynności w celu wyczyszczenia zasobów:

- Usunięcie lokalnych maszyn wirtualnych ze spisu serwera vCenter.
- Usunięcie lokalnych maszyn wirtualnych z lokalnych zadań kopii zapasowej.
- Aktualizacja dokumentacji wewnętrznej w celu wskazania nowej lokalizacji i adresów IP maszyn wirtualnych OSTICKETWEB i OSTICKETMYSQL.
- Przejrzeć wszystkie zasoby korzystające z tych maszyn wirtualnych i zaktualizować wszelkie ustawienia lub dokumenty, aby odzwierciedlały nową konfigurację.
- Firma Contoso użyła usługi Azure Migrate z maszyną wirtualną zarządzania do oceny maszyn wirtualnych do migracji. Administratorzy powinni usunąć maszynę wirtualną migracji i maszyny wirtualne sieci Web z programu VmWare ESX Server.

## <a name="review-the-deployment"></a>Przegląd wdrożenia

Po uruchomieniu aplikacji firma Contoso musi w pełni zoperacjonalizować i zabezpieczyć nową infrastrukturę.

### <a name="security"></a>Zabezpieczenia

Zespół ds. zabezpieczeń firmy Contoso przegląda maszyny wirtualne OSTICKETWEB i OSTICKETMYSQL w celu ustalenia wszelkich problemów z zabezpieczeniami.

- Zespół przegląda sieciowe grupy zabezpieczeń używane do kontroli dostępu do maszyn wirtualnych. Sieciowe grupy zabezpieczeń zapewniają, że do aplikacji będzie przekazywany tylko dozwolony ruch.
- Zespół rozważa również zabezpieczenie danych na dyskach maszyn wirtualnych przy użyciu usług Disk Encryption i Azure Key Vault.

Aby uzyskać więcej informacji, zobacz [najlepsze rozwiązania w zakresie zabezpieczeń dotyczące obciążeń IaaS na platformie Azure](https://docs.microsoft.com/azure/security/fundamentals/iaas).

### <a name="bcdr"></a>Zapewnienie ciągłości działania i odzyskiwanie po awarii

W celu zapewnienia ciągłości działania i odzyskiwania po awarii firma Contoso podejmuje następujące działania:

- **Zachowaj bezpieczeństwo danych.** Firma Contoso tworzy kopie zapasowe danych na maszynach wirtualnych za pomocą usługi Azure Backup. [Dowiedz się więcej](https://docs.microsoft.com/azure/backup/backup-overview).
- **Zapewnienie ciągłości działania aplikacji.** Firma Contoso replikuje maszyny wirtualne aplikacji w regionie pomocniczym platformy Azure za pomocą usługi Site Recovery. [Dowiedz się więcej](https://docs.microsoft.com/azure/site-recovery/azure-to-azure-quickstart).

### <a name="licensing-and-cost-optimization"></a>Licencjonowanie i optymalizacja kosztów

- Po wdrożeniu zasobów firma Contoso przypisuje tagi platformy Azure zdefiniowane na etapie [wrażania infrastruktury platformy Azure](./contoso-migration-infrastructure.md#set-up-tagging).
- Firma Contoso nie ma żadnych problemów z licencjonowaniem serwerów z systemem Ubuntu.
- Firma Contoso będzie używać [Azure Cost Management](https://azure.microsoft.com/services/cost-management) , aby zapewnić, że pozostają w ramach budżetów ustanowionych przez ich lidera.
