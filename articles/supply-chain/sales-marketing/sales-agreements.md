---
title: Panoramica dei contratti di vendita
description: Vengono fornite le informazioni sui contratti di vendita. Un contratto di vendita è un contratto con cui il cliente si impegna ad acquistare prodotti in una determinata quantità o per uno specifico importo nel tempo in cambio di sconti o prezzi speciali.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage, SalesAgreementInvoiceJournal, SalesAgreementInvoicePart
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "9554"
- intro-internal
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f76e06f7265a4dc1837a66171d3db13bc2e580
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982511"
---
# <a name="sales-agreements-overview"></a>Panoramica dei contratti di vendita

[!include [banner](../includes/banner.md)]

Vengono fornite le informazioni sui contratti di vendita. Un contratto di vendita è un contratto con cui il cliente si impegna ad acquistare prodotti in una determinata quantità o per uno specifico importo nel tempo in cambio di sconti o prezzi speciali.

Un contratto di vendita è un contratto che impegna il cliente ad acquistare prodotti in una quantità specifica o per un importo specifico nel tempo, in cambio di prezzi speciali, sconti speciali nonché altre condizioni speciali, ad esempio pagamento e termini di consegna. I prezzi e gli sconti del contratto di vendita prevalgono sui prezzi e gli sconti dichiarati in eventuali contratti commerciali esistenti.  

Il periodo di validità di un contratto di vendita viene definito dai campi **Data di validità** e **Data di scadenza** del contratto. L'ordine cliente di un cliente si qualifica per le condizioni del contratto se la data di spedizione richiesta dell' ordine è compresa nel periodo di validità. Tutte le righe di ordine cliente collegate a un contratto di vendita contribuiscono all'esecuzione del contratto di vendita.  

È possibile creare un ordine cliente direttamente da un contratto di vendita mediante l'azione **Ordine di rilascio**. In alternativa, è possibile selezionare un contratto di vendita valido quando si prendono gli ordini (vedere la sezione “Applicazione di contratti di vendita nel processo di ordinazione" in questo articolo).  

> [Nota!] Nelle versioni precedenti, i contratti di vendita erano chiamati ordini cliente di copertura.

## <a name="commitment-types"></a>Tipi di impegno
Ogni riga di un contratto di vendita indica un impegno di vendita di un prodotto. In generale sono disponibili due categorie di impegno:

-   **Impegno valore**: il cliente accetta di acquistare prodotti per un importo specifico.
-   **Impegno quantità**: il cliente accetta di acquistare una quantità specifica di prodotti.

Inoltre, un contratto può impegnare il cliente ad acquistare uno o più prodotti specifici in una categoria di prodotti. Combinando questi due fattori (valore rispetto a quantità e prodotti specifici rispetto a categorie di prodotti), otteniamo quattro tipi di impegni:

-   **Impegno quantità prodotto**: il cliente accetta di acquistare una quantità specifica di prodotti. Le righe che utilizzano questo tipo di impegno sono definite da un numero di articolo e dalla quantità e unità concordate. Il campo **Importo** non è disponibile.
-   **Impegno valore prodotto**: il cliente accetta di acquistare prodotti specifici per un importo specifico. Le righe che utilizzano questo tipo di impegno sono definite da un numero di articolo e da un importo concordato. I campi **Quantità** e **Unità** non sono disponibili.
-   **Impegno valore categoria prodotto**: il cliente accetta di acquistare prodotti di una specifica categoria di vendita per un importo specifico. Le righe che utilizzano questo tipo di impegno sono definite da una categoria di vendita nella gerarchia di categorie di vendita e da un importo. I campi **Quantità** e **Unità** non sono disponibili.
-   **Impegno valore**: il cliente accetta di acquistare qualsiasi prodotto o prodotti in qualsiasi categoria di approvvigionamento per un importo specifico. I campi **Quantità** e **Unità** non sono disponibili.

Le righe nello stesso contratto di vendita possono avere diversi tipi di impegni.

