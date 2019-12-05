---
title: Effettuare il provisioning di Talent
description: Questo argomento descrive il processo di provisioning di un nuovo ambiente per Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 05/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: ba0d11efe868d57c74f6ae4b069d1cb8351f7213
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773059"
---
# <a name="provision-talent"></a>Eseguire il provisioning di Talent

[!include [banner](includes/banner.md)]

Questo argomento descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 Talent. In questo argomento si presuppone che sia stato acquistato Talent da un Cloud Solution Provider (CSP) o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Talent e non è possibile completare i passaggi in questo argomento, contattare il Supporto tecnico.

Per iniziare, l'amministratore globale deve accedere a [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e creare un nuovo progetto Talent. A meno che il problema di licenza non impedisca il provisioning di Talent, non è necessario rivolgersi all'assistenza del Supporto tecnico o ai rappresentanti di Dynamics Service Engineering (DSE).

## <a name="create-an-lcs-project"></a>Creare un progetto LCS
Per utilizzare LCS per la gestione degli ambienti Talent, è prima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Talent.
2. Selezionare il segno più (**+**) per creare un progetto.
3. Selezionare **Microsoft Dynamics 365 Talent** come nome e versione di prodotto.
4. Selezionare la metodologia **Dynamics 365 Talent**.
5. Selezionare **Crea**.

Per informazioni su come iniziare a utilizzare Talent, vedere la metodologa di **Talent** creata nel nuovo progetto. Al termine della creazione del progetto, attenersi alla seguente procedura per eseguire il provisioning dell'ambiente Talent.

## <a name="provision-a-talent-project"></a>Eseguire il provisioning di un progetto Talent
Dopo avere creato un progetto LCS, è possibile eseguire il provisioning di Talent in un ambiente.

1. Nel progetto LCS selezionare il riquadro **Gestione app Talent**.
2. Indicare se si tratta di un'istanza sandbox o di produzione di Talent. Le funzionalità in anteprima anticipata possono essere disponibili nelle istanze sandbox per consentire feedback e test. 
    > [!NOTE]
    > Il tipo di istanza di Talent è distinto dal tipo di istanza dell'ambiente Microsoft Power Apps, impostato nell'interfaccia di amministrazione di Power Apps.
