---
title: Provisioning di Human Resources
description: Questo articolo descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f982f3c3b2703a71e6c8a1a0d1be15fb260a6ef1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092248"
---
# <a name="provision-human-resources"></a>Provisioning di Human Resources

Questo articolo descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 Human Resources. In questo articolo si presuppone che Human Resources sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Human Resources e non è possibile completare i passaggi in questo articolo, contattare il Supporto tecnico.

Per iniziare, l'amministratore globale deve accedere a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e creare un nuovo progetto Human Resources. A meno che un problema relativo alla licenza impedisca il provisioning di Human Resources, non è necessario rivolgersi al Supporto tecnico o ai rappresentanti di Dynamics Service Engineering (DSE).

## <a name="create-an-lcs-project"></a>Creare un progetto LCS

Per utilizzare LCS per la gestione degli ambienti Human Resources, è dapprima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Human Resources.

2. Selezionare il segno più (**+**) per creare un progetto.

3. Selezionare **Microsoft Dynamics 365 Human Resources** come nome e versione di prodotto.

4. Selezionare la metodologia **Dynamics 365 Human Resources**.

5. Selezionare **Crea**.

Per informazioni su come iniziare a utilizzare Human Resources, vedere la metodologa di **Human Resources** creata nel nuovo progetto. Al termine della creazione del progetto, attenersi alla seguente procedura per eseguire il provisioning dell'ambiente Human Resources.

## <a name="provision-a-human-resources-project"></a>Eseguire il provisioning di un progetto Human Resources

Dopo avere creato un progetto LCS, è possibile eseguire il provisioning di Human Resources in un ambiente.

1. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.

2. Indicare se si tratta di un'istanza sandbox o di produzione di Human Resources. Le funzionalità in anteprima anticipata possono essere disponibili nelle istanze sandbox per consentire feedback e test.
   
    > [!NOTE]
    > Il tipo di istanza Talent non può essere modificato una volta impostato. Verificare che sia selezionato il tipo di istanza corretto prima di continuare.</br></br>
    > Il tipo di istanza di Human Resources è distinto dal tipo di istanza dell'ambiente Microsoft Power Apps, impostato nell'interfaccia di amministrazione di Power Apps.
    
3. Selezionare **Includi dati dimostrativi** se si desidera che l'ambiente includa lo stesso set di dati dimostrativi utilizzato nell'esperienza dei test drive di Human Resources. Questa opzione è utile negli ambienti di formazione o dimostrativi a lungo termine e non deve mai essere utilizzata per gli ambienti di produzione.  Tenere presente che è necessario scegliere questa opzione per la distribuzione di apertura. Non è possibile aggiornare una distribuzione esistente in seguito.

4. Il provisioning di Human Resources viene sempre eseguito in un ambiente Microsoft Power Apps per consentire l'integrazione e l'estendibilità di Power Apps. Leggere la sezione relativa alla selezione di un ambiente Power Apps in questo articolo prima di continuare. Se non si dispone già di un ambiente Power Apps, selezionare Gestione ambienti in LCS o accedere all'interfaccia di amministrazione di Power Apps. Attenersi quindi alla procedura indicata di seguito per [Creare un ambiente Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Selezionare l'ambiente in cui eseguire il provisioning di Human Resources.

6. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

   Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede in genere alcuni minuti. Se il processo di approvvigionamento ha esito negativo, è necessario contattare il Supporto tecnico.

7. Selezionare **Accesso a Human Resources** per utilizzare il nuovo ambiente.

    > [!NOTE]
    > Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Human Resources nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

    > Poiché solo due ambienti LCS sono consentiti con la sottoscrizione Human Resources, si potrebbe prendere in considerazione l'utilizzo di un [ambiente di valutazione Human Resources](https://dynamics.microsoft.com/talent/overview/) gratuito di 60 giorni. Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Human Resources. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Tali ambienti non sono destinati all'utilizzo come ambienti di produzione. Si noti che quando un ambiente di prova scade dopo 60 giorni, tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

## <a name="select-a-power-apps-environment"></a>Selezionare un ambiente Power Apps

L'integrazione tra Human Resources e gli ambienti Power Apps consente di integrare ed estendere l'utilizzo dei dati Human Resources tramite gli strumenti Power Apps. La comprensione dello scopo degli ambienti Power Apps non consente soltanto di creare app per estendere Human Resources, ma anche di selezionare l'ambiente corretto per il provisioning di Human Resources. Per informazioni sugli ambienti di Power Apps, incluso l'ambito dell'ambiente, l'accesso all'ambiente e la creazione e la scelta di un ambiente, vedere [Annuncio degli ambienti Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Utilizzare le seguenti linee guida per la determinazione dell'ambiente Power Apps in cui distribuire Human Resources: 

1. In LCS, selezionare **Gestione ambienti** o passare direttamente all'interfaccia di amministrazione di Power Apps, nella quale è possibile visualizzare gli ambienti esistenti e crearne di nuovi.

2. In un singolo ambiente Power Apps viene mappato un singolo ambiente Human Resources.

3. Un ambiente Power Apps contiene Human Resources e le corrispondenti applicazioni Power Apps, Power Automate e Common Data Service. Se l'ambiente Power Apps viene eliminato, vengono eliminate anche le app in esso contenute. Quando viene eseguito il provisioning di un ambiente Human Resources, può essere eseguito il provisioning di un ambiente **Versione di valutazione** o **Produzione**. Selezionare il tipo di ambiente in base a come verrà utilizzato l'ambiente. 

4. È consigliabile considerare l'utilizzo di strategie di integrazione e di test di dati, ad esempio Sandbox, UAT o produzione. Si consiglia di valutare le varie implicazioni per la distribuzione, poiché non è facile cambiare l'ambiente Human Resources mappato a un ambiente Power Apps successivamente.

5. Gli ambienti Power Apps seguenti non possono essere utilizzati per Human Resources e saranno filtrati in base all'elenco di selezione in LCS:
 
    - **Ambienti Power Apps predefiniti** - Sebbene ogni tenant venga dotato automaticamente di un ambiente Power Apps predefinito, non è consigliabile utilizzarli con Human Resources poiché tutti gli utenti del tenant hanno accesso all'ambiente Power Apps e potrebbero danneggiare erroneamente i dati di produzione durante i test e l'esplorazione con le integrazioni di Power Apps o Power Automate.
   
    - **Ambienti di valutazione** - Questi ambienti vengono creati con una data di scadenza e scadono dopo tale data, comportando la rimozione automatica dell'ambiente e di tutte le istanze di Human Resources in esso contenute.
   
    - **Regioni non supportate** - Attualmente Human Resources è supportato solo nelle regioni seguenti: Stati Uniti, Europa, Regno Unito, Australia, Canada e Asia.
  
6. Dopo aver determinato l'ambiente corretto da utilizzare, è possibile continuare il processo di approvvigionamento. 
 
## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente

Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. Tuttavia, è necessario concedere l'accesso in modo esplicito ad altri utenti dell'applicazione. Per concedere l'accesso, è necessario aggiungere utenti e assegnare i ruoli appropriati agli stessi nell'ambiente Human Resources. L'amministratore globale che ha distribuito Human Resources deve inoltre avviare Attract e Onboard per completare l'inizializzazione e abilitare l'accesso per altri utenti del tenant.  Se questa operazione non viene eseguita, gli altri utenti non potranno accedere ad Attract e Onboard e riceveranno errori di violazione dell'accesso. Per ulteriori informazioni, vedere [Creare nuovi utenti](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Assegnare gli utenti ai ruoli di sicurezza](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
