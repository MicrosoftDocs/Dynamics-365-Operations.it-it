---
title: Configurare le tabelle virtuali di Dataverse
description: In questo argomento viene descritto come configurare le tabelle virtuali per Dynamics 365 Human Resources. Genera e aggiorna tabelle virtuali esistenti e analizza tabelle generate e disponibili.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 04997aba427ae6013c8154593b09ae1a45a580c3
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935755"
---
# <a name="configure-dataverse-virtual-tables"></a>Configurare le tabelle virtuali di Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources è un'origine dati virtuale in Microsoft Dataverse. Fornisce operazioni complete di creazione, lettura, aggiornamento ed eliminazione (CRUD) di Dataverse e Microsoft Power Platform. I dati delle tabelle virtuali non sono archiviati in Dataverse, ma nel database dell'applicazione.

Per abilitare le operazioni CRUD nelle entità di Human Resources da Dataverse, devi rendere le entità disponibili come tabelle virtuali in Dataverse. Ciò consente di eseguire operazioni CRUD di Dataverse e Microsoft Power Platform sui dati presenti in Human Resources. Le operazioni supportano anche le convalide complete della logica aziendale di Human Resources per garantire l'integrità dei dati durante la scrittura degli stessi nelle entità.

> [!NOTE]
> Le entità di Human Resources corrispondono alle tabelle Dataverse. Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Tabelle virtuali disponibili per Human Resources

Tutte le entità Open Data Protocol (OData) di Human Resources sono disponibili come tabelle virtuali in Dataverse. Sono inoltre disponibili in Power Platform. Ora puoi creare app ed esperienze con dati direttamente da Human Resources mediante funzionalità CRUD complete, senza copiare o sincronizzare i dati in Dataverse. Puoi usare i portali Power Apps per creare siti Web rivolti all'esterno che consentono scenari di collaborazione per processi aziendali in Human Resources.

