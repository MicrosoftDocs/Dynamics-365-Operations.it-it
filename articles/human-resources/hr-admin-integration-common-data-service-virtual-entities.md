---
title: Configurare le entità virtuali di Common Data Service
description: In questo argomento viene descritto come configurare le entità virtuali di Dynamics 365 Human Resources. Genera e aggiorna entità virtuali esistenti e analizza entità generate e disponibili.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645603"
---
# <a name="configure-common-data-service-virtual-entities"></a>Configurare le entità virtuali di Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources è un'origine dati virtuale in Common Data Service. Fornisce operazioni complete di creazione, lettura, aggiornamento ed eliminazione (CRUD) di Common Data Service e Microsoft Power Platform. I dati delle entità virtuali non sono archiviati in Common Data Service, ma nel database dell'applicazione. 

Per abilitare le operazioni CRUD nelle entità di Human Resources da Common Data Service, devi rendere le entità disponibili come entità virtuali in Common Data Service. Ciò consente di eseguire operazioni CRUD di Common Data Service e Microsoft Power Platform sui dati presenti in Human Resources. Le operazioni supportano anche le convalide complete della logica aziendale di Human Resources per garantire l'integrità dei dati durante la scrittura degli stessi nelle entità.

## <a name="available-virtual-entities-for-human-resources"></a>Entità virtuali disponibili per Human Resources

Tutte le entità Open Data Protocol (OData) di Human Resources sono disponibili come entità virtuali in Common Data Service. Sono inoltre disponibili in Power Platform. Ora puoi creare app ed esperienze con dati direttamente da Human Resources mediante funzionalità CRUD complete, senza copiare o sincronizzare i dati in Common Data Service. Puoi usare i portali Power Apps per creare siti Web rivolti all'esterno che consentono scenari di collaborazione per processi aziendali in Human Resources.

