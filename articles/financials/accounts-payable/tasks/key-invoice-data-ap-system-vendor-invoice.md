---
title: Dati principali della fattura in sistema di contabilità fornitori utilizzando la fattura fornitore
description: Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "359108"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a>Dati principali della fattura in sistema di contabilità fornitori utilizzando la fattura fornitore

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Individuare un fornitore da selezionare. Ad esempio, scorrere verso il basso fino a US-104.
5. Seleziona il fornitore US-104.
6. Fare clic su OK.
7. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
8. Selezionare un articolo di magazzino. Ad esempio, selezionare il numero articolo 1000.
9. Espandere o comprimere la sezione Dettagli riga.
10. Fare clic sulla scheda Impostazioni.
    * È possibile sostituire i criteri di abbinamento per non utilizzare la corrispondenza, la corrispondenza o due elementi di verifica o quella a tre elementi di verifica.  
11. Espandere o comprimere la sezione Dettagli riga.
12. Nel riquadro azioni fare clic su Acquisti.
13. Fare clic su Conferma.

## <a name="receive-the-products"></a>Ricevere i prodotti
1. Nel riquadro azioni fare clic su Ricevimento.
2. Fare clic su Entrata prodotti.
3. Nel campo Entrata prodotti, immettere il numero dell'entrata prodotti. Ad esempio, immettere PR123.
4. Fare clic su OK per registrare l'entrata prodotti.
5. Chiudere la pagina.

## <a name="create-a-vendor-invoice"></a>Creare una fattura fornitore
1. Andare a Contabilità fornitori > Ordini acquisto > Ordini acquisto ricevuti ma non fatturati.
2. Selezionare l'ordine fornitore creato.
3. Nel riquadro azioni fare clic su Fattura.
4. Fare clic su Fattura.
5. Nel campo Numero immettere il numero di fattura.
6. Nel campo Descrizione fattura digitare un valore.
7. Immettere una data nel campo Data fattura.
8. Immettere 1200 nel campo Prezzo unitario.
9. Fare clic su Aggiungi riga.
10. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco, individuare il numero di articolo della spesa di installazione. Ad esempio, S0001
12. Selezionare il numero articolo della spesa di installazione.
    * Si noti che la corrispondenza non è stata eseguita da quando sono state apportate le modifiche.  
13. Fare clic su Aggiorna stato di abbinamento.
14. Nel riquadro azioni fare clic su Revisione.
15. Fare clic su Dettagli abbinamento.
    * La nuova riga con i servizi non deve essere abbinata, quindi lo stato rimane "Non eseguito".  
16. Selezionare l'entrata prodotti per l'articolo di magazzino ricevuto.
    * La riga con l'entrata prodotti è stata abbinata, ma la quantità o il prezzo non sono corrispondenti e pertanto restituisce l'esito negativo.  
17. Nel campo Prezzo unitario immettere un numero.
    * Ora che il prezzo unitario corrisponde, lo stato verrà aggiornato su Superato. Se i criteri consentono le discrepanze o se la corrispondenza è solo un avviso, è comunque possibile registrare la fattura.  
18. Chiudere la pagina.
19. Fare clic su Registra.
20. Chiudere il modulo.
    * Si noti che l'ordine fornitore non è più elencato come ricevuto ma come non fatturato.  

