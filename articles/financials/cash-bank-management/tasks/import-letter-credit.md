---
title: Importare la lettera di credito
description: In questa procedura vengono descritti i passaggi per importare una lettera di credito.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3d5539fbd17c880d8bbadd47444c9cc53fce039c
ms.sourcegitcommit: 0c1deb100d0bf6dacd14b328968bbc7a9d92583a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "771233"
---
# <a name="import-letter-of-credit"></a>Importare la lettera di credito

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per importare una lettera di credito. Prima di completare la procedura è necessario configurare quanto segue: le linee di credito bancarie, i profili registrazione, un contratto per linea di credito bancaria e i dettagli bancari del fornitore.

Questa procedura utilizza la società dimostrativa USMF.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Creare un ordine acquisto con una lettera di credito
1. Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.
2. Fare clic su Nuovo.
3. Nel campo Conto fornitore, immettere o selezionare un valore.
4. Trovare e selezionare il record desiderato nell'elenco.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Espandere la sezione Generale.
7. Nel campo Sito immettere o selezionare un valore.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Magazzino immettere o selezionare un valore.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Immettere una data nel campo Data di registrazione.
12. Immettere una data nel campo Data di consegna.
    * Nota: il campo 'Tipo di documento bancario' deve essere selezionato con il valore 'Lettera di credito'.  
13. Fare clic su OK.
14. Nel campo Numero di articoli immettere o selezionare un valore.
15. Nell'elenco trovare e selezionare il record desiderato.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Espandere la sezione Dettagli riga.
18. Fare clic sulla scheda Consegna.
19. Immettere una data nel campo Data di consegna.
20. Immettere una data nel campo Data di consegna confermata.
21. Nel campo Prezzo unitario immettere un numero.
    * Definire i dettagli della lettera di credito.  
22. Nel riquadro azioni, fare clic su Gestisci.
23. Fare clic su Lettera di credito/pagamento all'importazione.
24. Nel campo Data richiesta immettere una data e un'ora.
    * Verificare che il campo 'Conto bancario' contenga il conto bancario attivo predefinito in base alla data dell'applicazione.  
25. Digitare un valore nel campo Numero documento bancario.
26. Nel campo Data ricevimento immettere una data e un'ora.
27. Espandere la sezione Documento bancario.
28. Nel campo Data di scadenza immettere una data e un'ora.
29. Espandere la sezione Dettagli banca.
30. Nel campo Banca avvisante immettere o selezionare un valore.
31. Nell'elenco fare clic sul collegamento nella riga selezionata.
32. Fare clic su Salva.
33. Fare clic su Recupera spedizioni ordine fornitore.
34. Chiudere la pagina.
35. Nel riquadro azioni fare clic su Acquisti.
36. Fare clic su Conferma.
37. Nel riquadro azioni, fare clic su Gestisci.
38. Fare clic su Lettera di credito/pagamento all'importazione.
39. Fare clic su Elabora.
40. Fare clic su Conferma.
    * Verificare che il saldo linea di credito riduca l'importo dell'ordine fornitore.  In questo esempio, Importo acquisto = 500,00, Limite struttura = 10000,00, pertanto, Saldo linea di credito = 9500,00.  
41. Chiudere la pagina.
42. Nel campo Prezzo unitario immettere un numero.
43. Fare clic su Salva.
44. Nel riquadro azioni fare clic su Acquisti.
45. Fare clic su Conferma.
    * Modificare la lettera di credito, a causa della modifica del prezzo unitario.  
46. Nel riquadro azioni, fare clic su Gestisci.
47. Fare clic su Lettera di credito/pagamento all'importazione.
    * Modificare la lettera di credito, a causa della modifica del prezzo unitario di acquisto.  
