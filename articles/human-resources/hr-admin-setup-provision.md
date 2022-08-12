---
title: Effettuare il provisioning di Human Resources
description: Questo articolo spiega il processo di approvvigionamento di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6fc44b52e2f7662fc6be609562cec903a8755d1b
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178505"
---
# <a name="provision-human-resources"></a>Effettuare il provisioning di Human Resources

_**Si applica a**: Human Resources nell'infrastruttura autonoma_ 

> [!NOTE]
> A partire da giugno 2022, gli ambienti Human Resources possono essere distribuiti solo nell'infrastruttura delle app per la finanza e le operazioni. Per ulteriori informazioni, vedere [Provisioning di Human Resources nell'infrastruttura di finanza e operazioni](hr-admin-setup-provision-fo.md).

Questo articolo spiega il processo di approvvigionamento di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources. 

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare il provisioning di un nuovo ambiente di produzione, i seguenti prerequisiti devono essere presenti:

- Hai acquistato Human Resources tramite un accordo con un Cloud Solution Provider (CSP) o un'architettura aziendale (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Human Resources e non è possibile completare i passaggi in questo articolo, contattare il Supporto tecnico.

- L'amministratore globale ha effettuato l'accesso a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e ha creato un nuovo progetto Human Resources. 

## <a name="provision-a-human-resources-trial-environment"></a>Effettuare il provisioning di un ambiente di valutazione per Human Resources

