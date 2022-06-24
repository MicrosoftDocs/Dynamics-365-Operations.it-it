---
title: Transazioni di differimento nella fatturazione abbonamento
description: In questo articolo vengono descritte le varie transazioni che possono essere utilizzate nelle transazioni di differimento come parte del differimento di ricavi e spese nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c3862f1a250bf8e56303975b5c6a3560cd84c1e7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872588"
---
# <a name="deferral-default-transactions"></a>Transazioni predefinite di differimento

In questo articolo vengono descritte le transazioni che consentono il differimento di ricavi e spese. I programmi di differimento sono sempre basati e dipendono da un documento di origine o da un programma di fatturazione. I programmi di differimento vengono creati in base ai valori predefiniti e non possono essere inseriti o creati separatamente.

## <a name="sales-order-transaction-deferral"></a>Differimento della transazione ordine cliente

Usa la pagina **Differimenti** o **Crea nota di credito** per immettere o modificare i parametri di differimento per una riga ordine cliente.

> [!NOTE]
> Quando un ordine cliente viene creato da un programma di fatturazione, tutti i valori nella pagina **Differimenti** o **Crea nota di credito** sono di sola lettura e i parametri di differimento non possono essere modificati. Per modificare i valori, utilizza la pagina **Modifica programma**.

### <a name="edit-deferral-options"></a>Modificare le opzioni di differimento

Per modificare le opzioni di differimento per una riga, completa la seguente procedura.

1. Crea una transaziione ordine cliente.
2. Seleziona la riga, quindi seleziona **Differimenti**.
3. Nella pagina **Differimento transazione** l'opzione **Differito** deve essere impostata su **sì**. Modifica altri campi secondo le necessità.
4. Seleziona **Anteprima** per visualizzare l'anteprima del programma di differimento.
5. Se hai apportato modifiche al differimento della transazione, seleziona **OK** e torna alla pagina della transazione.
6. Conferma e registra la transazione.

Dopo che la transazione è stata registrata, apri la pagina **Tutti i programmi di differimento** per visualizzare il programma di differimento.

### <a name="create-a-credit-note"></a>Creare una nota di accredito

Per creare una nota di accredito, completa i passaggi seguenti.

1. Crea una transaziione ordine cliente.
2. Nella sezione **Righe ordine cliente** seleziona l'articolo per il quale desideri creare una nota di credito.
3. Seleziona **Riga ordine cliente** \> **Nuovo**, quindi seleziona **Nota di credito**.
4. Seleziona **Differimenti**.
5. Nella pagina **Differimento transazione ordine cliente** imposta l'opzione **Rettifica programma esistente** su **sì** per l'articolo.
6. Nel campo **Programma rettificato** seleziona il programma di differimento a cui vuoi applicare la nota di credito.
7. Aggiorna i campi **Data di ricalcolo** e **Data di fine** come richiesto.
8. Seleziona **OK**.
9. Completa la registrazione della transazione dell'ordine cliente.

### <a name="purchase-orders-and-purchase-invoices"></a>Ordini fornitore e fatture di acquisto

Se desideri utilizzare la funzionalità di differimento per un ordine fornitore, genera prima la fattura. Quindi usa la pagina **Fatture fornitore in sospeso** per modificare o aggiungere articoli di differimento. Non puoi modificare o aggiungere differimenti direttamente in un ordine fornitore.

1. Usa la pagina **Fatture fornitore in sospeso** per inserire una fattura fornitore.

    Quando inserisci una riga, il differimento viene impostato automaticamente per l'articolo o la categoria di approvvigionamento selezionati. Questo differimento si basa sull'impostazione del differimento della pagina **Valori predefiniti di differimento**. I differimenti possono essere modificati o aggiunti a livello di distribuzione.

3. Nella riga di acquisto, seleziona **Dati finanziari \> Importi distribuzione**.
4. Per ogni importo di distribuzione, seleziona **Differimenti**. Quando la fattura viene registrata, viene creato un programma di differimento per ogni distribuzione per cui è impostato un differimento.

### <a name="tax"></a>Imposta

In alcuni casi, l'importo dell'imposta può essere in tutto o in parte non recuperabile. Se l'importo dell'imposta di una riga differibile contiene un importo non recuperabile, l'importo dell'imposta non recuperabile viene incluso nell'importo del programma differibile al momento della registrazione della fattura.

