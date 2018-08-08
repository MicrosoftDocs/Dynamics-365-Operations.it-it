---
title: Garantire le scorte di sicurezza per gli articoli
description: "In questo argomento vengono fornite informazioni su come mantenere un livello di scorte di sicurezza e impostare la quantità di scorte di sicurezza per gli articoli."
author: roxanadiaconu
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: d6ecb346f7bfa54a4e16307f623c82acb3a86892
ms.contentlocale: it-it
ms.lasthandoff: 12/14/2017

---

# <a name="safety-stock-fulfillment-for-items"></a>Garantire le scorte di sicurezza per gli articoli

[!include [banner](../includes/banner.md)]

Le scorte di sicurezza indicano una quantità aggiuntiva di un articolo contenuto nel magazzino al fine di ridurre il rischio che l'articolo si esaurisca. Le scorte di sicurezza vengono utilizzate come scorta di margine nel caso in cui gli ordini cliente arrivino e il fornitore non sia in grado di consegnare gli articoli aggiuntivi per soddisfare la data di spedizione richiesta dal cliente. Quando le scorte di sicurezza vengono utilizzate per evadere un ordine cliente, la loro quantità diminuisce. È possibile utilizzare la pianificazione generale per riportare automaticamente le scorte magazzino a livello di sicurezza.    

## <a name="set-up-safety-stock-levels-for-items"></a>Impostare le scorte di sicurezza per gli articoli

Le scorte di sicurezza sono impostate come parte della copertura articoli nella pagina **Copertura articoli** in **Prodotti rilasciati** > **Piano** > **Copertura**.

Nel campo **Minimo** immettere la quantità minima di scorte o il livello scorte di sicurezza che si desidera mantenere per l'articolo. Il valore viene espresso in unità di magazzino. Se questo campo viene lasciato vuoto, il valore predefinito sarà pari a zero. Questo campo è disponibile se si seleziona **Periodo**, **Fabbisogno** o **Min/Max** nell'elenco **Codice copertura**. Il limite del livello di scorte si applica all'inventario disponibile, vale a dire che le prenotazioni e i contrassegni possono attivare il rifornimento di scorte di sicurezza prima che la quantità fisica scenda al di sotto del livello minimo specificato.

> [!NOTE]
> Prima di definire un valore per il campo **Minimo**, è necessario definire tutte le dimensioni pianificate per la copertura. Questo impedisce l'utilizzo di un record non valido durante la pianificazione generale. Una situazione di questo tipo può verificarsi, ad esempio, se un gruppo di dimensioni viene esteso con una dimensione di copertura pianificata aggiuntiva per cui le quantità in magazzino minime e massime non sono ancora state definite.

È possibile utilizzare le chiavi minime per gestire le fluttuazioni stagionali nella domanda. È possibile, ad esempio, ridurre il livello delle scorte minime per un articolo nella stagione morta e aumentarlo gradualmente nei mesi successivi. È possibile creare una chiave minima tramite **Pianificazione generale** > **Impostazione** > **Copertura** > **Chiavi minime/massime**. Si può specificare la chiave minima per rettificare il livello scorte di sicurezza in base alla stagione nel campo **Chiave min** della pagina **Copertura articoli**. 

## <a name="example-minimum-key"></a>Esempio: chiave minima
Se si desidera creare una chiave minima per spiegare l'aumento della domanda stagionale durante i mesi primaverili ed estivi, passare a **Pianificazione generale** > **Impostazione** > **Copertura** > **Chiavi minime/massime** ed effettuare le seguenti operazioni.

1. Creare 12 righe e assegnare un numero da 1 a 12 nelle righe del campo **Modifica**.
2. Nel campo **Unità** selezionare **Mesi**.
3. Nel campo **Fattore** immettere i valori descritti nella tabella che segue.

|Linea|Immettere questo valore|Risultato|
|---|---|---|
|1-3|1|Le scorte minime si basano sull'impostazione del periodo da gennaio a marzo nella pagina **Copertura articoli**.|
|4-5|2|Le scorte minime vengono moltiplicate per un fattore pari a 2 per aprile fino a maggio.|
|6-8|2,5|Le scorte minime vengono moltiplicate per un fattore pari a 2,5 per il periodo da giugno ad agosto.|
|9-12|1|Per le scorte minime viene di nuovo utilizzata l'impostazione della pagina **Copertura articolo** per il periodo da settembre a dicembre.|

