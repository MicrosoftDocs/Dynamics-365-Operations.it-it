---
title: Ordini di quarantena
description: In questo articolo viene descritto come usare gli ordini di quarantena per bloccare il magazzino.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e18735117d1f671e0efc0947248bbe266fa0ca6
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065601"
---
# <a name="quarantine-orders"></a>Ordini di quarantena

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come usare gli ordini di quarantena per bloccare il magazzino.

Gli ordini di quarantena ti consentono di bloccare il magazzino. Ad esempio, è possibile che si desideri mettere in quarantena gli articoli per motivi di controllo qualità. L'inventario messo in quarantena viene trasferito a un magazzino di quarantena.

> [!NOTE]
> Se si utilizzano processi di gestione avanzata del magazzino (nel modulo Gestione magazzino), l'elaborazione degli ordini di quarantena viene utilizzata solo per gli ordini cliente resi.

## <a name="quarantine-on-hand-inventory-items"></a>Quarantena degli articoli di magazzino disponibili

Quando si mettono articoli in quarantena, è possibile creare ordini di quarantena manualmente o impostare il sistema in modo da creare ordini di quarantena automaticamente durante l'elaborazione in entrata.

Per configurare il sistema in modo che generi automaticamente ordini di quarantena, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Scorte \> Gruppi di modelli di articoli**.
1. Selezionare un gruppo di modelli pertinente nel riquadro elenco o creare un nuovo gruppo di modelli.
1. Nella Scheda dettaglio **Criteri di inventario**, selezionare la casella di controllo **Gestione quarantena**.
1. Chiudere la pagina.
1. Specificare un magazzino di quarantena predefinito nel campo **Magazzino di quarantena**.

Quando un articolo registrato come ricevuto in magazzino appartiene a un gruppo di modelli in cui la casella di controllo **Gestione quarantena** è selezionata, il sistema genera un ordine di quarantena per esso. L'ordine di quarantena indica ai lavoratori di spostare l'articolo nel magazzino di quarantena.

Quando si creano manualmente ordini di quarantena nella pagina **Ordini di quarantena**, non è necessario che l'articolo venga impostato per la gestione della quarantena nel gruppo di modelli di articoli associato. Per questo processo, è necessario specificare il magazzino disponibile che deve essere messo in quarantena e il magazzino di quarantena che deve essere utilizzato. È possibile utilizzare gli stati dell'ordine di quarantena per pianificare il processo.

## <a name="quarantine-order-statuses"></a>Stati dell'ordine di quarantena

Agli ordini di quarantena possono essere assegnati i seguenti stati:

- Creata
- Avviato
- Dichiarato finito
- Operazione terminata

### <a name="created"></a>Creata

Quando un ordine di quarantena viene creato manualmente ma l'articolo non è ancora nel magazzino di quarantena, l'ordine di quarantena presenta lo stato **Creato**. Vengono generate due transazioni di magazzino. Una transazione è una transazione di uscita con lo stato **In ordinazione**, **Fisico prenotato** o **Prelevata**. L'altra transazione è una transazione di entrata con lo stato **Ordinato** o **Registrato** presso il magazzino in quarantena. È possibile prenotare, prelevare e registrare aggiornamenti al magazzino utilizzando i soliti processi.

### <a name="started"></a>Avviato

Quando un ordine di quarantena presenta lo stato **Avviato**, gli articoli di magazzino vengono trasferiti dal normale magazzino al magazzino di quarantena e vengono generate due transazioni di magazzino. Una transazione ha lo stato di **Detratto** e l'altra ha lo stato di **Ricevuto**. Contemporaneamente vengono generate due operazioni di magazzino per la gestione del trasferimento del reso. Queste transazioni non sono datate. Una transazione ha lo stato di **Fisico prenotato** e l'altra ha lo stato di **Ordinato**.

### <a name="reported-as-finished"></a>Dichiarato finito

Per segnalare un ordine di quarantena avviato come finito, apri l'ordine e seleziona **Dichiarato finito** nel riquadro azioni. L'articolo viene rilasciato dalla quarantena, ma non viene ancora ritrasferito al magazzino normale. Il movimento al magazzino normale può essere elaborato tramite un giornale di registrazione arrivi articoli che può essere inizializzato durante il processo di dichiarazione finito.

### <a name="ended"></a>Terminato

Quando un ordine di quarantena viene terminato, l'articolo viene spostato dal magazzino di quarantena al magazzino normale. Lo stato della transazione dell'articolo viene impostato su *Venduto* nel magazzino di quarantena e su *Acquistato* nel magazzino normale.

## <a name="quarantine-order-scrap"></a>Scarti ordine di quarantena

Nell'ambito dell'elaborazione dell'ordine di quarantena è possibile scartare le scorte. In questa fase, lo stato degli articoli di magazzino è impostati su *Venduto* tramite una transazione di uscita dal magazzino di quarantena.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Blocco scorte](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
