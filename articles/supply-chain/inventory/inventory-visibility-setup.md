---
title: Installare il componente aggiuntivo Visibilità magazzino
description: Questo argomento descrive come installare Il componente aggiuntivo di visibilità dell'inventario per Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2b85f533a3318701ed08857b899cf9bdd103863
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474822"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installare e configurare Visibilità inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Questo argomento descrive come installare Il componente aggiuntivo di visibilità dell'inventario per Microsoft Dynamics 365 Supply Chain Management.

È necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) per installare il componente aggiuntivo Visibilità dell'inventario. LCS è un portale di collaborazione che fornisce un ambiente e un insieme di servizi regolarmente aggiornati che ti aiutano a gestire il ciclo di vita delle applicazioni di finanza e operazioni.

Per ulteriori informazioni, vedere [Risorse Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Prerequisiti per la visibilità dell'inventario

Prima di installare la Visibilità dell'inventario, è necessario completare i seguenti compiti:

- Ottenere un progetto di implementazione LCS in cui almeno un ambiente è distribuito.
- Assicurati che i prerequisiti per l'impostazione degli componente aggiuntivo siano stati completati. Per informazioni su questi prerequisiti, vedi [Panoramica sugli componente aggiuntivo](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Visibilità magazzino non richiede un collegamento a doppia scrittura.
- Contatta il team del prodotto Visibilità dell'inventario all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere i seguenti file necessari:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (se la versione di Supply Chain Management in esecuzione è precedente alla versione 10.0.18)

> [!NOTE]
> I paesi e le aree geografiche attualmente supportati includono il Canada (CCA, ECA), gli Stati Uniti (WUS, EUS), l'Unione Europea (NEU, WEU), il Regno Unito (SUK, WUK), l'Australia (EAU, SEAU), il Giappone (EJP, WJP) e il Brasile (SBR, SCUS).

Se hai domande su questi prerequisiti, contatta il team del prodotto Visibilità dell'inventario.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Configurare Dataverse

Per impostare Dataverse in modo che possa essere utilizzato con Visibilità dell'inventario, utilizzare lo strumento di distribuzione dei pacchetti per distribuire il pacchetto Visibilità dell'inventario. Le seguenti sottosezioni descrivono come completare ogni compito.

> [!NOTE]
> Attualmente, solo gli ambienti Dataverse che sono stati creati usando LCS sono supportati. Se il tuo ambiente Dataverse è stato creato in qualche altro modo (per esempio, usando il centro amministrativo Power Apps ), e se è collegato al tuo ambiente di Supply Chain Management, devi prima contattare il team del prodotto Visibilità dell'inventario per risolvere il problema di mappatura. Puoi quindi installare Visibilità dell'inventario.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrare da una vecchia versione della soluzione Dataverse 

Se hai installato una versione precedente della soluzione Visibilità dell'inventario Dataverse , usa queste istruzioni per aggiornare la tua versione. Ci sono due casi:

- **Caso 1:** Se hai impostato manualmente Dataverse importando la soluzione `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip` , segui questi passi:

    1. Scaricate i seguenti tre file:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Importa manualmente `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` e `InventoryServiceBase_managed.cab` in Dataverse seguendo questi passi:

        1. Aprire l'URL del proprio ambiente Dataverse.
        1. Aprire la pagina delle **soluzioni** .
        1. Selezionare **Importa**.

    1. Usa lo strumento di distribuzione dei pacchetti per distribuire il pacchetto `InventoryServiceApplication.PackageDeployer.zip` . Per istruzioni, vedi la sezione [Usare lo strumento di distribuzione dei pacchetti per distribuire il pacchetto](#deploy-package) più avanti in questo argomento.

- **Caso 2:** Se hai impostato Dataverse usando lo strumento di distribuzione dei pacchetti prima di installare il vecchio pacchetto `.*PackageDeployer.zip` , scarica `InventoryServiceApplication.PackageDeployer.zip`, e fai un aggiornamento. Per istruzioni, vedi la sezione [Usare lo strumento di distribuzione dei pacchetti per distribuire il pacchetto](#deploy-package) .

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Utilizzare lo strumento di distribuzione dei pacchetti per distribuire il pacchetto

1. Installare gli strumenti di sviluppo come descritto in [Scaricare gli strumenti da NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Sblocca il file `InventoryServiceApplication.PackageDeployer.zip` che hai scaricato dal gruppo Teams seguendo questi passaggi:

    1. Seleziona e tieni premuto (o fai clic con il tasto destro del mouse) il file, quindi seleziona **Proprietà**.
    1. Nella finestra di dialogo **Proprietà**, nella scheda **Generale**, trova la sezione **Sicurezza**, seleziona **Sblocca** e applica la modifica. Se non c'è una sezione **Sicurezza** nella scheda **Generale** , il file non è bloccato. In questo caso, vai al passo successivo.

    ![Sbloccare il file scaricato](media/unblock-file.png "Sbloccare il file scaricato")

1. Decomprimete `InventoryServiceApplication.PackageDeployer.zip` per trovare i seguenti elementi:

    - Cartella `InventoryServiceApplication`
    - File `[Content_Types].xml`
    - File `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`

1. Copia ciascuno di questi elementi nella directory `.\Tools\PackageDeployment` . (Questa directory è stata creata quando hai installato gli strumenti di sviluppo)
1. Eseguite `.\Tools\PackageDeployment\PackageDeployer.exe`, e seguite le istruzioni sullo schermo per importare le soluzioni.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installare il componente aggiuntivo Visibilità magazzino

Prima di installare il componente aggiuntivo, registra un'applicazione e aggiungi un segreto cliente a Azure Active Directory (Azure AD) sotto il tuo abbonamento Azure. Per le istruzioni, vedi [Registrare un'applicazione](/azure/active-directory/develop/quickstart-register-app) e [Aggiungere un segreto cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Assicurati di prendere nota dei valori **ID dell'applicazione (cliente)**, **segreto del cliente** e **ID tenant** , perché ne avrai bisogno in seguito.

Dopo aver registrato un'applicazione e aggiunto un segreto del cliente a Azure AD, segui questi passi per installare il componente aggiuntivo Visibilità dell'inventario.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index).
1. Nella home page, selezionare il progetto in cui è distribuito l'ambiente.
1. Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.
1. Nella pagina dell'ambiente, scorri verso il basso fino a trovare la sezione **Environment componente aggiuntivos** nella sezione **Integrazione Power Platform** . Lì potete trovare il nome dell'ambiente Dataverse .
1. Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.

    ![Pagina dell'ambiente in LCS](media/inventory-visibility-environment.png "Pagina dell'ambiente in LCS")

1. Selezionare il collegamento **Installare un nuovo componente aggiuntivo**. Appare una lista di componente aggiuntivo disponibili.
1. Nell'elenco, seleziona **Visibilità dell'inventario**.
1. Imposta i seguenti campi per il tuo ambiente:

    - **ID dell'applicazione AAD (client)** - Inserisci l'ID dell'applicazione Azure AD che hai creato e di cui hai preso nota in precedenza.
    - **ID tenant AAD** - Inserisci l'ID tenant che hai annotato in precedenza.

    ![Pagina di installazione del componente aggiuntivo](media/inventory-visibility-setup.png "Pagina di installazione del componente aggiuntivo")

1. Accetta i termini e le condizioni selezionando la casella di controllo **Termini e condizioni** .
1. Seleziona **Installa**. Lo stato del componente aggiuntivo è mostrato come **Installazione in corso**. Quando l'installazione è completata, aggiorna la pagina. Lo stato dovrebbe cambiare in **Installato**.

> [!IMPORTANT]
> Se è disponibile più di un ambiente LCS, creare un'applicazione Azure AD diversa per ogni ambiente. Se si utilizza lo stesso ID applicazione e ID tenant per installare il componente aggiuntivo Visibilità inventario per ambienti diversi, si verificherà un problema relativo al token per gli ambienti meno recenti. Sarà valido solo l'ultimo installato.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Disinstallare il componente aggiuntivo per la visibilità dell'inventario

Per disinstallare il componente aggiuntivo di Visibilità dell'inventario, seleziona **Disinstalla** nella pagina LCS. Il processo di disinstallazione termina il componente aggiuntivo di Visibilità dell'inventario, disregistra il componente aggiuntivo da LCS ed elimina qualsiasi dato temporaneo che è memorizzato nella cache dei dati di Visibilità dell'inventario componente aggiuntivo. Tuttavia, i dati dell'inventario primario che sono memorizzati nel tuo abbonamento Dataverse non vengono cancellati.

Per disinstallare i dati dell'inventario che sono memorizzati nel tuo abbonamento Dataverse , apri [Power Apps](https://make.powerapps.com), seleziona **Ambiente** nella barra di navigazione e seleziona l'ambiente Dataverse che è legato al tuo ambiente LCS. Poi vai su **Soluzioni** e cancella le seguenti cinque soluzioni:

- Soluzione di ancoraggio per l'applicazione Visibilità inventario nelle soluzioni Dynamics 365.
- Soluzione per applicazioni di Dynamics 365 FNO SCM Inventory Visibility
- Configurazione del servizio di inventario
- Visibilità inventario autonomo
- Soluzione base di Dynamics 365 FNO SCM Inventory Visibility

Dopo aver cancellato queste soluzioni, anche i dati memorizzati nelle tabelle saranno cancellati.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurare Visibilità inventario in Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Distribuire il pacchetto di integrazione di Visibilità magazzino

Se si utilizza Supply Chain Management versione 10.0.17 o versione precedente, contattare il team di supporto di Visibilità magazzino all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per ottenere il file del pacchetto. Distribuire quindi il pacchetto in LCS.

> [!NOTE]
> Se durante la distribuzione si verifica un errore di mancata corrispondenza della versione, è necessario importare manualmente il progetto X++ nell'ambiente di sviluppo. Creare quindi il pacchetto distribuibile nell'ambiente di sviluppo e distribuirlo nell'ambiente di produzione.
>
> Il codice è incluso con Supply Chain Management versione 10.0.18. Se si esegue quella versione o una versione successiva, la distribuzione non è necessaria.

Assicurarsi che le seguenti funzionalità siano attivate nell'ambiente Supply Chain Management (per impostazione predefinita, sono attivate).

| Descrizione delle funzionalità | Versione codice | Alterna classe |
|---|---|---|
| Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Abilitare o disabilitare l'utilizzo delle dimensioni inventariali nella tabella InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Imposta integrazione di Visibilità magazzino

Dopo aver installato il componente aggiuntivo, preparare il sistema Supply Chain Management per utilizzarlo effettuando le seguenti operazioni:

1. In Supply Chain Management, aprire l'area di lavoro **[Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e attivare le seguenti funzionalità:
    - *Integrazione di Visibilità inventario* - Obbligatoria.
    - *Integrazione di Visibilità inventario con offset della prenotazione* - Consigliata ma facoltativa. Richiede la versione 10.0.22 o successiva. Per maggiori informazioni, vedere [Prenotazioni di visibilità dell'inventario](inventory-visibility-reservations.md).

1. Andare a **Gestione inventario \> Impostazione \> Parametri di integrazione di Visibilità inventario**.
1. Aprire la scheda **Generale** ed effettuare le seguenti impostazioni:
    - **Endpoint Visibilità inventario** - Immettere l'URL dell'ambiente in cui si sta eseguendo Visibilità inventario. Per maggiori informazioni, vedere [Trovare l'endpoint del servizio](inventory-visibility-configuration.md#get-service-endpoint).
    - **Numero massimo di record in una singola richiesta** - Impostare il numero massimo di record da includere in una singola richiesta. È necessario inserire un numero intero positivo minore o uguale a 1.000. Il valore predefinito è 512. Si consiglia vivamente di mantenere il valore predefinito a meno che il supporto tecnico Microsoft non abbia fornito indicazioni che sia necessario modificarlo o si sia altrimenti sicuri di tale necessità.

1. Se è stata abilitata la funzionalità *Integrazione di Visibilità inventario con offset della prenotazione*, aprire la scheda **Offset prenotazione** ed effettuare le seguenti impostazioni:
    - **Abilita offset prenotazione** - Impostare su *Sì* per abilitare questa funzionalità.
    - **Modificatore offset prenotazione** - Selezionare lo stato della transazione di inventario che eseguirà l'offset delle prenotazioni effettuato su Visibilità inventario. Questa impostazione determina la fase di elaborazione dell'ordine che attiva gli offset. La fase è tracciata dallo stato di transazione dell'inventario dell'ordine. Sono disponibili le seguenti opzioni:
        - *Su ordine* - Per lo stato *On transaction* , un ordine invierà una richiesta di offset quando viene creato. La quantità su cui è stato eseguito l'offset sarà la quantità dell'ordine creato.
        - *Riserva* - Per lo stato di *transazione Riserva ordinata* , un ordine invierà una richiesta di compensazione quando viene prenotato, prelevato, imbucato o fatturato. La richiesta sarà attivata solo una volta, per il primo passo quando si verifica il processo menzionato. La quantità su cui è stato eseguito l'offset sarà la quantità da cui lo stato della transazione di inventario è stato modificato da *Merci ordinate in corso di consegna* a *Ordinato prenotato* (o stato successivo) nella riga dell'ordine corrispondente.

1. Selezionare **Gestione articoli \> Periodico \> Integrazione di Visibilità magazzino** e abilitare il processo. Tutti gli eventi di modifica delle scorte di Supply Chain Management verranno ora registrati in Visibilità magazzino.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