Puoi visualizzare l'elenco delle tabelle virtuali abilitate nell'ambiente e iniziare a lavorare con le tabelle in [Power Apps](https://make.powerapps.com), nella soluzione **Dynamics 365 HR Virtual Tables**.

![Tabelle virtuali di Dynamics 365 HR in Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tabelle virtuali contro tabelle native

Le tabelle virtuali di Human Resources non sono uguali alle tabelle Dataverse native create per Human Resources. 

Le tabelle native per Human Resources vengono generate separatamente e gestite nella soluzione Gestione connessione ibrida comune in Dataverse. Con le tabelle native, i dati vengono archiviati in Dataverse e richiedono la sincronizzazione con il database dell'applicazione Human Resources.

> [!NOTE]
> Per un elenco delle tabelle Dataverse native per Human Resources, vedi [Tabelle di Dataverse](./hr-developer-entities.md).

## <a name="setup"></a>Attrezzaggio

Segui questi passaggi di configurazione per abilitare le tabelle virtuali nel tuo ambiente.

### <a name="enable-virtual-tables-in-human-resources"></a>Abilitare le tabelle virtuali in Human Resources

Innanzitutto, è necessario abilitare le tabelle virtuali nell'area di lavoro **Gestione delle funzionalità**.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare il riquadro **Gestione funzionalità**.

3. Selezionare **Supporto per tabelle virtuali per HR in Dataverse** e quindi seleziona **Abilita**.

Per ulteriori informazioni sull'abilitazione e sulla disabilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrare l'app in Microsoft Azure

È necessario registrare l'istanza di Human Resources nel portale di Azure di modo che Microsoft Identity Platform possa fornire servizi di autenticazione e autorizzazione per l'app e gli utenti. Per ulteriori informazioni sulla registrazione di app in Azure, vedi [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app).

1. Apri il [portale di Microsoft Azure](https://portal.azure.com).

2. Nell'elenco di servizi di Azure, seleziona **Registrazioni app**.

3. Seleziona **Nuova registrazione**.

4. Nel campo **Nome** immetti un nome descrittivo per l'app. Ad esempio, **Tabelle virtuali di Dynamics 365 Human Resources**.

5. Nel campo **URI di reindirizzamento**, immetti l'URL dello spazio dei nomi dell'istanza di Human Resources.

6. Seleziona **Registro**.

7. Al termine della registrazione, il portale di Azure visualizza il riquadro **Panoramica** della registrazione dell'app che include il relativo **ID applicazione (client)**. Prendi nota adesso dell'**ID applicazione (client)**. Immetterai queste informazioni quando si [configura l'origine dati delle tabelle virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. Nel riquadro di spostamento a sinistra, seleziona **Certificati e segreti**.

9. Nella sezione **Segreti client** della pagina, seleziona **Nuovo segreto client**.

10. Fornisci una descrizione, seleziona una durata e seleziona **Aggiungi**.

11. Registra il valore del segreto della proprietà **Value** della tabella. Immetterai queste informazioni quando si [configura l'origine dati delle tabelle virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Assicurati di prendere nota adesso del valore del segreto. Il segreto non viene mai visualizzato dopo la chiusura di questa pagina.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Installare l'app Dynamics 365 HR Virtual Table

Installa l'app Dynamics 365 HR Virtual Table nell'ambiente Power Apps per distribuire il pacchetto di soluzioni di tabelle virtuali in Dataverse.

1. In Human Resources, aprire la pagina **Integrazione di Microsoft Dataverse**.

2. Selezionare la scheda **Tabelle virtuali**.

3. Selezionare **Installa l'app Virtual Table**.

### <a name="configure-the-virtual-table-data-source"></a>Configurare l'origine dati delle tabelle virtuali

Il passaggio successivo consiste nel configurare l'origine dati delle tabelle virtuali nell'ambiente Power Apps.

1. Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2. Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.

3. Seleziona l'**URL ambiente** nella sezione **Dettagli** della pagina.

4. In **Hub integrità soluzione**, seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina dell'applicazione.

5. Nella pagina **Ricerca avanzata**, nell'elenco a discesa **Cerca**, seleziona **Configurazioni dell'origine dati virtuale di Finance and Operations**.

   > [!NOTE]
   > L'installazione dell'app Virtual Table dal passaggio di configurazione precedente può richiedere alcuni minuti. Se **Configurazioni dell'origine dati virtuale di Finance and Operations** non è disponibile nell'elenco, attendi un minuto e aggiorna l'elenco.

6. Seleziona **Risultati**.

7. Seleziona il record **Origine dati Microsoft HR**.

8. Immettere le informazioni necessarie per la configurazione dell'origine dati:

   - **URL di destinazione**: l'URL dello spazio dei nomi di Human Resources. Il formato dell'URL di destinazione è:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Ad esempio:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Assicurarsi di includere il carattere "**/**" alla fine dell'URL per evitare di ricevere un errore.

   - **ID tenant**: l'ID tenant di Azure Active Directory (Azure AD).

   - **ID applicazione AAD**: l'ID applicazione (client) creato per l'applicazione registrata nel portale di Microsoft Azure. Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **ID applicazione AAD**: il segreto client creato per l'applicazione registrata nel portale di Microsoft Azure. Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Origine dati di Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Seleziona **Salva e chiudi**.

### <a name="grant-app-permissions-in-human-resources"></a>Concedere autorizzazioni dell'app in Human Resources

Concedi autorizzazioni per due applicazioni Azure AD in Human Resources:

- L'app creata per il tenant nel portale di Microsoft Azure
- L'app Dynamics 365 HR Virtual Table installata nell'ambiente Power Apps 

1. In Human Resources, apri la pagina **Applicazioni di Azure Active Directory**.

2. Seleziona **Nuovo** per creare un nuovo record di applicazione:

    - Nel campo **ID client**, inserisci l'ID client dell'app che hai registrato nel portale di Microsoft Azure.
    - Nel campo **Nome**, immetti il nome dell'app che hai registrato nel portale di Microsoft Azure.
    - Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.

3. Seleziona **Nuovo** per creare un secondo record di applicazione:

    - **ID client**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nome**: Dynamics 365 HR Virtual Table
    - Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.

## <a name="generate-virtual-tables"></a>Generare tabelle virtuali

Al termine della configurazione, puoi selezionare le tabelle virtuali che desideri generare e abilitare nell'istanza di Dataverse.

1. In Human Resources, aprire la pagina **Integrazione di Microsoft Dataverse**.

2. Selezionare la scheda **Tabelle virtuali**.

> [!NOTE]
> L'interruttore **Abilita tabelle virtuale** sarà impostato su **Sì** automaticamente quando tutte le impostazioni richieste sono state completate. Se l'interruttore è impostato su **No**, rivedere i passaggi nelle sezioni precedenti di questo documento per assicurarsi che tutte le impostazioni dei prerequisiti siano state completate.

3. Seleziona la tabella o le tabelle da generare in Dataverse.

4. Selezionare **Genera/Aggiorna**.

![Integrazione di Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Controllare lo stato di generazione della tabella

Le tabelle virtuali vengono generate in Dataverse attraverso un processo in background asincrono. Aggiornamenti sulla visualizzazione del processo nel centro azioni. I dettagli sul processo, inclusi i log degli errori, vengono visualizzati nella pagina **Automazioni di processo**.

1. In Human Resources, aprire la pagina **Automazioni di processo**.

2. Selezionare la scheda **Processi in background**.

3. Seleziona **Processo in background dell'operazione asincrona di polling della tabella virtuale**.

4. Selezionare **Visualizza risultati più recenti**.

Il riquadro scorrevole mostra i risultati di esecuzione più recenti per il processo. È possibile visualizzare il registro del processo, inclusi eventuali errori restituiti da Dataverse.

## <a name="see-also"></a>Vedere anche

[Che cos'è Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tabelle in Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Panoramica delle relazioni tra tabelle](/powerapps/maker/common-data-service/relationships-overview)<br>
[Creare e modificare tabelle virtuali che contengono dati di un'origine dati esterna](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Cosa sono i portali di Power Apps?](/powerapps/maker/portals/overview)<br>
[Panoramica sulla creazione di app in Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
