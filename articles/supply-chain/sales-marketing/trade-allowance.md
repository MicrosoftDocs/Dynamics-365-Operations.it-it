---
title: Gestione sconto commerciale
description: Questo argomento descrive la gestione dello sconto commerciale per Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: MCRBrokerClaims, MCRBrokerWriteOffReasonPrompt, MCRRoyaltyVendTable, MCRRoyaltyVendTrans, PdsCustRebateGroup, PdsRebateAgreement, TAMCopyTradePromotions, TAMDeduction, TAMDeductionCreate, TAMDeductionDenyReason, TAMDeductionParmDeny, TAMDeductionParmMassUpdate, TAMDeductionParmMatch, TAMDeductionParmSplit, TAMDeductionParmWriteOff, TAMDeductionType, TAMDeductionWriteOffReason, TAMFundManagement, TAMFundUsage, TAMListPage, TAMMarketingObjective, TAMMerchEventType, TAMOneTimePromotion, TAMPromoCompareGraph, TAMPromoStatistic, TAMPromotionAnalysisSummary, TAMPromotionParameters, TAMPromotionPeriod, TAMTemplateListPage, TAMTradePromotionAnalysis, TAMTradePromotions, TAMWhatIfPromotionAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 15f324f66240380f698dbc67b95f3bea19314a18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974912"
---
# <a name="trade-allowance-management"></a>Gestione sconto commerciale

[!include [banner](../includes/banner.md)]

La gestione dello sconto commerciale aiuta le società a gestire i programmi di promozione delle vendite che offrono premi monetari basati sulla produttività ai clienti che raggiungono obiettivi comportamentali o di volume. Le funzionalità di questa caratteristica sono progettate per le società che si concentrano sui processi da promozione a profitto completi, dalla creazione del budget e l'allocazione del fondo per la promozione, all'impostazione del contratto di abbuoni, alla creazione e all'elaborazione dei reclami, all'elaborazione dei pagamenti, all'analisi dell'efficacia della promozione.


L'articolo offre una vasta panoramica della funzionalità di gestione dello sconto commerciale e consente di familiarizzare con il set tipico di attività previste nella gestione del programma di promozione delle vendite. Diversi tipi di utenti con responsabilità operative e decisionali utilizzano questa funzionalità per ottenere i rispettivi obiettivi:

- Assegnazione di fondi discrezionali ai conti selezionati e impostazione dei contratti di abbuoni commerciali per le promozioni, basati su note di accredito e pagamenti di somme forfettarie occasionali (per un servizio accettato)
- Esecuzione di contratti di promozione negoziati tramite le continue vendite e la generazione di note di accredito
- Calcolo, approvazione ed elaborazione delle note generate e passaggio alla contabilità clienti come detrazioni per la liquidazione dei pagamenti
- Riconciliazione del pagamento a breve termine del cliente con la detrazione dovuta
- Tracciabilità dell'utilizzo del fondo promozionale e valutazione della redditività e dell'efficacia del programma

## <a name="audience-and-purpose"></a>Destinatari e scopo

Le informazioni contenute in questo documento sono destinate ai decisori aziendali, ad esempio responsabili degli acquisti, responsabili finanziari e direttori amministrativi con le seguenti responsabilità:

- Budget di alto livello e allocazione dei fondi
- Pianificazione e analisi delle promozioni delle vendite
- Gestione del personale che elabora le note di accredito, esegue i pagamenti in base agli eventi commerciali e liquida i pagamenti a breve termine e le detrazioni

Le persone con questi ruoli sono alla ricerca di metodi per conseguire questi obiettivi:

- Migliore utilizzo dei fondi promozionali di marketing.
- Integrare in modo flessibile differenti tipi di programmi e abbuoni promozionali.
- Ridurre il carico e gli errori amministrativi associati al monitoraggio delle prestazioni promozionali e all'elaborazione delle attestazioni.
- Migliorare le previsioni di cassa accumulando passività future.
- Disporre di una base quantificata per le negoziazioni correnti e future con i clienti sulle promozioni.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Fondo promozionale e accordo con sconto commerciale

Un accordo con sconto commerciale è un programma di incentivi in cui vengono offerti premi monetari basati sulla produttività ai clienti che conseguono obiettivi di volume e/o obiettivi comportamentali specifici. I fondi promozionali sono spese a budget. In questo modo, è possibile acquisire campagne promozionali.

### <a name="promotional-fund"></a>Fondo promozionale

I fondi che vengono allocati agli accordi con sconto commerciale vengono registrati nella pagina **Fondi**. Per aprire la pagina **Fondi**, selezionare **Vendite e marketing** \> **Sconti commerciali** \> **Fondi** \> **Fondi**.

