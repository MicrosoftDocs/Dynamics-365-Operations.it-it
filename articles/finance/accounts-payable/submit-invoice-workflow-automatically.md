---
title: Inviare le fatture al sistema del flusso di lavoro e abbinare le righe di entrata prodotti
description: In questo argomento viene descritto il processo di invio di fatture fornitore al sistema del flusso di lavoro e di abbinamento automatico delle righe di entrata prodotti registrate alle righe di fattura fornitore.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0962ea2bfa28deb3e86620c364feffd209cfc38e
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109945"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Inviare le fatture al sistema del flusso di lavoro e abbinare le righe di entrata prodotti

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il processo di invio di fatture fornitore al sistema del flusso di lavoro e di abbinamento automatico delle righe di entrata prodotti registrate alle righe di fattura fornitore.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Inviare fatture fornitore importate al sistema del flusso di lavoro e abbinare righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, una fattura importata può essere inviata automaticamente al sistema del flusso di lavoro. Puoi configurare il processo di invio di fatture importate al sistema del flusso di lavoro nella scheda **Automazione fattura fornitore** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazione \> Parametri contabilità fornitori**). Il processo di invio al flusso di lavoro verrà eseguito in background, alla frequenza che hai specificato (oraria o giornaliera).

Quando invii automaticamente fatture al sistema del flusso di lavoro, devi iniziare con una fattura importata. Per garantire che la fattura possa essere elaborata dall'inizio alla fine senza intervento manuale, devi includere un'attività di registrazione automatizzata nella configurazione del flusso di lavoro. Le fatture correlate agli ordini fornitore e le fatture che contengono una categoria di approvvigionamento non ordine fornitore e righe non a magazzino possono essere inviate automaticamente al sistema del flusso di lavoro. Le fatture immesse manualmente devono essere inviate manualmente al sistema del flusso di lavoro.

Il valore **Inviata da** nel flusso di lavoro è l'ID utente immesso per l'attività di background **Inviare fatture fornitore a flusso di lavoro** nella pagina **Automazione del processo**. L'utente che dispone di tale ID utente sarà in grado di richiamare la fattura dal sistema del flusso di lavoro come richiesto.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Abbinare entrate prodotti a righe di fattura che hanno criteri di abbinamento a tre elementi di verifica

Come parte di un processo di fatturazione della contabilità fornitori senza contatto, le entrate prodotti registrate possono essere abbinate automaticamente a righe di fattura. Per questa attività è necessario definire criteri di abbinamento a tre elementi di verifica. Questa funzionalità è disponibile se la funzionalità **Automazione fattura fornitore** è stata abilitata nella pagina **Gestione funzionalità**.

Il processo di corrispondenza verrà eseguito fino a quando la quantità delle entrate prodotti abbinate non sarà uguale alla quantità della fattura. Tuttavia, se sono presenti più entrate prodotto per una singola riga di fattura, sarà necessario eseguire il processo più volte per ottenere la piena corrispondenza della quantità. Puoi specificare il numero massimo di tentativi del sistema di abbinare le entrate prodotti a una riga di fattura prima che il sistema consideri il processo come non riuscito. Il processo verrà eseguito in background, ogni ora o ogni giorno. 

Puoi eseguire il processo di abbinamento automatizzato come parte del processo di invio di fatture al sistema del flusso di lavoro. In alternativa, puoi eseguirlo come processo autonomo. Le impostazioni per il processo di abbinamento di entrate prodotto a righe di fattura sono configurate nella scheda **Automazione fattura fornitore** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazione \> Parametri contabilità fornitori**).

Le righe di fattura che hanno criteri di abbinamento a tre elementi di verifica, in cui la quantità di entrata prodotti abbinata è inferiore alla quantità di fattura, verranno incluse nel processo di abbinamento automatico all'entrata prodotti.

Per visualizzare lo stato **Ultimo abbinamento** per le fatture che non fanno parte del processo di invio automatico al flusso di lavoro, apri la fattura dalla pagina **Fatture fornitore**. Quando visualizzi la fattura, le informazioni di convalida dell'abbinamento vengono aggiornate. Lo stato **Ultima partita** può essere aggiornato automaticamente utilizzando l'attività **Convalida abbinamento fatture** in background. Puoi configurare il processo di aggiornamento automatico dello stato **Ultima partita** nella scheda **Processi in background** della pagina **Automazioni di processo** (**Amministrazione del sistema\> Configurazione\> Automazioni di processo**).

Una riga di fattura verrà esclusa dall'elaborazione automatizzata se viene soddisfatta una delle seguenti condizioni:

- Il valore **Stato corrispondenza entrate automatizzate** della riga di fattura è **Non riuscita**.
- La fattura è in uso.
- La fattura è nel sistema del flusso di lavoro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
