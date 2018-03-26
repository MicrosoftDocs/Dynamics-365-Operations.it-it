---
title: Eseguire il provisioning di Microsoft Dynamics 365 for Talent
description: Questo argomento descrive il processo di provisioning di un nuovo ambiente per Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: e4459e8be4bfab8e0789744eacd533286b6c05e0
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Eseguire il provisioning di Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Questo argomento descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 for Talent. In questo argomento si presuppone che sia stato acquistato Talent da un Cloud Solution Provider (CSP) o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Talent e non è possibile completare i passaggi in questo argomento, contattare il Supporto tecnico.

Per iniziare, l'amministratore globale deve accede a [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) e creare un nuovo progetto Talent. A meno che il problema di licenza non impedisca il provisioning di Talent, non è necessario rivolgersi all'assistenza del Supporto tecnico o ai rappresentanti di Dynamics Service Engineering (DSE).

## <a name="create-an-lcs-project"></a>Creare un progetto LCS
Per utilizzare LCS per la gestione degli ambienti Talent, è prima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Talent.
2. Selezionare il segno più (**+**) per creare un progetto.
3. Selezionare **Microsoft Dynamics 365 for Talent** come nome e versione di prodotto.
4. Selezionare la metodologia **Dynamics 365 for Talent**.
5. Selezionare **Crea**.

Per informazioni su come iniziare a utilizzare Talent, vedere la metodologa di **Talent** creata nel nuovo progetto. Al termine della creazione del progetto, attenersi alla seguente procedura per eseguire il provisioning dell'ambiente Talent.

## <a name="provision-a-talent-project"></a>Eseguire il provisioning di un progetto Talent
Dopo avere creato un progetto LCS, è possibile eseguire il provisioning di Talent in un ambiente.

