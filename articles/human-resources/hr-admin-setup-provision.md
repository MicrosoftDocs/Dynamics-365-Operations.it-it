---
title: Effettua il provisioning di Human Resources
description: Questo argomento descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58ffce072c8b73f4907b18c6c60b022f9a3b55f26cb785238367254021afdc28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756150"
---
# <a name="provision-human-resources"></a>Effettua il provisioning di Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources. In questo argomento si presuppone che Human Resources sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Human Resources e non è possibile completare i passaggi in questo articolo, contattare il Supporto tecnico.

Per iniziare, l'amministratore globale deve accedere a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e creare un nuovo progetto Human Resources. A meno che un problema relativo alla licenza impedisca il provisioning di Human Resources, non è necessario rivolgersi al Supporto tecnico o ai rappresentanti di Dynamics Service Engineering (DSE).

## <a name="provision-a-human-resources-trial-environment"></a>Effettuare il provisioning di un ambiente di valutazione per Human Resources

Prima di eseguire il provisioning del tuo primo ambiente di produzione o sandbox, potresti voler eseguire il provisioning di un [Ambiente di valutazione di Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962) per convalidare la funzionalità di Human Resources. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Human Resources. 

Gli ambienti di valutazione non sono destinati all'utilizzo come ambienti di produzione. Sono limitati a un periodo di valutazione di 60 giorni. Quando un periodo di valutazione scade, l'ambiente e tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. L'ambiente non può essere convertito in sandbox o ambiente di produzione. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

## <a name="plan-human-resources-environments"></a>Pianificare gli ambienti Human Resources

Prima di creare il primo ambiente Human Resources, è necessario pianificare attentamente le esigenze ambientali per il progetto. Un abbonamento di base a Human Resources include due ambienti: un ambiente di produzione e un ambiente sandbox. A seconda della complessità del progetto, potrebbe essere necessario acquistare ambienti sandbox aggiuntivi per supportare le attività del progetto. 

Le considerazioni per ambienti aggiuntivi includono, ma non sono limitate a, quanto segue:

- **Migrazione dei dati**: potresti dover considerare un ambiente aggiuntivo per le attività di migrazione dei dati per consentire l'utilizzo del tuo ambiente sandbox a scopo di test durante il progetto. Avere un ambiente aggiuntivo consente alle attività di migrazione dei dati di continuare mentre le attività di test e la configurazione si verificano simultaneamente in un ambiente diverso.
- **Integrazione**: potresti dover considerare un ambiente aggiuntivo per configurare e testare le integrazioni. Ciò potrebbe includere integrazioni native come le integrazioni LinkedIn Talent Hub di Ceridian Dayforce o integrazioni personalizzate come quelle per le buste paga, i sistemi di tracciamento dei candidati o i sistemi di benefit e i fornitori.
- **Formazione**: potrebbe essere necessario un ambiente separato configurato con una serie di dati di formazione per formare i dipendenti sull'uso del nuovo sistema. 
- **Progetto multifase**: potrebbe essere necessario un ambiente aggiuntivo per supportare la configurazione, la migrazione dei dati, il test o altre attività in una fase del progetto pianificata dopo la fase operativa iniziale del progetto.

 > [!IMPORTANT]
 > Si consiglia di utilizzare l'ambiente di produzione in tutto il progetto come ambiente di configurazione GOLD. Questo è importante perché non è possibile copiare un ambiente sandbox in un ambiente di produzione. Pertanto, nella fase di produzione, l'ambiente GOLD è il tuo ambiente di produzione e si completeranno le attività di cutover in questo ambiente.</br></br>
 > Si consiglia di utilizzare la sandbox o un altro ambiente per eseguire un cutover simulato prima della fase operativa. Puoi farlo aggiornando l'ambiente di produzione con la tua configurazione GOLD nel tuo ambiente sandbox.</br></br>
 > Si consiglia di mantenere un elenco di controllo dettagliato del cutover che includa ciascuno dei pacchetti di dati necessari per migrare i dati finali nell'ambiente di produzione durante la fase operativa del cutover.</br></br>
 > Si consiglia inoltre di utilizzare l'ambiente sandbox in tutto il progetto come ambiente di TEST. Se hai bisogno di ambienti aggiuntivi, la tua organizzazione può acquistarli a un costo aggiuntivo.</br></br>