48. Fare clic su Elabora.
49. Fare clic su Modifica.
50. Fare clic su Rimuovi.
51. Fare clic su Sì.
52. Fare clic su Recupera spedizioni ordine fornitore.
53. Fare clic su Elabora.
54. Fare clic su Conferma.
    * Verificare che il saldo linea di credito riduca l'importo dell'ordine fornitore.  In questo esempio, è stato modificato Importo acquisto = 600,00, Limite struttura = 10000,00, pertanto, Saldo linea di credito = 9400,00.  
55. Chiudere la pagina.

## <a name="post-packing-slip"></a>Registrare il documento di trasporto
1. Nel riquadro azioni fare clic su Ricevimento.
2. Fare clic su Entrata prodotti.
3. Digitare un valore nel campo PurchParmTable_Num.
    * Selezionare il numero di spedizione creato in riferimento alla lettera di credito.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Data entrata prodotti immettere una data.
6. Fare clic su OK.
7. Chiudere la pagina.
8. Chiudere la pagina.

## <a name="verify-import-letter-of-credit-status"></a>Verificare lo stato dell'importazione della lettera di credito
1. Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Verificare lo stato dell'importazione della lettera di credito.     
4. Chiudere la pagina.
5. Chiudere la pagina.

## <a name="post-purchase-invoice"></a>Registrare la fattura di acquisto
1. Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.
    * Selezionare l'ordine fornitore creato con la lettera di credito.  
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni fare clic su Fattura.
5. Fare clic su Fattura.
6. Digitare un valore nel campo Numero.
7. Nel campo Numero spedizione immettere o selezionare un valore.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Immettere una data nel campo Data fattura.
10. Fare clic su Aggiorna stato di abbinamento.
11. Fare clic su Registra.
12. Chiudere la pagina.
13. Chiudere la pagina.

## <a name="verify-import-letter-of-credit-status"></a>Verificare lo stato dell'importazione della lettera di credito
1. Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Verificare l'importazione della lettera di credito.  
    * Convalida : stato della spedizione = dettagli fatturati di linea di credito bancaria  
4. Fare clic su Visualizza.
5. Fare clic su Stampa richiesta.
6. Fare clic su OK.
    * Verificare che la richiesta di lettera di credito venga stampata.  
7. Chiudere la pagina.
8. Chiudere la pagina.
9. Chiudere la pagina.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Registrare il giornale di registrazione pagamenti fornitore per la fattura di acquisto creata con la lettera di credito
1. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Fare clic su Righe.
6. Nel campo Data immettere una data.
7. Nel campo Conto, specificare i valori desiderati.
8. Fare clic su Liquida transazioni.
9. Espandere la sezione Totali.
10. Selezionare un'opzione nel campo Mostra.
    * Verificare che i campi Numero documento bancario e Numero spedizione siano stati aggiornati.  
11. Selezionare la casella di controllo Contrassegna.
12. Fare clic su OK.
13. Fare clic sulla scheda Pagamento.
    * Verificare che i campi Numero documento bancario e Numero spedizione siano stati aggiornati.  
14. Fare clic su Registra.
15. Chiudere la pagina.
16. Chiudere la pagina.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Verificare lo stato della lettera di credito di importazione dopo la fattura pagata
1. Passare a Gestione cassa e banche > Lettere di credito > Lettera di credito di importazione e pagamento all'importazione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Verificare lo stato dell'importazione della lettera di credito.   
4. Chiudere la pagina.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Verificare il report di utilizzo e limite di linee di credito bancarie
1. Passare a Gestione cassa e banche > Richieste di informazioni e report Lettere di credito o garanzia > Report di utilizzo e linee di credito bancarie.
2. Espandere la sezione Record da includere.
3. Fare clic su Filtro.
    * Definire il campo Criteri con il conto bancario richiesto.  
4. Nel campo Criteri immettere o selezionare un valore.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su OK.
7. Fare clic su OK.
    * Verificare il report con l'elenco delle transazioni.  
    * Verificare che il report elenchi le transazioni con il numero di documento bancario, il limite struttura, l'importo utilizzato e l'importo del saldo linea di credito.  
8. Chiudere la pagina.

