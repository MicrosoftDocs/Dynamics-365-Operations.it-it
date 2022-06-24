---
title: Installare il componente aggiuntivo Visibilità magazzino
description: Questo articolo descrive come installare Il componente aggiuntivo di visibilità dell'inventario per Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ce81ed2ed79bfe5c7fff9724e14af150817af11f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895701"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installare e configurare Inventory Visibility

[!include [banner](../includes/banner.md)]

Questo articolo descrive come installare Il componente aggiuntivo di visibilità dell'inventario per Microsoft Dynamics 365 Supply Chain Management.

È necessario utilizzare Microsoft Dynamics Lifecycle Services (LCS) per installare il componente aggiuntivo Visibilità dell'inventario. LCS è un portale di collaborazione che fornisce un ambiente e un insieme di servizi regolarmente aggiornati che ti aiutano a gestire il ciclo di vita delle applicazioni di finanza e operazioni. Per ulteriori informazioni, vedere [Risorse Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Ti consigliamo di unirti al gruppo di utenti del componente aggiuntivo Visibilità inventario, dove puoi trovare guide utili, ricevere i nostri ultimi aggiornamenti e pubblicare eventuali domande sull'utilizzo di Visibilità inventario. Per aderire, invia un'e-mail al team del prodotto Visibilità inventario all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) e includi il tuo ID ambiente di Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Prerequisiti per la visibilità dell'inventario

Prima di installare la Visibilità dell'inventario, è necessario completare i seguenti compiti:

- Ottenere un progetto di implementazione LCS in cui almeno un ambiente è distribuito.
- Assicurati che i prerequisiti per l'impostazione degli componente aggiuntivo siano stati completati. Per informazioni su questi prerequisiti, vedi [Panoramica sugli componente aggiuntivo](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Visibilità magazzino non richiede un collegamento a doppia scrittura.

> [!NOTE]
> I paesi e le aree geografiche attualmente supportati includono il Canada (CCA, ECA), gli Stati Uniti (WUS, EUS), l'Unione Europea (NEU, WEU), il Regno Unito (SUK, WUK), l'Australia (EAU, SEAU), il Giappone (EJP, WJP) e il Brasile (SBR, SCUS).

In caso di domande su questi prerequisiti, contattare il team del prodotto Visibilità inventario all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installare il componente aggiuntivo Visibilità magazzino

Prima di installare il componente aggiuntivo, registra un'applicazione e aggiungi un segreto cliente a Azure Active Directory (Azure AD) sotto il tuo abbonamento Azure. Per le istruzioni, vedi [Registrare un'applicazione](/azure/active-directory/develop/quickstart-register-app) e [Aggiungere un segreto cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Assicurati di prendere nota dei valori **ID dell'applicazione (cliente)**, **segreto del cliente** e **ID tenant** , perché ne avrai bisogno in seguito.

> [!IMPORTANT]
> Se è disponibile più di un ambiente LCS, crea un'applicazione Azure AD diversa per ogni ambiente. Se si utilizza lo stesso ID applicazione e ID tenant per installare il componente aggiuntivo Visibilità inventario per ambienti diversi, si verificherà un problema relativo al token per gli ambienti meno recenti. Di conseguenza, sarà valida solo l'ultima installazione.

Dopo aver registrato un'applicazione e aggiunto un segreto del cliente a Azure AD, segui questi passi per installare il componente aggiuntivo Visibilità dell'inventario.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index).
1. Nella home page, selezionare il progetto in cui è distribuito l'ambiente.
1. Nella pagina del progetto, selezionare l'ambiente in cui si desidera installare il componente aggiuntivo.
1. Nella pagina dell'ambiente, scorri verso il basso fino a trovare la sezione **Environment componente aggiuntivos** nella sezione **Integrazione Power Platform** . Lì potete trovare il nome dell'ambiente Dataverse . Confermare che il nome dell'ambiente Dataverse sia quello che si desidera utilizzare per la Visibilità dell'inventario.

    > [!NOTE]
    > Attualmente, solo gli ambienti Dataverse che sono stati creati usando LCS sono supportati. Se l'ambiente Dataverse è stato creato in qualche altro modo (per esempio, usando l'interfaccia di amministrazione Power Apps) e se è collegato all'ambiente di Supply Chain Management, è necessario prima contattare il team del prodotto Visibilità inventario all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) per risolvere il problema di mapping. Puoi quindi installare Visibilità dell'inventario.

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
1. In Dataverse, selezionare la sezione **App** nella sezione nel riquadro di spostamento a sinistra e verificare che Power Apps **Visibilità inventario** sia installato correttamente. Se la sezione **App** non esiste, contattare il team del prodotto Visibilità inventario all'indirizzo [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!NOTE]
> Se l'installazione dalla pagina LCS impiega più di un'ora, è probabile che il tuo account utente non abbia l'autorizzazione per installare le soluzioni nell'ambiente Dataverse. Per risolvere il problema, segui questi passaggi:
>
> 1. Annulla il processo di installazione del componente aggiuntivo di Visibilità dell'inventario dalla pagina LCS.
> 1. Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) e assicurati che l'account utente che desideri utilizzare per installare il componente aggiuntivo abbia la licenza "Piano di Dynamics 365 Unified Operations" assegnata. Assegna la licenza se necessario.
> 1. Accedi all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com) utilizzando il relativo account utente. Quindi installa il componente aggiuntivo per la visibilità dell'inventario effettuando le seguenti operazioni:
>     1. Seleziona l'ambiente in cui vuoi installare il componente aggiuntivo.
>     1. Seleziona **App Dynamics 365**.
>     1. Seleziona **Installa app**.
>     1. Seleziona **Visibilità inventario**
>
> 1. Al termine dell'installazione, torna alla pagina LCS e riprova a reinstallare il componente aggiuntivo **Visibilità inventario**.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Disinstallare il componente aggiuntivo per la visibilità dell'inventario

Per disinstallare il componente aggiuntivo di Visibilità dell'inventario, seleziona **Disinstalla** nella pagina LCS. Il processo di disinstallazione termina il componente aggiuntivo di Visibilità dell'inventario, disregistra il componente aggiuntivo da LCS ed elimina qualsiasi dato temporaneo che è memorizzato nella cache dei dati di Visibilità dell'inventario componente aggiuntivo. Tuttavia, i dati dell'inventario primario che sono memorizzati nel tuo abbonamento Dataverse non vengono cancellati.

Per disinstallare i dati dell'inventario che sono memorizzati nel tuo abbonamento Dataverse , apri [Power Apps](https://make.powerapps.com), seleziona **Ambiente** nella barra di navigazione e seleziona l'ambiente Dataverse che è legato al tuo ambiente LCS. Andare quindi a **Soluzioni** ed eliminare le seguenti cinque soluzioni in questo ordine:

1. Soluzione di ancoraggio per l'applicazione Visibilità inventario nelle soluzioni Dynamics 365.
1. Soluzione per applicazioni di Dynamics 365 FNO SCM Inventory Visibility
1. Configurazione del servizio di inventario
1. Visibilità inventario autonomo
1. Soluzione base di Dynamics 365 FNO SCM Inventory Visibility

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
