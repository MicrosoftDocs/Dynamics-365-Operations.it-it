---
title: Dati principali della fattura in contabilità fornitori utilizzando una fattura fornitore
description: Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c441d197957674d68c4c92b454a9dca91d76ea0
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775190"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a>Dati principali della fattura in contabilità fornitori utilizzando una fattura fornitore

[!include [banner](../../includes/banner.md)]

Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Passare al pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto fornitore** fare clic sul pulsante a discesa per aprire la ricerca.
4. Individuare un fornitore da selezionare. Ad esempio, scorrere verso il basso fino a US-104.
5. Seleziona il fornitore US-104.
6. Fare clic su **OK**.
7. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
8. Selezionare un articolo di magazzino. Ad esempio, selezionare il numero articolo 1000.
9. Espandere la Scheda dettaglio **Dettagli riga**.
10. Fare clic sulla scheda **Impostazione**. È possibile sostituire i criteri di abbinamento per utilizzare nessun abbinamento, l'abbinamento a due elementi di verifica o quello a tre elementi di verifica.  
11. Nel riquadro azioni, fare clic su **Acquisti**.
12. Fare clic su **Conferma**.

## <a name="receive-the-products"></a>Ricevere i prodotti
1. Nel riquadro azioni, fare clic su **Ricevimento**.
2. Fare clic su **Entrata prodotti**.
3. Nel campo **Entrata prodotti**, immettere il numero dell'entrata prodotti. Ad esempio, immettere PR123.
4. Fare clic su **OK** per registrare l'entrata prodotti.
5. Chiudere la pagina.

## <a name="create-a-vendor-invoice"></a>Creare una fattura fornitore
1. Passare al pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Ordini fornitore ricevuti ma non fatturati**.
2. Selezionare l'ordine fornitore creato.
3. Nel riquadro azioni fare clic su **Fattura**.
4. Fare clic su **Fattura**.
5. Nel campo **Numero** immettere il numero di fattura.
6. Nel campo **Descrizione fattura** digitare un valore.
7. Immettere una data nel campo **Data fattura**.
8. Immettere 1200 nel campo **Prezzo unitario**.
9. Fare clic su **Aggiungi riga**.
10. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco, individuare il numero di articolo della spesa di installazione. Ad esempio, S0001
12. Selezionare il numero articolo della spesa di installazione. Si noti che la corrispondenza non è stata eseguita da quando sono state apportate le modifiche.  
13. Fare clic su **Aggiorna stato di abbinamento**.
14. Nel riquadro azioni fare clic su **Revisione**.
15. Fare clic su **Dettagli abbinamento**. La nuova riga con i servizi non deve essere abbinata, quindi lo stato rimane "Non eseguito".  
16. Selezionare l'entrata prodotti per l'articolo di magazzino ricevuto. La riga con l'entrata prodotti è stata abbinata, ma la quantità o il prezzo non sono corrispondenti e pertanto restituisce l'esito negativo.  
17. Immettere un numero nel campo **Prezzo unitario**. Ora che il prezzo unitario corrisponde, lo stato verrà aggiornato su Superato. Se i criteri consentono le discrepanze o se la corrispondenza è solo un avviso, è comunque possibile registrare la fattura.  
18. Chiudi la pagina.
19. Fare clic su **Registra**.
20. Chiudi la pagina. 

>[!Note] 
>L'ordine fornitore non è più elencato come ricevuto ma come non fatturato.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
