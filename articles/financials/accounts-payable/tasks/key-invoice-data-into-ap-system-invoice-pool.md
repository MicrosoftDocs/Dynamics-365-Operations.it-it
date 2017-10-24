--- 
title: "Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture"
description: "Questa guida attività indicherà come utilizzare il registro fatture per creare le fatture."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96040b1c1ba130f773ba0defbf7bf1dcebedfc13
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa guida attività indicherà come utilizzare il registro fatture per creare le fatture.  Utilizzare quindi il pool di fatture per abbinare la fattura a un ordine fornitore e per finalizzare la spesa nella pagina della fattura fornitore.


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Fare clic su Contabilità fornitori > Ordini fornitore > Ordini fornitore.
2. Fare clic su Nuovo per creare un nuovo ordine fornitore.
3. Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.
4. Selezionare il fornitore dall'elenco. Ad esempio, il fornitore 1001.
5. Fare clic su OK.
6. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
7. Individuare il numero di articolo servizi nell'elenco. Selezionare, ad esempio S0001.
8. Fare clic sul numero di articolo e selezionarlo.
    * L'importo netto è 75,00.  Si tratta dell'importo previsto nella fattura.  
9. Nel riquadro azioni fare clic su Acquisti.
10. Fare clic su Conferma.

## <a name="create-and-post-and-invoice"></a>Creare e registrare una fattura
1. Andare a Contabilità fornitori > Fatture > Registro fatture.
2. Fare clic su Nuovo.
3. Aprire la ricerca per selezionare il nome del registro fatture che si desidera utilizzare.
4. Selezionare il nome del registro fatture che si desidera utilizzare.
5. Fare clic su Righe per aprire il registro e immettere le righe di spesa.
6. Nella ricerca selezionare un fornitore. Ad esempio, fare clic sul fornitore 1001.
7. Nel campo Fattura immettere il numero di fattura.
8. Digitare un valore nel campo Descrizione.
9. Nel campo Credito immettere un numero.
10. Nel campo Ordine fornitore fare clic sul pulsante a discesa per aprire la ricerca.
11. Selezionare l'ordine fornitore creato in precedenza.
12. Nel campo Approvata da fare clic sul pulsante a discesa per aprire la ricerca.
13. Evidenzi un approvatore e fare clic su per selezionare tale approvatore.
14. Fare clic su Registra.
15. Chiudere il modulo.
16. Chiudere il modulo.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Aprire una fattura dal pool e abbinarla a un ordine fornitore per completare il processo di fatturazione
1. Andare a Contabilità fornitori > Fatture > Pool fatture.
2. Fare clic su Ordine fornitore per creare una fattura fornitore dalla fattura nel pool.
3. Selezionare la fattura che si desidera rivedere.
4. Fare clic su Aggiorna stato di abbinamento per completare la l'abbinamento.
5. Nel riquadro azioni fare clic su Opzioni.
6. Fare clic su Cambia visualizzazione.
7. Fare clic su Visualizzazione griglia.
8. Fare clic su Registra.
9. Chiudere il modulo.
10. Passare a Contabilità fornitori > Fornitori > Fornitori.
11. Selezionare il fornitore dell'ordine fornitore. Selezionare, ad esempio, il fornitore 1001.
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Nel riquadro azioni, fare clic su Fornitore.
14. Fare clic su Transazioni.
15. Selezionare la fattura creata.
    * Il rateo del registro fatture è stato stornato e registrato nel conto spese appropriato.  