>[!NOTE]
> A partire da aprile 2022, gli ambienti di prova di Human Resources non saranno disponibili nell'applicazione autonoma. I potenziali clienti interessati a valutare le funzionalità di Human Resources all'interno delle app per la finanza e le operazioni possono farlo utilizzando la versione di valutazione gratuita di 30 giorni insieme ai dati demo. Dynamics 365 Finance includerà le funzionalità di Human Resources introdotte nell'infrastruttura di Finance tramite l'unione dell'applicazione autonoma. Per ulteriori informazioni, vedere[L'unione delle offerte per HR riunisce le funzionalità per i clienti](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Per ulteriori informazioni sulle versioni di valutazione di Dynamics 365 Finance, consultare la [guida dettagliata](../fin-ops-core/fin-ops/get-started/before-you-buy.md). 


Prima di eseguire il provisioning del tuo primo ambiente di produzione o sandbox, potresti voler eseguire il provisioning di un [Ambiente di valutazione di Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962) per convalidare la funzionalità di Human Resources. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Human Resources. 

Gli ambienti di prova permettono di valutare la funzionalità delle risorse umane per le persone che non hanno già accesso a un ambiente Human Resources. Se stai effettuando il provisioning di un ambiente di valutazione e l'utente autenticato ha già accesso a uno o più ambienti Human Resources esistenti, l'utente verrà reindirizzato all'ambiente esistente o all'elenco di ambienti.

Gli ambienti di valutazione non sono destinati all'utilizzo come ambienti di produzione. Sono limitati a un periodo di valutazione di 30 giorni. Quando un periodo di valutazione scade, l'ambiente e tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. L'ambiente non può essere convertito in ambiente sandbox o di produzione. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

Quando si crea un ambiente di prova Human Resources, viene creato anche un ambiente di prova Power Apps sul tenant e collegato all'ambiente Human Resources. L'ambiente Power Apps, denominato "TestDrive", ha lo stesso periodo di prova dell'ambiente Human Resources.

> [!NOTE]
> Il provisioning di un ambiente di prova Human Resources fallirà se l'utente autenticato non dispone dell'autorizzazione per creare ambienti di prova Power Apps. L'utente deve essere incluso nel gruppo di utenti in grado di creare ambienti di prova nell'interfaccia di amministrazione di Power Platform. Per ulteriori informazioni, vedere [Controllare chi può creare e gestire ambienti nell'interfaccia di amministrazione di Power Platform](/power-platform/admin/control-environment-creation).

## <a name="plan-human-resources-environments"></a>Pianificare gli ambienti Human Resources

Prima di creare il primo ambiente Human Resources, è necessario pianificare attentamente le esigenze ambientali per il progetto. Un abbonamento di base a Human Resources include due ambienti: un ambiente di produzione e un ambiente sandbox. A seconda della complessità del progetto, potrebbe essere necessario acquistare ambienti sandbox aggiuntivi per supportare le attività del progetto. 

Considerazioni per altri ambienti:

- **Migrazione dei dati**: le attività di migrazione dei dati consentono di usare l'ambiente sandbox a scopo di test durante il progetto. Avere un ambiente aggiuntivo consente alle attività di migrazione dei dati di continuare mentre le attività di test e la configurazione si verificano simultaneamente in un ambiente diverso.
- **Integrazione**: configurazione e test delle integrazioni, che potrebbe includere integrazioni native, come Ceridian Dayforce, o personalizzate.
- **Formazione**: potrebbe essere necessario un ambiente separato configurato con una serie di dati di formazione per formare i dipendenti sull'uso del nuovo sistema. 
- **Progetto multifase**: supporto della configurazione, della migrazione dei dati, del test o di altre attività in una fase del progetto pianificata dopo la fase operativa iniziale del progetto.

 > [!IMPORTANT]
 > Mentre consideri il tuo ambiente, ti raccomandiamo quanto segue:
 > - Usa il tuo ambiente di produzione per tutto il progetto come ambiente di configurazione GOLD. Questo è importante perché non è possibile copiare un ambiente sandbox in un ambiente di produzione. Pertanto, nella fase di produzione, l'ambiente GOLD è il tuo ambiente di produzione e si completeranno le attività di cutover in questo ambiente.</br></br>
 > - Usa la tua sandbox o un altro ambiente per eseguire un finto cutover prima del go-live. Puoi farlo aggiornando l'ambiente di produzione con la tua configurazione GOLD nel tuo ambiente sandbox.</br></br>
 > - Tenete una lista di controllo dettagliata per il cutover che include ciascuno dei pacchetti di dati richiesti per migrare i dati finali nell'ambiente di produzione durante il go-live cutover.</br></br>
 > - Usa il tuo ambiente sandbox in tutto il progetto come ambiente di TEST. Se hai bisogno di ambienti aggiuntivi, la tua organizzazione può acquistarli a un costo aggiuntivo.</br></br>

## <a name="create-an-lcs-project"></a>Creare un progetto LCS

Per utilizzare LCS per la gestione degli ambienti Human Resources, è dapprima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Human Resources.

   > [!NOTE]
   > Per garantire il corretto provisioning, l'account utilizzato per eseguire il provisioning dell'ambiente Human Resources deve essere assegnato al ruolo **Amministratore di sistema** o **Personalizzatore di sistema** nell'ambiente Power Apps associato all'ambiente Human Resources. Per ulteriori informazioni sull'assegnazione dei ruoli di sicurezza agli utenti in Power Platform, vedere [Configurare la sicurezza degli utenti per le risorse](/power-platform/admin/database-security).

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
    
3. Seleziona l'opzione **Includi dati demo** se vuoi che il tuo ambiente includa lo stesso set di dati demo usato nell'ambiente di prova delle risorse umane. I dati dimostrativi sono utili per ambienti dimostrativi o di formazione a lungo termine e non devono mai essere utilizzati per ambienti di produzione. È necessario scegliere questa opzione al momento della distribuzione iniziale. Non è possibile aggiornare una distribuzione esistente in seguito.

4. Il provisioning di Human Resources viene sempre eseguito in un ambiente Microsoft Power Apps per consentire l'integrazione e l'estendibilità di Power Apps. Leggere la sezione relativa alla selezione di un ambiente Power Apps in questo articolo prima di continuare. Se non si dispone già di un ambiente Power Apps, selezionare Gestione ambienti in LCS o accedere all'interfaccia di amministrazione di Power Apps. Attenersi quindi alla procedura indicata di seguito per [Creare un ambiente Power Apps](/powerapps/administrator/create-environment).

5. Selezionare l'ambiente in cui eseguire il provisioning di Human Resources.

6. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

   Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia **Distribuito**. Questo processo richiede in genere alcuni minuti. Se il processo di approvvigionamento ha esito negativo, contattare il Supporto tecnico.

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

5. I seguenti ambienti Power Apps non possono essere utilizzati per le risorse umane. Sono filtrati dall'elenco di selezione all'interno di LCS:
 
    - **Ambienti Power Apps predefiniti** - Mentre a ciascun tenant viene automaticamente assegnato un ambiente Power Apps predefinito, non è consigliabile utilizzarli con Human Resources. Tutti gli utenti tenant possono accedere all'ambiente Power Apps e potrebbero danneggiare involontariamente i dati di produzione durante i test e le esplorazioni con integrazioni Power Apps o Power Automate.
   
    - **Ambienti prova** - Questi ambienti vengono creati con una data di scadenza. Alla scadenza, l'ambiente e tutte le istanze di Human Resources in esso contenute verranno rimosse automaticamente.
   
    - **Aree geografiche non supportate** - L'ambiente deve essere in un'area geografica supportata. Per ulteriori informazioni, vedere [Aree geografiche supportate](hr-admin-setup-provision.md#supported-geographies).

6. Funzionalità di doppia scrittura per l'integrazione dei dati di Human Resources con l'ambiente Power Apps può essere utilizzato solo se l'opzione **Abilita app Dynamics 365** è selezionata per l'ambiente. Per ulteriori informazioni, vedere [Home page della doppia scrittura](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md).

    > [!NOTE]
    > L'opzione **Abilita app Dynamics 365** deve essere selezionata al momento della creazione dell'ambiente Power Apps. Se l'opzione non è selezionata al momento del provisioning, non sarai in grado di utilizzare la doppia scrittura per integrare i dati tra Dynamics 365 Human Resources e l'ambiente Power Apps o installare le app Dynamics 365 come Dynamics 365 Sales e Field Service nell'ambiente. Questa opzione non è reversibile. 
    > -  Human Resources non supporta la modifica dell'istanza Dataverse collegata una volta che è stato distribuito. </br></br>
    > Per ulteriori informazioni, vedi [Alcune considerazioni importanti quando si crea un nuovo ambiente](/power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment) sul sito della documentazione di Power Platform.  

7. Dopo aver determinato l'ambiente corretto da utilizzare, è possibile continuare il processo di provisioning. 

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

Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. È necessario concedere esplicitamente l'accesso ad altri utenti dell'applicazione. È necessario aggiungere utenti e assegnare loro i ruoli appropriati nell'ambiente Human Resources. Per ulteriori informazioni, vedere [Creare nuovi utenti](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Assegnare gli utenti ai ruoli di sicurezza](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]

