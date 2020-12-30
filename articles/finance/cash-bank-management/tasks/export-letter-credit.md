---
title: Esportare lettera di credito
description: In questa procedura vengono descritti i passaggi per esportare una lettera di credito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3cd18320ca8505b1357ce505dfb4c94e81aaae91
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444745"
---
# <a name="export-letter-of-credit"></a>Esportare lettera di credito

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per esportare una lettera di credito.

Una lettere di credito è un contratto emesso da una banca, nel quale la banca acconsente a garantire un pagamento per conto dell'acquirente, qualora vengano osservati i termini del contratto tra l'acquirente e il venditore.



Eseguire la procedura 'Impostare le linee di credito bancarie e i profili registrazione' e la procedura 'Creare un contratto per linea di credito bancaria per la lettera di credito' prima di questa procedura. La società di dati dimostrativi USMF deve essere selezionata per eseguire questa procedura correttamente.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Creare un ordine cliente per lettera di credito di esportazione
1. Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Espandere o comprimere la sezione Generale.
7. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il sito in cui è stoccato l'articolo da emettere.  
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare il magazzino in cui è stoccato l'articolo da emettere.  
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Nota: il campo Tipo di documento bancario deve essere selezionato con il valore Lettera di credito.  
11. Selezionare 'Lettera di credito' nel campo Tipo di documento bancario.
12. Espandere o comprimere la sezione Consegna.
    * Selezionare Controllo data di consegna = Nessuno.  
13. Nel campo Data di ricevimento richiesta immettere una data.
14. Fare clic su OK.
15. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
    * Selezionare l'articolo richiesto da emettere/vendere.  
16. Nell'elenco trovare e selezionare il record desiderato.
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Immettere un numero nel campo Prezzo unitario.
19. Espandere o comprimere la sezione Dettagli riga.
20. Fare clic sulla scheda Consegna.
21. Nel campo Data di spedizione richiesta immettere una data.
22. Nel campo Data di spedizione confermata immettere una data.
23. Nel riquadro azioni, fare clic su Gestisci.
24. Fare clic su Lettera di credito.
25. Digitare un valore nel campo Numero documento bancario.
26. Nel campo Data di scadenza immettere una data e un'ora.
27. Espandere o comprimere la sezione Dettagli banca.
28. Nel campo Banca emittente fare clic sul pulsante a discesa per aprire la ricerca.
29. Nell'elenco fare clic sul collegamento nella riga selezionata.
30. Nel campo Banca avvisante fare clic sul pulsante a discesa per aprire la ricerca.
31. Trovare e selezionare il record desiderato nell'elenco.
32. Nell'elenco fare clic sul collegamento nella riga selezionata.
33. Fare clic su Recupera spedizioni ordine cliente.
34. Fare clic su Emetti documento bancario.
35. Chiudere la pagina.

## <a name="post-packing-slip"></a>Registrare il documento di trasporto
1. Nel riquadro azioni fare clic su Preleva e imballa.
2. Fare clic su Registra documento di trasporto.
3. Espandere o comprimere la sezione Parametri.
4. Nel campo Quantità selezionare "Tutto".
5. Espandere o comprimere la sezione Impostazione.
6. Immettere una data nel campo Data documento di trasporto.
7. Selezionare il numero spedizione.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su OK.
10. Fare clic su OK.

## <a name="post-sales-invoice"></a>Registrare la fattura di vendita
1. Nel riquadro azioni fare clic su Fattura.
2. Fare clic su Fattura.
3. Espandere o comprimere la sezione Panoramica.
4. Selezionare il numero spedizione.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Espandere o comprimere la sezione Impostazione.
7. Immettere una data nel campo Data fattura.
8. Fare clic su OK.
9. Fare clic su OK.

## <a name="shipment-document-submitted-status"></a>Stato del documento di spedizione inviato
1. Nel riquadro azioni, fare clic su Gestisci.
2. Fare clic su Lettera di credito.
3. Espandere o comprimere la sezione Righe.
    * Nota: il campo inviato 'Documento inviato' deve essere impostato 'Sì'.  

## <a name="verify-export-letter-of-credit"></a>Verificare la lettera di credito di esportazione
1. Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di esportazione e pagamento all'importazione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Verificare che la lettera di credito di esportazione abbia lo stato della spedizione 'Fatturato'.  

## <a name="customer-payment"></a>Pagamento cliente
1. Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su Righe.
7. Nel campo Data immettere una data.
8. Nel campo Conto, specificare i valori desiderati.
9. Fare clic su Liquidazione.
10. Selezionare la casella di controllo sull'intestazione di Totali.
    * Nota: impostare il campo Mostra su 'Lettera di credito'.  
11. Nell'elenco trovare e selezionare il record desiderato.
12. Selezionare o deselezionare la casella di controllo Contrassegna.
13. Fare clic su OK.
14. Fare clic sulla scheda Pagamento.
    * Verificare i dettagli del numero di spedizione e del numero di documento bancario  
15. Fare clic su Registra.

## <a name="verify-export-letter-of-credit-after-payment"></a>Verificare la lettera di credito di esportazione dopo il pagamento
1. Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di esportazione e pagamento all'importazione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Verificare Stato spedizione = Pagamento ricevuto e importo saldo = 0,00.  

