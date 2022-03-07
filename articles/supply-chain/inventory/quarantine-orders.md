---
title: Ordini di quarantena
description: In questo argomento viene descritto il modo in cui gli ordini di quarantena vengono utilizzati per bloccare il magazzino.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08bb75228c79a0575e8476f41c935d0a03e00f35
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209613"
---
# <a name="quarantine-orders"></a>Ordini di quarantena

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il modo in cui gli ordini di quarantena vengono utilizzati per bloccare il magazzino.

Gli ordini di quarantena possono essere utilizzati per bloccare il magazzino. Ad esempio, è possibile che si desideri mettere in quarantena gli articoli per motivi di controllo qualità. L'inventario messo in quarantena viene trasferito a un magazzino di quarantena. **Nota:** se si utilizzano processi di gestione avanzata del magazzino (in Gestione magazzino), l'elaborazione degli ordini di quarantena viene utilizzata solo per gli ordini cliente resi.

## <a name="quarantine-on-hand-inventory-items"></a>Quarantena degli articoli di magazzino disponibili
Quando si mettono articoli in quarantena, è possibile creare ordini di quarantena manualmente o impostare il sistema in modo da creare ordini di quarantena automaticamente durante l'elaborazione in entrata. Per creare automaticamente ordini di quarantena, selezionare l'opzione **Gestione quarantena** nella scheda **Criteri di inventario** nella pagina **Gruppi di modelli di articoli**. È anche necessario specificare un magazzino di quarantena predefinito nel campo **Magazzino di quarantena** per i magazzini riceventi. Quando gli articoli di magazzino fisicamente disponibili vengono registrati in un ordine fornitore o di produzione, gli articoli in quarantena vengono spostati automaticamente in un magazzino di quarantena in Supply Chain Management. Il movimento si verifica perché lo stato dell'ordine di quarantena viene modificato su **Iniziato**. Quando si creano manualmente ordini di quarantena, non è necessario che l'articolo venga impostato per la gestione della quarantena nel gruppo di modelli dell'articolo associato. Per questo processo, è necessario specificare il magazzino disponibile che deve essere messo in quarantena e il magazzino di quarantena che deve essere utilizzato. È possibile utilizzare gli stati dell'ordine di quarantena per pianificare il processo.

## <a name="quarantine-order-statuses"></a>Stati dell'ordine di quarantena
Agli ordini di quarantena possono essere assegnati i seguenti stati:

-   Creata
-   Avviato
-   Dichiarato finito
-   Operazione terminata

### <a name="created"></a>Creata

Quando un ordine di quarantena viene creato manualmente ma l'articolo non è ancora nel magazzino di quarantena, l'ordine di quarantena presenta lo stato **Creato**. Vengono generate due transazioni di magazzino. Una transazione è una transazione di uscita con lo stato **In ordinazione**, **Fisico prenotato** o **Prelevata**. L'altra transazione è una transazione di entrata con lo stato **Ordinato** o **Registrato** presso il magazzino in quarantena. È possibile prenotare, prelevare e registrare aggiornamenti al magazzino utilizzando i soliti processi.

### <a name="started"></a>Avviato

Quando un ordine di quarantena presenta lo stato **Avviato**, gli articoli di magazzino vengono trasferiti dal normale magazzino al magazzino di quarantena e vengono generate due transazioni di magazzino. Una transazione ha lo stato di **Detratto** e l'altra ha lo stato di **Ricevuto**. Contemporaneamente vengono generate due operazioni di magazzino per la gestione del trasferimento del reso. Queste transazioni non sono datate. Una transazione ha lo stato di **Fisico prenotato** e l'altra ha lo stato di **Ordinato**.

### <a name="reported-as-finished"></a>Dichiarato finito

Se si fa clic su **Dichiarazione di finito**, è possibile dichiarare che un ordine di quarantena avviato è finito. L'articolo viene rilasciato dalla quarantena, ma non viene ancora ritrasferito al magazzino normale. Il movimento al magazzino normale può essere elaborato tramite un giornale di registrazione arrivi articoli che può essere inizializzato durante il processo di dichiarazione finito.

### <a name="ended"></a>Operazione terminata

Quando un ordine di quarantena viene terminato, l'articolo viene spostato dal magazzino di quarantena al magazzino normale. Lo stato della transazione dell'articolo viene impostato su **Venduto** nel magazzino di quarantena e su **Acquistato** nel magazzino normale.

## <a name="quarantine-order-scrap"></a>Scarti ordine di quarantena
Nell'ambito dell'elaborazione dell'ordine di quarantena è possibile scartare le scorte. In questa fase, lo stato degli articoli di magazzino sono impostati su **Venduto** tramite una transazione di uscita dal magazzino di quarantena.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Blocco scorte](inventory-blocking.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]