### <a name="variance"></a>Scostamento

Se l'importo nella riga della fattura fornitore è diverso dall'importo nella riga dell'ordine fornitore, vengono create le distribuzioni di scostamento. Se la riga è differita, il conto contabile per queste distribuzioni viene impostato sul conto di differimento e gli importi vengono inclusi nell'importo programma differibile al momento della registrazione della fattura. Queste distribuzioni sono denominate **Scostamento prezzi** e **Scostamento costi**.

### <a name="general-journals-and-invoice-journals"></a>Giornali di registrazione generali e giornali di registrazione fatture

Usa la pagina **Differimenti** per immettere i parametri di differimento per una riga di giustificativo del giornale di registrazione. Puoi anche visualizzare in anteprima il programma di differimento per i differimenti a quote costanti. Quando immetti una riga, il differimento viene impostato automaticamente in base all'impostazione dei conti di differimento della pagina **Valori predefiniti di differimento**. Puoi modificare manualmente le opzioni di differimento per ciascuna riga. Quando il giustificativo giornale di registrazione viene registrato, viene creato il programma di differimento.

#### <a name="post-and-transfer"></a>Registrare e trasferire

Per registrare il giustificativo del giornale di registrazione, utilizza il comando **Registra e trasferisci**. Le opzioni di differimento seguiranno la riga a cui si applica il giustificativo. Per i giustificativi che non presentano errori, viene creato un programma di differimento se è differito. Per un giustificativo che presenta un errore e viene trasferito, con esso vengono trasferite anche eventuali opzioni di differimento.

#### <a name="tax"></a>Imposta

In alcuni casi, l'importo dell'imposta può essere in tutto o in parte non recuperabile. Se l'importo dell'imposta di una riga differibile contiene un importo non recuperabile, l'importo dell'imposta non recuperabile viene incluso nell'importo del programma differibile al momento della registrazione della fattura.

## <a name="free-text-invoice-transaction-deferral"></a>Differimento della transazione fattura a testo libero

Usa la pagina **Differimenti** per immettere i parametri di differimento per una distribuzione riga di fattura a testo libero. Quando una distribuzione viene immessa, il differimento viene impostato automaticamente in base alle impostazioni di differimento della pagina **Valori predefiniti di differimento**.

## <a name="fields"></a>Campi

La pagina **Differimento transazione** contiene i seguenti campi.