## <a name="pricing-terms-for-sales-agreements"></a>Termini per la determinazione del prezzo dei contratti di vendita
I termini per la determinazione del prezzo possono variare a seconda del tipo di impegno. In un ordine cliente che è collegato a un contratto di vendita, i termini per la determinazione del prezzo di quel contratto di vendita prevalgono su tutti gli altri termini per la determinazione del prezzo applicabili in base ad accordi commerciali. Nella seguente tabella vengono descritti i campi relativi al prezzo interessati da ciascun tipo di impegno. "Sì" indica che il campo può essere aggiornato in una riga ordine.

| Tipo di impegno                   | Prezzo unitario | Unità di prezzo | Percentuale sconto | Importo sconto di cassa |
|-----------------------------------|------------|------------|------------------|----------------------|
| Impegno quantità prodotto       | Sì        | Sì        | Sì              | Sì                  |
| Impegno valore prodotto          |            |            | Sì              |                      |
| Impegno valore categoria prodotto |            |            | Sì              |                      |
| Impegno valore                  |            |            | Sì              |                      |

## <a name="policies-for-sales-agreements"></a>Criteri per i contratti di vendita
I criteri seguenti influiscono sulla modalità di funzionamento del collegamento tra un impegno del contratto di vendita e le righe corrispondenti dell'ordine cliente:

-   **Valore massimo applicato** - La quantità o l'importo totale per tutte le righe ordine non può superare la quantità o l'importo specificato nell'impegno correlato.
-   **Prezzo e sconto fissi** – Il prezzo in un riga ordine e il prezzo dell'impegno correlato non possono essere diversi. Se il prezzo viene modificato nella riga ordine, il collegamento all'impegno viene interrotto. In questo caso, la riga ordine non contribuisce all'evasione dell'impegno.
-   **Importo minimo rilascio** e **Importo massimo rilascio** - Se un importo viene specificato, viene visualizzato un messaggio se si apporta una modifica a una riga ordine rendendola diversa dall'impegno correlato.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Calcoli relativi all'evasione dei contratti di vendita
La scheda **Evasione** della Scheda dettaglio **Dettagli riga** nella pagina **Contratti di vendita** mostra le quantità e gli importi di evasione.  

Nell'area **Evasione** è possibile visualizzare le quantità e gli importi totali per tutte le righe ordine che sono collegate al contratto di vendita specificato. È inoltre possibile visualizzare la quantità o l'importo rimanente necessario per evadere l'impegno.  

Nell'area **Contratto** è possibile visualizzare le quantità e gli importi del contratto di vendita specificato. Le quantità e gli importi indicati rappresentano le quantità e gli importi totali che sono stati impegnati.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Conferme e storico della versione per i contratti di vendita
Quando si conferma un contratto di vendita, la versione corrente del contratto viene archiviata in una tabella dello storico. Se si modifica il contratto di vendita, è possibile confermarlo di nuovo per archiviare un'altra versione del contratto di vendita nello storico.  

Se non si conferma un contratto di vendita, è comunque possibile utilizzarlo per creare ordini cliente. Tuttavia, le informazioni sullo storico per il contratto di vendita non vengono archiviate.  

È possibile visualizzare in anteprima o stampare tutte le revisioni delle conferme. È possibile quindi condividere le revisioni con il cliente per ottenere l'approvazione.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Applicazione di contratti di vendita nel processo di ordinazione
Se gli ordini clienti non vengono rilasciati direttamente per un contratto di vendita, è comunque possibile collegare un contratto di vendita a un ordine durante il processo di registrazione dell'ordine. Quando si crea un nuovo ordine cliente e si seleziona un contratto di vendita, le condizioni del contratto, ad esempio i termini di pagamento, termini di consegna e l'indirizzo di consegna, vengono applicati all'intestazione ordine e il collegamento tra il contratto e l'ordine viene creato. Quindi, nelle righe ordine, quando è possibile selezionare i prodotti e le categorie specificate nel contratto di vendita, i prezzi e gli sconti vengono copiati dal contratto. Lo stesso ordine cliente può includere sia le righe che non sono correlate a un contratto di vendita sia le righe con un impegno per un contratto di vendita.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Modifica degli ordini cliente collegati ai contratti di vendita
Se è stato creato (rilasciato) un ordine cliente a fronte di un contratto di vendita, è possibile modificare alcuni campi nelle righe di tale ordine cliente solo se si rimuove il collegamento alle righe del contratto di vendita associato. Nella tabella riportata di seguito sono elencati alcuni di questi campi.

