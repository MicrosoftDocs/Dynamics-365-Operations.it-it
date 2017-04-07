---
title: Gruppi di calcoli DBA
description: "In questo articolo sono riportate informazioni sui gruppi di calcolo per le distinte base (DBA) e su come impostarli. Per eseguire un calcolo DBA, è necessario impostare i gruppi di calcolo e assegnarli ai singoli articoli oppure impostare un gruppo di calcolo predefinito. Le impostazioni di calcolo dal gruppo di calcolo vengono poi utilizzate come valori predefiniti nella pagina Calcolo DBA al momento del calcolo DBA."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 893c6d42fc3de3e07d63f0ac61a287e81685cbad
ms.lasthandoff: 03/31/2017


---

# <a name="bom-calculations-groups"></a>Gruppi di calcoli DBA

In questo articolo sono riportate informazioni sui gruppi di calcolo per le distinte base (DBA) e su come impostarli. Per eseguire un calcolo DBA, è necessario impostare i gruppi di calcolo e assegnarli ai singoli articoli oppure impostare un gruppo di calcolo predefinito. Le impostazioni di calcolo dal gruppo di calcolo vengono poi utilizzate come valori predefiniti nella pagina Calcolo DBA al momento del calcolo DBA. 

È necessario un gruppo di calcolo predefinito nella pagina **Parametri di gestione articoli e magazzino** o un gruppo di calcolo specifico del prodotto nella pagina **Dettagli prodotto rilasciato**. Il sistema prima ricerca di impostazione del gruppo di calcolo ** modulo Dettagli prodotto rilasciato ** nella pagina. Se non viene trovata un gruppo di calcolo, quale verrà considerata ** parametri di Gestione articoli e magazzino scorte ** la pagina. Se non viene individuato un gruppo di calcolo, verrà generato un messaggio di errore durante il calcolo. Un gruppo di calcolo contiene i criteri per il modello prezzo di costo, il modello prezzo di vendita e l'elenco di controllo di avvisi. Le impostazioni di calcolo dal gruppo di calcolo vengono utilizzate come valori predefiniti nella pagina **Calcolo DBA** al momento del calcolo DBA.

## <a name="purposes-of-bom-calculation-groups"></a>Scopi dei gruppi di calcolo DBA
Si assegna un gruppo di calcolo DBA agli articoli per diversi motivi:

-   Impostando il campo **Modello prezzo di costo**, si indica l'origine dei dati sui contributi costi di un componente acquistato durante il calcolo del costo pianificato di un articolo prodotto. Alcuni produttori calcolano i costi pianificati sulla base degli accordi commerciali sui prezzi di acquisto per i componenti acquistati o su altre basi, ad esempio i record di prezzo di acquisto in una versione di determinazione costi.
-   Impostando il campo **Modello prezzo di vendita**, si indica la modalità di utilizzo dei dati dell'articolo per calcolare un prezzo di vendita consigliato. È possibile specificare il prezzo di vendita o il gruppo di costi dell'articolo. Alcuni produttori desiderano calcolare un prezzo di vendita consigliato per gli articoli prodotti. Il prezzo di vendita calcolato può riflettere un approccio di riduzione basato sul record del prezzo di vendita del componente. In alternativa, il prezzo di vendita calcolato può riflettere un approccio comprendente una percentuale di ricarico basato sul costo del componente e sulla percentuale di profitto applicabile (associato al gruppo di costi dell'articolo).
-   Utlizzando il campo **Interrompi esplosione**, si indica che un articolo prodotto deve essere considerato come un articolo acquistato ai fini del rollup dei costi durante i calcoli DBA. Gli scenari più tipici prevedono la presenza di un articolo acquistato che viene prodotto occasionalmente oppure la presenza di un articolo prodotto che al momento viene acquistato. L'articolo inizialmente sarà designato come articolo prodotto allo scopo di definire le informazioni relative alla DBA e al ciclo di lavorazione e di supportare gli ordini di produzione a esso relativi. Tuttavia, il flag **Interrompi esplosione** impedisce di utilizzare la DBA e il ciclo di lavorazione dell'articolo nel calcolo dei costi. Il calcolo DBA utilizza invece i costi specificati dell'articolo.

## <a name="calculation-groups"></a>Gruppi di calcolo
Si definiscono i gruppi di calcolo in **Impostazione criteri di costo predeterminati** in Gestione costi. I gruppi di calcolo che vengono assegnati agli articoli consentono di specificare come il prezzo di costo o di vendita dei componenti, come delineato dal gruppo di calcolo, viene derivato per il calcolo. Nella pagina **Gruppi di calcolo**, è possibile definire un modello di prezzo di costo, un modello di prezzo di costo alternativo, un modello di prezzo di vendita e gli avvisi.

### <a name="cost-price-model"></a>Modello prezzo di costo

Sono disponibili quattro opzioni per il campo **Modello prezzo di costo**:

-   **Prezzo di costo articolo** : il prezzo di costo dalla tabella **Prodotto rilasciato** viene utilizzato o la combinazione di dimensioni articolo viene utilizzata come prezzo di costo.
-   **Prezzo di acquisto articolo** : il prezzo di acquisto dal campo **Prezzo di costo** della scheda **Acquisto** della pagina **Prodotti rilasciati** viene utilizzato.
-   **Accordi commerciali** – è possibile configurare accordi commerciali per specifiche combinazioni di articoli e fornitori o per siti specifici. Quindi, quando si seleziona l'opzione **Accordi commerciali** qui, l'accordo commerciale che è stato creato per il prezzo di acquisto con l'articolo e il sito verrà utilizzato.
-   **Prezzo scorte** : il valore di magazzino corrente per l'articolo viene utilizzato per calcolare il costo unitario nel calcolo DBA. Un prezzo di costo unitario viene calcolato solo se la quantità registrata e la quantità fisica sono maggiori di 0 (zero).

### <a name="alternative-cost-price"></a>Prezzo di costo alternativo

Il campo **Prezzo di costo alternativo** ha le stesse opzioni del campo **Modello prezzo di costo**. Tuttavia, questo campo viene utilizzato solo quando non è possibile trovare un prezzo nel modello di prezzo di costo primario.

### <a name="sales-price-model"></a>Modello prezzo di vendita

Sono disponibili due opzioni per il calcolo del campo **Prezzi di vendita**:

-   **Gruppo di costi** : quando questa opzione è selezionata, il prezzo di vendita viene calcolato in base al prezzo di costo e la percentuale di impostazione del profitto dal gruppo di costi.
-   **Prezzo di vendita articolo** : quando questa opzione è selezionata, viene utilizzato il prezzo di vendita nella Scheda dettaglio **Vendi** della tabella Prodotti rilasciati.

### <a name="stop-explosion"></a>Interrompi esplosione

La casella di controllo **Interrompi esplosione** viene utilizzata per indicare quando un articolo prodotto deve essere considerato come un articolo di acquisto. In genere, si lascerà la casella di controllo **Interrompi esplosione** deselezionata. Selezionare questa casella di controllo per indicare che un articolo prodotto deve essere trattato come un componente di acquisto (anziché come componente prodotto) ai fini del calcolo DBA. In base al sito, i costi dell'articolo possono comunque essere calcolati utilizzando calcoli DBA. L'esplosione di ordini fornitore e ordini di produzione pianificati viene interrotta nella distinta base i cui componenti sono associati al calcolo di gruppo per cui la casella di controllo **Interrompi esplosione** è selezionata. Durante la programmazione generale verranno generati gli ordini pianificati presenti nella DBA stessa e non negli articoli inclusi nella DBA. In sostanza, selezionando questa casella di controllo, si specifica che non verrà aggiunto un costo al calcolo DBA per gli articoli che dispongono di questo gruppo di calcolo.

### <a name="warnings"></a>Avvisi

Nella scheda dettaglio **Avvisi**, si selezionano le opzioni per i messaggi di avviso che gli utenti devono ricevere quando effettuano i calcoli DBA. Ad esempio, se si seleziona la casella di controllo **Nessuna DBA**, l'utente riceve un avviso se non viene trovata alcuna versione DBA attiva per uno dei componenti o l'articolo padre per cui viene eseguito il calcolo DBA. Se si seleziona la casella di controllo **Nessun ciclo di lavorazione**, l'utente riceve un avviso se non è presente alcuna versione attiva del ciclo di lavorazione. Se si utilizzano le risorse nei cicli di lavorazione e le operazioni, è possibile indicare al sistema di verificare la presenza di tali risorse. Quindi, se non viene trovata una risorsa su ogni riga del ciclo di lavorazione attivo, l'utente riceve un messaggio di avviso. È inoltre possibile verificare e controllare il consumo. Il consumo è la quantità in un particolare ciclo di lavorazione. In genere, rappresenta la quantità di tempo necessario per eseguire un'operazione specifica per un processo di produzione. È possibile verificare se un articolo non ha alcun prezzo di costo. Se non vi è alcun prezzo di costo attivo per un articolo, nel calcolo DBA non viene aggiunto alcun costo. È inoltre possibile controllare e verificare la validità del prezzo di costo. Ad esempio, immettere **60** per indicare che il prezzo di costo unitario deve essere rivalutato dopo 60 giorni. Se viene raggiunto questo limite, il sistema genera un avviso. Ad esempio, un prezzo di costo immesso per un articolo nel mese di gennaio dell'anno in corso. Se ora è agosto, ovvero più di 60 giorni dopo l'immissione del prezzo di costo, l'utente riceve un avviso quando viene eseguito il calcolo DBA. È possibile immettere una percentuale nel campo **Margine di contribuzione minimo**. Questo valore indica il punto in cui il margine di contribuzione minimo non è soddisfatto. Se il margine di contribuzione per un particolare componente non è soddisfatto, l'utente riceve un messaggio di avviso. Questo campo assicura pertanto che non si riducano eccessivamente i costi e costi di mantenimento aggiuntivi che potrebbero essere necessari per gli articoli.
Impostazione predefinita in Parametri di gestione articoli e magazzino
--------------------------------------------------------------

Poiché i gruppi di calcolo sono necessari per eseguire calcoli, è necessario impostare un gruppo di calcolo predefinito nei parametri di Gestione articoli. Questa impostazione consente alle aziende di disporre di un gruppo di costi e un'impostazione di profitto standard per tutti gli articoli. Quindi, se un particolare articolo presenta requisiti particolari di calcolo, l'utente può assegnare un altro gruppo di calcolo a quell'articolo. In genere, è possibile impostare gruppi di calcolo per gli articoli di componente DBA invece gli articoli DBA. Tuttavia, quando sono visualizzati messaggi di avviso, i gruppi di calcolo possono essere applicati. Un gruppo di calcolo assegnato agli articoli sostituisce il valore predefinito impostato nei parametri di Gestione articoli. È possibile impostare il parametro predefinito a ** gestione dei costi ** &gt; ** inventariate i criteri contabili impostati ** &gt; ** parametri ** &gt; ** contabilità scorte ** &gt; ** gruppo di calcolo **. Impostando un gruppo di configurazione predefinito, è inoltre possibile configurare le condizioni di avviso per gli utenti durante il processo di calcolo DBA, se i componenti selezionati potrebbero causare errori di calcolo.
Visualizzazione dei messaggi di avviso nella pagina Operazione completata
------------------------------------------

Un calcolo DBA genera messaggi di avviso. È possibile visualizzare avvisi su un articolo selezionato. Ad esempio in Vendite e marketing, creare un nuovo ordine cliente per l'articolo D0001. Quindi, nella riga dell'ordine cliente, nel menu **Aggiorna riga**, fare clic su **Calcola in base a DBA/formula** per visualizzare i dettagli di calcolo e gli avvisi. È inoltre possibile visualizzare i risultati del calcolo DBA nella pagina **Operazione completata**. Per i messaggi di avviso, sono applicabili solo due condizioni di avviso agli articoli prodotti, mentre per tutti gli altri articoli ne sono applicabili quattro.
-   Identificare quando a un articolo prodotto non è associata una DBA attiva.
-   Identificare quando a un articolo prodotto non è associato un ciclo di lavorazione attivo.
-   Identificare quando per l'articolo in una riga DBA la quantità è pari a 0 (zero).
-   Identificare quando per l'articolo in una riga DBA il costo è pari a 0 (zero) o quando non è disponibile un record di costo.
-   Identificare quando per l'articolo in una riga DBA è presente un costo non aggiornato. Nell'avviso viene effettuato un confronto tra la data di calcolo e il numero di giorni specificato come validità massima del costo.
-   Identificare quando per l'articolo in una riga DBA è indicata una percentuale di redditività inferiore a quella desiderata.

È possibile definire più gruppi di calcolo DBA, a seconda dei requisiti per le variazioni nei messaggi di avviso. Un solo gruppo ad esempio con condizioni di avviso per una DBA attiva, una quantità componente pari a 0 (zero) e un costo componente pari a 0 (zero) potrebbe essere sufficiente. Quando si avvia un calcolo DBA, le condizioni di avviso associate al gruppo di calcolo DBA possono essere sostituite. È anche possibile aggiungere o rimuovere condizioni di avviso. Ad esempio, è possibile rimuovere la condizione di avviso relativa a un ciclo di lavorazione attivo se per la situazione corrente non sono coinvolti dati su tale ciclo. **Nota:** Orario e presenze include una pagina **Gruppi di calcolo**, ma la pagina non ha relazioni con i gruppi di calcolo DBA. In Orario e presenze i lavoratori possono essere assegnati a gruppi di calcolo che riflettono il raggruppamento dei lavoratori associati allo stesso supervisore o responsabile. Il calcolo delle registrazioni dei lavoratori può essere eseguito automaticamente o manualmente da un supervisore o un responsabile.