Se il codice di copertura è **Chiavi minime/massime**, è possibile anche specificare la quantità in inventario **Massimo** che si desidera garantire per l'articolo. Il valore viene anche espresso in unità di magazzino. Se il livello delle scorte disponibili previste scende al di sotto della quantità minima, durante la pianificazione generale verrà creato un ordine pianificato per soddisfare qualsiasi altro fabbisogno e ripristinare la quantità massima specificata. In modo analogo all'impostazione del valore **Minimo**, è necessario definire tutte le dimensioni di copertura pianificate prima di poter impostare il campo **Massimo**.

## <a name="example-minmax-coverage-code"></a>Esempio: codice di copertura Min/Max
La quantità minima è 10 e quella massima è 15. La quantità corrente di scorte disponibili è 4, quindi il fabbisogno quantitativo minimo è 6. Tuttavia, poiché la quantità massima è 15, durante la pianificazione generale verrà creato automaticamente un ordine pianificato pari a 11 articoli.

Per gli articoli che seguono le richieste stagionali, potrebbe essere necessario mantenere diversi livelli massimi. A tale scopo, è necessario definire **Chiavi massime** in **Pianificazione generale** > **Impostazione** > **Copertura** > **Chiavi minime/massime**. Compilare il campo **Chiave massima** nella pagina **Copertura articoli**. È possibile visualizzare informazioni sui livelli di scorte di sicurezza definiti tramite le chiavi minime nella scheda **Min/Max** nella pagina **Copertura articoli**. È necessario assicurarsi che, per un determinato periodo, i valori minimo e massimo siano sincronizzati.

## <a name="safety-stock-fulfillment"></a>Soddisfare le scorte di sicurezza 

Il parametro **Soddisfa minimo** consente di selezionare la data o il periodo di tempo durante il quale il livello delle scorte deve soddisfare la quantità specificata nel campo **Minimo**. Questo campo è disponibile se si seleziona **Periodo**, **Fabbisogno** o **Min/Max** nell'elenco **Codice copertura**.

Se vengono utilizzate le **Chiavi minime**, selezionare la casella di controllo **Periodi minimi** per soddisfare il livello scorte minime per tutti i periodi impostati per la chiave minima. Se si deseleziona la casella di controllo, le scorte minime vengono soddisfatte solo per il periodo corrente.

Nel seguente scenario viene illustrato come questo parametro viene eseguito e quali sono le differenze tra i valori.

> [!NOTE]
> Per tutte le illustrazioni in questo argomento, l'asse x rappresenta l'inventario, l'asse y rappresenta i giorni, le barre rappresentano il livello di inventario, le frecce rappresentano le transazioni, come le righe degli ordini cliente, le righe degli ordini fornitore o gli ordini pianificati.

