---
title: Operazione Richiama ordine nel POS
description: In questo argomento vengono descritte le funzionalità disponibili per le pagine Richiama ordine nel POS.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2f7ad4f53917bb607afe84a2c457518c3f8f7a08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799108"
---
# <a name="recall-order-operation-in-pos"></a>Operazione Richiama ordine nel POS

[!include [banner](includes/banner.md)]

L'operazione **Richiama ordine** nel POS fornisce funzionalità di ricerca e filtro degli ordini aggiornate e informazioni specifiche dell'ordine. Questa funzionalità è disponibile in Commerce versione 10.0.15 e successive.

Per abilitare questa funzionalità, attiva la funzionalità **Operazione Richiama ordine migliorata nel POS** nell'area di lavoro **Gestione funzionalità** in Commerce Headquarters. Dopo aver abilitato la funzionalità, valuta la possibilità di aggiornare i [layout dello schermo](pos-screen-layouts.md) nel POS per utilizzare alcune delle funzionalità modificate.

La configurazione del pulsante dell'operazione **Richiama ordine** consente alle organizzazioni di distribuire l'operazione con una visualizzazione predefinita.

![Configurazione della griglia dei pulsanti](media/recallorderbuttongrid.png)

Le opzioni di visualizzazione sono riportate di seguito.
- **Nessuna** - Questa opzione distribuisce l'operazione senza una visualizzazione specifica. Quando un utente apre l'operazione con questa configurazione, gli viene richiesto di cercare e trovare ordini o di scegliere da un filtro di ordini predefinito.
- **Ordini da evadere** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini che devono essere evasi dal punto vendita corrente dell'utente. Questi ordini sono configurati per il prelievo presso il punto vendita o la spedizione dal punto vendita e le righe di questi ordini non sono ancora state prelevate o imballate.
- **Ordini da prelevare** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini configurati per il prelievo presso il punto vendita corrente dell'utente.
- **Ordini da spedire** - Quando un utente avvia l'operazione, viene eseguita automaticamente una query per cercare e visualizzare un elenco di ordini configurati per la spedizione dal punto vendita corrente dell'utente.

Quando si avvia l'operazione **Richiama ordine** dal POS, se il display è impostato su **Nessuna**, un utente sarà in grado di cercare e recuperare ordini in uno dei seguenti modi.
- Scansione di codici a barre di ordini. In questo modo, vengono cercate le corrispondenze ai campi di numero ordine, riferimento canale e ID ricevuta.
- Selezione dell'icona **Cerca ordini** o **Cerca e filtra** nella barra dell'applicazione per utilizzare il meccanismo di filtro con cui individuare gli ordini che soddisfano i criteri di filtro.
- Scelta di un filtro predefinito nel menu a discesa **Mostra ordini** (ordini da evadere, ordini da prelevare o ordini da spedire).

![RecallOrderMainMenu](media/recallordermain.png)

Dopo aver applicato i criteri di ricerca, l'applicazione visualizzerà un elenco di ordini di vendita corrispondenti. È importante notare che quando si utilizzano le opzioni di ricerca/filtro, gli ordini recuperati non devono essere ordini collegati al punto vendita corrente dell'utente. Questo processo di ricerca recupererà e visualizzerà qualsiasi ordine cliente che corrisponde ai criteri di ricerca, anche se l'ordine è stato creato o impostato per essere evaso da un altro punto vendita/canale o ubicazione di magazzino.

![RecallOrderDetail](media/orderrecalldetail.png)

Un utente può selezionare un ordine nell'elenco per visualizzare ulteriori dettagli. Il pannello delle informazioni sul lato destro della schermata visualizza le specifiche sull'ordine selezionato, inclusi i dettagli su riga dell'ordine, consegna e evasione.

Un utente può selezionare un'operazione nella barra dell'applicazione. A seconda dello stato dell'ordine, è possibile che alcune operazioni non siano disponibili.

- **Reso** - Avvia il processo di creazione di un reso per uno qualsiasi dei prodotti fatturati nell'ordine cliente selezionato.

- **Annulla** - Emette un annullamento completo dell'ordine cliente selezionato. Questa opzione non sarà disponibile per gli ordini avviati tramite un canale del servizio clienti e non può essere utilizzata per annullare parzialmente un ordine.

- **Evadi** - Trasferisce l'utente alla pagina di evasione dell'ordine, che verrà pre-filtrata per l'ordine selezionato. Vengono visualizzate solo le righe dell'ordine aperte per l'evasione dal punto vendita dell'utente per l'ordine selezionato.

- **Modifica** - Consente agli utenti di apportare modifiche all'ordine cliente selezionato. Gli ordini sono modificabili solo in [determinati scenari](customer-orders-overview.md#edit-an-existing-customer-order).

- **Preleva** - Questa opzione sarà disponibile se l'ordine ha una o più righe designate per il prelievo presso il punto vendita corrente dell'utente. Questa operazione avvia il flusso di prelievo, che consente all'utente di scegliere i prodotti da prelevare e crea la transazione di prelievo delle vendite.

## <a name="add-notifications-to-the-recall-order-operation"></a>Aggiungere notifiche all'operazione di richiamo dell'ordine

Se lo si desidera, nella versione 10.0.18 e in quelle successive, è possibile configurare notifiche POS e avvisi con riquadri animati per l'operazione **Richiama ordine** . Per ulteriori informazioni, vedere [ Visualizzare le notifiche degli ordini nel POS](notifications-pos.md).  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
