---
title: Creare fatture di ordine cliente
description: Questo argomento come fatturare un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7976d310e9c80dfe683359f1157b85e46c758c48
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713446"
---
# <a name="create-sales-order-invoices"></a>Creare fatture di ordine cliente

[!include [banner](../../includes/banner.md)]

Questo argomento come fatturare un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch. Questa procedura utilizza la società dimostrativa USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>Creare una fattura da un ordine cliente.
1. Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Ordini > Ordini cliente spediti ma non fatturati**.
2. Selezionare un ordine cliente nell'elenco. 
3. Nel **riquadro azioni**, fare clic su **Fattura > Gnera > Fattura**. Si noti che all'ordine cliente sono associati più documenti di trasporto. Verrà visualizzata solo la parola *più* anziché il numero del documento di trasporto.  
4. Espandere la sezione **Parametri**.
    - La registrazione deve essere impostata su Sì per registrare la fattura. È inoltre possibile disabilitare la registrazione e stampare solo la fattura. Tuttavia, è possibile ottenere lo stesso risultato creando una fattura proforma anziché una fattura.  
    - Questa opzione viene utilizzata per i processi batch. La query viene eseguita quando viene eseguito il processo batch.
5. Selezionare "Dopo" nel campo **Stampa**.
6. Selezionare **Sì** per **Stampa fattura**. Gestione stampa consente di stampare più copie della fattura, nonché di inviare la fattura tramite posta elettronica come file PDF.  
7. Selezionare "Riepiloga" nel campo **Stampa addebiti**.
8. Nel campo **Verifica limite di credito**, selezionare "Saldo".
9. Fare clic su **Annulla**.

## <a name="combine-orders-into-a-single-invoice"></a>Combina gli ordini in un'unica fattura
1. Passare al **pannello di navigazione >Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Individuare un cliente con più fatture aperte.
3. Selezionare molteplici ordini cliente aperti dallo stesso cliente.
4. Nel **riquadro azioni**, fare clic su **Fattura > Gnera > Fattura**.
5. Espandere la sezione **Parametri**.
6. Nel campo **Quantità** selezionare "Tutto". Si noti che nella sezione relativa alla panoramica vengono elencate due fatture. Ora uniamole in una singola fattura.  
7. Nel campo **Aggiorna riepilogo per**, selezionare "Conto fatture".
8. Fare clic su **Disponi** per unire gli ordini cliente in una singola fattura. I due ordini cliente sono ora uniti in una singola fattura.   
9. Fare clic su **Annulla**.
10. Fare clic su **Sì**.

## <a name="post-invoices-in-a-batch"></a>Registra le fatture in un batch
1. Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Fatture > Fatturazione batch > Fattura**.
2. Fare clic su **Seleziona**.
3. Fare clic su **OK**.
4. Fare clic su **Batch**.
5. Selezionare **Sì** in **Elaborazione batch**.
6. Fare clic su **Ricorrenza**.
7. Selezionare **Giorni**.
8. Fare clic su **OK**.
9. Fare clic su **OK**.
10. Fare clic su **Annulla**.
11. Fare clic su **Sì**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