Puoi visualizzare l'elenco delle entità virtuali abilitate nell'ambiente e iniziare a lavorare con le entità in [Power Apps](https://make.powerapps.com), nella soluzione **Dynamics 365 HR Virtual Entities**.

![Dynamics 365 HR Virtual Entities in Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Entità virtuali e entità naturali

Le entità virtuali di Human Resources non sono uguali alle entità Common Data Service naturali create per Human Resources. Le entità naturali per Human Resources vengono generate separatamente e gestite nella soluzione Gestione connessione ibrida comune in Common Data Service. Con le entità naturali, i dati vengono archiviati in Common Data Service e richiedono la sincronizzazione con il database dell'applicazione Human Resources.

> [!NOTE]
> Per un elenco delle entità Common Data Service naturali per Human Resources, vedi [Entità di Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Configurazione

Segui questi passaggi di configurazione per abilitare le entità virtuali nel tuo ambiente.

### <a name="enable-virtual-entities-in-human-resources"></a>Abilitare le entità virtuali in Human Resources

Innanzitutto, è necessario abilitare le entità virtuali nell'area di lavoro **Gestione delle funzionalità**.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare il riquadro **Gestione funzionalità**.

3. Selezionare **Supporto per entità virtuali in HR/CDS** e quindi selezionare **Abilita**.

Per ulteriori informazioni sull'abilitazione e sulla disabilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrare l'app in Microsoft Azure

È necessario registrare l'istanza di Human Resources nel portale di Azure di modo che Microsoft Identity Platform possa fornire servizi di autenticazione e autorizzazione per l'app e gli utenti. Per ulteriori informazioni sulla registrazione di app in Azure, vedi [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Apri il [portale di Microsoft Azure](https://portal.azure.com).

2. Nell'elenco di servizi di Azure, seleziona **Registrazioni app**.

3. Seleziona **Nuova registrazione**.

4. Nel campo **Nome** immetti un nome descrittivo per l'app. Ad esempio, **Entità virtuali di Dynamics 365 Human Resources**.

5. Nel campo **URI di reindirizzamento**, immetti l'URL dello spazio dei nomi dell'istanza di Human Resources.

6. Seleziona **Registro**.

7. Al termine della registrazione, il portale di Azure visualizza il riquadro **Panoramica** della registrazione dell'app che include il relativo **ID applicazione (client)**. Prendi nota adesso dell'**ID applicazione (client)**. Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. Nel riquadro di spostamento a sinistra, seleziona **Certificati e segreti**.

9. Nella sezione **Segreti client** della pagina, seleziona **Nuovo segreto client**.

10. Fornisci una descrizione, seleziona una durata e seleziona **Aggiungi**.

11. Registra il valore del segreto. Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > Assicurati di prendere nota adesso del valore del segreto. Il segreto non viene mai visualizzato dopo la chiusura di questa pagina.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>Installare l'app Dynamics 365 HR Virtual Entity

Installa l'app Dynamics 365 HR Virtual Entity nell'ambiente Power Apps per distribuire il pacchetto di soluzioni di entità virtuali in Common Data Service.

1. Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2. Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.

3. Nella sezione **Risorse** della pagina, seleziona **App Dynamics 365**.

4. Seleziona l'azione **Installa app**.

5. Seleziona **Dynamics 365 HR Virtual Entity** e quindi **Avanti**.

6. Leggi le condizioni d'uso e accettale.

7. Seleziona **Installa**.

L'installazione richiede alcuni minuti. Al termine, continua con i passaggi successivi.

![Installare l'app Dynamics 365 HR Virtual Entity dall'interfaccia di amministrazione di Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>Configurare l'origine dati delle entità virtuali 

Il passaggio successivo consiste nel configurare l'origine dati delle entità virtuali nell'ambiente Power Apps. 

1. Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2. Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.

3. Seleziona l'**URL ambiente** nella sezione **Dettagli** della pagina.

4. In **Hub integrità soluzione**, seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina dell'applicazione.

5. Nella pagina **Ricerca avanzata**, nell'elenco a discesa **Cerca**, seleziona **Configurazioni dell'origine dati virtuale di Finance and Operations**.

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
- L'app Dynamics 365 HR Virtual Entity installata nell'ambiente Power Apps 

1. In Human Resources, apri la pagina **Applicazioni di Azure Active Directory**.

2. Seleziona **Nuovo** per creare un nuovo record di applicazione:

    - Nel campo **ID client**, inserisci l'ID client dell'app che hai registrato nel portale di Microsoft Azure.
    - Nel campo **Nome**, immetti il nome dell'app che hai registrato nel portale di Microsoft Azure.
    - Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.

3. Seleziona **Nuovo** per creare un secondo record di applicazione:

    - **ID client**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nome**: Dynamics 365 HR Virtual Entity
    - Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.

## <a name="generate-virtual-entities"></a>Generare entità virtuali

Al termine della configurazione, puoi selezionare le entità virtuali che desideri generare e abilitare nell'istanza di Common Data Service.

1. In Human Resources, aprire la pagina **Integrazione di Common Data Service (CDS)**.

2. Selezionare la scheda **Entità virtuali**.

> [!NOTE]
> L'interruttore **Abilita entità virtuale** sarà impostato su **Sì** automaticamente quando tutte le impostazioni richieste sono state completate. Se l'interruttore è impostato su **No**, rivedere i passaggi nelle sezioni precedenti di questo documento per assicurarsi che tutte le impostazioni dei prerequisiti siano state completate.

3. Selezionare l'entità o le entità da generare in Common Data Service.

4. Selezionare **Genera/Aggiorna**.

![Integrazione di Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a>Controllare lo stato di generazione dell'entità

Le entità virtuali vengono generate in Common Data Service attraverso un processo in background asincrono. Aggiornamenti sulla visualizzazione del processo nel centro azioni. I dettagli sul processo, inclusi i log degli errori, vengono visualizzati nella pagina **Automazioni di processo**.

1. In Human Resources, aprire la pagina **Automazioni di processo**.

2. Selezionare la scheda **Processi in background**.

3. Selezionare **Processo in background dell'operazione asincrona di polling dell'entità virtuale**.

4. Selezionare **Visualizza risultati più recenti**.

Il riquadro scorrevole mostra i risultati di esecuzione più recenti per il processo. È possibile visualizzare il registro del processo, inclusi eventuali errori restituiti da Common Data Service.

## <a name="see-also"></a>Vedere anche

[Che cos'è Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Panoramica delle entità](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Panoramica delle relazioni tra entità](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Creare e modificare entità virtuali che contengono dati di un'origine dati esterna](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Cosa sono i portali di Power Apps?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Panoramica sulla creazione di app in Power Apps](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]