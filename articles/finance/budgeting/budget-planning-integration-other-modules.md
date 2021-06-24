---
title: Integrazione della pianificazione del budget con altri moduli
description: I piani di budget possono essere generati tramite molteplici risorse differenti. Gli elementi di base del processo periodico sono uguali per tutte le risorse.
author: ShylaThompson
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edac31cb8a4f28f06819c791b308286f474c9b55
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188664"
---
# <a name="budget-planning-integration-with-other-modules"></a>Integrazione della pianificazione del budget con altri moduli

[!include [banner](../includes/banner.md)]

 I piani di budget possono essere generati tramite molteplici risorse differenti. Gli elementi di base del processo periodico sono uguali per tutte le risorse. 



## <a name="periodic-processes-for-generating-budget-plans"></a>Processi periodici per la generazione di piani di budget

I piani di budget possono essere generati tramite le risorse seguenti:

-   Transazioni relative alla contabilità generale
-   Cespiti
-   Posizioni previste
-   Previsioni progetto
-   Previsioni dell'offerta
-   Previsioni della domanda
-   Voci del registro di budget
-   Altri piani di budget

Gli elementi di base del processo periodico sono uguali per tutti i processi. Le schede consentono di definire l'origine dei dati, gli attributi di destinazione (piano di budget) e le opzioni del processo in background come processo batch. Nelle sezioni successive di questo articolo vengono descritti gli aspetti che potrebbero non essere evidenti in ciascun processo.

### <a name="actions"></a>Azioni

Per ciascun processo di creazione, sono disponibili tre azioni:

-   **Crea un nuovo piano di budget**: consente di creare un nuovo piano con gli attributi selezionati nella sezione **Destinazione**. Questi attributi non devono essere univoci. Di conseguenza, due piani possono avere lo stesso nome e altri valori uguali.
-   **Sostituisci lo scenario del piano di budget esistente**: consente di eliminare tutti i dati del piano di budget di destinazione nello scenario del piano di budget selezionato e creare nuove righe che utilizzano i dati di origine selezionati.
-   **Aggiornare lo scenario del piano di budget esistente e aggiungere nuovi dati**: consente di aggiornare le righe esistenti del piano di destinazione che corrispondono alle righe di origine e aggiungere nuove righe per i nuovi dati. La corrispondenza si basa su conto CoGe, data, classe del budget e diversi altri campi. Ad esempio, quando si genera di piano di budget dalle posizioni previste, il numero di posizione è un campo importante. Tutte le righe con un numero di posizione che corrisponde al numero di posizione di origine vengono sostituite dalle nuove righe dall'origine.

### <a name="source"></a>Origine

Per tutti i processi, la scheda **Origine** consente di filtrare i dati utilizzando il pulsante **Filtro**. Per impostazione predefinita, i campi specifici vengono aggiunti al filtro per ciascun processo. Ad esempio per il processo **Genera piano di budget da contabilità generale**, le categorie **Conto CoGe** e **Conto principale** sono disponibili e compaiano nella pagina della creazione. Tutti i campi aggiunti al filtro vengono aggiunti anche alla pagina, insieme a qualsiasi altro criterio aggiunto.

### <a name="target"></a>Destinatari

