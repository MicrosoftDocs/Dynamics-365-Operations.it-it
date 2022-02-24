---
title: Generare ed elaborare sconti cliente
description: Questa procedura mostra come elaborare gli sconti dalla creazione della richiesta al punto di passarli come ratei alla Contabilità clienti.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8ebc281036842bdc8965e062990438e1fb466ff
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431275"
---
# <a name="generate-and-process-customer-rebates"></a>Generare ed elaborare sconti cliente

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come elaborare gli sconti dalla creazione della richiesta al punto di passarli come ratei alla Contabilità clienti. Utilizza un esempio specifico per spiegare come le diverse condizioni nelle righe dello sconto influiscono sugli importi finali che verranno accreditati al cliente. È necessario utilizzare la società di dati demo USMF e svolgere le seguenti attività prima di iniziare la guida: (1) andare alla pagina dei parametri Contabilità clienti ed espandere la scheda Prezzi, quindi la scheda Dettagli prezzo e controllare che l'opzione Abilita dettagli prezzo sia impostata su Sì. (2) Andate alla pagina Accordi sugli sconti e selezionare l'accordo sugli sconti del cliente: USMF-000001. Se il campo Stato di approvazione flusso di lavoro non è impostato su Approvato, devi fare clic su Convalida nel riquadro azioni per approvarlo.


## <a name="review-a-customer-rebate-agreement"></a>Rivedere un accordo sugli sconti cliente
1. Passare a **Pannello di navigazione > Moduli > Vendite e marketing > Riduzioni cliente > Accordi sugli sconti**.
    - I passaggi successivi analizzano le condizioni del contratto USMF-000001. In questo modo si rende più semplice comprendere come i valori di credito del cliente vengano calcolati in un secondo momento della procedura.  
    - L'accordo è per un singolo cliente, in questo esempio il cliente US-009.  
    - Gli sconti vengono forniti al cliente quando acquista un prodotto specifico. In questo caso, il prodotto ha il numero di articolo T0020.   
    - Le prestazioni di vendita del cliente, a fronte delle quali viene calcolato lo sconto totale, devono essere accumulate su base settimanale.  
    - L'impostazione del "Prezzo ricavato da" è Lordo, pertanto non viene applicata la riduzione dello sconto riga all'importo vendite della riga in base al quale viene stimata la richiesta.  
    - Nel campo Tipo di interruzione riga sconto viene visualizzato il metodo per il calcolo degli sconti. In questo caso, l'obiettivo di vendita in base al quale devono essere stimati gli sconti è impostato su Quantità.   
    - Le righe del contratto specificano il tipo di importo dello sconto, il valore effettivo dello sconto e le soglie. In questo esempio, il cliente si qualificherà per uno sconto di 20 EUR per unità venduta, se gli acquisti settimanali del prodotto rientrano in 1 - 50 unità e uno sconto di 40 EUR per unità venduta, se acquista più di 50 unità.  
2. Chiudere la pagina.