## <a name="create-an-lcs-project"></a>Creare un progetto LCS

Per utilizzare LCS per la gestione degli ambienti Human Resources, è dapprima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Human Resources.

   > [!NOTE]
   > Per garantire il corretto provisioning, l'account utilizzato per eseguire il provisioning dell'ambiente Human Resources deve essere assegnato al ruolo **Amministratore di sistema** o **Personalizzatore di sistema** nell'ambiente Power Apps associato all'ambiente Human Resources. Vedere [Configurare la sicurezza degli utenti per le risorse](/power-platform/admin/database-security) per ulteriori informazioni sull'assegnazione dei ruoli di sicurezza agli utenti in Power Platform.

2. Selezionare il segno più (**+**) per creare un progetto.

3. Selezionare **Microsoft Dynamics 365 Human Resources** come nome e versione di prodotto.

4. Selezionare la metodologia **Dynamics 365 Human Resources**.

5. Selezionare **Crea**.

Per informazioni su come iniziare a utilizzare Human Resources, vedere la metodologa di **Human Resources** creata nel nuovo progetto. Al termine della creazione del progetto, attenersi alla seguente procedura per eseguire il provisioning dell'ambiente Human Resources.

## <a name="provision-a-human-resources-project"></a>Eseguire il provisioning di un progetto Human Resources

Dopo avere creato un progetto LCS, è possibile eseguire il provisioning di Human Resources in un ambiente.

1. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.

2. Indicare se si tratta di un'ambiente Sandbox o un istanza di produzione Human Resources. Le funzionalità in anteprima anticipata possono essere disponibili nelle istanze sandbox per consentire feedback e test.
   
    > [!NOTE]
    > Il tipo di istanza Human Resources non può essere modificato una volta impostato. Verificare che sia selezionato il tipo di istanza corretto prima di continuare.</br></br>
    > Il tipo di istanza di Human Resources è distinto dal tipo di istanza dell'ambiente Microsoft Power Apps, impostato nell'interfaccia di amministrazione di Power Apps.
    
3. Selezionare **Includi dati dimostrativi** se si desidera che l'ambiente includa lo stesso set di dati dimostrativi utilizzato nell'esperienza dei test drive di Human Resources. I dati dimostrativi sono utili per ambienti dimostrativi o di formazione a lungo termine e non devono mai essere utilizzati per ambienti di produzione. È necessario scegliere questa opzione al momento della distribuzione iniziale. Non è possibile aggiornare una distribuzione esistente in seguito.

4. Il provisioning di Human Resources viene sempre eseguito in un ambiente Microsoft Power Apps per consentire l'integrazione e l'estendibilità di Power Apps. Leggere la sezione relativa alla selezione di un ambiente Power Apps in questo articolo prima di continuare. Se non si dispone già di un ambiente Power Apps, selezionare Gestione ambienti in LCS o accedere all'interfaccia di amministrazione di Power Apps. Attenersi quindi alla procedura indicata di seguito per [Creare un ambiente Power Apps](/powerapps/administrator/create-environment).

5. Selezionare l'ambiente in cui eseguire il provisioning di Human Resources.

6. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

   Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede in genere alcuni minuti. Se il processo di approvvigionamento ha esito negativo, è necessario contattare il Supporto tecnico.

7. Selezionare **Accesso a Human Resources** per utilizzare il nuovo ambiente.

    > [!NOTE]
    > Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Human Resources nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

## <a name="select-a-power-apps-environment"></a>Selezionare un ambiente Power Apps

È possibile integrare ed estendere l'utilizzo dei dati di Human Resources utilizzando gli strumenti di Power Apps. Per informazioni sugli ambienti di Power Apps, incluso l'ambito dell'ambiente, l'accesso all'ambiente e la creazione e la scelta di un ambiente, vedere [Annuncio degli ambienti Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Utilizzare le seguenti linee guida per la determinazione dell'ambiente Power Apps in cui distribuire Human Resources: 

1. In LCS selezionare **Gestione ambienti**. E' possibile andare direttamente all'interfaccia di amministrazione di Power Apps, dove poter visualizzare gli ambienti esistenti e crearne di nuovi.