![Pagina dei fondi](./media/trade-allowance-management-funds-page.png "Pagina dei fondi")

Nella pagina **Fondi** è possibile visualizzare i dettagli dei fondi promozionali.

La Scheda dettaglio **Generale** mostra il periodo di validità del fondo e il relativo importo a budget. Per consentire l'allocazione del fondo all'accordo promozionale, il campo **Stato** deve essere impostato sul valore **Approvato**.

La Scheda dettaglio **Clienti** mostra la gerarchia dei clienti. Per selezionare i clienti a cui è destinato il fondo, trascinarli sotto **Fondi per clienti**. Questa Scheda dettaglio mostra anche la distribuzione dell'importo totale del fondo.

La Scheda dettaglio **Articoli** mostra gli articoli che sono inclusi nella promozione.

### <a name="trade-allowance-agreement"></a>Accordo con sconto commerciale

Dopo avere definito il fondo, il passaggio successivo nella pianificazione della promozione consiste nel registrare i contratti promozionali (noti come accordi con sconto commerciale), allocare i fondi e definire gli obiettivi di prestazioni per ogni evento commerciale.

Gli accordi con sconto promozionale vengono registrati nella pagina **Accordi con sconto commerciale**. Per aprire la pagina **Accordi con sconto commerciale**, selezionare **Vendite e marketing** \> **Sconti commerciali** \> **Accordi con sconto commerciale**.

![Pagina degli accordi con sconto commerciale](./media/trade-allowance-management-agreements-page.png "Pagina degli accordi con sconto commerciale")

#### <a name="header"></a>Intestazione

Selezionare **Intestazione** per passare alla visualizzazione intestazione.

Nella Scheda dettaglio **Generale**, i campi **Ordine a** e **Ordine da** definiscono il periodo di validità dell'accordo. Lo stato di approvazione **Approvazione interna** per l'accordo indica che l'accordo non è ancora valido e non può essere applicato durante l'elaborazione degli ordini cliente.

La sezione **Analisi** della Scheda dettaglio **Generale** contiene campi importanti che definiscono le quantità e i costi che vengono utilizzati per la valutazione della promozione:

- Il campo **Unità di base** specifica la quantità di prodotti che devono essere venduti ai clienti selezionati prima che la promozione venga applicata.
- Il valore di **Quantità di spedizione calcolata** viene calcolato in base al valore di **Percentuale lift**, che è un incentivo per raggiungimento obiettivi pianificato per questa promozione.
- Il campo **Costo sconto commerciale** viene calcolato in base alle quantità dei vari eventi nell'accordo con sconto commerciale.

Nella Scheda dettaglio **Clienti**, nell'elenco di sinistra è possibile selezionare e visualizzare gruppi di clienti che sono impostati come gerarchie predefinite. È possibile selezionare l'intera gerarchia o account specifici come destinatari dell'accordo con sconto commerciale.

Nella Scheda dettaglio **Articoli**, come nella Scheda dettaglio **Articoli** della pagina **Fondi**, i prodotti vengono aggiunti all'accordo per associare le vendite allo sconto concordato.

Nella Scheda dettaglio **Fondi** è possibile visualizzare i fondi promozionali che sono associati all'accordo. È inoltre possibile visualizzare l'allocazione dei costi dell'evento dell'accordo. Un'allocazione dei costi dell'evento del 100% indica che questa promozione sarà finanziata esclusivamente da un unico fondo. In alternativa, un accordo promozionale può utilizzare più fondi e può utilizzare l'allocazione di percentuale uguale o differenziale.

#### <a name="lines"></a>Righe

Al termine, scegliere **Righe** per passare alla visualizzazione Righe.

Nella scheda **Eventi merchandising** vengono visualizzati i tipi di eventi coperti da un accordo. Sono disponibili tre tipi: nota di accredito, somma forfettaria e sconto temporaneo in fattura.

Quando si seleziona un evento di merchandising e quindi si seleziona la scheda **Importi**, i dettagli dell'evento vengono rilevati.

![Righe accordo con sconto commerciale](./media/trade-allowance-management-agreements-lines.png "Righe accordo con sconto commerciale")

Nella sezione **Righe sconto commerciale** si specificano gli intervalli di quantità o importi che il cliente deve raggiungere per definizioni per ottenere gli sconti.

Nel caso di un evento di merchandising di tipo **Nota di accredito**, la sezione superiore della scheda **Importi** definisce le regole con cui la nota di accredito sarà applicata, generata e pagata. Ad esempio, le regole possono specificare i seguenti termini per la nota di accredito:

- Sono in base alla data di creazione dell'ordine cliente (il valore **Tipo di data di calcolo** è **Creato**).
- Viene calcolata in base all'importo prima degli sconti, non l'importo netto della riga ordine cliente, compresi gli sconti (il valore **Origine** è **Lordo**).
- È in base al volume dei prodotti venduti, non all'importo (il valore **Tipo di interruzione riga sconto** è **Quantità**).
- Viene calcolata per periodo di un mese (il valore **Cumula vendite per** è **Mese**). 
- Viene liquidata come detrazione, non usando la contabilità fornitori (il valore **Tipo di pagamento** è **Detrazioni cliente**).

Nel caso di un evento di merchandising di tipo **Somma forfettaria**, la scheda **Importi** mostra la quantità che verrà pagata al cliente sotto forma di detrazione quando il cliente raggiunge le prestazioni specifiche. Uno stato di approvazione **Aperto** indica che la somma forfettaria non è ancora stata pagata.

Per applicare l'accordo agli ordini cliente che soddisfano le condizioni, lo stato del contratto deve essere **Confermato**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Eseguire le vendite nell'evento di merchandising pianificato e generare note di accredito

Quando si crea un ordine cliente con righe che soddisfano i requisiti dell'accordo, è possibile visualizzare le informazioni correlati nella pagina **Ordine cliente** selezionando **Riga ordine cliente** \> **Visualizza** \> **Dettagli prezzo**.

Nella pagina **Dettagli prezzo**, nella scheda dettaglio **Sconti** l'addetto vendite può vedere una nota di accredito di un accordo con sconto commerciale valido (l'ID del programma di sconti è visibile) e l'importo totale che viene applicato alla riga. Questo importo viene mostrato nel campo **Importo sconto** nella sezione **Stima margine** della pagina **Dettagli prezzo**.

Quando la fattura di vendita viene registrata, viene generata una nota di accredito corrispondente per ogni riga di fattura.

> [!NOTE]
> Per vedere la pagina **Dettagli prezzo**, nella pagina **Parametri contabilità clienti**, nella scheda **Prezzi** selezionare la casella di controllo **Abilita dettagli prezzo**. b

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Elaborare le note di accredito e passarle come detrazioni alla contabilità fornitori

I passaggi successivi nel processo di gestione delle note di accredito consistono nell'esaminare, calcolare e approvare le note e convertirle in detrazioni.

Il workbench note di accredito è dove il titolare dell'accordo per la promozione esamina ed elabora periodicamente le note di accredito generate. È anche dove l'amministratore della contabilità fornitori converte le note di accredito approvate in detrazioni o pagamenti regolari, a seconda del metodo di pagamento della nota.

Nella pagina **Workbench note di accredito** è possibile esaminare le righe di nota. Se le note sono nello stato **Da ricalcolare**, devono essere ricalcolate per qualsiasi effetto cumulativo.

### <a name="recalculate-claims"></a>Ricalcolare le note

Per ricalcolare le note, nel riquadro azioni selezionare **Cumula**. Nella finestra di dialogo **Cumula sconti** selezionare quindi il cliente.

A seguito del ricalcolo, il programma genera nuove note per gli importi per rettificare le note originali all'importo per unità idoneo. Una richiesta di rettifica viene generata per ogni combinazione univoca di un cliente, un articolo, una valuta, un'unità di misura, dimensioni inventariali, dimensioni finanziarie e una fascia IVA. Tali richieste di rettifica hanno lo stesso riferimento al numero di fattura e dell'ordine cliente delle richieste da rettificare (ovvero le note originariamente create dal documento di vendita). A differenza della richiesta originale, la richiesta di rettifica non ha valori nei campi che descrivono gli importi e la quantità della riga dell'ordine cliente originale.

Dopo il ricalcolo, lo stato delle note viene modificato in **Calcolato**. Per approvare le note, nel riquadro azioni, selezionare **Approva**.

### <a name="process-claims-and-pass-them-to-ar"></a>Elaborare le note di accredito e passarle alla contabilità fornitori

Le note sono ora pronte per l'elaborazione nella contabilità fornitori. Per elaborarle, nel riquadro azioni, selezionare **Elabora**. 

Durante l'elaborazione delle note, lo stato è passato a **Contrassegna** e indica che una registrazione del giornale (il giornale in cui viene eseguita la registrazione è il Giornale di registrazione ratei sconto, come specificato nei parametri della contabilità fornitori) ha causato i seguenti eventi: 

- Le note sono state trasferite nel saldo temporaneo del cliente come detrazioni.
- Sul conto di attribuzione per competenza dello sconto è stato effettuato l'accredito per passività futura verso il cliente.
- È stato effettuato l'addebito sul conto spese dello sconto, nel rispetto del costo sostenuto in relazione alle vendite.

