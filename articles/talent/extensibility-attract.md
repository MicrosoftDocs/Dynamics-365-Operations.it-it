---
title: "Estendibilità in Attract"
description: In questo argomento viene descritto come possibile estendere l'applicazione Microsoft Dynamics 365 for Talent - Attract utilizzando Microsoft Power Platform.
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: it-it
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>Estendibilità in Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent si basa sulla piattaforma Common Data Service per le app e può essere esteso in vari modi utilizzando Microsoft Power Platform e le funzionalità di Common Data Service per le app. Di conseguenza, è possibile configurare e personalizzare il sistema mediante Microsoft PowerApps e Microsoft Flow. È inoltre possibile ottenere l'analisi aggiuntive sulle persone utilizzando Microsoft Power BI. Inoltre, le nuove attività personalizzate, ad esempio le attività PowerApps e di contenuto Web (iframe), rendono il processo di assunzione più adattabile che Mai. Con queste attività, è possibile personalizzare il processo di assunzione in base alle esigenze e processi aziendali e assicurarsi che sia il team di assunzione che i candidati fruiscano di un'esperienza personalizzata e priva di problemi.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Sfruttare Microsoft Power Platform 

Poiché tutti i dati di Attract risiedono in Common Data Service per le app, è possibile utilizzare gli strumenti di Microsoft Power Platform per includere specifiche esigenze aziendali in Attract.

### <a name="powerapps"></a>PowerApps

È possibile utilizzare PowerApps per creare facilmente app di collegamento ai dati Attract e che utilizzano espressioni come lle espressioni in Microsoft Excel per aggiungere la logica. Le app create con PowerApps possono essere eseguite sul Web e su dispositivi Apple iOS e Google Android.

Ad esempio, è possibile facilitare le attività di selezione in occasione delle fiere di orientamento professionale sviluppando un'app leggera che consenta di analizzare i curriculum e inserire i candidati per una posizione in Attract. In alternativa, è possibile creare un'app che soddisfi i requisiti di conformità dell'organizzazione. Per ulteriori informazioni su PowerApps e come utilizzarlo per creare app, vedere [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

È possibile utilizzare Microsoft Flow per creare flussi di lavoro automatici da eseguire sui dati Attract. È possibile connettersi facilmente a centinaia di app e servizi popolari senza dover scrivere un codice. Creando flussi che interagiscono con le entità Mansione, Candidato e Domanda di lavoro di Attract in Common Data Service per le app, è possibile automatizzare varie azioni. Ad esempio, quando accetta un candidato un'offerta, una notifica può essere inviata a un team di inserimento o la notizia può essere annunciata su Twitter. Per ulteriori informazioni sui flussi, vedere la [documentazione di Microsoft Flow](https://docs.microsoft.com/en-us/flow/).

### <a name="power-bi"></a>Power BI

Power BI consente di creare e visualizzare report e dashboard personalizzati che consentono di approfondire l'analisi dei dati di Attract. Per ulteriori informazioni su Power BI e come creare report e dashboard interattivi, vedere la [documentazione di Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Attività personalizzate 

È possibile aggiungere attività personalizzate, ad esempio le attività di app PowerApps e di contenuto Web (iframe), a livello del modello di processo della mansione o mentre si crea una nuova mansione. Queste attività consentono di personalizzare il processo di assunzione e introdurre la logica di business specifica dell'organizzazione in Attract.

#### <a name="powerapps-activity"></a>Attività PowerApps 

L'attività PowerApps consente al creatore di una mansione di un modello di processo della mansione di incorporare un'app di PowerApps nel flusso di assunzione. Dopo aver creato e pubblicato il app, è possibile immettere il relativo ID nelle configurazioni delle attività. Utilizzando un app di PowerApps, è possibile leggere e scrivere dati in Common Data Service per le app. È anche possibile collegare l'app a un flusso. Ad esempio, è possibile avere un app che utilizzano i selezionatori per compilare un modulo mentre svolgono colloqui telefonici. In questo caso, è possibile collegare l'app a un flusso che valuta se un candidato può essere passare alla fase successiva nel processo della domanda di lavoro per una mansione. Questo tipo di attività può essere visualizzato solo dai membri del team di assunzione. Per ulteriori informazioni su come configurare l'attività PowerApps, vedere [Attività in Attract](./activities-attract.md)..

> [!NOTE]
> L'attività PowerApps è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

#### <a name="web-content-iframe-activity"></a>Attività contenuto Web (iframe)

L'attività contenuto Web (iframe) consente di incorporare una soluzione Web personalizzata che è stato sviluppata nel processo di assunzione o nel portale del candidato. È possibile leggere e scrivere i dati direttamente da Common Data Service per le app. È inoltre possibile personalizzare la soluzione in modo che attivi flussi o sfrutti le funzionalità di Microsoft Azure. Per ulteriori informazioni su come configurare l'attività contenuto Web, vedere [Attività in Attract](./activities-attract.md)..

> [!NOTE]
> L'attività contenuto Web è disponibile solo con il componente aggiuntivo per l'assunzione a livello globale.

