---
title: Rilascio batch degli ordini di trasferimento parzialmente prenotati
description: In questo argomento viene descritto come impostare e applicare il rilascio batch degli ordini di trasferimento parzialmente prenotati da un dispositivo mobile.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0fbe12b66da68bcd130fdb188eb0106b686200c3b59edc2af96b79f65022567a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759384"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Rilascio batch degli ordini di trasferimento parzialmente prenotati

[!include [banner](../includes/banner.md)]

La funzionalità per il rilascio batch degli ordini di trasferimento parzialmente prenotati consente di rilasciare parzialmente gli ordini di trasferimento a un magazzino utilizzando un processo batch.
Poiché si ha la possibilità di rilasciare una quantità parziale, non è necessario attendere che l'intera quantità dell'ordine sia disponibile nel magazzino prima di rilasciare un ordine.

Il rilascio di ordini a un magazzino è un processo di gestione magazzino avanzato. Questo processo include attività come prelievo, imballaggio e spedizione che un addetto al magazzino può eseguire mediante un dispositivo mobile.

## <a name="where-it-applies"></a>Dove si applica

Per questa funzionalità, gli ordini di trasferimento vengono rilasciati a un magazzino utilizzando un processo batch. Questa funzionalità è utile quando non si hanno scorte sufficienti in magazzino, ma si desidera comunque trasferire articoli da un magazzino a un altro.

## <a name="how-it-is-set-up"></a>Come si imposta

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Specificare i parametri di evasione per gli ordini di trasferimento e gli ordini cliente

Per poter rilasciare parzialmente un ordine a un magazzino in un batch, è necessario soddisfare i parametri di evasione. Questi parametri di evasione sono determinati dal criterio di evasione.

I criteri di evasione per gli ordini di trasferimento e gli ordini cliente sono definiti a livello aziendale. A seconda dell'impostazione del criterio di evasione, il rilascio degli ordini in un batch verrà accettato o rifiutato. Gli ordini verranno quindi elaborati di conseguenza.

-   Per creare criteri di evasione per ordini di trasferimento e ordini cliente, fare clic su **Gestione magazzino** \> **Impostazione** \> **Rilascia in magazzino** \> **Criteri di evasione** e quindi creare un criterio di evasione immettendo un nome e una descrizione.

-   Per specificare una percentuale di evasione, un tipo di valore e il messaggio visualizzato se il criterio di evasione viene violato, fare clic su **Gestione magazzino** \> **Impostazione** \> **Rilascia in magazzino** \> **Regola di evasione** e quindi impostare i campi **Percentuale evasione**, **Tipo di valore** e **Messaggio di violazione adempimento**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Impostare i criteri di evasione per gli ordini di trasferimento e gli ordini cliente

-   Per impostare i criteri di evasione per gli ordini di trasferimento, fare clic su **Gestione articoli** \> **Impostazione** \> **Parametri di gestione articoli e magazzino** \> **Ordini di trasferimento** \> **Gestione magazzino** e selezionare un criterio di evasione per gli ordini di trasferimento.

-   Per impostare i criteri di evasione per gli ordini cliente, fare clic su **Contabilità clienti** \> **Impostazione** \> **Parametri contabilità clienti** \> **Gestione magazzino** e selezionare un criterio di evasione per gli ordini cliente.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>Consentire il rilascio in un batch e specificare la quantità da rilasciare in un batch

Un processo batch viene utilizzato per rilasciare ordini a un magazzino in un batch. I parametri che determinano gli ordini da eseguire in un processo batch vengono impostati nel processo batch stesso.

Il parametro **Quantità** specifica se l'intera quantità o la quantità prenotata fisicamente deve essere rilasciata nel batch. Il parametro **Consenti rilascio degli ordini parzialmente rilasciati** determina se gli ordini nel batch devono essere accettati o rifiutati nel caso siano stati parzialmente rilasciati in precedenza.

-   Per impostare i parametri **Consenti rilascio degli ordini parzialmente rilasciati** e **Quantità** per gli ordini di trasferimento, fare clic su **Gestione magazzino** \> **Rilascia in magazzino** \> **Rilascio automatico degli ordini di trasferimento**.

-   Per impostare i parametri **Consenti rilascio degli ordini parzialmente rilasciati** e **Quantità** per gli ordini cliente, fare clic su **Gestione magazzino** \> **Rilascia in magazzino** \> **Rilascio automatico degli ordini cliente**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]