Per completare il processo, l'addetto alla contabilità fornitori deve ora gestire le detrazioni trasferendoli nel saldo cliente come nota di accredito (passività). 

Per avviare l'attività, nel riquadro azioni della pagina **Cliente**, selezionare **Raccogli** \> **Liquida transazioni**. Nella pagina **Liquida transazioni** selezionare quindi **Funzioni** \> **Programma note di accredito**. Questa pagina di sconto mostra tutte le note di accredito precedentemente elaborate.

Se si vuole creare una nota di accredito, selezionare la casella di controllo **Contrassegna** per tutte le righe e quindi selezionare **Funzioni** \> **Crea nota di accredito**.

Dopo la creazione di una nota di accredito, viene registrato un giornale. Il giornale in cui viene eseguita la registrazione e il Giornale di registrazione consumo contabilità clienti, come specificato nei parametri della contabilità fornitori. L'importo di passività reale (credito) è stato quindi spostato nel saldo cliente. Dal punto di vista finanziario, questa situazione implica che si sono verificati gli eventi seguenti:

- È stata accreditata la contabilità clienti del cliente.
- È stato addebitato il conto di attribuzione per competenza dello sconto.

Per approvare un evento di merchandising di tipo **Somma forfettaria**, selezionare l'evento nella pagina **Accordi con sconto commerciale** e quindi nella scheda **Importo** selezionare **Approva**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Liquidare la detrazione dovuta e il pagamento e breve termine del cliente utilizzando il workbench detrazione

Spesso in previsione di note di accredito i clienti scelgono di eseguire il pagare a breve termine le fatture selezionate. Per evitare problemi di riconciliazione dei pagamenti in futuro, l'addetto della contabilità fornitori registra questi pagamenti a breve termine come detrazioni quando registra i pagamenti effettivi del cliente. Quindi nel workbench detrazione queste detrazioni del cliente possono facilmente essere liquidate per gli importi delle note di credito dovuti dalla società.

Per registrare un pagamento a breve termine di un cliente nel giornale di registrazione pagamenti, selezionare **Contabilità clienti** \> **Pagamenti** \> **Giornale di registrazione pagamenti** e creare un nuovo giornale di registrazione pagamenti. Nel riquadro azioni seleziona quindi **Detrazioni**. Nella pagina **Detrazione** è possibile creare e tenere traccia dell'importo che è stato pagato a breve termine.

Il responsabile della raccolta è ora responsabile della liquidazione della transazione di nota di accredito aperta e della transazione del pagamento a breve termine reciproci nel workbench detrazione.

Per gestire le detrazioni, selezionare **Vendite e marketing** \> **Sconti commerciali** \> **Detrazioni** \> **Workbench detrazione**. La sezione superiore della pagina contiene righe che rappresentano i pagamenti a breve termine dal cliente. La sezione inferiore della pagina contiene le transazioni di credito aperte del cliente. 

Per liquidare la detrazione per la transazione aperta, contrassegnare la riga della detrazione e quindi nella scheda Transazioni aperte contrassegnare la riga. Nel riquadro azioni fare clic su Gestisci > Associa.

Lo stato delle note originarie è ora impostato su **Completato**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analizzare l'efficienza della promozione e il consumo dei fondi

Per ottenere una panoramica delle statistiche chiave del programma e dell'utilizzo dei fondi, è possibile utilizzare più report e visualizzazioni analitiche disponibili in Gestione sconto commerciale.

Nella pagina **Attività sconto commerciale** nella scheda **Panoramica** vengono visualizzati i dettagli principali dell'accordo con sconto commerciale. Le altre schede mostrano i dettagli più specifici sui documenti associati, i pagamenti e altri eventi correlati al programma.

La scheda **Riepilogo** visualizza la quantità totale di prodotti venduti nella promozione, l'importo vendite fatturato e le note di accredito e le somme forfettarie pagate.

La scheda **Crediti note di accredito** contiene i dettagli delle note di accredito singole che sono state accreditate al cliente.

Per ottenere una panoramica più analitica delle varie misurazioni delle prestazioni per la promozione, è possibile utilizzare la visualizzazione di analisi. Per passare alla visualizzazione analisi, fare clic su **Vendite e marketing** \> **Sconti commerciali** \> **Accordi con sconto commerciale**. Nel riquadro azioni, fare clic su **Analisi**.  

Per ottenere una panoramica più analitica delle varie misurazioni delle prestazioni per la promozione, è possibile utilizzare la visualizzazione di analisi. Per passare alla visualizzazione analisi, fare clic su **Vendite e marketing** \> **Sconti commerciali** \> **Accordi con sconto commerciale**. Nel riquadro azioni, fare clic su **Analisi**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]