| Campo | Description |
|-------|-------------|
| Differito | <p>Specifica se la riga è un differimento:</p><ul><li>**Sì** – La riga è un differimento.</li><li>**No** – La riga non è un differimento.</li></ul><p>Quando questa opzione è impostata su **sì**, l'opzione **Rettifica programma esistente** non è disponibile. Per gli articoli e gli addebiti già impostati come differiti, questa opzione è impostata su **sì**. Per gli articoli e gli addebiti che non sono impostati come differiti per impostazione predefinita, imposta questa opzione su **sì**.</p> |
| Rettifica programmazione esistente | <p>Specifica se la riga è una rettifica di un programma di differimento esistente:</p><ul><li>**Sì** – La nuova riga di vendita è una rettifica di un programma di differimento esistente. In questo caso, è possibile selezionare un programma di differimento nel campo **Programma rettificato**.</li><li>**No** – La nuova riga di vendita non è una rettifica di un programma di differimento esistente.</li></ul><p>Quando questa opzione è impostata su **sì**, l'opzione **Differito** non è disponibile.</p> |
| Programmazione rettificata | <p>Seleziona il programma di differimento che la riga sta rettificando. Tutti i valori nella pagina vengono quindi aggiornati con i valori del programma di differimento di origine. Questi valori non possono essere modificati.</p><p>Questo campo è disponibile solo quando l'opzione **Rettifica programma esistente** è impostata su **Sì**.</p> |
| Data di ricalcolo | <p>Specifica la data di inizio del periodo da cui vuoi ricalcolare l'importo residuo. La data predefinita è la data del successivo periodo non riconosciuto.</p><p>Questo campo è disponibile solo quando l'opzione **Rettifica programma esistente** è impostata su **Sì**.</p> |
| Data di fine | <p>A seconda del tipo di differimento, la data di fine potrebbe essere aggiornata o meno:</p><ul><li>Per un differimento a quote costanti, specifica la nuova data di fine del programma. La data di fine esistente del programma di differimento è il valore predefinito.</li><li>Per un differimento basato su evento, specifica la data di fine della riga dell'evento di credito. Questa data non è obbligatoria.</li></ul><p>Questo campo è disponibile solo quando l'opzione **Rettifica programma esistente** è impostata su **Sì**.</p> |
| Numero programmazione fatturazione | <p>Il numero del programma di fatturazione.</p><p>Questo campo è disponibile solo per i programmi di fatturazione del contratto ricorrenti.</p> |
| Metodo di rettifica differimento | <p>Il metodo di rettifica differita. Il valore corrisponde al valore della pagina **Elaborazione di terminazione di massa** per il programma di fatturazione del contratto ricorrente.</p><p>Questo campo è disponibile solo per i programmi di fatturazione del contratto ricorrenti.</p> |
| **Conti - Ricavi** | |
| Conto differimento | <p>Il conto di differimento, ovvero il contro di registrazione visualizzato nella pagina **Ordine cliente**.</p><p>Se la riga non è differita, questo campo è vuoto. In questo caso, il conto di registrazione è il conto ricavi predefinito.</p> |
| Conto riconoscimento | <p>Specifica il conto utilizzato quando viene riconosciuto un differimento. Questo conto deve essere diverso dal conto differimento.</p><p>Quando l'opzione **Differito** è inizialmente impostata su **sì**, i valori di dimensione utilizzati nel conto di differimento vengono copiati nel conto di riconoscimento. Se la dimensione nel conto di differimento non esiste per il conto di riconoscimento, viene ignorata.</p> |
| Conto riconoscimento iniziale | <p>Seleziona il conto per il riconoscimento iniziale dei ricavi. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Metodo di registrazione differita** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese**.</p> |
| Conto di contropartita riconoscimento | <p>Seleziona il conto per la contropartita del riconoscimento ricavi. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Metodo di registrazione differita** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese**.</p> |
| **Importi - Sconto** | Questa sezione viene visualizzata solo per gli articoli differiti. È nascosta per gli addebiti differiti. |
| Conto differimento | <p>Specifica il numero di conto di differimento sconto. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Opzione di differimento sconto** è impostato su **Programma separato per lo sconto** nella pagina **Parametri di differimento ricavi e spese** e viene applicato uno sconto sulla riga.</p> |
| Conto riconoscimento | <p>Specifica il numero di conto di riconoscimento sconto. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Opzione di differimento sconto** è impostato su **Programma separato per lo sconto** nella pagina **Parametri di differimento ricavi e spese** e viene applicato uno sconto sulla riga.</p> |
| Conto riconoscimento iniziale | <p>Seleziona il conto per il riconoscimento iniziale degli sconti. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **metodo di registrazione differimento** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese** e viene applicato uno sconto sulla riga.</p> |
| Conto di contropartita riconoscimento | <p>Seleziona il conto per la contropartita del riconoscimento ricavi. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **metodo di registrazione differimento** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese** e viene applicato uno sconto sulla riga.</p> |
| **Conti - Consumi** | Questa sezione viene visualizzata solo per gli articoli differiti. È nascosta per gli addebiti differiti. |
| Conto differimento | <p>Specifica il numero di conto di differimento consumo.</p><p>Per i prodotti standard vengono creati due programmi di differimento:</p><ul><li>**Vendite standard** – Un programma dei ricavi con un saldo a credito. In questo caso, seleziona il conto di differimento dei consumi.</li><li>**Consumo** – Un programma delle spese di consumo (costo del venduto \[COGS\]) con saldo a debito. In questo caso, seleziona il conto di riconoscimento dei consumi.</li></ul><p>Quando la fattura viene registrata, l'importo del consumo viene registrato nel conto di differimento del consumo specificato. Questi campi non sono disponibili per gli articoli di servizio.</p> |
| Conto riconoscimento | Specifica il numero di conto di riconoscimento consumo. |
| Conto riconoscimento iniziale | <p>Specifica il conto per l'importo di riconoscimento del consumo iniziale. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Metodo di registrazione differita** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese**.</p> |
| Conto di contropartita riconoscimento | <p>Specifica il conto per l'importo di contropartita riconoscimento del consumo. Il valore predefinito è dalla pagina **Valori predefiniti di differimento**.</p><p>Questo campo è disponibile solo quando il campo **Metodo di registrazione differita** è impostato su **Profitti e perdite** nella pagina **Parametri di differimento ricavi e spese**.</p> |
| **Fissa appuntamento** | |
| Tipo di programmazione | <p>Seleziona il tipo di programma di differimento: **A quote costanti** (predefinito) o **Basato su eventi**.</p><p>Le opzioni visualizzate nella pagina si basano sul tipo di programma di differimento selezionato.</p><p>Se il modello predefinito è impostato nella pagina **Valori predefiniti di differimento** per la riga della transazione, il tipo di programma di differimento è basato sul tipo di modello selezionato.</p> |
| **Programma - A quote costanti** | |
| Consolida periodi precedenti | <p>Specifica se desideri consolidare le righe programma di differimento per periodi precedenti:</p><ul><li>**Sì** – Consolida le righe programma di differimento per periodi precedenti.</li><li>**No** – Non consolida le righe programma di differimento per periodi precedenti.</li></ul><p>Il valore predefinito è dalla pagina **Parametri di differimento ricavi e spese**.</p> |
| Uguale per periodo | <p>Specifica se il numero di giorni in ogni periodo è uguale o varia in base al periodo:</p><ul><li>**Sì** – Ogni periodo ha lo stesso numero di giorni.</li><li>**No** – I periodi non hanno lo stesso numero di giorni.</li></ul><p>Quando questa opzione è impostata su **No**, il numero di giorni in un periodo viene considerato quando viene calcolato l'importo in ciascun periodo per un programma di differimento.</p><p>Il valore predefinito è dalla pagina **Parametri di differimento ricavi e spese**.</p> |
| Programmazione da modello | <p>Specifica se il programma di differimento viene creato in base a un modello o a una data di fine:</p><ul><li>**Sì** – Il programma di differimento viene creato in base a un modello.</li><li>**No** – Il programma di differimento viene creato in base a una data di fine.</li></ul> |
| Modello | Seleziona il modello di differimento. |
| Data di inizio sostituzione | <p>Specifica se vuoi sostituire la data di inizio:</p><ul><li>**Sì** – Sostituisci la data di inizio con la data che hai inserito nel campo **Data di inizio**.</li><li>**No** – La data di inizio è la regola **Data di inizio differimento predefinita** applicata alla data della fattura specificata nella pagina **Registrazione fattura**. Questa regole può essere impostata nella pagina **Parametri di differimento ricavi e spese**.</li></ul> |
| Data di inizio differimento | Specifica la data di inizio del differimento. La data della transazione è il valore predefinito. |
| Data di fine differimento | <p>La data di fine del differimento.</p><p>Questa data viene calcolata automaticamente in base al modello di differimento. Se non è selezionato alcun modello, è necessario inserire manualmente la data.</p> |
| **Programma - Basato su eventi** | |
| Modello | <p>Seleziona il modello basato su eventi. Questo campo è facoltativo.</p><p>Se selezioni un modello, i valori del modello sostituiscono tutti i dati basati su eventi e le righe degli eventi.</p> |
| Tipo di allocazione | <p>Seleziona il tipo di allocazione per le righe degli eventi:</p><ul><li>**Importi variabili** – Un importo di allocazione specifico viene immesso per ogni riga.</li><li>**Importi uguali** – L'importo è ripartito equamente per ciascuna riga.</li><li>**Percentuale** – Un importo viene allocato in base al valore percentuale inserito per ciascuna riga.</li><li>**Percentuale di completamento** – Viene immesso un valore di completamento cumulativo per ciascuna riga.</li><p>**Quantità variabile** – Una quantità di allocazion specifica viene immessa per ogni riga.</li></ul><p>**Nota:** Se vuoi selezionare **Percentuale di completamento**, le date devono essere in ordine crescente.</p> |
| **Crea eventi separati per unità** | |
| Description | <p>Specifica se desideri separare gli eventi per unità:</p><ul><li>**Sì** – Separa le righe degli eventi in modo che vi sia una riga per quantità.<p>Ad esempio, sono presenti tre righe di eventi e la fattura ha una quantità di quattro. In questo caso, il programma di differimento risultante ha 12 righe.</p></li><li>**No** – Non separare le righe degli eventi.</li></ul> |
| Conto scadenza | <p>Seleziona il conto utilizzato per le righe scadute riconosciute. È possibile selezionare il conto dopo aver creato il programma di differimento.</p><p>Se viene impostata una data di scadenza per un evento, durante il processo di riconoscimento, l'importo di riconoscimento va sul conto di scadenza anziché sul conto di riconoscimento.</p> |
| **Programma - Righe basate su eventi** | |
| Description | Una descrizione dell'evento. |
| Data di fine differimento | <p>Seleziona la data di fine dell'evento.</p><p>**Nota:** Se selezioni una data di fine, il campo **Data di scadenza** viene cancellato. Non puoi utilizzare sia una data di fine che una data di scadenza.</p> |
| Data di scadenza | <p>Seleziona la data di scadenza dell'evento.</p><p>**Nota:** Se selezioni una data di fine, il campo **Data di scadenza** viene cancellato. Non puoi utilizzare sia una data di fine che una data di scadenza.</p> |
| Quantity | <p>Specifica la quantità di allocazione. Il valore predefinito per tutte le righe è **0** (zero). Se aggiorni la quantità, la quantità totale di tutte le righe deve essere uguale o inferiore alla quantità specificata per la voce nell'ordine cliente.</p><p>Questo campo è disponibile solo quando il campo **Tipo di allocazione** è impostato su **Quantità variabile**.</p><p>Se la quantità della voce nell'ordine cliente viene modificata in modo che sia inferiore alla quantità originale e viene creata la fattura, vengono create meno righe basate su eventi. La quantità totale allocata non supera la quantità specificata nell'ordine cliente di origine o nel programma di fatturazione.</p> |
| Percentuale di allocazione | <p>Specifica la percentuale di allocazione. Se il campo **Tipo di allocazione** è impostato su **Percentuale** o **Percentuale di completamento**, puoi inserire manualmente una percentuale. In caso contrario, viene calcolata automaticamente.</p><p>Se il campo **Tipo di allocazione** è impostato su **Percentuale**, il totale delle percentuali deve essere 100.</p> |
| Importo | <p>Specifica l'importo di allocazione. Se il campo **Tipo di allocazione** è impostato su **Importi variabili** o **Percentuale di completamento**, puoi inserire manualmente un importo.</p><p>Se il campo **Tipo di allocazione** è impostato su **Percentuale di completamento**, e qui inserisci un importo, il valore del campo **Percentuale di completamento** viene calcolato automaticamente.</p><p>A causa dell'arrotondamento, l'importo calcolato potrebbe non corrispondere esattamente a quanto inserito manualmente. Se hai bisogno di un importo esatto, imposta il campo **Tipo di allocazione** su **Importi variabili**.</p> |
| Percentuale di completamento | <p>Specifica la percentuale di completamento. Il valore deve essere un numero tra 0 (zero) e 100.</p><p>Questo campo è disponibile solo quando il campo **Tipo di allocazione** è impostato su **Percentuale di completamento**.</p> |
| Importo completamento | <p>Il totale calcolato per tutte le righe nel programma di differimento.</p><p>Se il campo **Tipo di allocazione** è impostato su **Percentuale di completamento**, puoi inserire manualmente un importo. In questo caso, il valore del campo **Percentuale di completamento** viene calcolato in base all'importo immesso.</p><p>A causa dell'arrotondamento, l'importo calcolato potrebbe non corrispondere esattamente a quanto inserito manualmente.</p><p>Questo campo è disponibile solo quando il campo **Tipo di allocazione** è impostato su **Percentuale di completamento**.</p> |
| Riconoscimento al momento della registrazione | <p>Specifica se la riga viene riconosciuta automaticamente non appena la transazione viene registrata:</p><ul><li>**Selezionato** – La riga viene riconosciuta automaticamente non appena la transazione viene registrata.</li><li>**Deselezionato** – La riga non viene riconosciuta non appena la transazione viene registrata.</li></ul> |
| Conto riconoscimento | <p>Specifica il conto di riconoscimento per l'evento, se il conto è diverso dal conto utilizzato per l'intero programma di differimento.</p><p>È possibile utilizzare questo campo insieme all'opzione **Riconoscimento al momento della registrazione**.</p> |
