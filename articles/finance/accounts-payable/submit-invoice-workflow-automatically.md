---
title: Inviare fatture al sistema del flusso di lavoro e abbinare le righe di entrata prodotti (anteprima)
description: In questo argomento viene descritto il processo di invio di fatture fornitore al sistema del flusso di lavoro e di abbinamento automatico delle righe di entrata prodotti registrate alle righe di fattura fornitore.
author: abruer
manager: AnnBe
ms.date: 09/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cde164ee89b542d769d81d8d483049fb7ca001c4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444626"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines-preview"></a>Inviare fatture al sistema del flusso di lavoro e abbinare le righe di entrata prodotti (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritto il processo di invio di fatture fornitore al sistema del flusso di lavoro e di abbinamento automatico delle righe di entrata prodotti registrate alle righe di fattura fornitore.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Inviare fatture fornitore importate al sistema del flusso di lavoro e abbinare righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, puoi fare in modo che il sistema invii automaticamente una fattura importata al sistema del flusso di lavoro. Puoi configurare il processo di invio di fatture importate al sistema del flusso di lavoro nella scheda **Automazione fattura fornitore** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazione \> Parametri contabilità fornitori**). Il processo di invio al flusso di lavoro verrà eseguito in background, alla frequenza che hai specificato (oraria o giornaliera).

Quando invii automaticamente fatture al sistema del flusso di lavoro, devi iniziare con una fattura importata. Per garantire che la fattura possa essere elaborata dall'inizio alla fine senza intervento manuale, devi includere un'attività di registrazione automatizzata nella configurazione del flusso di lavoro. Le fatture correlate agli ordini fornitore e le fatture che contengono una categoria di approvvigionamento non ordine fornitore e righe non a magazzino possono essere inviate automaticamente al sistema del flusso di lavoro. Le fatture immesse manualmente devono essere inviate manualmente al sistema del flusso di lavoro.

Il valore **Inviata da** nel flusso di lavoro è l'ID utente immesso per l'attività di background **Inviare fatture fornitore a flusso di lavoro** nella pagina **Automazione del processo**. L'utente che dispone di tale ID utente sarà in grado di richiamare la fattura dal sistema del flusso di lavoro come richiesto.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Abbinare entrate prodotti a righe di fattura che hanno criteri di abbinamento a tre elementi di verifica

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, il sistema può abbinare automaticamente le entrate prodotti registrate a righe di fattura. Per questa attività è necessario definire criteri di abbinamento a tre elementi di verifica. Questa funzionalità è disponibile se la funzionalità **Automazione fattura fornitore** è stata abilitata nella pagina **Gestione funzionalità**.

Il processo verrà eseguito fino a quando la quantità delle entrate prodotti abbinate non sarà uguale alla quantità della fattura. Come parte di questo processo, puoi specificare il numero massimo di tentativi del sistema di abbinare le entrate prodotti a una riga di fattura prima che il sistema consideri il processo come non riuscito. Il processo verrà eseguito in background, ogni ora o ogni giorno. Puoi eseguire il processo di abbinamento automatizzato come parte del processo di invio di fatture al sistema del flusso di lavoro. In alternativa, puoi eseguirlo come processo autonomo. Le impostazioni per il processo di abbinamento di entrate prodotto a righe di fattura sono configurate nella scheda **Automazione fattura fornitore** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazione \> Parametri contabilità fornitori**).

Le righe di fattura che hanno criteri di abbinamento a tre elementi di verifica, in cui la quantità di entrata prodotti abbinata è inferiore alla quantità di fattura, verranno incluse nel processo di abbinamento automatico all'entrata prodotti.

Per visualizzare lo stato **Ultimo abbinamento** per le fatture che non fanno parte del processo di invio automatico al flusso di lavoro, apri la fattura dalla pagina **Fatture fornitore**. Quando visualizzi la fattura, le informazioni di convalida dell'abbinamento vengono aggiornate.

Una riga di fattura verrà esclusa dall'elaborazione automatizzata se viene soddisfatta una delle seguenti condizioni:

- Il valore **Stato corrispondenza entrate automatizzate** della riga di fattura è **Non riuscita**.
- La fattura è in uso.
- La fattura è nel sistema del flusso di lavoro.
