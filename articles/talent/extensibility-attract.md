---
title: Estendibilità in Attract
description: In questo argomento viene descritto come possibile estendere l'applicazione Microsoft Dynamics 365 for Talent - Attract utilizzando la piattaforma Microsoft Power.
author: josaw
manager: AnnBe
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c77c64070cb82180441f4b629b6884981b9b81d2
ms.sourcegitcommit: 0bd0215d0735ed47b1b8af93a80bcdbf7ca2cc49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "789653"
---
# <a name="extensibility-in-attract"></a>Estendibilità in Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent si basa sulla piattaforma Common Data Service per le app e può essere esteso in vari modi utilizzando la piattaforma Microsoft Power e le funzionalità di Common Data Service per le app. Di conseguenza, è possibile configurare e personalizzare il sistema mediante Microsoft PowerApps e Microsoft Flow. È inoltre possibile ottenere l'analisi aggiuntive sulle persone utilizzando Microsoft Power BI. Inoltre, le nuove attività personalizzate, ad esempio le attività PowerApps e di contenuto Web (iframe), rendono il processo di assunzione più adattabile che Mai. Con queste attività, è possibile personalizzare il processo di assunzione in base alle esigenze e processi aziendali e assicurarsi che sia il team di assunzione che i candidati fruiscano di un'esperienza personalizzata e priva di problemi.

## <a name="extending-option-sets-in-attract"></a>Estensione di set di opzioni in Attract

Un **set di opzioni** (elenco a discesa) è un tipo di campo che può essere incluso in un'entità e che definisce un set di opzioni. Quando un set di opzioni è visualizzato in un modulo utilizza un controllo di elenco a discesa.  In Attract sono presenti più campi che sono set di opzioni.  Stiamo iniziando a introdurre la funzionalità di estensione di set di opzioni, a partire dai campi Motivo del rifiuto, Tipo di impiego e Tipo di anzianità.   Inoltre, è possibile aggiungere etichette di visualizzazione localizzate per le opzioni aggiunte.  Per ulteriori informazioni, consultare [Personalizzazione delle etichette di set di opzioni](https://docs.microsoft.com/en-us/poweapps/developer/common-data-service/customize-labels-suport-multiple-languages)

> [!NOTE]
> La funzionalità di pubblicazione di annunci di lavoro in LinkedIn richiede l'utilizzo del campo **Tipo di impiego** e **Tipo di anzianità** nella pagina **Dettagli mansione**. I valori predefiniti in questi campi sono supportati da LinkedIn e visualizzati quando l'annuncio viene pubblicato. Di conseguenza, se si pubblicano annunci di lavoro in LinkedIn e si modificano i valori del set di opzioni esistente per tali campi, l'annuncio verrà ancora pubblicato ma LinkedIn non visualizzerà i valori **Tipo di anzianità** e **Tipo di impiego**.  

Sono elencate di seguito le procedure per aggiornare il campo **Motivo del rifiuto** con i valori specifici dell'azienda.  

1. Per estendere il set di opzioni **Motivo del rifiuto**, accedere al [sito Web di amministrazione di PowerApps](Https://admin.powerapps.microsoft.com).
2. È possibile che venga richiesto di accedere al proprio account. Immettere la password e l'ID utente utilizzati per accedere a Dynamics365 e/o Office365 quindi fare clic su **Avanti**.
3. Nella scheda **Ambienti**, selezionare l'ambiente che si desidera gestire e fare doppio clic per visualizzare la scheda **Dettagli**.
4. Nella scheda **Dettagli**, selezionare **Centro amministrativo di Dynamics 365**.
5. Selezionare l'istanza che si intende modificare e selezionare **Apri**.
6. Selezionare **Impostazioni** e **Personalizzazioni**, quindi scegliere **Personalizza il sistema**.
7. Trovare l'entità per la quale si desidera espandere il set di opzioni selezionando **Entità** ed espandendo il gruppo. In questo esempio sarà l'**entità Domanda di lavoro**.
8. Accedere al campo per il quale si desidera estendere il set di opzioni selezionando l'opzione **Campi**. In questo esempio sarà **msdyn_rejectionreason**. Fare doppio clic sul campo.
9. Nel campo **Set di opzioni**, scegliere **Modifica**.
10. Selezionare l'icona **+**.
11. Immettere un'**etichetta**  (deve essere un valore univoco e non un duplicato).
12. Selezionare **Salva**.
13. Selezionare **Pubblica** nella parte superiore della pagina.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Sfruttare Microsoft Power Platform 

Poiché tutti i dati di Attract risiedono in Common Data Service per le app, è possibile utilizzare gli strumenti della piattaforma Microsoft Power per includere specifiche esigenze aziendali in Attract.

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