1. Nel progetto LCS selezionare il riquadro **Gestione app Talent**.
2. Il provisioning di Talent viene sempre eseguito in un ambiente Microsoft PowerApps, per consentire l'integrazione e l'estensibilità di PowerApps. Se non si dispone già di un ambiente PowerApps, seguire i passaggi nella sezione "Creare un nuovo ambiente PowerApps (se necessario)" di questo argomento prima di continuare.

    > [!NOTE]
    > Per visualizzare gli ambienti esistenti o crearne di nuovi, l'amministratore di tenant che esegue il provisioning di Talent deve essere assegnato alla licenza PowerApps Piano 2. Se l'organizzazione non dispone di una licenza PowerApps Piano 2, se ne può ottenere una dal CSP o dalla [pagina dei prezzi di PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Selezionare **Aggiungi** e quindi selezionare l'ambiente in cui eseguire il provisioning di Talent.
4. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

    Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede normalmente solo alcuni minuti. Se il processo di approvvigionamento ha esito negativo, è necessario contattare il Supporto tecnico.

6. Selezionare **Accesso a Talent** per utilizzare il nuovo ambiente.

> [!NOTE]
> Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Talent nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

> [!NOTE]
> Negli ambienti Talent con provisioning tramite LCS non contengono dati dimostrativi configurati per le Attività delle Risorse umane o specifici per Talent. Nel caso sia necessario un ambiente con dati dimostrativi, si consiglia la registrazione gratuita per l'utilizzo di un [ambiente di prova Talent](https://dynamics.microsoft.com/en-us/talent/overview/) per 60 giorni. Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Core HR. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Tali ambienti non sono destinati all'utilizzo come ambienti di produzione. Si noti che quando l'ambiente di prova scade dopo 60 giorni, tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

## <a name="create-a-new-powerapps-environment-if-required"></a>Creare un nuovo ambiente PowerApps (se necessario)
L'integrazione tra Talent e gli ambienti PowerApps consente di integrare ed estendere l'utilizzo dei dati Talent tramite gli strumenti PowerApps. La comprensione dello scopo degli ambienti PowerApps aiuta a creare app che soddisfano le esigenze di estensione di Talent. Per informazioni sugli ambienti di PowerApps, incluso l'ambito dell'ambiente, l'accesso all'ambiente e la creazione e la scelta di un ambiente, vedere [Annuncio degli ambienti PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/) Mentre ciascun tenant viene automaticamente fornito in un ambiente PowerApps predefinito, questo potrebbe non essere l'ambiente migliore da utilizzare per la distribuzione Talent. Durante questo passaggio è necessario prendere in considerazione l'integrazione dei dati e le strategie di test, pertanto si consiglia di considerare le implicazioni per l'implementazione, poiché alcune decisioni non possono essere modificate facilmente in seguito. 

Sebbene ciascun tenant viene automaticamente fornito in un ambiente PowerApps predefinito, questo potrebbe non essere l'ambiente migliore da utilizzare per la distribuzione Talent. In questo passaggio dovrebbero essere considerate le strategie di integrazione dei dati e di test. Pertanto, si consiglia di valutare le varie implicazioni per la distribuzione, poiché non è facile cambiare l'ambiente PowerApps successivamente.

1. In LCS selezionare **Gestione ambienti**. Viene visualizzata l'[interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/environments), in cui è possibile visualizzare ambienti esistenti e creare nuovi ambienti.
2. Selezionare **Nuovo ambiente**.
3. Immettere un nome univoco per l'ambiente e selezionare la posizione in cui eseguire la distribuzione.

    > [!NOTE]
    > Talent non è disponibile in tutte le aree. Di conseguenza, assicurarsi di verificare la disponibilità prima di selezionare la posizione per l'ambiente.

4. Quando viene chiesto se si desidera creare un database, selezionare **Creare database** per creare il database CDS (Common Data Service) che deve ospitare parte dei dati di Talent. Creando un database, è inoltre possibile integrare applicazioni PowerApps con Talent.
5. Viene chiesto il livello di accesso da utilizzare per il database. È consigliabile selezionare **Limitare l'accesso**, poiché questa opzione impedisce agli utenti di Talent di accedere direttamente ai dati sensibili mediante un'applicazione PowerApps.
6. Il database CDS che viene creato contiene dati dimostrativi che aggiungono dipendenti inattivi e indirizzi fittizi, tra le altre informazioni, all'ambiente di produzione. Per rimuovere i dati dimostrativi, seguire questi passaggi dopo avere creato il database CDS:

    > [!IMPORTANT]
    > Se in precedenza è stato creato un database CDS e vi sono stati immessi dati di produzione della società, questi passaggi rimuovono **tutti** i dati nel database selezionato, anche i dati di produzione della società.

    1. Accedere a [PowerApps](https://preview.web.powerapps.com/home).
    2. Nell'elenco a discesa in alto a destra, selezionare l'ambiente creato nel passaggio 2.
    3. Nel pannello di navigazione sinistro espandere **Common Data Service** e quindi selezionare **Entità**.
    4. Sul lato destro della pagina, fare clic sul pulsante di ellisse (**…**) e quindi selezionare **Cancella tutti i dati**.
    5. Selezionare **Elimina dati** per confermare che si desidera rimuovere i dati. Questa azione rimuove tutti i dati dimostrativi che sono inclusi nel CDS per impostazione predefinita. Rimuove inoltre eventuali altri dati che sono stati immessi nel database selezionato.

È ora possibile utilizzare il nuovo ambiente.

## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente
Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. Tuttavia, è necessario concedere l'accesso in modo esplicito ad altri utenti dell'applicazione. Per concedere l'accesso, è necessario [aggiungere gli utenti](../dev-itpro/sysadmin/tasks/create-new-users.md) e [assegnare i ruoli appropriati correlati](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) nell'ambiente Core HR. Inoltre, è necessario aggiungere tali utenti all'ambiente PowerApps in modo che possano accedere alle applicazioni Attract e Onboard. La procedura viene descritta in questo argomento. Per assistenza per il completamento dei passaggi, vedere il post di blog di [presentazione dell'interfaccia di amministrazione di PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Questa procedura viene completata dall'amministratore globale che ha distribuito l'ambiente di Talent.

1. Aprire l'[interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/environments).
2. Selezionare gli ambienti appropriati.
3. Nella scheda **Sicurezza**, aggiungere gli utenti necessari al ruolo **Creatore dell'ambiente**.

Tenere presente che questo passaggio finale di aggiunta manuale di utenti all'ambiente PowerApps è temporaneo. Alla fine, verrà completato automaticamente quando gli utenti vengono aggiunti in Core HR.