[![Scenario comune di mantenimento delle scorte di sicurezza](./media/Scenario1.png)](./media/Scenario1.png) Il parametro **Soddisfa minimo** può contenere i seguenti valori:
### <a name="todays-date"></a>Data odierna 
La quantità minima specificata viene soddisfatta alla data di esecuzione della pianificazione generale. Il sistema tenta di soddisfare il più presto possibile il limite di scorta di sicurezza, anche se può essere non realistico a causa del lead time. 
[![Fabbisogno alla data odierna](./media/TodayReq.png)](./media/TodayReq.png) L'ordine pianificato P1 viene creato per la data odierna per portare l'inventario disponibile sopra il livello di scorte di sicurezza in questa data. Le righe dell'ordine cliente da S1 a S3 continuano a ridurre il livello delle scorte. Gli ordini pianificati P2 a P4 vengono generati dalla pianificazione generale in modo da riportare il livello di scorta al limite di sicurezza dopo ogni fabbisogno dell'ordine cliente.
Quando viene usato il codice di copertura **Fabbisogno**, vengono creati più ordini pianificati. È sempre consigliabile utilizzare la copertura **Periodo** o **Min/Max** per gli articoli e i materiali di domande frequenti, per aggregare il rifornimento. Nella figura seguente è illustrato un esempio del codice di copertura **Periodo**.
[![Periodo. Data odierna](./media/TodayPeriod.png)](./media/TodayPeriod.png) Nella figura seguente è illustrato un esempio del codice di copertura **Min/Max**.
[![MinMax. Data odierna](./media/TodayMinMax.png)](./media/TodayMinMax.png)
### <a name="todays-date--procurement-time"></a>Data odierna + tempo di approvvigionamento 
La quantità minima specificata viene soddisfatta alla data di esecuzione della pianificazione generale posticipata in base al tempo di produzione o di acquisto. Questa volta include eventuali margini di sicurezza. Se per l'articolo è stato definito un accordo commerciale e la casella di controllo **Trova accordi commerciali** della pagina **Parametri di pianificazione generale** è selezionata, il lead time di consegna indicato nell'accordo commerciale non verrà preso in considerazione. I lead time vengono ricavati dalle impostazioni di copertura articoli o dall'articolo.
Questa modalità di evasione creerà piani con meno ritardi e meno ordini pianificati indipendentemente dal gruppo di copertura impostato per l'articolo. Nella figura seguente è illustrato il risultato del piano solo se il codice di copertura è **Fabbisogno** o **Periodo**.  
[![Fabbisogno. Periodo. Data odierna e lead time](./media/TodayPLTReq.png)](./media/TodayPLTReq.png) Nella figura seguente è illustrato il risultato del piano se il codice di copertura è **Min/Max**.  
[![MinMax. Data odierna e lead time](./media/TodayPLTMinMax.png)](./media/TodayPLTMinMax.png)
### <a name="first-issue"></a>Prima uscita 
La quantità minima specificata viene soddisfatta alla data in cui le scorte disponibili diminuiscono al di sotto del livello minimo, come illustrato nella figura seguente. Anche se le scorte disponibili sono inferiori al livello minimo alla data in cui viene eseguita la pianificazione principale, **Prima uscita** non tenterà di coprirlo finché non verrà introdotto il fabbisogno successivo.
Nella figura seguente è illustrato un esempio del codice di copertura **Fabbisogno**.
[![Pianificazione di un articolo con codice di copertura **Fabbisogno** ed evasione **Prima uscita**](./media/FirstIssueReq.png)](./media/FirstIssueReq.png) Nella figura seguente è illustrato un esempio del codice di copertura **Periodo**.
[![Pianificazione di un articolo con codice di copertura **Periodo** ed evasione **Prima uscita**](./media/FirstIssuePeriod.png)](./media/FirstIssuePeriod.png) Nella figura seguente è illustrato un esempio del codice di copertura **Min/Max**.
[![Pianificazione di un articolo con codice di copertura **MinMax** ed evasione **Prima uscita**](./media/FirstIssueMinMax.png)](./media/FirstIssueMinMax.png) Nella data in cui la pianificazione generale viene eseguita, se le scorte disponibili sono ancora nel limite di scorta di sicurezza, **Data odierna** e **Data odierna + tempo di approvvigionamento** attivano immediatamente il rifornimento. **Prima uscita** attenderà fino a quando non ci sarà un'altra transazione di uscita, come l'ordine cliente e il requisito della riga distinta base, per l'articolo, quindi attiverà il rifornimento alla data di questa transazione. Nella data in cui la pianificazione generale viene eseguita, se le scorte disponibili non rientrano nel limite delle scorta di sicurezza, **Data odierna** e **Prima uscita** forniranno esattamente lo stesso risultato, come illustrato nella figura seguente. 

