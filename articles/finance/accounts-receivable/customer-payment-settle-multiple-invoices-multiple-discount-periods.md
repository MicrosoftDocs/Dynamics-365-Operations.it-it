---
title: Utilizzare un pagamento cliente per liquidare più fatture che coprono più periodi di sconto
description: Questo argomento mostra come vengono pagate più fatture quando ogni fattura consente di ottenere uno sconto di cassa. Gli scenari in questo articolo evidenziano le variazioni degli sconti di cassa ottenuti, a seconda di quando si effettua il pagamento.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7ae0bdc8245db1391103ca0f214fb3120f93f5b
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4445008"
---
# <a name="use-a-customer-payment-to-settle-multiple-invoices-that-span-multiple-discount-periods"></a>Utilizzare un pagamento cliente per liquidare più fatture che coprono più periodi di sconto

[!include [banner](../includes/banner.md)]

Questo argomento mostra come vengono pagate più fatture quando ogni fattura consente di ottenere uno sconto di cassa. Gli scenari in questo articolo evidenziano le variazioni degli sconti di cassa ottenuti, a seconda di quando si effettua il pagamento.

Fabrikam vende merci al cliente 4032. Fabrikam offre uno sconto di cassa dell'1% se la fattura viene pagata entro 14 giorni. Fabrikam offre inoltre sconti di cassa su pagamenti parziali. I parametri di liquidazione si trovano nella pagina **Parametri contabilità clienti**.

## <a name="invoices"></a>Fatture
Il cliente 4032 ha tre fatture con totale 3.000,00:

-   La fattura FTI-10040, per 1.000,00, è stata immessa il 15 maggio. Questa fattura è idonea a uno sconto di cassa dell'1% se viene pagata entro 14 giorni.
-   La fattura FTI-10041, per 1.000,00, è stata immessa il 25 giugno. Questa fattura è idonea a uno sconto di cassa dell'1% se viene pagata entro 14 giorni.
-   La fattura FTI-10042, per 1.000,00, è stata immessa il 25 giugno. Questa fattura è idonea a uno sconto di cassa del 2% se pagata entro cinque giorni e di uno sconto dell'1% se pagata entro 14 giorni.

## <a name="settle-all-invoices-on-june-29"></a>Liquidare tutte le fatture il 29 giugno
Se Arnie crea un giornale di registrazione pagamenti per liquidare completamente le fatture il 29 giugno, il pagamento sarà pari a 2.970,00. Il totale di tutti gli importi di sconto è 30,00. Arnie crea un pagamento per il cliente 4032 e quindi apre la pagina **Liquida transazioni**. Nella pagina **Liquida transazioni** Arnie contrassegna tutte le tre righe di fattura per la liquidazione:

-   Il pagamento per la fattura FTI-10040 è 1.000,00. Nessuno sconto di cassa viene applicato.
-   Il pagamento per la fattura FTI-10041 è 990,00. Viene applicato uno sconto di cassa dell'1%, ovvero 10,00.
-   Il pagamento per la fattura FTI-10042 è 980,00. Viene applicato uno sconto di cassa del 2%, ovvero 20,00.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selezionata                 | Normale            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | GBP      | 1.000,00         |
| Selezionato                 | Normale            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | GBP      | 990,00           |
| Selezionato ed evidenziato | Normale            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | GBP      | 980,00           |

Dopo che il pagamento viene registrato, il saldo cliente è 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Liquidare tutte le fatture il 1° luglio
Se Arnie crea un giornale di registrazione pagamenti per liquidare completamente le fatture il 1° luglio, il pagamento sarà pari a 2.980,00. Arnie crea un pagamento per il cliente 4032 e quindi apre la pagina **Liquida transazioni**. Nella pagina **Liquida transazioni** Arnie contrassegna tutte le tre righe di fattura per la liquidazione:

-   Il pagamento per la fattura FTI-10040 è 1.000,00. Nessuno sconto di cassa viene applicato.
-   Il pagamento per la fattura FTI-10041 è 990,00. Viene applicato uno sconto di cassa dell'1%, ovvero 10,00.
-   Il pagamento per la fattura FTI-10042 è 990,00. Viene applicato uno sconto di cassa dell'1%, ovvero 10,00. Sebbene il 1° luglio sia successivo al periodo per lo sconto del 2%, è ancora nel periodo per lo sconto dell'1%.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selezionata                 | Normale            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | GBP      | 1.000,00         |
| Selezionato                 | Normale            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | GBP      | 990,00           |
| Selezionato ed evidenziato | Normale            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | GBP      | 990,00           |

