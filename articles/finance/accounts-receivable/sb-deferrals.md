---
title: Differimenti di ricavi e spese nella fatturazione abbonamento
description: Questo argomento spiega come impostare i differimenti di ricavi e spese nella fatturazione abbonamento.
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
ms.openlocfilehash: 9a12cf52d904db0396aa9914b8e324060289710f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690950"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Differimenti di ricavi e spese nella fatturazione abbonamento

Questo argomento spiega come impostare e usare i differimenti di ricavi e spese nella fatturazione abbonamento. I programmi di differimento sono sempre basati e dipendono da un documento di origine sottostante o da un programma di fatturazione. Poiché vengono creati in base ai valori predefiniti, non possono essere inseriti o creati separatamente.

Il processo di impostazione e utilizzo dei differimenti di riicavi e spese avviene in più pagine:

- Nella pagina **Parametri di differimento ricavi e spese** è possibile definire le preferenze dell'azienda.
- Nella pagina **Valori predefiniti di differimento** è possibile impostare i conti e i modelli predefiniti utilizzati per i programmi di differimento.
- Nelle pagine **Modelli di differimento** e **Modelli di differimento basati su eventi** è possibile definire i modelli utilizzati per i programmi di differimento.
- Nella pagina **Tutti i programmi di differimento** è possibile visualizzare e modificare qualsiasi programma di differimento.

I differimenti di ricavi e spese possono essere utilizzati insieme alla fatturazione contratto ricorrente.

## <a name="revenue-and-expense-deferral-parameters"></a>Parametri di differimento ricavi e spese

La **Parametri di differimento ricavi e spese** contiene i seguenti campi.

