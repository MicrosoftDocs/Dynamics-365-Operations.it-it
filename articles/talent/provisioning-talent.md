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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: it-it
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Eseguire il provisioning di Microsoft Dynamics 365 for Talent
Questo argomento descrive il processo di provisioning di un nuovo ambiente per Microsoft Dynamics 365 for Talent. In questo argomento si presuppone che sia stato acquistato Talent da un Cloud Solution Provider (CSP) o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Talent e non è possibile completare i passaggi in questo argomento, contattare il Supporto tecnico.

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

    Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede normalmente solo alcuni minuti. Se il provisioning non riesce, è necessario contattare il Supporto.

6. Selezionare **Accesso a Talent** per utilizzare il nuovo ambiente.

> [!NOTE]
> Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Talent nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

## <a name="create-a-new-powerapps-environment-if-required"></a>Creare un nuovo ambiente PowerApps (se necessario)
1. Selezionare **Gestione ambienti** in LCS. Viene visualizzata l'[interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/environments), dove è possibile visualizzare ambienti esistenti e creare nuovi ambienti.
2. Selezionare il nuovo pulsante (**+**) **Nuovo ambiente**.
3. Immettere un nome univoco per l'ambiente e selezionare la posizione in cui eseguire la distribuzione.

    > [!NOTE]
    > Talent non è disponibile in tutte le aree. Di conseguenza, assicurarsi di verificare la disponibilità prima di selezionare la posizione per l'ambiente.

4. Quando viene chiesto se si desidera creare un database, selezionare **Creare database** per creare il database CDS (Common Data Service) che deve ospitare parte dei dati di Talent. Creando un database, è inoltre possibile integrare applicazioni PowerApps con Talent.
5. Viene chiesto il livello di accesso che si desidera utilizzare per il database. È consigliabile selezionare **Limitare l'accesso**, poiché questa opzione impedisce agli utenti di Talent di accedere direttamente ai dati sensibili mediante un'applicazione PowerApps.
6. Il database CDS che viene creato contiene dati dimostrativi. Questi dati dimostrativi sono utili, poiché è possibile utilizzare la società di dati dimostrativi per i test o per creare file di Registrazione attività o guide attività. Tuttavia, i dati dimostrativi aggiungono dipendenti inattivi e indirizzi fittizi, tra le altre informazioni, all'ambiente di produzione. Per rimuovere i dati dimostrativi, seguire questi passaggi dopo avere creato il database CDS:

    > [!IMPORTANT]
    > Se in precedenza è stato creato un database CDS e vi sono stati immessi dati di produzione della società, tenere presente che questi passaggi rimuovono **tutti** i dati nel database selezionato, anche i dati di produzione della società.

    1. Accedere a [PowerApps](https://preview.web.powerapps.com/home) e passare all'ambiente che è stato creato nel passaggio 2.
    2. Selezionare **Entità**. Sul lato destro della pagina, fare clic sul pulsante di ellisse (**…**) e quindi selezionare **Cancella tutti i dati**.
    3. Selezionare **Elimina dati** per confermare che si desidera rimuovere i dati. Questa azione rimuove tutti i dati dimostrativi che sono inclusi nel CDS per impostazione predefinita. Rimuove inoltre eventuali altri dati che sono stati immessi nel database selezionato.

È ora possibile utilizzare il nuovo ambiente.

