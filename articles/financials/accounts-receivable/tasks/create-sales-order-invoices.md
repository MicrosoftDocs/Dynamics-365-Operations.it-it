--- 
title: Creare fatture ordine cliente
description: "Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-order-invoices"></a>Creare fatture ordine cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch. Questa procedura utilizza la società dimostrativa USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Creare una fattura da un ordine cliente.
1. Fare clic su Contabilità clienti > Ordini > Ordini cliente spediti ma non fatturati.
2. Selezionare un ordine cliente nell'elenco. 
3. Nel riquadro azioni fare clic su Fattura.
4. Fare clic su Fattura.
    * Si noti che all'ordine cliente sono associati più documenti di trasporto. Verrà visualizzata solo la parola <multiple> anziché il numero del documento di trasporto.  
5. Espandere la sezione Parametri.
    * La registrazione deve essere impostata su Sì per registrare la fattura. È inoltre possibile disabilitare la registrazione e stampare solo la fattura. Tuttavia, è possibile ottenere lo stesso risultato creando una fattura proforma anziché una fattura.  
    * Questa opzione viene utilizzata per i processi batch. La query viene eseguita quando viene eseguito il processo batch.    
6. Selezionare "Dopo" nel campo Stampa.
7. Selezionare Sì per Stampa fattura.
    * Gestione stampa consente di stampare più copie della fattura, nonché di inviare la fattura tramite posta elettronica come file PDF.  
8. Selezionare "Riepiloga" nel campo Stampa addebiti.
9. Nel campo Verifica limite di credito, selezionare "saldo".
10. Scegliere Annulla.

## <a name="combine-orders-into-a-single-invoice"></a>Combina gli ordini in un'unica fattura
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Individuare un cliente con più fatture aperte.
3. Selezionare un ordine cliente aperto.
4. Selezionare un altro ordine cliente aperto per lo stesso cliente.
5. Nel riquadro azioni fare clic su Fattura.
6. Fare clic su Fattura.
7. Espandere la sezione Parametri.
8. Nel campo Quantità selezionare "Tutto".
    * Si noti che nella sezione relativa alla panoramica vengono elencate due fatture. Ora uniamole in una singola fattura.  
9. Nell'aggiornamento riepilogativo del campo, selezionare "Conto fatture".
10. Fare clic su Disponi per unire gli ordini cliente in una singola fattura.
    * I due ordini cliente sono ora uniti in una singola fattura.   
11. Scegliere Annulla.
12. Fare clic su Sì.

## <a name="post-invoices-in-a-batch"></a>Registra le fatture in un batch
1. Fare clic su Contabilità clienti > Fatture > Fatturazione batch > Fattura.
2. Fare clic su Seleziona.
3. Fare clic su OK.
4. Fare clic su Batch.
5. Fare clic su Sì cui per abilitare l'elaborazione batch.
6. Fare clic su Ricorrenza.
7. Selezionare Giorni
8. Fare clic su OK.
9. Fare clic su OK.
10. Scegliere Annulla.
11. Fare clic su Sì.