| Campo | Description |
|---|---| 
| Scheda **Programma** | |
| Uguale per periodo | <p>Specifica se il numero di giorni in un periodo viene utilizzato quando viene calcolato l'importo per periodo per un programma di differimento:</p><ul><li>**Sì** – L'importo per ciascun periodo è lo stesso, indipendentemente dal numero di giorni del periodo. I periodi parziali (come i periodi all'inizio o alla fine di un programma di differimento) saranno ripartiti proporzionalmente.</li><li>**No** – L'importo viene calcolato in base al numero di giorni di ogni periodo.</li></ul><p>È possibile ignorare questa impostazione a livello di transazione.</p> |
| Opzione di differimento sconto vendite | <p>Specifica se vengono creati programmi di differimento separati per lo sconto e gli importi dell'ordine cliente:</p><ul><li>**Programma separato per lo sconto** – L'importo dello sconto viene mantenuto separato dall'importo dei ricavi.<p>In questo caso, vengono creati due programmi di differimento quando viene creato un ordine cliente e quindi registrato. Gli importi degli sconti e dei ricavi verranno registrati in conti di differimento diversi.</p></li><li>**Unisci sconto con ricavi** – L'importo dello sconto viene combinato con l'importo dei ricavi. Viene creato un programma di differimento e sia l'importo dello sconto che l'importo dei ricavi vengono registrati nello stesso conto di differimento.<p>In questo caso, viene creato un programma di differimento quando viene creato un ordine cliente e quindi registrato. Sia l'importo dello sconto che l'importo dei ricavi vengono registrati nello stesso conto di differimento.</p></li></ul><p>**Nota:** Per applicare sconti agli articoli che utilizzano la funzione ricavi non fatturati, seleziona l'opzione **Programma separato per lo sconto**. Gli sconti possono quindi essere applicati a tutti gli articoli, indipendentemente dal fatto che venga utilizzata la funzione dei ricavi non fatturati. Se l'opzione **Unisci sconto con ricavi** è selezionata, non è possibile applicare sconti agli articoli che utilizzano la funzione ricavi non fatturati.</p> |
| Opzione di differimento sconto acquisti | <p>Specifica se vengono creati programmi di differimento separati per lo sconto e gli importi dell'ordine fornitore:</p><ul><li>**Programma separato per lo sconto** – L'importo dello sconto viene mantenuto separato dall'importo delle spese.<p>In questo caso, vengono creati due programmi di differimento quando viene creato un ordine fornitore e quindi registrato. Gli importi degli sconti e delle spese verranno registrati in conti di differimento diversi.</p></li><li>**Unisci sconto con ricavi** – L'importo dello sconto viene combinato con l'importo delle spese. Viene creato un programma di differimento e sia l'importo dello sconto che l'importo delle spese vengono registrati nello stesso conto di differimento.<p>In questo caso, viene creato un programma di differimento quando viene creato un ordine fornitore e quindi registrato. Sia l'importo dello sconto che l'importo delle spese vengono registrati nello stesso conto di differimento.</p></li></ul> |
| Consolida periodi precedenti | <p>Specifica se le righe programma di differimento per periodi precedenti sono consolidate:</p><ul><li>**Sì** – Se la data di inizio del differimento è in un periodo precedente alla data della transazione, tutti gli importi fino al periodo della data della transazione vengono combinati in un'unica riga del programma di differimento.</li><li>**No** – Gli importi di tutti i periodi sono mantenuti su righe del programma di differimento separate.<p>Se la data di inizio del differimento è nello stesso periodo o in un periodo successivo alla data della transazione, questa opzione non ha effetto.</p></li></ul><p>Questa impostazione può essere aggiornata al livello di transazione.</p> |
| Data di inizio differimento predefinita | <p>Seleziona la regola utilizzata per determinare la data di inizio del programma di differimento:</p><ul><li>**Data transazione**: utilizza la data di transazione come data di inizio.</li><li>**Inizio mese corrente** – Utilizza il primo del mese corrente come data di inizio. Se la data della transazione è il primo di un mese, il primo del mese corrente è la data di inizio.</li><li>**Inizio mese successivo** – Utilizza il primo del mese successivo come data di inizio. Se la data della transazione è il primo del mese, viene utilizzata la data della transazione. In caso contrario, viene utilizzato il primo del mese successivo.</li><li>**Regola del 15** – Se la data della transazione è compresa tra il primo e il quindici, utilizza come data di inizio il primo del mese in corso. Se la data della transazione è il sedici o dopo, usa il primo del mese successivo come data di inizio.</li></ul><p>Puoi aggiornare questa impostazione a livello di transazione.</p> |
| Metodo di differimento a breve termine | <p>Seleziona il metodo di differimento a breve termine: **Nessuno**, **Periodi di rolling**, o **Anno fisso**.</p><p>|
| Metodo di registrazione differimento | <p>Seleziona il metodo utilizzato per creare transazioni di differimento:</p><ul><li>**Stato patrimoniale** – Utilizza il metodo di registrazione stato patrimoniale per creare transazioni di differimento.</li><li>**Profitti e perdite**: utilizza il metodo di registrazione di profitti e perdite per creare transazioni di differimento. Quando le transazioni vengono registrate, è possibile esaminare il giustificativo fattura per visualizzare i movimenti aggiuntivi che bilanciano il riconoscimento iniziale e gli importi di contropartita del riconoscimento.</li></ul> |
| Storna profitti e perdite in avere | <p>**Nota:** Questo campo è disponibile solo quando il campo **metodo di registrazione differimento** è impostato su **Profitti e perdite**.</p><p>Specificare se gli importi di profitti e perdite vengono stornati quando uno storno, una terminazione o un rimborso viene applicato a un programma di fatturazione o a un ordine cliente:</p><ul><li>**Sì** – Storna gli importi di profitti e perdite e applica un importo di rettifica del credito al programma di differimento.<p>Se lo storno avviene a metà del periodo di fatturazione, gli importi vengono ripartiti proporzionalmente.</p></li><li>**No** – Non viene creata alcuna transazione di storno per i profitti e perdite quando uno storno, una terminazione o un rimborso viene applicato a un programma di fatturazione o a un ordine cliente.</li></ul> |
| Scheda **Riconoscimento** | |
| Registra automaticamente giornali di registrazione generali | <p>Specifica se i movimenti creati da differimenti di ricavi e spese vengono registrati automaticamente:</p><ul><li>**Sì** – I movimenti creati da differimenti di ricavi e spese vengono registrati automaticamente.<p>**Suggerimento:** Selezionando **sì**, puoi aiutare a prevenire incoerenze contabili causate da modifiche manuali ai giustificativi.</p></li><li>**No** – I movimenti creati da differimenti di ricavi e spese non vengono registrati automaticamente. Devi registrare manualmente ogni giornale di registrazione.</li></ul> |
| Riepilogo giornale di registrazione riconoscimenti | <p>Specifica se i giustificativi di riconoscimento sono consolidati per impostazione predefinita:</p><ul><li>**Sì** – Crea un unico giustificativo per tutte le righe di riconoscimento che hanno la stessa data. Tutte le righe di un giustificativo che hanno lo stesso conto vengono consolidate in un'unica riga.</li><li>**No** – Crea un giustificativo per ogni riga di riconoscimento.</li></ul><p>Puoi aggiornare questa impostazione nella pagina **Elaborazione riconoscimento**.</p> |
| Nome giornale di registrazione predefinito | Seleziona il nome del giornale di registrazione per i giornali che vengono creati da processi di differimento di ricavi e spese, come l'elaborazione del riconoscimento. |
| Descrizione della riga giornale di registrazione riconoscimenti | <p>Seleziona la descrizione che appare nella descrizione della riga del giustificativo del giornale di registrazione:</p><ul><li>**Date riga di programma** – Mostra le date della riga di programma nella descrizione della riga del giornale di registrazione.</li><li>**Dettagli transazione di origine** – Mostra le informazioni sulla transazione di origine nella descrizione della riga del giornale di registrazione.<p>**Esempio:** USMF-0001, CIV-00839, Ricavi software</p></li></ul> |
| Scheda **Sequenze numeriche** | Utilizza questa scheda per impostare i valori predefiniti per le sequenze numeriche di leasing. La procedura guidata di generazione della sequenza numerica viene utilizzata per generare e assegnare automaticamente le sequenze numeriche. Non è necessario modificare la sequenza numerica a meno che non vuoi apportare modifiche manuali alle sequenze numeriche generate. |
| Numero programmazione | Il numero che la sequenza utilizza per i programmi di differimento. |

## <a name="deferral-templates"></a>Modelli di differimento

Usa la pagina **Modelli di differimento** per definire i modelli a quote costanti utilizzati per i programmi di differimento.

Ecco alcuni dei vantaggi dell'utilizzo di un modello:

* La durata del differimento viene calcolata automaticamente.
* Consenti programmi di differimento con periodi in cui il riconoscimento viene ignorato.
* Puoi automatizzare i differimenti assegnando il modello a un prodotto, un gruppo di prodotti, una categoria di prodotti, clienti o un gruppo di clienti. L'assegnazione del modello viene eseguita dalla pagina **Valori predefiniti di differimento**.

Sono disponibili diverse frequenze di periodo per i modelli: periodi giornalieri, mensili o fiscali.

Le righe del modello sono costituite da un tipo (**Riconosciuto** o **Ignorato**) e dalla durata del periodo. Le righe ignorate hanno un importo pari a 0 (zero) nelle righe del programma di differimento. Questo comportamento può essere utile se non vuoi riconoscere i ricavi in tutti i periodi.

### <a name="create-a-deferral-template"></a>Creare un modello di differimento

Per creare un modello di differimento, completa i passaggi seguenti.

1. Nella pagina **Modelli di differimento**, seleziona **Nuovo**.
2. Nel campo **Modello** immetti un nome.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Frequenza periodo** seleziona la frequenza del periodo.
5. Seleziona **Aggiungi** per aggiungere una riga all'inizio dell'elenco di righe oppure seleziona **Aggiungi** per aggiungere una riga in fondo all'elenco.
6. Nel campo **Tipo** seleziona il tipo di periodo.
7. Nel campo **Durata periodo** specifica la durata del periodo.
8. Ripeti i passaggi da 5 a 7 per ogni ulteriore riga richiesta.
9. Seleziona **Salva**.

## <a name="deferral-defaults"></a>Valori predefiniti differimento

Usa la pagina **Valori predefiniti di differimento** per impostare i conti di differimento predefiniti per gli articoli e per assegnare modelli predefiniti agli articoli differibili. Puoi anche impostare conti di differimento per gli addebiti e assegnare i modelli agli addebiti differibili.

**Differimento per articolo**

Per le transazioni che contengono un articolo (ad esempio, ordini cliente), è possibile assegnare conti e modelli ad articoli e clienti specifici. Queste impostazioni verranno utilizzate come valori predefiniti quando una transazione viene differita. Per rendere la transazione differibile per impostazione predefinita, è necessario impostare gli articoli nella pagina **Articoli differibili**.

**Differimento per conto**

Per le transazioni che non hanno articoli (ad esempio, giornali di registrazione generali), è possibile specificare i conti di differimento. Quando questi conti vengono utilizzati su una riga di transazione, la transazione viene automaticamente contrassegnata come differita. Il modello e il conto di riconoscimento corrispondenti verranno assegnati alla riga della transazione.

**Tutti i tipi di transazione (ad esempio, nelle schede Ordine cliente, Acquisti e Giornale di registrazione generale)**

I conti nella pagina sono i conti principali che non hanno dimensioni finanziarie. Le dimensioni finanziarie del conto di riconoscimento provengono dal cliente o dall'articolo, in base all'organizzazione.

Ciascuna riga del modello deve avere un modello a quote costanti o un modello basato su eventi. Non può averli entrambi.

### <a name="for-sales-orders"></a>Per gli ordini cliente

Per specificare i valori predefiniti di differimento per gli ordini cliente, completa la seguente procedura.

1. Nella scheda **Ordine cliente** seleziona il tipo di differimento.
2. Seleziona **Aggiungi** per aggiungere una riga.
3. Nel campo **Codice articolo** seleziona il codice articolo. Il codice articolo determina come vengono applicati i valori predefiniti del differimento.
4. Specifica come viene applicato il codice articolo:

    * Se il campo **Codice articolo** è impostato su **Tabella** o **Gruppo**, seleziona la relazione articolo nel campo **Relazione articolo**.
    * Se il campo **Codice articolo** è impostato su **Categoria**, seleziona la relazione categoria in **Relazione categoria**.
    * Se il campo **Codice articolo** è impostato su **Tutto**, i valori predefiniti si applicano a tutti i record applicabili.

5. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto nel campo **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il conto si applica a tutti i record.

6. Nel campo **Conto principale** seleziona il conto principale per il differimento.
7. Se il campo **Metodo registrazione differimento** è impostato su **Profitti e perdite**, seleziona il conto ricavi iniziali nel campo **Conto ricavi iniziali** e il conto di contropartita ricavi nel campo **Conto di contropartita ricavi**.
8. Se il campo **Metodo di differimento a breve termine** è impostato su **Periodi di rolling** o **Anno fisso**, seleziona il conto di differimento a breve termine nel campo **Conto di differimento a breve termine**.
9. Per un modello, puoi selezionare **Aggiungi** per aggiungere una riga.
10. Nel campo **Codice articolo** seleziona il codice articolo.
11. Specifica come viene applicato il codice articolo:

    * Se il campo **Codice articolo** è impostato su **Tabella** o **Gruppo**, seleziona la relazione articolo nel campo **Relazione articolo**.
    * Se il campo **Codice articolo** è impostato su **Categoria**, seleziona la relazione categoria nel campo **Relazione categoria**.
    * Se il campo **Codice articolo** è impostato su **Tutto**, i valori predefiniti si applicano a tutti i record applicabili.

12. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto nel campo **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il conto si applica a tutti i record applicabili.
    * Seleziona il modello a quote costanti nel campo **Modello a quote costanti** o il modello basato su eventi nel campo **Modello basato su eventi**.

13. Seleziona **Salva**.

### <a name="for-purchase-orders"></a>Per gli ordini fornitore

Per specificare i valori predefiniti di differimento per gli ordini fornitore, completa la seguente procedura.

1. Nella scheda **Acquisti** seleziona il tipo di differimento.
2. Seleziona **Aggiungi** per aggiungere una riga.
3. Nel campo **Codice articolo** seleziona il codice articolo.
4. Specifica come viene applicato il codice articolo:

    * Se il campo **Codice articolo** è impostato su **Tabella** o **Gruppo**, seleziona la relazione articolo nel campo **Relazione articolo**.
    * Se il campo **Codice articolo** è impostato su **Categoria**, seleziona la relazione categoria nel campo **Relazione categoria**.
    * Se il campo **Codice articolo** è impostato su **Tutto**, i valori predefiniti si applicano a tutti i record applicabili.

5. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto nel campo **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il conto si applica a tutti i record applicabili.

6. Nel campo **Conto principale** seleziona il conto principale per il differimento.
7. Se il campo **Metodo registrazione differimento** è impostato su **Profitti e perdite**, seleziona il conto ricavi iniziali nel campo **Conto ricavi iniziali** e il conto di contropartita ricavi nel campo **Conto di contropartita ricavi**.
8. Se il campo **Metodo di differimento a breve termine** è impostato su **Periodi di rolling** o **Anno fisso**, seleziona il conto di differimento a breve termine nel campo **Conto di differimento a breve termine**.
9. Per un modello, seleziona **Aggiungi** per aggiungere una riga. 
10. Nel campo **Codice articolo** seleziona il codice articolo.
11. Specifica come viene applicato il codice articolo:

    * Se il campo **Codice articolo** è impostato su **Tabella** o **Gruppo**, seleziona la relazione articolo nel campo **Relazione articolo**.
    * Se il campo **Codice articolo** è impostato su **Categoria**, seleziona la relazione categoria nel campo **Relazione categoria**.
    * Se il campo **Codice articolo** è impostato su **Tutto**, i valori predefiniti si applicano a tutti i record applicabili.

12. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto in **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il conto si applica a tutti i record applicabili.
    * Seleziona il modello a quote costanti nel campo **Modello a quote costanti** o il modello basato su eventi nel campo **Modello basato su eventi**.

13. Seleziona **Salva**.

### <a name="for-general-journals"></a>Per i giornali di registrazione generali

Per specificare i valori predefiniti di differimento per i giornali di registrazione generali, completa la seguente procedura.

1. Seleziona la scheda **Giornale di registrazione generale**.
2. Per un differimento, seleziona **Aggiungi** per aggiungere una riga.
3. Se il campo **Metodo di differimento a breve termine** è impostato su **Periodi di rolling** o **Anno fisso**, seleziona il conto di differimento a breve termine nel campo **Conto di differimento a breve termine**.
4. Nel campo **Conto differimento** seleziona il conto differimento.
5. Nel campo **Conto riconoscimento** seleziona il conto riconoscimento.
6. Se il campo **Metodo registrazione differimento** è impostato su **Profitti e perdite**, seleziona il conto ricavi iniziali nel campo **Conto ricavi iniziali** e il conto di contropartita ricavi nel campo **Conto di contropartita ricavi**.
7. Seleziona il modello a quote costanti nel campo **Modello a quote costanti** o il modello basato su eventi nel campo **Modello basato su eventi**.
8. Seleziona **Salva**.

### <a name="for-free-text-invoices"></a>Per le fatture a testo libero

Per specificare i valori predefiniti di differimento per le fatture a testo libero, completa la seguente procedura.

1. Seleziona la scheda **Fattura a testo libero**.
2. Per un differimento, seleziona **Aggiungi** per aggiungere una riga.
3. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto nel campo **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il codice conto si applica a tutti i record applicabili.

4. Nel campo **Conto differimento** seleziona il conto differimento.
5. Se il campo **Metodo di differimento a breve termine** è impostato su **Periodi di rolling** o **Anno fisso**, seleziona il conto di differimento a breve termine nel campo **Conto di differimento a breve termine**.
6. Nel campo **Conto riconoscimento** seleziona il conto riconoscimento.
7. Se il campo **Metodo registrazione differimento** è impostato su **Profitti e perdite**, seleziona il conto ricavi iniziali nel campo **Conto ricavi iniziali** e il conto di contropartita ricavi nel campo **Conto di contropartita ricavi**.
8. Seleziona il modello a quote costanti nel campo **Modello a quote costanti** o il modello basato su eventi nel campo **Modello basato su eventi**.
9. Seleziona **Salva**.

### <a name="for-invoice-journals"></a>Per i giornali di registrazione fatture

Per specificare i valori predefiniti di differimento per i giornali di registrazione fatture, completa la seguente procedura.

1. Seleziona la scheda **Giornale di registrazione fatture**.
2. Per un differimento, seleziona **Aggiungi** per aggiungere una riga.
3. Specifica come viene applicato il codice conto:

    * Se il campo **Codice conto** è impostato su **Tabella** o **Gruppo**, seleziona la relazione conto nel campo **Relazione conto**.
    * Se il campo **Codice conto** è impostato su **Tutto**, il codice conto si applica a tutti i record applicabili.

4. Nel campo **Conto differimento** seleziona il conto differimento.
5. Se il campo **Metodo di differimento a breve termine** è impostato su **Periodi di rolling** o **Anno fisso**, seleziona il conto di differimento a breve termine nel campo **Conto di differimento a breve termine**.
6. Nel campo **Conto riconoscimento** seleziona il conto riconoscimento.
7. Se il campo **Metodo registrazione differimento** è impostato su **Profitti e perdite**, seleziona il conto ricavi iniziali nel campo **Conto ricavi iniziali** e il conto di contropartita ricavi nel campo **Conto di contropartita ricavi**.
8. Seleziona il modello a quote costanti nel campo **Modello a quote costanti** o il modello basato su eventi nel campo **Modello basato su eventi**.
9. Seleziona **Salva**.

### <a name="items-that-are-deferred-by-default"></a>Articoli differiti per impostazione predefinita

Usa la pagina **Articoli differiti per impostazione predefinita** per definire quali articoli sono differiti per impostazione predefinita. È possibile impostare i tipi di transazioni per cui gli articoli verranno differiti. È possibile specificare se viene differito un singolo articolo o un intero gruppo o categoria di articoli.

Quando imposti gli articoli come differiti, seleziona i conti e i modelli predefiniti nella pagina **Valori predefiniti di differimento**. Se i conti e i modelli non sono selezionati, le righe di transazione in cui sono presenti tali articoli non verranno differite.

Per gli articoli differiti in base alla categoria di vendita o acquisto a cui sono associati, le impostazioni di differimento si basano sulla categoria. Tuttavia, se la categoria non è selezionata nel campo **Relazione categoria** vengono utilizzate le impostazioni di differimento della categoria più alta in classifica. Ad esempio, aggiungi una categoria di vendita **Home video** ma non una categoria di vendita **Televisione**. Quando aggiungi un articolo di differimento associato alla categoria **Televisione** le impostazioni di differimento della **Home video** sono utilizzate per l'articolo.

### <a name="set-up-deferred-items"></a>Impostare gli articoli differiti

Per impostare gli articoli differiti per impostazione predefinita, completa la seguente procedura.

1. Nella pagina **Articoli differiti per impostazione predefinita** seleziona la scheda che desideri: **Ordine cliente** o **Acquisti**.
2. Seleziona **Aggiungi** per aggiungere una riga.
3. Nel campo **Codice articolo** seleziona il codice articolo.
4. Specifica come viene applicato il codice articolo:

    * Se il campo **Codice articolo** è impostato su **Gruppo** o **Tabella**, seleziona la relazione articolo nel campo **Relazione articolo**.
    * Se il campo **Codice articolo** è impostato su **Categoria**, seleziona la relazione categoria nel campo **Relazione categoria**.

5. Ripeti i passaggi da 2 a 4 per ogni ulteriore riga richiesta.
6. Seleziona **Salva**.

## <a name="deferred-charges"></a>Addebiti differiti

Usa la pagina **Addebiti di differimento** per definire quali addebiti sono differiti per impostazione predefinita.

> [!NOTE]
> * Attualmente, gli addebiti differibili sono disponibili solo per gli ordini cliente.
> * Gli addebiti possono essere differti solo a livello di riga. Per differire un addebito a livello di intestazione dell'ordine cliente, puoi impostare l'addebito come articolo differito su una riga separata dell'ordine cliente.
> * Per differire un addebito per una fattura a testo libero, è necessario inserire l'addebito come riga di fattura differita separata.
> * Questa funzionalità non è disponibile per gli addebiti di supporto e la funzionalità di suddivisione ricavi.

### <a name="set-up-deferred-charges"></a>Impostare gli addebiti differiti

Per impostare gli addebiti differiti, effettua le seguenti operazioni.

1. Nella pagina **Addebiti di differimento** seleziona **Aggiungi** per aggiungere una riga.
2. Nel campo **Codice addebito** seleziona il codice addebito.
3. Nel campo **Relazione addebito** seleziona la relazione addebito.
4. Ripeti i passaggi da 1 a 3 per ogni ulteriore riga richiesta.
5. Seleziona **Salva**.

## <a name="event-based-deferral-templates"></a>Modelli di differimento basati su evento

Usa la pagina **Modelli di differimento basati su eventi** per definire i modelli di differimento basati su eventi che è possibile utilizzare nelle transazioni di differimento e assegnare nella pagina **Valori predefiniti di differimento**.

### <a name="create-an-event-based-template"></a>Creare un modello basato su eventi

Per creare un modello di differimento basato su eventi, completa i passaggi seguenti.

1. Nella pagina **Modelli di differimento basati su eventi**, seleziona **Nuovo**.
2. Nel campo **Modello** immetti un nome univoco per il modello.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Tipo di allocazione** seleziona il tipo di allocazione:

    * **Importo variabile** – Alloca un importo specifico per ogni riga inserita.
    * **Importo uguale** – Alloca lo stesso importo per ogni riga inserita. 
    * **Percentuale** – Alloca un importo basato sul valore percentuale inserito per ciascuna riga.
    * **Percentuale di completamento** – Alloca un valore di completamento cumulativo per ciascuna riga immessa.
    * **Quantità variabile** – Alloca una quantità specifica per ogni riga inserita.

5. Imposta l'opzione **Crea eventi separati per unità** su **Sì** se vuoi che ogni riga di evento sia divisa equamente per il numero di unità nella transazione della fattura. Impostala su **No** se non vuoi dividere le righe dell'evento.
6. Nel campo **Conto scadenza** seleziona il conto scadenza.
7. Seleziona **Aggiungi** per aggiungere una riga all'inizio dell'elenco di righe oppure seleziona **Aggiungi** per aggiungere una riga in fondo all'elenco.
8. Nel campo **Descrizione** immetti una descrizione dell'evento.
9. Se il campo **Tipo di allocazione** è impostato su **Percentuale**, specifica la percentuale di allocazione nel campo **Percentuale di allocazione**. La percentuale deve essere un numero tra 0 (zero) e 100. Se lasci il campo **Percentuale di allocazione** vuoto, la percentuale è considerata 0. La somma di tutte le percentuali è mostrata nel campo **Percentuale totale** in fondo alla pagina e deve essere uguale a 100.
10. Nel campo **Mesi alla scadenza** specifica il numero di mesi di validità dell'evento. La data di scadenza del differimento della transazione viene inserita automaticamente in base a questo valore.
11. Seleziona la casella di controllo **Riconosci quando registrato** per riconoscere automaticamente i ricavi quando la transazione viene registrata. Se lasci deselezionata la casella di controllo, il ricavo deve essere riconosciuto manualmente.
12. Nel campo **Conto di riconoscimento**, seleziona il conto di riconoscimento per l'evento, se l'evento utilizza un conto diverso rispetto all'intera pianificazione del differimento. Questo campo viene utilizzato insieme alla casella di controllo **Riconosci quando registrato**.
13. Ripeti i passaggi da 7 a 12 per ogni ulteriore riga richiesta.
14. Seleziona **Salva**.
