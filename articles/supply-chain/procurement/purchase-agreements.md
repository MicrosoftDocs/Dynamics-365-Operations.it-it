---
title: Contratti di acquisto
description: Questo articolo fornisce informazioni sui contratti di acquisto. Un contratto di acquisto è un contratto con cui un'organizzazione si impegna ad acquistare una quantità o un importo specificato utilizzando più ordini fornitore nel tempo. In cambio dell'impegno, l'acquirente riceve prezzi e sconti speciali.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, AgreementLine, AgreementLinePrompt, PurchAgreement, PurchAgreementCreate, PurchAgreementGenerateReleaseOrder, PurchAgreementHistory, PurchAgreementInvoiceJournal, PurchLine, AgreementLines
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11634
ms.assetid: 8ac20adf-7412-4929-be8c-aaedf23a76ad
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9d97461efb39154e1e9b63c20669985aad349d0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247768"
---
# <a name="purchase-agreements"></a>Contratti di acquisto

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui contratti di acquisto. Un contratto di acquisto è un contratto con cui un'organizzazione si impegna ad acquistare una quantità o un importo specificato utilizzando più ordini fornitore nel tempo. In cambio dell'impegno, l'acquirente riceve prezzi e sconti speciali. 

I contratti di acquisto possono essere applicati a una specifica quantità di un prodotto, a un importo in valuta specifico di un prodotto o a un importo in valuta specifico dei prodotti in una categoria di approvvigionamento. I prezzi e gli sconti del contratto di acquisto sostituiscono i prezzi e gli sconti specificati in eventuali contratti commerciali esistenti.  

Nella pagina **Contratti di acquisto** è possibile creare, applicare e controllare i contratti di acquisto esistenti tra l'organizzazione e i relativi fornitori. Ad esempio, una volta creato un contratto di acquisto, è possibile effettuare un ordine direttamente da tale contratto. Ogni contratto di acquisto ha un periodo di validità definito dalla persona che crea il contratto. La data di consegna di un acquisto deve essere compresa nelle date effettive del periodo di validità.  

Dopo avere creato un contratto di acquisto, è necessario attivarlo prima che entri in vigore. Per attivare un contratto di acquisto, impostare l'opzione **Contrassegna contratto come valido** su **Sì**. 

Per impedire che il contratto di acquisto venga utilizzato e confermato, contrassegnare lo stato del contratto come **Chiuso**. È comunque possibile aggiornare lo stato a **Valido** in qualsiasi momento dopo aver apportato questa modifica.

## <a name="responsible-workers-on-purchase-agreements"></a>Lavoratori responsabili dei contratti di acquisto

È possibile identificare un lavoratore responsabile principale e un lavoratore responsabile secondario nella classificazione del contratto di acquisto. Questi valori saranno ereditati dal contratto di acquisto risultante. Non è obbligatorio aggiungere lavoratori responsabili al contratto di acquisto e possono essere modificati direttamente caso per caso sul contratto di acquisto stesso. Non è possibile specificare un lavoratore responsabile secondario senza un lavoratore responsabile primario, sebbene non sia necessario disporre di un lavoratore responsabile secondario. Non è possibile specificare lo stesso lavoratore come lavoratore responsabile principale e secondario.

> [!IMPORTANT]
> Prima di poter utilizzare la funzionalità della parte responsabile, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:
> 
> - **Modulo:** *Attività di approvvigionamento*
> - **Nome funzionalità:** *Parte responsabile del contratto di acquisto*

## <a name="commitment-types"></a>Tipi di impegno
Ogni riga di un contratto di acquisto è un impegno di acquisto di un prodotto. È possibile utilizzare righe di più ordini fornitore (PO) per evadere l'impegno. Sono disponibili quattro tipi di impegni:

-   **Impegno quantità prodotto**: si acquista una quantità specifica di un prodotto.
-   **Impegno valore prodotto**: si acquista un importo valuta specifico di un prodotto.
-   **Impegno valore categoria prodotto**: si acquista un importo valuta specifico in una categoria di approvvigionamento. L'importo può riguardare un articolo in catalogo o fuori catalogo.
-   **Impegno valore**: si acquista un importo in valuta specifico di qualsiasi prodotto o prodotti in qualsiasi categoria di approvvigionamento.

## <a name="pricing-terms-for-purchase-agreements"></a>Termini per la determinazione del prezzo dei contratti di acquisto
I termini per la determinazione del prezzo possono variare a seconda del tipo di impegno. I termini per la determinazione del prezzo dei contratti di acquisto sostituiscono tutti gli altri termini per la determinazione del prezzo impostati per gli accordi commerciali. Nella seguente tabella vengono descritti i campi relativi al prezzo interessati da ciascun tipo di impegno. I campi contenenti **Sì** possono essere aggiornati in una riga ordine.

| Tipo di impegno                   | Prezzo unitario | Unità di prezzo | Percentuale sconto | Importo sconto di cassa |
|-----------------------------------|------------|------------|------------------|----------------------|
| Impegno quantità prodotto       | Sì        | Sì        | Sì              | Sì                  |
| Impegno valore prodotto          |            |            | Sì              |                      |
| Impegno valore categoria prodotto |            |            | Sì              |                      |
| Impegno valore                  |            |            | Sì              |                      |

## <a name="policies-for-purchase-agreements"></a>Criteri dei contratti di acquisto
I criteri seguenti influiscono sulla modalità di collegamento tra un impegno del contratto di acquisto e le righe corrispondenti dell'ordine acquisto:

-   **Valore massimo applicato** - La quantità o l'importo totale per tutte le righe ordine non può superare la quantità o l'importo specificato nell'impegno correlato.
-   **Prezzo e sconto fissi** – Il prezzo in un riga ordine e il prezzo dell'impegno correlato devono essere uguali. Se il prezzo viene modificato nella riga ordine, il collegamento all'impegno viene interrotto. In questo caso, la riga ordine non contribuisce all'evasione dell'impegno.
-   **Importo minimo rilascio e Importo massimo rilascio**  - Se un importo viene specificato, viene visualizzato un messaggio se si apporta una modifica a una riga ordine rendendola diversa dall'impegno correlato.

## <a name="fulfillment-calculations-for-purchase-agreements"></a>Calcoli relativi all'adempimento dei contratti di acquisto
La scheda **Evasione** della Scheda dettaglio **Dettagli riga** nella pagina **Contratti di acquisto** mostra le quantità e gli importi di evasione.  

È inoltre possibile visualizzare la quantità o l'importo rimanente necessario per evadere l'impegno nell'area **Evasione**.  

L'area **Contratto** indica la quantità totale o l'importo totale per cui la riga del contratto di vendita è valida.  

È possibile accedere alle righe di ORDINE FORNITORE e alle righe di fattura che contribuiscono al calcolo di evasione selezionando l'azione **Informazioni correlate** sulle righe o sull'intestazione di un contratto di acquisto.

## <a name="confirmations-and-version-history-for-purchase-agreements"></a>Conferme e storico della versione per i contratti di acquisto
Quando si conferma un contratto di acquisto, la versione corrente del contratto viene archiviata in una tabella dello storico. Se si modifica il contratto di acquisto, è possibile confermarlo di nuovo per archiviare un'altra versione del contratto di acquisto nello storico. Se non si conferma un contratto di acquisto, è comunque possibile utilizzarlo per creare ordini fornitore. Tuttavia, le informazioni sullo storico per il contratto di acquisto non vengono archiviate. È possibile visualizzare in anteprima o stampare tutte le versioni dell'accordo. È possibile quindi condividere le revisioni con il fornitore per ottenere l'approvazione.