## <a name="partial-settlement-on-june-29"></a>Liquidazione parziale il 29 giugno
Il cliente 4032 può pagare un importo parziale, ad esempio metà di ciascuna fattura. Arnie crea un pagamento per il cliente 4032 e quindi apre la pagina **Liquida transazioni**. Nella pagina **Liquida transazioni** Arnie contrassegna tutte le tre righe di fattura per la liquidazione: In ciascuna riga, immette l'importo da liquidare, in base alle istruzioni fornite dal cliente. Quando una riga è selezionata, Arnie vede l'importo dello sconto per la riga e l'importo dello sconto di cassa che viene applicato. Poiché il cliente paga metà della fattura, Arnie vede che il valore nel campo **Importo sconto di cassa** per FTI-10042 è **20,00**, ma che il valore nel campo **Sconto di cassa applicato** è **10,00**. L'importo del pagamento è 1.485,00.

| Contrassegna                     | Utilizzare lo sconto di cassa | Giustificativo   | Conto | Data      | Data di scadenza  | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Valuta | Importo da liquidare |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selezionata                 | Normale            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | GBP      | 500,00           |
| Selezionato                 | Normale            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | GBP      | 495,00           |
| Selezionato ed evidenziato | Normale            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | GBP      | 490,00           |

Arnie può inoltre immettere manualmente l'importo del pagamento di 1.485,00 prima di aprire la pagina **Liquida transazioni**. Se Arnie immette manualmente l'importo del pagamento e quindi contrassegna tutte e tre le transazioni, ma non rettifica il valore nel campo **Importo da liquidare** per ciascuna transazione, riceve il seguente messaggio alla chiusura della pagina:

> L'importo totale delle transazioni contrassegnate è diverso da quello riportato nel giornale di registrazione. Modificare l'importo del giornale?

Se Arnie desidera che l'importo del pagamento sia solo 1.485,00, fa clic su **No**, quindi registra il giornale di registrazione. Le transazioni vengono liquidate come segue:

1.  La fattura FTI-10040 è completamente liquidata per 1.000,00, poiché è stata immessa il 15 maggio ed è la fattura meno recente. Nessuno sconto di cassa viene applicato. L'importo rimanente nella transazione di pagamento è 485,00.
2.  La fattura FTI-10041 non viene liquidata affatto. Le fatture FTI-10041 e FTI-10042 sono state immesse alla stessa data. Tuttavia, uno sconto dell'1% è disponibile per la fattura FTI-10041 e uno sconto del 2% è disponibile per la fattura FTI-10042. Poiché il migliore sconto sarà disponibile per fatturare FTI-10042, i 485,00 rimanenti vengono liquidati con la fattura FTI-10042.
3.  La fattura FTI-10042 viene liquidata con i 485,00 rimanenti. Fabrikam offre gli sconti parziali. In questo caso, lo sconto è 9,90 (= 485,00 ÷ 0,98 × 0,02). L'importo (485,00) viene suddiviso per 0,98, poiché è presente uno sconto del 2%, in modo che il cliente paghi il 98% della fattura. Il risultato viene quindi moltiplicato per la percentuale di sconto, ovvero il 2%. Il pagamento di 485,00 più lo sconto del 9,90 è pari a 494,90. L'importo della fattura originale è 1.000,00. Pertanto la transazione ha un saldo pari a 505,10, ovvero 1.000,00 - 494,90.

Arnie visualizza le informazioni nella pagina **Transazioni cliente**.

| Giustificativo    | Tipo di transazione | Data      | Fattura | Importo Dare in valuta transazione | Importo Avere in valuta transazione | Saldo  | Valuta |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Fattura          | 15/5/2015 | 10040   | 1.000,00                             |                                       | 0,00     | GBP      |
| FTI-10041  | Fattura          | 25/6/2015 | 10041   | 1.000,00                             |                                       | 1.000,00 | GBP      |
| FTI-10042  | Fattura          | 25/6/2015 | 10042   | 1.000,00                             |                                       | 505,10   | GBP      |
| ARP-10040  | Pagamento          | 29/6/2015 |         |                                      | 1.485,00                              | 0,00     | GBP      |
| DISC-10040 | Sconto di cassa    | 29/6/2015 |         |                                      | 9,90                                  | 0,00     | GBP      |