| Campo                                                             | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Data di spedizione richiesta                                               | Se si modifica la data di spedizione richiesta con una data precedente al valore di **Data di validità** nella riga del contratto di vendita, è necessario rimuovere il collegamento alla riga del contratto di vendita prima di poter salvare la data di spedizione modificata. Se si modifica la data di spedizione richiesta con una data successiva al valore di **Data di scadenza** nella riga del contratto di vendita, è necessario rimuovere il collegamento alla riga del contratto di vendita prima di poter salvare la data di spedizione modificata. |
| Importo CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet | Se si modifica il valore di uno di questi campi e la casella di controllo **Prezzo e sconto fissi** è selezionata in una riga del contratto di vendita associato, una finestra di messaggio richiede di salvare la modifica: Fare clic su **Sì** per rimuovere il collegamento alla riga del contratto di vendita e ricalcolare il prezzo. Fare clic su **No** per rimuovere il collegamento alla riga del contratto di vendita senza ricalcolare il prezzo.                                                                   |
| Importo netto                                                        | Se si specifica un importo che supera quello indicato in una riga del contratto di vendita in cui è selezionata la casella di controllo **Valore massimo applicato**, una finestra di messaggio richiede di salvare l'importo modificato. Fare clic su **Sì** per rimuovere il collegamento alla riga del contratto di vendita e ricalcolare il prezzo. Fare clic su **No** per rimuovere il collegamento alla riga del contratto di vendita senza ricalcolare il prezzo.                                                                 |
| Quantità                                                          | Se si specifica una quantità che supera quella indicata in una riga del contratto di vendita in cui è selezionata la casella di controllo **Valore massimo applicato**, una finestra di messaggio richiede di salvare la quantità modificata. Fare clic su **Sì** per rimuovere il collegamento alla riga del contratto di vendita e ricalcolare il prezzo. Fare clic su **No** per rimuovere il collegamento alla riga del contratto di vendita senza ricalcolare il prezzo.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Restituzione di un articolo ordinato da un contratto di vendita
Quando un cliente restituisce un prodotto ordinato da un contratto di vendita, Supply Chain Management può trovare e aggiornare automaticamente l'impegno del contratto di vendita correlato per riflettere la modifica nella quantità o nell'importo. Creando un ordine di reso in base all'ordine cliente originario che è collegato a un contratto di vendita, si stabilisce una relazione tra l'impegno del contratto di vendita, la riga ordine cliente e la fattura di ordine di reso.  

Se non si desidera detrarre la quantità di reso dall'impegno del contratto di vendita, è possibile utilizzare il controllo **Rimuovi collegamento** nella pagina **Ordine di reso** per rimuovere il collegamento tra l'ordine di reso e l'impegno del contratto di vendita. Se è necessario ristabilire successivamente il collegamento, fare clic su **Crea collegamento**.  

**Nota:** Un ordine di reso può essere collegato a un solo contratto di vendita. Se il cliente restituisce più di un prodotto ordinato da più di un contratto di vendita, è necessario creare un nuovo ordine di reso per ogni prodotto e creare un collegamento al contratto di vendita corrispondente.

## <a name="automatic-search-for-sales-agreements"></a>Ricerca automatica dei contratti di vendita
In alcune situazioni in cui gli ordini cliente vengono creati indirettamente, ad esempio quando si crea una nota di accredito o ordini cliente interaziendali, è possibile definire se il sistema deve cercare automaticamente i contratti di vendita applicabili.

## <a name="financial-dimensions-on-sales-agreements"></a>Dimensioni finanziarie nei contratti di vendita
È possibile copiare le dimensioni finanziarie in intestazioni documento o in singole righe di un contratto di vendita. È possibile modificare le dimensioni nell'intestazione o in una riga del contratto in qualsiasi momento. In questo caso, le dimensioni vengono automaticamente copiate nell'intestazione di rilascio o nella riga di rilascio degli ordini di rilascio.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]