[![NotUnderLimit](./media/ReqFirstIssue.png)](./media/ReqFirstIssue.png) Nella data in cui la pianificazione generale viene eseguita, se le scorte disponibili non rientrano nel limite delle scorte di sicurezza, **Data odierna + tempo di approvvigionamento** fornirà il seguente risultato, poiché pospone l'evasione fino alla fine del lead time di approvvigionamento.
![Pianificazione di un articolo con codice di copertura **Fabbisogno** ed evasione **Prima uscita**](./media/ReqTodayLT.png)
### <a name="coverage-time-fence"></a>Intervallo temporale di copertura
La quantità minima specificata viene soddisfatta durante il periodo di tempo specificato nel campo **Intervallo temporale di copertura**. Questa opzione è utile quando la pianificazione generale non consente di utilizzare le scorte disponibili per ordini reali, come vendite o trasferimenti, nel tentativo di mantenere il livello di sicurezza. Tuttavia, in una versione successiva, questa modalità di rifornimento non sarà più necessaria e questa opzione verrà rimossa.
## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Progettare il rifornimento delle scorte di sicurezza per gli articoli FEFO (First expired/First out)
In qualsiasi momento, l'entrata in magazzino con la data di scadenza più recente verrà utilizzata per le scorte di sicurezza per consentire che la domanda reale, ad esempio righe vendita o DBA, venga soddisfatta nell'ordine FEFO (First expired/First out).
Per mostrare come funziona, si consideri il seguente scenario:
[![FEFOScenario](./media/FEFOScenario.png)](./media/FEFOScenario.png) Quando viene eseguita la pianificazione, questa coprirà il primo ordine cliente con le scorte disponibili esistenti e un ulteriore ordine fornitore per la quantità rimanente.
[![FEFO1](./media/FEFO1.png)](./media/FEFO1.png) Un ordine pianificato viene creato in modo che le scorte disponibili siano riportate di nuovo al limite di sicurezza.
[![FEFO2](./media/FEFO2.png)](./media/FEFO2.png) Quando il secondo ordine cliente viene pianificato, l'ordine pianificato creato in precedenza che copre le scorte di sicurezza viene utilizzato per coprire questa quantità. Di conseguenza, le scorte di sicurezza vengono costantemente aggiornate.
[![FEFO3](./media/FEFO3.png)](./media/FEFO3.png) Infine, un altro ordine pianificato viene creato per coprire le scorte di sicurezza.
[![FEFO4](./media/FEFO4.png)](./media/FEFO4.png) Tutti i processi batch scadono di conseguenza e gli ordini pianificati vengono creati per rifornire le scorte di sicurezza dopo la scadenza.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Modalità di gestione della pianificazione generale per il vincolo delle scorte di sicurezza

Le scorte di sicurezza vengono registrate nel sistema come tipo di fabbisogno, come il fabbisogno delle righe di vendita o della DBA. È possibile visualizzare la riga fabbisogno delle scorte di sicurezza nella pagina **Fabbisogno netto** se si rimuove il filtro predefinito nella colonna **Tipo di requisito**.

L'evasione della transazione del fabbisogno di scorte di sicurezza perde priorità se il sistema determina che ciò causa ritardi nell'evasione della domanda reale, ad esempio righe di vendita, righe distinta base, requisiti di trasferimento o righe di previsione. In caso contrario, sei ci si accerta che le scorte disponibili siano superiori alla quantità di scorte di sicurezza, è possibile consentire che le scorte abbiano la stessa priorità di qualsiasi altro tipo di domanda. Ciò garantisce che non ci siano ritardi per le transazioni reali e aiuta a prevenire un eccesso di rifornimento e il rifornimento anticipato delle scorte di sicurezza.

Durante la fase di copertura della pianificazione generale, il rifornimento delle scorte di sicurezza non perderà più priorità. Le scorte disponibili in magazzino possono essere utilizzate prima di qualsiasi altro tipo di domanda. Durante il calcolo del ritardo, verrà aggiunta nuova logica per superare le righe di vendita con ritardo, il fabbisogno della riga DBA e tutti gli altri tipi di domanda, per determinare se possono essere consegnati in tempo, a condizione che vengano utilizzate le scorte di sicurezza. Se il sistema determina che può ridurre al minimo i ritardi usando le scorte di sicurezza, le righe di vendita o DBA sostituiranno la relativa copertura iniziale con le scorte di sicurezza e il sistema attiverà invece il rifornimento per le scorte di sicurezza.

Se il piano o l'articolo non è impostato per il calcolo con ritardo, il vincolo delle scorte di sicurezza avrà la stessa avrà priorità di eventuali altri tipi di domanda. Ciò significa che è presente una prenotazione delle scorte disponibili e di altre scorte disponibili prima di altri tipi di domanda.

