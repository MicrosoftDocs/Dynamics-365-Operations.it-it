---
title: Notifiche dell'ordine di visualizzazione in POS
description: "Questo argomento descrive come abilitare le notifiche degli ordini nel POS e nel framework delle notifiche, che può essere esteso ad altre operazioni."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: a1206aea3f78246951581c1dc6338e39a0942ea2
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="display-notifications-in-point-of-sale"></a>Notifiche di visualizzazione in POS

[!include[banner](includes/banner.md)]

Nell'odierno ambiente di vendita al dettaglio, ai collaboratori del POS vengono assegnate varie attività, come aiutare i clienti, inserire transazioni, eseguire conteggi di inventario e ricevere ordini nel POS. Il client POS consente ai collaboratori di eseguire queste attività e molto altro, tutto in un'unica applicazione. Con diversi compiti da svolgere durante un giorno, potrebbe essere necessario che i collaboratori vengano avvisati quando qualcosa richiede la loro attenzione. Il framework di notifica nel POS risolve questo problema consentendo ai rivenditori di configurare notifiche basate su ruoli. Nell'Aggiornamento applicazione 5 di Dynamics 365 for Retail, le notifiche possono essere configurate solo per le operazioni di POS.

Attualmente, il sistema offre la possibilità di visualizzare le notifiche per l'evasione degli ordini, tuttavia, il framework è progettato per essere estensibile, in modo che in futuro gli sviluppatori possano scrivere un gestore di notifiche per qualsiasi operazione e visualizzare le notifiche nel POS.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Attivare le notifiche per le operazioni di evasione dell'ordine

Per attivare le notifiche per le operazioni di evasione dell'ordine, fare riferimento alle seguenti operazioni:

 - Passare alla pagina **Operations** (**Retail** > **Impostazione canale** > **Impostazioni POS** > **POS** > **Operazioni**).
 - Individuare l'operazione di evasione ordine e selezionare la casella di controllo **Abilita notifiche** per l'operazione. Ciò indica al framework di notifica di ascoltare il gestore per l'operazione di evasione degli ordini. Se il gestore è implementato, le notifiche verranno visualizzate sul POS, altrimenti le notifiche non verranno visualizzate per questa operazione.
- Passare alle autorizzazioni di POS associate ai lavoratori e nella scheda dettaglio **Notifiche** aggiungere l'operazione di evasione ordine con "ordine di visualizzazione" 1. Quando è presente più di una notifica configurata, l'ordine di visualizzazione viene utilizzato per gestire le notifiche dall'alto verso il basso, in cui il valore 1 indica l'elemento nella parte superiore. È possibile aggiungere solo quelle operazioni per le quali è stata selezionata la casella di controllo **Abilita notifiche**. Inoltre, le notifiche vengono visualizzate solo per le operazioni che sono state aggiunte in questo campo e solo ai lavoratori per cui le operazioni sono state aggiunte alle autorizzazioni corrispondenti di POS. 

> [!NOTE]
> Le notifiche possono essere ignorate a livello utente passando al record del lavoratore e selezionando **Autorizzazioni POS** e quindi modificando la sottoscrizione di notifica dell'utente.

 - Passare alla pagina **Profilo funzionalità** (**Retail** > **Impostazione canale** > **Impostazione POS** > **Profili POS** > **Profili funzionalità**). Aggiornare la proprietà **Intervallo di notifica** per impostare l'intervallo in minuti in cui le notifiche devono essere recuperate. Si consiglia di impostare il valore su 10 minuti per evitare comunicazioni superflue alla sede centrale. Impostando l'intervallo di notifica su "0 "le notifiche verranno disattivate.  

 - Passare a **Retail** > **IT vendita al dettaglio** > **Programmazione della distribuzione**. Selezionare la pianificazione "1060, Personale" per sincronizzare le impostazioni di sottoscrizione della notifica e quindi fare clic su **Esegui ora**. Quindi, sincronizzare l'intervallo di autorizzazione selezionando "1070 (configurazione canale)", quindi fare clic su **Esegui ora**. 

## <a name="view-notifications-in-pos"></a>Visualizzare notifiche in POS

Dopo che i passaggi precedenti sono stati completati, i lavoratori, per cui le notifiche vengono impostate, possono visualizzare le notifiche in POS. Per visualizzare le notifiche, fare clic sull'icona di notifica nella barra del titolo del POS. Viene visualizzato un centro di notifica con le notifiche per l'operazione di evasione dell'ordine. Il centro di notifica deve visualizzare i seguenti gruppi nell'operazione di evasione dell'ordine: 

- **Ordini in sospeso** - Questo gruppo visualizza il conteggio degli ordini in sospeso, come gli ordini che devono essere accettati da un operatore del POS, con le autorizzazioni necessarie per l'evasione del punto vendita. Se si fa clic sul numero del gruppo verrà aperta la pagina **Evasione ordine**, filtrata per visualizzare solo gli ordini in sospeso assegnati al punto vendita per l'evasione. Se gli ordini vengono accettati automaticamente per il punto vendita, il conteggio per tale gruppo sarà zero.

- **Ritiro presso punto vendita** - Il gruppo visualizza il conteggio degli ordini con la modalità di consegna **Prelievo** e il prelievo viene programmato dal punto vendita corrente. Se si fa clic sul numero del gruppo verrà aperta la pagina **Evasione ordine**, filtrata per visualizzare gli ordini attivi impostati per il prelievo dal punto vendita.

- **Spedizione da punto vendita** - Il gruppo visualizza il conteggio degli ordini con la modalità di consegna **Spedizione** e la spedizione viene programmato dal punto vendita corrente. Se si fa clic sul numero del gruppo verrà aperta la pagina **Evasione ordine**, filtrata per visualizzare gli ordini attivi impostati per la spedizione dal punto vendita.

Se sono presenti nuovi ordini assegnati al punto vendita per l'evasione, l'icona di notifica verrà modificata per indicare che le nuove notifiche e i gruppi corrispondenti verranno aggiornati. L'utente può anche fare clic sull'icona di aggiornamento, accanto al nome dell'operazione, per aggiornare immediatamente il conteggio dei gruppi. Anche il conteggio verrà aggiornato all'intervallo predefinito. Qualsiasi gruppo con un nuovo elemento, che non è visualizzato dal lavoratore attuale, mostrerà un'icona che indica che questo gruppo ha un nuovo articolo. Facendo clic sui riquadri all'interno delle notifiche si aprirà l'operazione specifica per la quale è configurata tale notifica. Negli scenari sopra indicati, facendo clic sulle notifiche si aprirà la pagina **Evasione ordine** e si passeranno i parametri appropriati: ordini in sospeso, prelievo del punto vendita e spedizione dal punto vendita. 

> [!NOTE]
> Le notifiche degli ordini in sospeso verranno abilitate in un aggiornamento successivo di Dynamics 365 for Retail. 