## <a name="generate-rebate-claims"></a>Generare le richieste di sconto
1. Andare a **Pannello di navigazione > Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Fare clic su **Nuovo**. Per riprodurre la modalità in cui saranno generate le richieste di sconto, l'attività successiva è di creare un ordine cliente, in cui il prodotto e la quantità qualificheranno il cliente in questione per uno sconto.    
3. Nel campo **Conto cliente**, immettere o selezionare un valore.
4. Fare clic su **OK**.
5. Nel campo **Numero articolo** immettere o selezionare un valore.
6. Impostare **Quantità** su '40'.
7. Sotto la sezione **Righe ordine cliente** fare clic su **Riga ordine cliente**.
8. Fare clic su **Dettagli prezzo**. Se non si vede questa opzione, è poiché l'opzione **Abilita dettagli prezzo** non è impostata su "Sì" prima di avere avviato la guida.     
9. Espandere la sezione **Sconti**. Nella scheda **Sconti** sono elencati tutti gli accordi sugli sconti che sono applicabili alla riga ordine corrente e viene visualizzato l'importo stimato dello sconto. Si noti che gli importi visualizzati sono solo indicazioni di quelle che potrebbero essere le richieste future di sconto. Gli importi effettivi dello sconto possono essere diversi a seconda del volume di vendita totale raggiunto dal cliente ai sensi di un accordo sugli sconti periodico, se il cliente aveva restituito quantità totali o parziali e se l'ordine cliente applicabile era stato fatturato.
10. Chiudere la pagina.
11. Fare clic su **Aggiungi riga**.
12. Nel campo **Numero articolo** immettere o selezionare un valore.
13. Impostare **Quantità** su '60'.
14. Fare clic su **Salva**.
15. Nel **riquadro azioni** fare clic su **Fattura**.
16. Fare clic su **Fattura**.
17. Espandere la sezione **Parametri**.
18. Nel campo **Quantità** selezionare "Tutto".
19. Fare clic su **OK**.
20. Fare clic su **OK**.

## <a name="process-rebate-claims"></a>Elaborare le attestazioni di sconto
1. Passare a **Pannello di navigazione > Moduli > Vendite e marketing > Riduzioni cliente > Sconti**.
    - La pagina degli sconti funge da workbench in cui è possibile esaminare, approvare ed elaborare richieste di sconto. Ora verranno elaborate le richieste create in seguito alla fatturazione dell'ordine cliente US-009, che è l'oggetto dell'accordo sugli sconti USMF-000001.   
    - La prima riga rappresenta una richiesta di sconto per 800 EUR, basata sulla vendita di 40 unità di prodotto T0020, calcolate a 20 EUR per unità. Questo corrisponde alle condizioni del primo intervallo di quantità nell'accordo sugli sconti.  
    - La seconda richiesta è di 2.400 EUR, a fronte delle vendite di 60 unità di prodotto T0020, calcolate a 40 EUR per unità, in base alla seconda interruzione di quantità dell'accordo.  
    - Entrambe le richieste sono nello stato "da calcolare". Ciò significa che sono associate a un accordo che tiene traccia delle prestazioni di vendita del cliente su base periodica e che devono essere ricalcolate per rappresentare il volume di vendita totale nel rispettivo periodo.   
2. Fare clic su **Cumula**.
3. Nel campo **Cliente** immettere o selezionare un valore.
4. Nel campo **Data di inizio** selezionare la data odierna.
5. Fare clic su **OK**. In seguito all'esecuzione della funzione **Cumula**, l'importo stimato della richiesta è stato rettificato per rappresentare il fatto che il volume di vendita totale del cliente nel periodo rilevante è superiore a quando il primo sconto è stato generato. In modo più specifico, poiché la quantità totale acquistata ha raggiunto 100 unità, il cliente ora si qualifica per 40 EUR per unità (in base alla seconda interruzione di quantità dell'accordo) o per 400 EUR dell'importo totale dello sconto. La differenza verrà registrata come una nuova “rettifica” della richiesta per 800 EUR aggiuntivi. Lo stato delle richieste dello sconto incluse nell'aggiornamento Cumula ora è impostato su Calcolato. 
6. Nell'elenco selezionare tutte le righe.
7. Fare clic su **Approva**.
8. Fare clic su **Elabora**.
9. Nel campo **Cliente** immettere o selezionare un valore.
10. Fare clic su **OK**. Un messaggio indica che lo sconto è stato elaborato correttamente e lo stato delle richieste è stato modificato in Contrassegna. Ciò significa che, a seguito della registrazione di un giornale di registrazione ratei sconto:
    - Le note sono ora state trasferite nel saldo temporaneo del cliente come detrazioni.
    - Sul conto di attribuzione per competenza dello sconto è stato effettuato l'accredito per passività futura verso il cliente.
    - È stato effettuato l'addebito sul conto spese dello sconto, nel rispetto del costo sostenuto in relazione alle vendite.   

