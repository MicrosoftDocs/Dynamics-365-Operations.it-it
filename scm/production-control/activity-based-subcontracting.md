---
title: "in conto lavoro basato su attività"
description: "In questo argomento viene descritto, dettaglio, come utilizzare le attività in conto lavoro in un flusso di produzione per la produzione snella."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>in conto lavoro basato su attività

In questo argomento viene descritto, dettaglio, come utilizzare le attività in conto lavoro in un flusso di produzione per la produzione snella.

In Microsoft Dynamics 365 per le operazioni, sono presenti due metodi per subappaltare: ordini di produzione e la produzione snella. Nell'approccio della produzione snella, il conto lavoro di lavoro è modellizzato come servizio correlato a un'attività del flusso di produzione. Tipo speciale di tipo di gruppo di costi denominato ** esternalizzazione diretta ** è stato introdotto e il conto lavoro che i servizi non fanno parte di più una distinta base (BOM). La contabilità industriale di lavoro in conto lavoro è completamente integrata nella soluzione di determinazione costi per la produzione snella.

## <a name="production-flows-that-involve-subcontractors"></a>Flussi di produzione che includono i terzisti
Il principio di base di un flusso di produzione non cambia quando le attività vengono subappaltate. Materiale ancora scorre tra ubicazioni, attività convertito di attività di processo ai prodotti e le attività di trasferimento spostare il materiale o di prodotti da una posizione a un'altra. È possibile definire le ubicazioni e le celle di lavoro come fornitore è assegnato il conto fornitore a un magazzino o a una risorsa a un gruppo di risorse.  

In base a queste funzionalità, la produzione snella non richiede funzionalità specifiche per supportare il flusso di materiale e prodotti. Tutti gli scenari possibili che coinvolgono fornitori come fornitori di servizi di trasporto o di produzione possono essere modellati in base all'architettura di flusso di produzione e delle attività.  

Ad esempio, un terzista risolve di un'area di deposito con sede al terzista. Quando le unità movimentazione vengono svuotate al terzista, le schede kanban vengono restituite alla cella di assembly con la spedizione successivo. Area di deposito al terzista viene quindi completati. I trasferimenti nel conto possono essere modellati come attività di trasferimento esplicite per supportare un prelievo e un processo di spedizione. Se una registrazione esplicita non è obbligatoria per supportare il trasporto fisico, le attività di trasferimento possono essere omesse.  

Un fornitore può essere utilizzato per bilanciare il carico la capacità complessivo del flusso di produzione. Ad esempio, un flusso di produzione è modellizzato utilizzando le regole kanban programmate. La pianificazione viene utilizzata la scheda della programmazione kanban per programmare e caricare a livello entrambe le celle di lavoro se necessario. Il'controlla anche la programmazione consolidata di fornitura per l'area di deposito ** programmazione di fornitura ** nella pagina. I terzisti possono più essere modellati in uno o più flussi di produzione sono e dovessero essere più regole kanban che possono essere utilizzate per immettere lo stesso prodotto nello stesso percorso a diverse attività. La pianificazione possibile convertire kanban in regola kanban alternativa riprogrammare un kanban originariamente è stato creato per la produzione interna a un processo alternativo. Infatti, la natura in conto lavoro della cella di lavoro non ha effetto sul flusso di produzione. Lo stesso principio di esecuzione è valido per due celle di lavoro o interne parallele per due celle in conto lavoro.   

Come per altre attività di un flusso di produzione, le attività in conto lavoro possono utilizzare e materiali e fornire prodotti inventariati, non inventariati \[semilavorato (WIP)\] e semilavorati. Negli argomenti riportati di seguito, i processi di programmazione e l'esecuzione delle attività in conto lavoro sono uguali. Inoltre, questi l'elaborazione dello stesso dei processi di lavoro interno.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Processo di acquisto per attività in conto lavoro (servizi)
Il processo di acquisto per attività in conto lavoro è basato sul flusso di materiale fisico registrato dallo stato del processo kanban, ad esempio, inizio o completamento. Il flusso finanziario, ad esempio, costo di lavoro in conto lavoro, è un flusso secondario che segue il flusso fisico. Contemporaneamente, il processo di acquisto è un processo indipendente che consente rettifica manuale dei documenti di acquisto in corrispondenza di ciascun passaggio. Di seguito è riportato il processo di acquisto per attività in conto lavoro:

1.  Creare un contratto di acquisto. Il contratto di acquisto viene creato per il servizio e è collegato all'attività del flusso di produzione.
2.  Creare un ordine fornitore. Un ordine fornitore di rilascio è possibile creare per il servizio, in base ai processi kanban programmati. I processi per lo stesso assistenza possono essere raggruppati alle righe ordine fornitore per giorno, settimana, o al mese. Le righe ordine fornitore possono essere create in qualsiasi momento dopo i processi kanban vengono creati. Le righe ordine fornitore possono essere create successivamente il i fatti. Questa opzione è selezionata se in genere un terzista fornisce servizi avviso senza ulteriore, in base ai kanban o le schede kanban che riceve il terzista. In questo caso, gli scostamenti tra l'ordine fornitore e la fattura è possibile minimizzate.
3.  Genera le schede kanban, il materiale e una distinta di prelievo da inviare al terzista per preparare per l'elaborazione. In base alla modellizzazione dettagliata del flusso di produzione, la preparazione viene effettuata nella bacheca kanban per le attività di processo operazione utilizzando la distinta di prelievo e la funzione di preparazione. In alternativa, la preparazione viene effettuata nella bacheca kanban per i processi di trasferimento operazione utilizzando la distinta di prelievo e l'avvio o il completamento. Per inventariato materiale, entrambi i processi possono essere supportati da un processo di spedizione e di WMS- prelievo. La polizza di carico può essere creata se necessario.
4.  Generare le unità movimentazione e le schede kanban di kanban. Dopo l'elaborazione, le schede vengono restituite dal fornitore. In genere, le schede includono una bolla di consegna che specifica il materiale fisico già spedita. Riferimento ai servizi forniti non è obbligatorio. In entrata del materiale o di prodotti al cliente viene registrato nella bacheca kanban, a seconda delle schede kanban. (La bacheca kanban per le attività di processo o la bacheca kanban per i processi di trasferimento viene utilizzata, a seconda delle attività. modellistiche).
5.  Creare un advisory di entrata. Il advisory di entrata può essere utilizzato per sostituire un documento di trasporto per i servizi ricevuti. I advisories entrate possono essere generati in base ai processi kanban per completare l'attività di conto lavoro per un periodo selezionato. Per ciascuna ricevuta dei processi, i advisories vengono creati per la riga di ordine fornitore. Il advisory di entrata può essere stampato e inviato al terzista come conferma dell'entrata.
6.  Generazione di una fattura.

Il processo termina quando il terzista viene fatturato a un periodo. L'abbinamento fatture viene effettuata in base ai advisories di entrata creati. Poiché i advisories del conto entrate per l'entrata fisica esatta di materiale, l'abbinamento a tre elementi di verifica viene semplificata.

## <a name="configuring-activities-for-subcontracting"></a>Attività di configurazione per subappaltare
Nelle sezioni seguenti viene descritto come configurare attività per subappaltare.

### <a name="subcontracted-services"></a>Servizi in conto lavoro

L'articolo di pagamento utilizzato nel conto lavoro basato sulle attività deve essere un prodotto con le seguenti proprietà:

-   ** Tipo di prodotto: ** Il servizio
-   ** Gruppo di modelli inventariali: ** Non stoccato

Tale requisito applica l'utilizzo del primo In, First Out) modello inventariale (FIFO). ** Nota: ** Il calcolo di costo voce doganale necessario che il costo standard del servizio sia definito. Un contratto di acquisto con il fornitore è obbligatorio. In caso contrario, il servizio non è possibile utilizzare per il conto lavoro basato sull'attività.

### <a name="subcontracted-process-activities"></a>Attività di processo in conto lavoro

Per configurare un'attività di processo come attività in conto lavoro, effettuare le seguenti operazioni.

1.  Configurare una cella di lavoro in conto lavoro. Per configurare una cella di lavoro come subappaltata, è necessario creare una risorsa ** del fornitore ** la digitazione e associate alla cella di lavoro (gruppo di risorse). Una categoria di costi di runtime ** esternalizzazione diretta ** del tipo del gruppo deve essere assegnato alla cella di lavoro. Le categorie di costo per l'impostazione e la quantità non sono obbligatorie.
2.  Dopo aver un'attività di processo verrà creata e correlata a una cella di lavoro in conto lavoro, è necessario impostare un servizio dell'attività prima della versione del flusso di produzione possa essere attivata. Effettuare questo passaggio ** attività ** ** i dettagli ** pagina. Per le attività associate a una cella di lavoro in conto lavoro, il servizio ** ** definisce la Scheda dettaglio è visualizzato. In questa Scheda dettaglio, aggiungere un servizio predefinito è valido per tutti gli articoli in uscita. Se gli articoli specifici in uscita richiedono i servizi diversi o i diversi parametri di calcolo di assistenza, ad esempio un report di assistenza diverso), è possibile aggiungere altri servizi all'attività.

## <a name="subcontracted-transfer-activities"></a>Attività di trasferimento in conto lavoro
Attività di trasferimento è configurata come attività in conto lavoro, secondo ** spedito per via da ** l'impostazione dell'attività di trasferimento. Sono disponibili le seguenti opzioni:

-   ** Lo spedizioniere ** - l'attività è subappaltato se il trasferimento dal magazzino viene gestito da un fornitore (definito da una proprietà del magazzino). Tutti i contratti di acquisto selezionati per i servizi devono avere la stessa identificazione del fornitore di magazzino.
-   ** Il destinatario ** - l'attività è subappaltato se il trasferimento nel magazzino viene gestito da un fornitore (definito da una proprietà del magazzino). Tutti i contratti di acquisto selezionati per i servizi devono avere la stessa identificazione del fornitore di magazzino.
-   ** Il vettore ** - l'attività è subappaltato qualsiasi fornitore che fornisce il servizio. Per essere valido, un vettore deve essere creato per la gestione magazzino e deve essere assegnato un conto fornitore.

Per quanto riguarda le attività di processo, è necessario impostare un servizio predefinita per le attività di trasferimento in conto lavoro ** termini di assistenza ** clic ** attività ** ** dettagli ** pagina.

## <a name="service-quantity-calculation"></a>Calcolo della quantità del servizio
Il processo di acquisto di l è basato su un riferimento articolo per un servizio. Questo riferimento articolo viene misurato in un'unità di misura di un servizio. I servizi vengono misurati in genere il numero di unità servizi () o nel tempo. Per calcolare la quantità di assistenza, in base al completamento di registrazione processi kanban, è possibile utilizzare i seguenti metodi:

-   ** Il calcolo basato sul numero di processi ** un processo kanban viene determinato dividendo le unità di *n* di assistenza, indipendentemente dalla quantità di prodotto che viene inserita. Nella produzione snella, un processo corrisponde a un'unità movimentazione. Questo metodo viene applicato a tutti i servizi con prezzo fisso per unità di movimentazione. Di conseguenza, questo metodo viene applicata in genere alle attività di trasferimento. Tuttavia, è applicabile anche alle attività di processo di elaborazione delle intere unità movimentazione.
-   ** Il calcolo in base alla quantità di prodotto ** la quantità di assistenza base alla quantità di prodotto programmata o inserita. Quando la quantità di prodotto specificata viene calcolata, le quantità difettose è possibile includere o escludere. Questo metodo viene applicato a tutti i casi in cui il prezzo di assistenza per unità di prodotto viene elaborato accordato al valore specificato.
-   ** Il calcolo basato sul tempo di attività ** i tempi teorici di attività, viene calcolato in base al tempo di elaborazione dell'attività, la quantità in lavorazione totale e di report di produttività del prodotto elaborato. Questo metodo viene applicato ai servizi che vengono pagati rapidamente oraria e hanno uno scostamento a tempo di elaborazione prodotto.

## <a name="cost-accounting-of-subcontracted-services"></a>Contabilità industriale servizi in conto lavoro
Quando la ricevuta consultiva o un documento di trasporto del fornitore in un ordine fornitore creato per un flusso di produzione (ovvero un ordine fornitore generato in base ai processi kanban per le attività in conto lavoro) viene registrata, il valore della transazione in entrata viene distribuito nei conti WIP del flusso di produzione. Gli scostamenti dalle fatture sono state contabilizzate al flusso di produzione. Una categoria di costi per il lavoro in conto lavoro è stata introdotta. Questa categoria dei costi consente per abilitare chiare del valore di lavoro in conto lavoro assegnato al WIP e viene consumato per periodo.  

La determinazione costi di tipo backflush della produzione snella alla fine di un periodo di determinazione costi vengono calcolati gli scostamenti effettivi di prodotti che sono prodotti del flusso di produzione durante il periodo di determinazione costi.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modellizzazione i trasferimenti come attività in conto lavoro
Persone spesso considerato il trasporto non produttività e prevede che non aggiungere il valore. Tuttavia, quando il costo di conto lavoro viene confrontato con il costo di produzione interna, il costo di attività di trasporto aggiuntive deve essere considerato. Flusso di produzione in misura più sedi e richiede i servizi di trasporto deve definire il costo di trasporto come parte del costo di fornitura di prodotti al cliente. 

in conto lavoro basato su attività nella produzione snella consente di integrare i vettori e trasportare i fornitori che determinano lo spostamento materiali e di prodotti tra ubicazioni di un flusso di produzione. Riservata un'attività di trasferimento, è possibile assegnare un vettore o un fornitore. Le attività di trasferimento o processi è basata su un servizio e su un contratto di acquisto e sarà possibile creare ordini fornitore e i advisories di entrata, in base ai processi effettivi di trasferimento. Questa funzionalità è la stessa della funzionalità per le attività di processo in conto lavoro.  

Di conseguenza, Dynamics 365 per le operazioni ora supporta il calcolo DBA che comprende servizi di trasporto, la creazione di ordini fornitore correlati, la registrazione integrata di ricevimento e l'integrazione dei costi del servizio di trasporto nella determinazione costi del flusso di produzione.