## <a name="applying-purchase-agreements-in-the-ordering-process"></a>Applicazione di contratti di acquisto nel processo di ordinazione
Quando si crea un ORDINE FORNITORE, è possibile applicarvi un contratto di acquisto. Le informazioni dei termini del contratto, ad esempio termini di pagamento, termini di consegna e indirizzo di consegna, vengono copiate nell'intestazione del PO. Se il PO contiene una o più righe che si riferiscono a prodotti e categorie specificati nel contratto, per tali righe vengono utilizzati i prezzi e gli sconti del contratto di acquisto. L'importo o la quantità nella riga ordine contribuiscono all'evasione dell'impegno nel contratto di acquisto. Lo stesso PO può includere sia le righe che non sono correlate a un contratto di acquisto sia le righe con un impegno per un contratto di acquisto.  

È possibile selezionare un contratto di acquisto solo quando si crea un ORDINE FORNITORE. Non è possibile selezionare un contratto di acquisto dopo che il PO è stato creato.  
In alcune situazioni in cui gli ordini acquisto vengono creati indirettamente, è possibile stabilire se in Supply Chain Management deve essere eseguita la ricerca automatica dei contratti di acquisto applicabili, ad esempio è possibile effettuare questa operazione quando si esegue la stabilizzazione automatica degli ordini fornitore pianificati o si creano ordini fornitore basati su ordini cliente.

## <a name="matching-policy-on-purchase-agreements"></a>Criteri di abbinamento dei contratti di acquisto
È possibile definire i criteri di abbinamento riga nell'intestazione del contratto di acquisto. Questi criteri di abbinamento riga rispettano i parametri della contabilità fornitori quando il campo **Consenti di ignorare i criteri di abbinamento** della pagina **Parametri contabilità fornitori** (scheda dettaglio **Abbinamento prezzo e quantità** ) è impostato **Superiore ai criteri società**. I documenti che fanno riferimento al contratto di acquisto utilizzano i criteri di abbinamento riga definiti nell'intestazione del contratto di acquisto a meno che altrimenti definito nei corrispondenti criteri di acquisto per l'articolo, l'articolo e il fornitore o la categoria.

## <a name="purchase-agreements-and-intercompany-trade"></a>Contratti di acquisto e commercio interaziendale
Le relazioni commerciali interaziendali possono essere create tra conti fornitore e conti cliente in persone giuridiche diverse. Quando un ordine cliente o un ordine fornitore viene creato per una delle parti, viene creata una catena di ordini interaziendali. Nella catena di ordini, l'ordine cliente e l'ordine fornitore vengono creati nelle persone giuridiche competenti.  

È possibile creare un contratto di acquisto o un contratto di vendita per una delle parti commerciali interaziendali. È quindi possibile generare il contratto di vendita o il contratto di acquisto corrispondente per l'altra parte commerciale interaziendale nell'altra persona giuridica.  

Se si crea un ordine fornitore interaziendale che utilizza il contratto di acquisto interaziendale in una persona giuridica, l'ordine cliente interaziendale corrispondente utilizza il contratto di vendita interaziendale corrispondente nell'altra persona giuridica. L'evasione degli impegni dei contratti di vendita e l'adempimento dei contratti di acquisto sono sincronizzate, così come sono sincronizzati l'ordine cliente interaziendale e l'ordine fornitore interaziendale.

## <a name="financial-dimensions-on-purchase-agreements"></a>Dimensioni finanziare nei contratti di acquisto
È possibile copiare le dimensioni finanziarie in intestazioni documento o in singole righe di un contratto di acquisto. Se si modificano le dimensioni nell'intestazione del contratto o nella riga del contratto, la modifica non influisce sugli ordini rilasciati, ma verrà considerata in tutti i nuovi ordini.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Creare un contratto di acquisto](tasks/create-purchase-agreement.md)

[Creare un ordine fornitore di rilascio da un contratto di acquisto](tasks/create-purchase-release-order-purchase-agreement.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]