3. Selezionare **Includi dati dimostrativi** se si desidera che l'ambiente includa lo stesso set di dati dimostrativi utilizzato in passato nell'esperienza dei test drive di Talent. Questa opzione è utile negli ambienti di formazione o dimostrativi a lungo termine e non deve mai essere utilizzata per gli ambienti di produzione.  Tenere presente che è necessario scegliere questa opzione per la distribuzione di apertura. Non è possibile aggiornare una distribuzione esistente in seguito.
4. Il provisioning di Talent viene sempre eseguito in un ambiente Microsoft Power Apps per consentire l'integrazione e l'estensibilità di Power Apps. Leggere la sezione relativa alla selezione di un ambiente Power Apps in questo argomento prima di continuare. Se non si dispone già di un ambiente Power Apps, selezionare Gestione ambienti in LCS o accedere all'interfaccia di amministrazione di Power Apps. Attenersi quindi alla procedura indicata di seguito per [Creare un ambiente Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

    > [!NOTE]
    > Per visualizzare gli ambienti esistenti o crearne di nuovi, l'amministratore di tenant che esegue il provisioning di Talent deve essere assegnato alla licenza Power Apps Piano 2. Se l'organizzazione non dispone di una licenza Power Apps Piano 2, se ne può ottenere una dal CSP o dalla [pagina dei prezzi di Power Apps](https://powerapps.microsoft.com/pricing/).

5. Selezionare l'ambiente in cui eseguire il provisioning di Talent.
6. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

    Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede in genere alcuni minuti. Se il processo di approvvigionamento ha esito negativo, è necessario contattare il Supporto tecnico.

7. Selezionare **Accesso a Talent** per utilizzare il nuovo ambiente.

    > [!NOTE]
    > Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Talent nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

    > Poiché solo due ambienti LCS sono consentiti con la sottoscrizione Talent, si potrebbe prendere in considerazione l'utilizzo di un [ambiente di valutazione Talent](https://dynamics.microsoft.com/talent/overview/) gratuito di 60 giorni. Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Core HR. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Tali ambienti non sono destinati all'utilizzo come ambienti di produzione. Si noti che quando un ambiente di prova scade dopo 60 giorni, tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

## <a name="select-a-power-apps-environment"></a>Selezionare un ambiente Power Apps

L'integrazione tra Talent e gli ambienti Power Apps consente di integrare ed estendere l'utilizzo dei dati Talent tramite gli strumenti Power Apps. La comprensione dello scopo degli ambienti Power Apps non consente soltanto di creare app per estendere Talent, ma anche di selezionare l'ambiente corretto per il provisioning di Talent. Per informazioni sugli ambienti di Power Apps, incluso l'ambito dell'ambiente, l'accesso all'ambiente e la creazione e la scelta di un ambiente, vedere [Annuncio degli ambienti Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Utilizzare le seguenti linee guida per la determinazione dell'ambiente Power Apps in cui distribuire Talent: 

1. In LCS, selezionare **Gestione ambienti** o passare direttamente all'interfaccia di amministrazione di Power Apps, nella quale è possibile visualizzare gli ambienti esistenti e crearne di nuovi.
2. In un singolo ambiente Power Apps viene mappato un singolo ambiente Talent.
3. Un ambiente Power Apps contiene Talent e le corrispondenti applicazioni Power Apps, Power Automate e Common Data Service. Se l'ambiente Power Apps viene eliminato, vengono eliminate anche le app in esso contenute. Quando viene eseguito il provisioning di un ambiente Talent, può essere eseguito il provisioning di un ambiente **Versione di valutazione** o **Produzione**. Selezionare il tipo di ambiente in base a come verrà utilizzato l'ambiente. 
4. È consigliabile considerare l'utilizzo di strategie di integrazione e di test di dati, ad esempio Sandbox, UAT o produzione. Si consiglia di valutare le varie implicazioni per la distribuzione, poiché non è facile cambiare l'ambiente Talent mappato a un ambiente Power Apps successivamente.
5. Gli ambienti Power Apps seguenti non possono essere utilizzati per Talent e saranno filtrati in base all'elenco di selezione in LCS:
 
    - **Ambienti Power Apps predefiniti** - Sebbene ogni tenant venga dotato automaticamente di un ambiente Power Apps predefinito, non è consigliabile utilizzarli con Talent poiché tutti gli utenti del tenant hanno accesso all'ambiente Power Apps e potrebbero danneggiare erroneamente i dati di produzione durante i test e l'esplorazione con le integrazioni di Power Apps o Power Automate.
   
    - **Ambienti di valutazione** - Questi ambienti vengono creati con una data di scadenza e scadono dopo tale data, comportando la rimozione automatica dell'ambiente e di tutte le istanze di Talent in esso contenute.
   
    - **Regioni non supportate** - Attualmente Talent è supportato solo nelle regioni seguenti: Stati Uniti, Europa, Regno Unito, Australia, Canada e Asia.
  
6. Dopo aver determinato l'ambiente corretto da utilizzare, è possibile continuare il processo di approvvigionamento. 
 
## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente
Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. Tuttavia, è necessario concedere l'accesso in modo esplicito ad altri utenti dell'applicazione. Per concedere l'accesso, è necessario aggiungere utenti e assegnare i ruoli appropriati agli stessi nell'ambiente Core HR. L'amministratore globale che ha distribuito Talent deve inoltre avviare Attract e Onboard per completare l'inizializzazione e abilitare l'accesso per altri utenti del tenant.  Se questa operazione non viene eseguita, gli altri utenti non potranno accedere ad Attract e Onboard e riceveranno errori di violazione dell'accesso. Per ulteriori informazioni, vedere [Creare nuovi utenti](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Assegnare gli utenti ai ruoli di sicurezza](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
