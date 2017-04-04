---
title: Impostare le opzioni di elaborazione dell&quot;ordine
description: In questo argomento vengono fornite informazioni sull&quot;elaborazione degli ordini per le call center mediante Microsoft Dynamics 365 per le operazioni al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eb62073fdfa50576d2c613594f3d85cbc0b322f6
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-order-processing-options"></a>Impostare le opzioni di elaborazione dell'ordine

In questo argomento vengono fornite informazioni sull'elaborazione degli ordini per le call center mediante Microsoft Dynamics 365 per le operazioni al dettaglio. 

La vendita al dettaglio e il commercio in Dynamics 365 per le operazioni supporta i canali al dettaglio in cui sono, ad esempio i punti vendita in linea, i punti vendita del mattone-e- mortaio e le call center. Nei servizi clienti, i lavoratori prendono gli ordini dei clienti per telefono e creano gli ordini cliente. In questo argomento viene descritto come creare un servizio clienti e configurare le opzioni del servizio clienti. Ogni servizio clienti può avere propri utenti, metodi di pagamento, gruppi di prezzi, dimensioni finanziarie e modalità di consegna. È possibile configurare queste opzioni quando si crea il servizio clienti. **Importante:** prima di poter utilizzare i flussi di lavoro per call center quando l'utente corrente di Dynamics AX crea ordini cliente, è necessario assegnare l'utente al call center come utente di call center. È possibile utilizzare la pagina **Call center** per attivare o disattivare i gruppi di funzionalità che sono esclusive dei call center. È possibile abilitare i seguenti gruppi di funzionalità:

-   **Completamento ordine** - Questo gruppo include funzionalità correlate ai pagamenti e al completamento degli ordini nella pagina **Ordine cliente**.
-   **Vendita diretta** - Questo gruppo include funzionalità che sono correlate ai codici di origine, agli script e alla richieste di catalogo.

Quando si abilitano nelle impostazioni del call center, queste funzionalità diventano disponibili nella pagina **Ordine cliente** per gli utenti che sono associati al call center. La maggior parte delle funzionalità richiedono una configurazione aggiuntiva prima di poter essere utilizzate. Le immagini e gli script vengono attivati durante l'impostazione della vendita diretta per lo specifico call center. Se questa funzionalità è abilitata, gli script e le immagini dei prodotti vengono visualizzati nel riquadro Dettaglio informazioni della pagina **Ordine cliente**. Viene mostrata l'immagine predefinita del prodotto. È possibile configurare degli script per un articolo, un catalogo, un cliente o un articolo nel contesto di un catalogo. Gli ordini del call center possono mostrare dettagli aggiuntivi sulla determinazione del prezzo per una riga d'ordine specifica. Ad esempio, gli ordini mostrano quali sconti sono stati applicati. I a questa funzionalità ** contabilità clienti ** &gt; ** all'impostazione ** &gt; ** parametri di contabilità clienti ** &gt; ** prezzi ** &gt; ** dettagli di prezzi **. È possibile accedere alla pagina **Dettagli prezzo** dall'elenco a discesa **Riga ordine cliente**. È possibile utilizzare la tracciabilità degli eventi ordine per motivi di controllo, per esaminare le azioni intraprese su un ordine durante il ciclo di vita dell'ordine o per tenere traccia delle azioni di un utente specifico. Ad esempio, è possibile registrare l'azione ogni volta che un utente crea un ordine cliente, sospende un ordine, sostituisce una spesa o aggiorna una riga ordine. È possibile impostare degli eventi ordine per tenere traccia delle azioni di utenti specifici, gruppi di utenti o tutti gli utenti durante un periodo specifico. È possibile visualizzare le azioni effettuate su un documento aprendo la pagina **Eventi ordine** dal riquadro azioni sulla pagina del documento. È possibile configurare gli eventi dell'ordine ** Vendite e marketing ** &gt; ** all'impostazione ** &gt; ** eventi ** &gt; ** eventi dell'ordine **. Quando l'ordine di un cliente non può essere spedito in tempo, una società può automaticamente inviare messaggi e-mail di notifica al cliente per spiegare lo stato dell'ordine e dare al cliente l'opportunità di annullarlo. Se il ritardo si prolunga oltre una soglia specificata, l'ordine può essere annullato automaticamente. Fino a tre messaggi di posta elettronica possono essere inviati a intervalli specificati:

1.  **Primo avviso di annullamento**: il cliente può annullare l'ordine.
2.  **Secondo avviso di annullamento**: il cliente può annullare l'ordine.
3.  **Avviso finale di annullamento**: l'ordine viene annullato dal sistema e il cliente viene informato dell'avvenuto annullamento.

È possibile esentare i singoli clienti e prodotti dal processo automatico di annullamento e di notifica. Un avviso sul margine viene attivato quando si aggiunge un articolo a un ordine. L'avviso contiene informazioni importanti sull'articolo, tra cui il margine di prezzo e la redditività dell'articolo. È possibile utilizzare queste informazioni per decidere se la sostituzione dei prezzi è appropriata quando si aggiunge un articolo all'ordine cliente. Ad esempio, è possibile impostare le soglie dei margini commerciali per specificare che una soglia del 40% o più sopra il costo è accettabile per un articolo, ma che una soglia dal 20 al 39% sopra il costo è problematica. In questo caso, qualsiasi articolo con una soglia tra il 20 e il 39% genera un avviso. Qualsiasi articolo con una soglia inferiore al 20% sopra il costo non può essere venduto e il prezzo dell'articolo non può essere rettificato. È possibile configurare gli avvisi di margine ** contabilità clienti ** &gt; ** all'impostazione ** &gt; ** parametri di contabilità clienti ** &gt; ** avvisi di margine **. Quando si imposta l'assegnazione dell'IVA in base alle regole predefinite, è possibile stabilire una priorità di corrispondenza per gli elementi dell'indirizzo. Ad esempio, è possibile specificare che la corrispondenza di una fascia IVA per codice postale ha una priorità più alta rispetto alla corrispondenza di una fascia IVA per stato. Quando si inseriscono nuovi record di indirizzo del cliente, la fascia IVA viene assegnata automaticamente in base a come l'indirizzo del cliente corrisponde alle regole predefinite e alla corrispondenza di priorità definite. È possibile configurare la funzionalità nella pagina **Parametri di contabilità generale**.


