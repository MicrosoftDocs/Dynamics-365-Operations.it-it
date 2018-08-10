---
title: "Conto lavoro basato su attività"
description: "In questo argomento viene descritto in dettaglio come utilizzare le attività in conto lavoro in un flusso di produzione per il lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 59b41b31931a128898ee70a583bfb9c515f90abc
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="activity-based-subcontracting"></a>Conto lavoro basato su attività

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto in dettaglio come utilizzare le attività in conto lavoro in un flusso di produzione per il lean manufacturing.

In Microsoft Dynamics 365 for Finance and Operations sono presenti due approcci per il conto lavoro: ordini di produzione e lean manufacturing. Nell'approccio lean manufacturing, il lavoro in conto lavoro è modellizzato come servizio correlato a un'attività del flusso di produzione. Un tipo speciale di tipo di gruppo di costi denominato **Esternalizzazione diretta** è stato introdotto e i servizi in conto lavoro non fanno più parte di una distinta base (DBA). La contabilità industriale di lavoro in conto lavoro è completamente integrata nella soluzione di determinazione costi per il lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Flussi di produzione che includono terzisti
Il principio di base di un flusso di produzione non cambia quando le attività sono in conto lavoro. Il materiale ancora si sposta tra ubicazioni, le attività di processo convertono il materiale in prodotti e le attività di trasferimento spostano il materiale o i prodotti da un'ubicazione a un'altra. È possibile modellare le ubicazioni e le celle di lavoro come gestire dal fornitore assegnando il conto fornitore a un magazzino o a una risorsa di un gruppo di risorse.  

In base a queste funzionalità, il lean manufacturing non richiede caratteristiche specifiche per supportare il flusso di materiale e prodotti. Tutti gli scenari possibili che coinvolgono fornitori come fornitori di servizi di trasporto o di produzione possono essere modellati in base all'architettura del flusso di produzione e delle attività.  

Ad esempio, un terzista lavora in un'area di deposito con sede presso il terzista. Quando le unità movimentazione vengono svuotate presso il terzista, le schede kanban vengono restituite alla cella di assembly con la spedizione successiva. L'area di deposito presso il terzista viene quindi rifornita. I trasferimenti verso e dal terzista possono essere modellati come attività di trasferimento esplicite per supportare un processo di prelievo e spedizione. Se una registrazione esplicita non è obbligatoria per supportare il trasporto fisico, le attività di trasferimento possono essere omesse.  

Un terzista può essere utilizzato per bilanciare il carico della capacità complessiva del flusso di produzione. Ad esempio, un flusso di produzione è modellizzato utilizzando le regole kanban programmate. Il responsabile pianificazione utilizza la bacheca di programmazione kanban per programmare e caricare a livello entrambe le celle di lavoro a richiesta. Monitora inoltre la programmazione di fornitura consolidata per l'area di deposito nella pagina **Programmazione fornitura**. Più terzisti possono essere modellati in uno o più flussi di produzione e possono essere presenti più regole kanban che possono essere utilizzate per fornire lo stesso prodotto nella stessa ubicazione tramite diverse attività. Il responsabile pianificazione può convertire kanban in una regola kanban alternativa per riprogrammare un kanban originariamente creato per la produzione interna in un processo alternativo. Infatti, la natura in conto lavoro della cella di lavoro non ha effetto sul flusso di produzione. Lo stesso principio di esecuzione è valido per due celle di lavoro interne parallele o per due celle in conto lavoro.   

Come per qualsiasi altra attività di un flusso di produzione, le attività in conto lavoro possono utilizzare e fornire materiali e prodotti inventariati, non inventariati (semilavorati \[WIP\]) e semifiniti. In tutti i casi, i processi di programmazione ed esecuzione delle attività in conto lavoro sono uguali. Inoltre, questi hanno la stessa elaborazione dei processi di lavoro interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processo di acquisto per attività in conto lavoro (servizi)
Il processo di acquisto per attività in conto lavoro è basato sul flusso di materiale fisico registrato dallo stato del processo kanban, ad esempio, Inizio o Completo. Il flusso finanziario, ad esempio, costo di lavoro in conto lavoro, è un flusso secondario che segue il flusso fisico. Contemporaneamente, il processo di acquisto è un processo indipendente che consente rettifica manuale dei documenti di acquisto in corrispondenza di ciascun passaggio. Ecco il processo di acquisto per attività in conto lavoro:

1.  Creare un contratto di acquisto. Il contratto di acquisto viene creato per il servizio e collegato all'attività del flusso di produzione.
2.  Creare un ordine fornitore. Un ordine fornitore di rilascio può essere creato per il servizio, in base ai processi kanban programmati. I processi per lo stesso servizio possono essere raggruppati in righe ordine fornitore per giorno, settimana, o mese. Le righe ordine fornitore possono essere create in qualsiasi momento dopo i processi kanban vengono creati. Le righe ordine fornitore possono essere create anche successivamente al fatto. Questa opzione è selezionata in genere se un terzista fornisce servizi senza ulteriore preavviso, in base ai kanban o le schede kanban che riceve il terzista. In questo caso, gli scostamenti tra l'ordine fornitore e la fattura possono essere minimizzati.
3.  Generare le schede kanban, il materiale e una distinta di prelievo da inviare al terzista per preparare per l'elaborazione. In base alla modellizzazione dettagliata del flusso di produzione, la preparazione viene effettuata nella bacheca kanban per le attività di processo utilizzando la distinta di prelievo e la funzione di preparazione. In alternativa, la preparazione viene effettuata nella bacheca kanban per i processi di trasferimento utilizzando la distinta di prelievo e l'avvio o il completamento. Per il materiale inventariato, entrambi i processi possono essere supportati da un processo di prelievo e spedizione WMS. Una polizza di carico può essere creata a richiesta.
4.  Generare le unità movimentazione kanban e le schede kanban. Dopo l'elaborazione, le schede vengono restituite dal terzista. In genere, le schede includono una bolla di consegna che specifica il materiale fisico già spedito. Un riferimento ai servizi forniti non è obbligatorio. L'arrivo del materiale o di prodotti al cliente viene registrato nella bacheca kanban, a seconda delle schede kanban. (La bacheca kanban per le attività di processo o la bacheca kanban per i processi di trasferimento viene utilizzata, a seconda delle attività modellate).
5.  Creare un avviso di ricevimento. L'avviso di ricevimento può essere utilizzato per sostituire un documento di trasporto per i servizi ricevuti. Gli avvisi di ricevimento possono essere generati in base ai processi kanban completati dell'attività in conto lavoro per un periodo selezionato. Per ciascuna entrata processo, avvisi vengono creati per la riga di ordine fornitore correlata. L'avviso di ricevimento può essere stampato e inviato al terzista come conferma dell'entrata.
6.  Generare una fattura.

Il processo termina quando al terzista viene fatturato un periodo. L'abbinamento fattura viene effettuato in base agli avvisi di ricevimento creati. Poiché gli avvisi di ricevimento rappresentano l'entrata fisica esatta di materiale, l'abbinamento a tre elementi di verifica viene semplificato.

## <a name="configuring-activities-for-subcontracting"></a>Configurazione di attività per il conto lavoro
Nelle sezioni seguenti viene descritto come configurare attività per il conto lavoro.

### <a name="subcontracted-services"></a>Servizi in conto lavoro

L'articolo di pagamento utilizzato nel conto lavoro basato sulle attività deve essere un prodotto con le seguenti proprietà:

-   **Tipo di prodotto**: Servizio
-   **Gruppo di modelli inventariali:** non stoccato

Tale requisito forza l'utilizzo del modello inventariale FIFO. **Nota:** Il calcolo dei costi dei prodotti richiede che il costo standard del servizio sia definito. Un contratto di acquisto con il fornitore è obbligatorio. In caso contrario, il servizio non può essere utilizzato per il conto lavoro basato sull'attività.

### <a name="subcontracted-process-activities"></a>Attività di processo in conto lavoro

Per configurare un'attività di processo come attività in conto lavoro, effettuare le seguenti operazioni.

1.  Configurare una cella di lavoro in conto lavoro. Per configurare una cella di lavoro come in conto lavoro, è necessario creare una risorsa di tipo **Fornitore** e associarla alla cella di lavoro (gruppo di risorse). Una categoria di costi di runtime del tipo di gruppo di costi **Esternalizzazione diretta** deve essere assegnata alla cella di lavoro. Le categorie di costo per l'impostazione e la quantità non sono obbligatorie.
2.  Dopo che un'attività di processo è creata e correlata a una cella di lavoro in conto lavoro, è necessario configurare un servizio per l'attività prima che la versione del flusso di produzione possa essere attivata. Effettuare questo passaggio nella pagina **Dettagli** **attività**. Per le attività associate a una cella di lavoro in conto lavoro, viene visualizzata la Scheda dettaglio **Condizioni di servizio**. In questa Scheda dettaglio, aggiungere un servizio predefinito valido per tutti gli articoli in uscita. Se specifici articoli in uscita richiedono servizi diversi o i diversi parametri di calcolo di servizio, ad esempio una percentuale di utilizzo servizio diversa, è possibile aggiungere altri servizi all'attività.

## <a name="subcontracted-transfer-activities"></a>Attività di trasferimento in conto lavoro
Un'attività di trasferimento è configurata come attività in conto lavoro, secondo l'impostazione **Noleggiato da** dell'attività di trasferimento. Sono disponibili le seguenti opzioni:

-   **Spedizioniere**: l'attività è in conto lavoro se il trasferimento dal magazzino viene gestito da un fornitore (definito da una proprietà del magazzino). Tutti i contratti di acquisto selezionati per i servizi devono avere lo stesso ID fornitore del magazzino.
-   **Destinatario**: l'attività è in conto lavoro se il trasferimento al magazzino viene gestito da un fornitore (definito da una proprietà del magazzino). Tutti i contratti di acquisto selezionati per i servizi devono avere lo stesso ID fornitore del magazzino.
-   **Vettore**- l'attività è in conto lavoro a qualsiasi fornitore che fornisce il servizio. Per essere valido, un vettore deve essere creato per la gestione magazzino e deve avere un conto fornitore assegnato.

Per quanto riguarda le attività di processo, è necessario configurare un servizio predefinito per le attività di trasferimento in conto lavoro nella Scheda dettaglio **Condizioni di servizio**  della pagina **Dettagli** **attività**.

## <a name="service-quantity-calculation"></a>Calcolo della quantità del servizio
L'intero processo di acquisto è basato su un riferimento articolo per un servizio. Questo riferimento articolo viene misurato in un'unità di misura di un servizio. I servizi vengono misurati in genere o in numero di servizi (unità) o in tempo. Per calcolare la quantità di servizio, in base al completamento registrato dei processi kanban, è possibile utilizzare i seguenti metodi:

-   **Calcolo basato sul numero di processi**: un processo kanban è uguale a *n* unità di servizio, indipendentemente dalla quantità di prodotto fornita. In lean manufacturing, un processo corrisponde a un'unità movimentazione. Questo metodo di calcolo viene applicato a tutti i servizi con prezzo fisso per unità di movimentazione. Di conseguenza, questo metodo viene applicato in genere alle attività di trasferimento. Tuttavia, è applicabile anche alle attività di processo che elaborano delle intere unità movimentazione.
-   **Calcolo basato sulla quantità di prodotto**: la quantità di servizio è relativa alla quantità di prodotto programmato/fornito. Quando la quantità di prodotto fornito viene calcolata, è possibile includere o escludere le quantità difettose . Questo metodo viene applicato a tutti i casi in cui il prezzo del servizio per unità di prodotto elaborato viene concordato.
-   **Calcolo basato sul tempo di attività**: i tempi teorici di attività vengono calcolati in base al tempo di elaborazione dell'attività, la quantità elaborata totale e il rapporto di produttività del prodotto elaborato. Questo metodo di calcolo viene applicato ai servizi che vengono pagati su base oraria e hanno uno scostamento di tempo per prodotto elaborato.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilità industriale dei servizi in conto lavoro
Quando l'avviso di ricevimento o un documento di trasporto del fornitore in un ordine fornitore creato per un flusso di produzione (ovvero un ordine fornitore generato in base ai processi kanban per le attività in conto lavoro) viene registrato, il valore dell'entrata viene contabilizzato nei conti WIP del flusso di produzione. Gli scostamenti dalle fatture vengono anche contabilizzati nel flusso di produzione. Una categoria di costi per il lavoro in conto lavoro è stata introdotta. Questa categoria dei costi consente la traccia trasparente del valore del lavoro in conto lavoro allocato al WIP e utilizzato per periodo.  

La determinazione costi di tipo backflush del lean manufacturing alla fine di un periodo di determinazione costi calcola gli scostamenti effettivi di prodotti che sono prodotti dal flusso di produzione durante il periodo di determinazione costi.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modellizzazione dei trasferimenti come attività in conto lavoro
Le persone spesso considerano il trasporto non produttivo e pensano che aggiunga valore. Tuttavia, quando il costo del conto lavoro viene confrontato con il costo di produzione interna, il costo di attività di trasporto aggiuntive deve essere considerato. Un flusso di produzione che comprende più ubicazioni e richiede i servizi di trasporto deve modellare il costo di trasporto come parte del costo di fornitura di prodotti al cliente. 

Il conto lavoro basato su attività nel lean manufacturing consente di integrare i vettori e i fornitori di trasporto che spostano materiale e prodotti tra ubicazioni di un flusso di produzione. Modellando un'attività di trasferimento, è possibile assegnare un vettore o un fornitore. Le attività o il processo di trasferimento è basato su un contratto di servizio e di acquisto e sarà possibile creare ordini fornitore e avvisi di ricevimenti, in base ai processi di trasferimento effettivi. Questa funzionalità è la stessa della funzionalità per le attività di processo in conto lavoro.  

Di conseguenza, Finance and Operations ora supporta il calcolo DBA che comprende servizi di trasporto, la creazione di ordini fornitore correlati, la registrazione integrata dell'entrata e l'integrazione dei costi del servizio di trasporto nella determinazione costi del flusso di produzione.