L'opzione **Storico** nella scheda **Destinazione** consente di utilizzare le date dei dati di origine come data di validità del piano di budget. In genere, la data di validità deve rientrare nel ciclo di budget del piano. Quando si imposta l'opzione **Storico** su **Sì**, la data (anche l'anno) di origine verrà utilizzata, in modo che sia possibile utilizzare i dati passati come base per il confronto. Non è possibile modificare i dati storici nel piano di budget e il piano è impostato su uno stato del flusso di lavoro approvato. Tuttavia, è possibile reimpostare lo stato se altri scenari nel piano richiedono modifiche.

Anche il campo **Aggrega totale per** nella parte superiore della pagina determina la data utilizzata. Questo campo somma gli importi e facoltativamente applica la data di validità al primo giorno dell'anno fiscale o del periodo fiscale. 

Molti dei campi nella scheda <strong>Destinazione</strong> diventano modificabili o di sola lettura, a seconda dell'azione selezionata. Quando si cambia dalla creazione di un nuovo di piano di budget all'aggiornamento di un piano esistente, il campo **Nome piano di budget** non risulta disponibile e i campi correlati alla selezione di un piano esistente diventano disponibili. Nella scheda **Destinazione** e nella scheda **Origine**, il campo **Contabilità generale** non è mai disponibile, poiché il valore dipende dal processo di pianificazione del budget selezionato. 

Il campo **Classe budget** consente di impostato le righe del piano di budget come transazioni di spesa o transazioni ricavi. In genere, le transazioni ricavi vengono accreditate in un conto CoGe e vengono quindi salvate come importi negativi. In genere, queste transazioni vengono visualizzate anche come importi negativi nel piano di budget. Tuttavia, aggiungendo la classe del budget come un campo del layout del piano, è possibile abilitare la visualizzazione dei ricavi come importi di positivi.

### <a name="generation-rules"></a>Regole di generazione

Tre campi forniscono funzionalità aggiuntive: **Fattore**, **Minimo** e **Regola** **di arrotondamento**. 

Il valore nel campo **Fattore** viene moltiplicato per l'importo di origine per impostare l'importo nel piano di budget. È quindi possibile apportare correzioni quando si creano righe di piano di budget. Ad esempio, è possibile immettere **1,03** come un incremento del 3%. Il fattore deve essere un numero positivo. 

Il campo **Minimo** consente di impostare l'importo di soglia per la creazione di una riga del piano di budget. Se l'importo di origine è inferiore a questo numero, la riga del piano di budget non verrà creata. Un valore di  **0.00** consente tutti gli importi ma non limita le righe agli importi positivi. (Se non si specifica nessun valore le righe vengono limitate agli importi positivi. Gli importi negativi vengono sempre inclusi e in genere rappresentano le voci in Avere).

Il campo **Regola di arrotondamento** consente di impostare la precisione delle righe di piano di budget create. È possibile arrotondare gli importi in valuta alla cifra più vicina 1,00, 10,00, 100,00 e così via.

## <a name="notes-for-specific-processes"></a>Note per processi specifici
### <a name="generate-budget-plan-from-general-ledger"></a>Genera piano di budget da contabilità generale

Quando si crea di piano di budget dai dati della contabilità generale, è necessario impostare il campo **Aggrega totale per** su **Anno fiscale** se l'opzione **Storico** è impostata su **No**. I periodi e le date dell'origine potrebbero non corrispondere ai periodi nelle date della destinazione. Poiché il processo non ha un modo affidabile di mappare tali valori, è necessario limitare il processo al primo anno. 

Nella destinazione, il campo **Classe budget** viene impostato su **Spese** o **Ricavi**. Questa impostazione viene utilizzata per selezionare l'attributo **Tipo di budget** per le righe create, se il conto principale in una riga non è di tipo **Ricavi** o **Spesa**.

### <a name="generate-budget-plan-from-fixed-assets"></a>Genera piano di budget da cespiti

Il processo **Genera piano di budget da cespiti** non ha alcuna opzione per l'aggregazione per periodo o giorno. Non c'è inoltre nessuna opzione per l'impostazione del piano come storico. È possibile utilizzare questo processo periodico per includere le transazioni previste per i cespiti nella pianificazione del budget.

### <a name="generate-budget-plan-from-forecast-positions"></a>Genera righe del piano di budget da posizioni previste

Il processo **Genera righe del piano di budget da posizioni previste** assegna la posizione prevista di origine alla riga del piano di budget. È possibile visualizzare la posizione sommando la posizione prevista come una riga nel layout del piano di budget o tramite la richiesta **Righe del piano di budget**. Se non si desidera che la posizione prevista sia assegnata alle righe del piano del budget, impostare l'opzione **Includi posizione nella riga del piano di budget** su **No**.

Le righe del piano di budget verranno aggregate per conto CoGe e posizione. Tuttavia, è possibile escludere il numero di posizione, in modo che le righe vengano aggregate solo per conto CoGe. Nella scheda **Destinazione** impostare l'opzione **Includi posizione nella riga del piano di budget** su **No**.

Nel campo **Scenario FTE del piano di budget** è possibile selezionare uno scenario per includere il numero di equivalenti a tempo pieno (FTE) nel piano di budget. Questo campo è limitato a scenari di tipo quantità inclusi nel layout del piano di budget di destinazione. Se si seleziona uno scenario FTE, è necessario selezionare anche un conto principale FTE. Questo conto viene utilizzato per creare le righe di piano di budget di quantità. 

Il processo di pianificazione del budget e lo scenario del piano di budget selezionati nell'origine determinano il processo di pianificazione del budget e lo scenario dello scenario di destinazione. Poiché questi attributi vengono assegnati alle posizioni previste, devono corrispondere di piano di budget. Di conseguenza, questi attributi non possono essere modificati nella destinazione.

### <a name="generate-budget-plan-from-project-forecasts"></a>Genera piano di budget da previsioni di progetto

Il processo **Genera piano di budget da previsioni di progetto** analogamente al processo **Genera righe del piano di budget da posizioni previste** presenta un'opzione per includere le quantità di progetto (ore, spese e articoli) in uno scenario di quantità. I due processi hanno anche filtri simili per le colonne nel layout di piano di budget. 

Nella scheda **Origine** tre opzioni della sezione **Includi rendiconto** determinano quali righe di piano di budget vengono create. Queste opzioni sono le stesse delle opzioni disponibili quando si creano le voci del registro di budget direttamente dalle previsioni di progetto. Impostare l'opzione **Profitti e perdite** su **Sì** per creare le righe dei costi e dei ricavi. Impostare l'opzione **WIP** su **Sì** per creare il lavoro delle voci del semilavorato. Impostare l'opzione **Allocazione retribuzioni** su **Sì** per creare le righe per la retribuzione del conto di contropartita per le transazioni orarie. 

Non esiste un campo **Classe budget** poiché la classe del budget (**Spesa** o **Ricavi**) è determinata dall'origine. 

È possibile utilizzare i budget di progetto come origine selezionando il modello previsionale che contiene gli importi del budget di progetto. Si ricordi che i budget di progetto creano le voci di previsione di progetto quando vengono approvate.

Per selezionare solo i costi o ricavi per le righe di piano del budget, utilizzare il filtro per selezionare <strong>Aggiornamenti budget: tipo di importo = costo</strong>. Per selezionare solo un tipo di previsione, utilizzare il filtro per selezionare <strong>Aggiornamenti budget: tipo di transizione = *xxx</strong>*. 

Solo un modello previsionale può essere utilizzato per generare uno scenario del piano di budget. Se si esegue il processo per un modello previsionale e quindi si esegue un aggiornamento e si prova a specificare un altro modello, il primo modello verrà sovrascritto quando si applicano lo stesso progetto e gli stessi conti CoGe. Per generare uno scenario del piano di budget da più di un modello previsionale, generare i diversi scenari del piano di budget e utilizzare le opzioni di allocazione per aggiungerle in un altro scenario. 

Il processo **Genera piano di budget da previsioni di progetto** assegna anche il progetto di origine alla riga del piano di budget.

### <a name="generate-budget-plan-from-supply-forecast"></a>Genera piano di budget da previsione dell'offerta

Le opzioni di filtro di origine in **Genera piano di budget da previsione dell'offerta** nel processo sono state modellate in base alle opzioni della funzione **Trasferisci budget acquisti nella contabilità generale**, a causa di similarità tra il processo e la funzione.

### <a name="generate-budget-plan-from-demand-forecast"></a>Genera piano di budget da previsioni della domanda

Per il processo **Genera piano di budget da previsioni della domanda** è possibile impostare l'opzione **Ordine cliente** su **Sì** per generare le righe dei ricavi nel piano di budget, impostare **Consumo** su **Sì** per creare le righe di spesa o impostare entrambe le opzioni su **Sì**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Genera piano di budget da voci del registro di budget

Per il processo **Genera piano di budget da voci del registro di budget** l'origine deve specificare un sottomodello, un codice budget e un numero voce. Ovvero è possibile creare le righe di piano di budget solo per una voce del registro di budget alla volta. È possibile utilizzare le voci aggiuntive nello stesso piano di budget eseguendo una volta il processo per ogni voce di origine.

### <a name="generate-budget-plan-from-budget-plan"></a>Genera piano di budget da piano di budget

Per il processo **Genera piano di budget da piano di budget**, è disponibile un set aggiuntivo di opzioni nella scheda **Destinazione** che consente di assegnare nuove dimensioni finanziarie. Se una dimensione finanziaria viene selezionata, il valore verrà utilizzato per tutte le righe di piano di budget. Di conseguenza, è possibile utilizzare un piano di budget di base per altri piani di budget, ma è possibile assegnare, ad esempio, un reparto o centro di costo diverso a nuovi piani di budget.

## <a name="looking-back-from-the-budget-plan"></a>Effettuare ricerche dal piano di budget
### <a name="budget-plans-by-dimension-set-inquiry"></a>Richiesta di informazioni Piani di budget per set di dimensioni

La richiesta **Piani di budget per set di dimensioni** include più opzioni che consentono di eseguire una query per identificare l'origine dei dati di piano di budget. 

Selezionare una riga e fare clic sul pulsante **Righe di piano di budget** per eseguire la query **Righe del piano di budget**. I risultati vengono filtrati per i valori delle dimensioni della riga selezionata. È quindi possibile applicare i parametri necessari. 

Utilizzare i pulsanti **Previsione dell'offerta** e **Previsione della domanda** per eseguire le query. In entrambi i casi, la query eseguono la ricerca delle righe di previsione che possono avere creato le righe di piano di budget. 

Report aggiuntivi disponibili includono il report **Posizioni previste per piano di budget**. Questo report è particolarmente utile se si desidera determinare se una posizione sia stata allocata al piano di budget in modo corretto.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]