2. In un singolo ambiente Power Apps viene mappato un singolo ambiente Human Resources.

3. Un ambiente Power Apps contiene Human Resources e le corrispondenti applicazioni Power Apps, Power Automate e Dataverse. Se l'ambiente Power Apps viene eliminato, vengono eliminate anche le app in esso contenute. Quando viene eseguito il provisioning di un ambiente Human Resources, può essere eseguito il provisioning di un ambiente **Versione di valutazione** o **Produzione**. Selezionare il tipo di ambiente in base a come verrà utilizzato l'ambiente. 

4. È consigliabile considerare l'utilizzo di strategie di integrazione e di test di dati, ad esempio Sandbox, UAT o produzione. Si considerino attentamente le implicazioni per la distribuzione, poiché successivamente non è semplice cambiare l'ambiente Human Resources mappato a un ambiente Power Apps.

5. Non è possibile utilizzare i seguenti ambienti Power Apps per Human Resources. Sono filtrati dall'elenco di selezione all'interno di LCS:
 
    - **Ambienti Power Apps predefiniti** - Mentre a ciascun tenant viene automaticamente assegnato un ambiente Power Apps predefinito, non è consigliabile utilizzarli con Human Resources. Tutti gli utenti tenant possono accedere all'ambiente Power Apps e potrebbero danneggiare involontariamente i dati di produzione durante i test e le esplorazioni con integrazioni Power Apps o Power Automate.
   
    - **Ambienti prova** - Questi ambienti vengono creati con una data di scadenza. Alla scadenza, l'ambiente e tutte le istanze di Human Resources in esso contenute verranno rimosse automaticamente.
   
    - **Aree geografiche non supportate** - L'ambiente deve essere in un'area geografica supportata. Per ulteriori informazioni, vedere [Aree geografiche supportate](hr-admin-setup-provision.md#supported-geographies).

6. Dopo aver determinato l'ambiente corretto da utilizzare, è possibile continuare il processo di provisioning. 

### <a name="supported-geographies"></a>Aree geografiche supportate

Human Resources attualmente supporta le seguenti aree geografiche:

- Stati Uniti
- Europa
- Regno Unito
- Australia
- Canada
- Asia 

Quando crei un ambiente Human Resources, selezioni un ambiente Power Apps da associare all'ambiente Human Resources. Viene quindi eseguito il provisioning dell'ambiente Human Resources nella stessa area geografica di Azure dell'ambiente Power Apps selezionato. È possibile selezionare dove risiedono fisicamente l'ambiente e il database Human Resources selezionando l'area geografica durante la creazione dell'ambiente Power Apps che sarà associato all'ambiente Human Resources.

Puoi selezionare l'*area geografica* di Azure in cui viene eseguito il provisioning dell'ambiente, ma non è possibile selezionare la specifica *area* di Azure. L'automazione determina la area specifica all'interno dell'area geografica in cui l'ambiente viene creato per ottimizzare il bilanciamento del carico e le prestazioni. È possibile trovare informazioni sulle aree geografiche e sulle aree di Azure nella documentazione sulle [aree geografiche di Azure](https://azure.microsoft.com/global-infrastructure/geographies).

I dati per l'ambiente Human Resources saranno sempre contenuti nell'area geografica di Azure in cui vengono creati. Tuttavia, non saranno sempre contenuti nella stessa area di Azure. Ai fini del ripristino di emergenza, i dati verranno replicati sia nell'area di Azure primaria che in un'area di failover secondaria all'interno dell'area geografica.

 > [!NOTE]
 > La migrazione di un ambiente Human Resources da un'area di Azure all'altra non è supportata.

## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente

Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. È necessario concedere esplicitamente l'accesso ad altri utenti dell'applicazione. È necessario aggiungere utenti e assegnare loro i ruoli appropriati nell'ambiente Human Resources. L'amministratore globale che ha distribuito Human Resources deve inoltre avviare Attract e Onboard per completare l'inizializzazione e abilitare l'accesso per altri utenti del tenant. Se questa operazione non viene eseguita, gli altri utenti non potranno accedere ad Attract e Onboard e riceveranno errori di violazione dell'accesso. Per ulteriori informazioni, vedere [Creare nuovi utenti](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Assegnare gli utenti ai ruoli di sicurezza](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
