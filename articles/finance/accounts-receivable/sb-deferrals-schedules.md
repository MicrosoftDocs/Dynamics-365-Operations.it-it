---
title: Programmi di differimento in differimenti di ricavi e spese
description: Questo argomento descrive i programmi di differimento nei differimenti di ricavi e spese.
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
ms.openlocfilehash: 9135ac733496a0c5d79669c35972c273c209f81d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685979"
---
# <a name="deferral-schedules"></a>Programmazioni differimento

I programmi di differimento vengono creati dopo la registrazione di una transazione.

Puoi usare la pagina **Tutti i programmi di differimento** o **Programmi di differimento attivi** per rivedere i dettagli su un programma di differimento. Le informazioni visualizzate dipendono dal tipo di programma di differimento (a quote costanti o basato su eventi) e dal tipo di transazione. Include le righe del programma di differimento e gli importi totali per il programma di differimento. Puoi usare la pagina per modificare il programma di differimento.

## <a name="recognize-revenue"></a>Riconoscere ricavi

> [!NOTE]
> - Per riconoscere i ricavi per un programma di differimento, inizia dal passaggio 1.
> - Per riconoscere i ricavi per più programmi, inizia dal passaggio 2.

1. Nella pagina **Tutti i programmi di differimento**, nella griglia **Righe programma** seleziona le righe che vuoi riconoscere, quindi seleziona **Riconosci**.
2. Nella pagina **Elaborazione riconoscimento** imposta il campo **Azione di riconoscimento** su **Crea giornale di registrazione riconoscimenti**.
3. Nel campo **Data limite** seleziona la data limite. L'elaborazione includerà solo le righe in cui la data di fine è precedente o uguale alla data limite selezionata.
4. Seleziona **Filtro** e aggiungi i filtri di dati in modo che l'elenco mostri solo l'intervallo di record desiderato.
5. Seleziona **Visualizza anteprima** per visualizzare le righe.
6. Nell'elenco delle righe, seleziona le righe che non desideri elaborare, quindi seleziona **Rimuovi**.
7. Seleziona se vuoi riepilogare la scrittura contabile del riconoscimento.
8. Nella sezione **Data transazione** puoi sostituire la data della transazione con una data specifica per elaborare la transazione. La data della transazione può essere specificata per i periodi chiusi.
9. Per eseguire l'elaborazione come parte di un batch, seleziona **Batch**. Nella finestra di dialogo **Elaborazione batch** imposta i parametri per il batch e quindi seleziona **OK** per tornare alla pagina **Elaborazione riconoscimento**. Il riconoscimento dei ricavi verrà elaborato successivamente, quando il batch verrà elaborato.
10. Seleziona **Elabora**. Se non hai aggiunto la transazione a un batch, tutte le righe vengono elaborate immediatamente. In caso contrario, le righe verranno elaborate al momento dell'elaborazione del batch.

## <a name="modify-a-schedule"></a>Modificare un programma

Per modificare un programma di differimento, attieniti a questa procedura.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Contabilità \> Modifica programma**.
2. Nella pagina **Modifica programma** modifica le opzioni che desideri. A seconda del programma di differimento, non sarai in grado di modificare tutte le opzioni.
3. Seleziona **Anteprima** per esaminare le modifiche al programma di differimento.
4. Seleziona **OK**.

### <a name="straight-line-deferral-schedules"></a>Programmi di differimento a quote costanti

Se il programma di differimento non ha righe riconosciute o registrate esternamente, è possibile modificare l'intero programma di differimento, inclusa la data di inizio.

Se il programma di differimento contiene righe riconosciute o registrate esternamente e si modifica il programma di differimento, il comportamento risultante dipende dalla data di ricalcolo e dalla data di fine del differimento delle righe riconosciute. Per impostazione predefinita, il primo periodo non riconosciuto determina la data di fine del differimento.

Per utilizzare la data di riconoscimento, seleziona uno dei seguenti valori nel campo **Inizio del programma**: 
- **Recupero** – L'importo dopo il ricalcolo di tutte le righe riconosciute.
- **Storno** – Eventuali righe successive alla data di ricalcolo vengono stornate utilizzando il nome del giornale di registrazione e la data di registrazione specificati. L'importo dopo la data di ricalcolo viene quindi ricalcolato.

Se viene utilizzato un modello, i periodi saltati vengono ignorati e il modello viene utilizzato solo per calcolare la data di fine.

### <a name="event-based-deferral-schedules"></a>Programmi di differimento basati su eventi

Per un programma di differimento basato su eventi, è possibile modificare tutte le righe non riconosciute.

Se il programma di differimento non ha righe riconosciute o registrate esternamente, non è possibile modificare il tipo di modello o allocazione per il programma di differimento. Quando modifichi un programma di differimento esistente, non puoi modificare il valore del campo **Crea eventi separati per unità**.

Se una riga è riconosciuta o registrata esternamente, la casella di controllo **Riconosciuto** è selezionata.

## <a name="modify-a-deferral-or-recognition-account"></a>Modificare un conto di differimento o riconoscimento

Per modificare il conto di differimento o riconoscimento per un programma di diffferimento attieniti alla seguente procedura.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Contabilità \> Modifica conto**.
2. Nella pagina **Modifica conto** seleziona il conto che desideri modificare (differimento, a breve termine o riconoscimento).
3. Nel campo **Nuovo conto** seleziona il nuovo conto.
4. Seleziona se le modifiche al conto creano scritture contabili di rettifica.
5. Se si imposta l'opzione su **sì** nel passaggio precedente, seleziona il nome del giornale di registrazione nel campo **Nome giornale di registrazione** e specifica la data della transazione nel campo **Data transazione**.
6. Seleziona **OK**.

## <a name="put-a-deferral-schedule-on-hold"></a>Mettere in attesa un programma di differimento

Per mettere in attesa un programma di differimento, attieniti a questa procedura.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Attesa \> Metti in attesa**.
2. Nella pagina **Metti in attesa** seleziona se vuoi trasferire il saldo dal conto di differimento o dal conto in attesa.
3. Se ha selezionato di trasferire il saldo, seleziona il nome del giornale di registrazione nel campo **Nome giornale di registrazione**, seleziona il conto in attesa nel campo **Conto in attesa** e specifica la data della transazione nel campo **Data transazione**.
4. Seleziona **OK**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Rimuovere un'attesa da un programma di differimento

Per rimuovere un programma di differimento da un'attesa, attieniti alla seguente procedura.

1. Nell'elenco **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Attesa \> Rimuovi attesa**.
2. Seleziona il nome del giornale di registrazione nel campo **Nome giornale di registrazione**.
3. Nel campo **Data transazione** specifica la data della transazione.
4. Seleziona **OK**.

## <a name="cancel-unrecognized-amounts"></a>Annulla importi non riconosciuti

> [!NOTE]
> Eventuali righe già riconosciute o registrate esternamente sono escluse da questo processo.

Per annullare gli importi non riconosciuti in un programma di differimento, attieniti a questa procedura.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Annulla \> Importi non riconosciuti**.
2. Nella pagina **Annulla importo non riconosciuto** seleziona se vuoi creare voci di annullamento.
3. Se ha selezionato di creare le voci di annullamento, seleziona il nome del giornale di registrazione nel campo **Nome giornale di registrazione**, seleziona il conto di annullamento nel campo **Conto annullamento** e specifica la data della transazione nel campo **Data transazione**.
4. Seleziona **OK**.

## <a name="cancel-a-completed-schedule"></a>Annullare un programma completato

Usa la pagina **Tutti i programmi di differimento** per stornare eventuali importi riconosciuti o registrati esternamente e annullare il programma di differimento per impedire un ulteriore riconoscimento.

Per annullare l'intero programma di differimento, attieniti a questa procedura.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento, quindi seleziona **Annulla \> Programma completato**.
2. Nella pagina **Annulla programma completato** seleziona se vuoi creare voci di annullamento.
3. Se ha selezionato di creare le voci di annullamento, seleziona il nome del giornale di registrazione nel campo **Nome giornale di registrazione**, seleziona il conto nel campo **Conto annullamento** e specifica la data della transazione nel campo **Data transazione**.
4. Seleziona **OK**.

## <a name="reverse-transactions"></a>Storna transazioni

> [!NOTE]
> - Per stornare il riconoscimento ricavi per un programma di differimento, inizia dal passaggio 1.
> - Per stornare il riconoscimento ricavi per più programmi, inizia dal passaggio 2.

1. Nella pagina **Tutti i programmi di differimento**, nella griglia **Righe programma** seleziona le righe di cui vuoi annullare il riconoscimento, quindi seleziona **Storna**.
2. Nella pagina **Elaborazione riconoscimento** imposta il campo **Azione di riconoscimento** su **Storna giornale di registrazione riconoscimenti**.
3. Nel campo **Data limite** seleziona la data limite. L'elaborazione includerà solo le righe in cui la data di fine è precedente o uguale alla data limite specificata.
4. Seleziona **Filtro** e aggiungi i filtri di dati in modo che l'elenco mostri solo l'intervallo di record desiderato.
5. Seleziona **Visualizza anteprima** per visualizzare le righe.
6. Nell'elenco delle righe, seleziona le righe che non desideri elaborare, quindi seleziona **Rimuovi**.
7. I campi **Nome** e **Descrizione** vengono aggiornati automaticamente con il nome e la descrizione del giornale di registrazione predefiniti. Puoi modificare i valori come necessario. Puoi anche selezionare se riepilogare la scrittura contabile del riconoscimento.
8. Nella sezione **Data transazione** puoi sostituire la data della transazione con una data specifica per elaborare la transazione. La data della transazione può essere specificata per i periodi chiusi.
9. Per eseguire l'elaborazione come parte di un batch, seleziona **Batch**. Nella finestra di dialogo **Elaborazione batch** imposta i parametri per il batch e quindi seleziona **OK** per tornare alla pagina **Elaborazione riconoscimento**. Il riconoscimento dei ricavi stornati verrà elaborato successivamente, quando il batch verrà elaborato.
10. Seleziona **OK**. Se non hai aggiunto la transazione a un batch, tutte le righe vengono elaborate immediatamente. In caso contrario, le righe verranno elaborate al momento dell'elaborazione del batch.

## <a name="apply-or-unapply-a-credit-note"></a>Applicare o annullare una nota di credito

Per applicare una nota di accredito, completa i passaggi seguenti.

> [!NOTE]
> Quando crei una nota di credito dalla pagina **Differimento transazione ordine cliente** e imposti l'opzione **Modifica programma esistente** su **sì**, la nota di credito viene applicata automaticamente alla pianificazione al momento della registrazione.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento.
2. Nell'elenco **Rettifiche credito** seleziona una riga, quindi seleziona **Applica**.
3. Nella pagina **Applica nota di credito (differimenti)** specifica la data di ricalcolo nel campo **Data di ricalcolo** e la data di fine nel campo **Data di fine**.
4. Nell'elenco **Intestazione** seleziona l'**Ordine di vendita** con le note di credito.
5. Nell'elenco **Righe** seleziona la riga.
6. Seleziona **OK**.
7. Selezionare **Sì**.

> [!NOTE]
> Per applicare una nota di credito a più articoli singoli di fatture diverse, è necessario ripetere questi passaggi.

Per annullare l'applicazione di una nota di accredito, completa i passaggi seguenti.

1. Nella pagina **Tutti i programmi di differimento** seleziona il programma di differimento.
2. Nell'elenco **Rettifiche credito** seleziona la fattura, quindi seleziona **Annulla applicazione**.
3. Selezionare **Sì**.

## <a name="fields"></a>Campi

La pagina **Tutti i programmi di differimento** contiene i seguenti campi.

| Campi | Description |
|--------|-------------|
| **Intestazione** | |
| **Fissa appuntamento** | |
| Tipo di allocazione | Il tipo di allocazione, per i differimenti basati su eventi: **Percentuale** o **Importo**. |
| Data di riclassificazione | <p>La data più recente in cui è stata elaborata la riclassificazione a breve termine per un programma di differimento. Questa data viene aggiornata ogni volta che **Riclassificazione dell'evento a breve termine** viene utilizzato per il programma di differimento.</p>Questo campo è disponibile solo quando si utilizza il metodo di differimento a breve termine per periodi di rolling o anno fisso. |
| **Conto** | |
| Conto differimento | Il conto utilizzato per l'importo di differimento. |
| Conto riconoscimento | Il conto utilizzato per l'importo di riconoscimento. |
| Tipo di riconoscimento | Il tipo di riconoscimento. |
| Tipo di distribuzione | Il tipo di distribuzione. |
| **Transazione** | |
| Origine creazione | L'origine da cui la transazione è stata creata. |
| Tipo di transazione | Tipo di transazione. |
| Ordine cliente | Numero dell'ordine cliente. |
| Fattura | Numero di fattura. |
| Elemento | Il numero di articolo. |
| **Programmazione fatturazione** | |
| Numero programmazione fatturazione | Il numero del programma di fatturazione corrispondente. |
| Stato riga fatturazione | Lo stato della voce del programma di fatturazione corrispondente. |
| Riferimenti esterni | Informazioni sui riferimenti esterni dal programma di fatturazione: **Esterno** e **Numero riga**. |
| Totali | <p>Importi totali per il programma di differimento:</p><ul><li>**Lungo termine** – La somma degli importi differiti a lungo termine. Questo valore è disponibile solo quando il campo **Metodo di differimento a breve termine** è impostato su **Nessuno** nella pagina **Parametri di differimento ricavi e spese** o l'importo a breve termine è maggiore di 0 (zero).</li><li>**Breve termine** – La somma degli importi differiti a breve termine. Questo valore è disponibile solo quando il campo **Metodo di differimento a breve termine** è impostato su **Nessuno** nella pagina **Parametri di differimento ricavi e spese** o l'importo a breve termine è maggiore di 0 (zero).</li><li>**Non riconosciuto** – La somma degli importi non riconosciuti per tutte le righe.</li><li>**Sottoposto a stub** – La somma degli importi registrati esternamente per tutte le righe.</li><li>**Riconosciuto** – La somma degli importi riconosciuti per tutte le righe.</li><li>**Registrato e riconosciuto esternamente** – La somma degli importi registrati e riconosciuti esternamente per tutte le righe.</li><li>**Importo totale** – La somma degli importi per tutte le righe.</li></ul> |
| **Righe programmazione** | |
| Riga | Il numero della sequenza di riga. |
| Data di inizio differimento | La data di inizio del programma di differimento. |
| Data di fine differimento | La data di fine del programma di differimento. |
| Importo | Importo del differimento. |
| Registrato esternamente | Valore che indica se la riga è stata registrata esternamente. |
| Riconosciuto | Valore che indica se la riga è stata riconosciuta. |
| Numero batch giornale di registrazione | Il numero di batch in cui è stato riconosciuto l'importo. |
| Descrizione evento | Una descrizione dell'evento. Questo campo è disponibile solo per i programmi di differimento basati su eventi. |
| **Rettifiche credito** | |
| Fattura | <p>Numero di fattura.</p><p>Il valore indica la fattura per la rettifica della nota di credito che è stata già applicata al programma di differimento.</p> |
| Importo applicato | L'importo della rettifica del credito che è già stato applicato al programma di differimento. |
| Data di applicazione | Data di applicazione della rettifica del credito. |
| **Correzione** | I valori di rettifica vengono visualizzati solo se è stata elaborata una nota di credito per il programma di differimento. Se non è stata elaborata alcuna nota di credito, questi valori vengono nascosti. |
| Importo di rettifica | L'importo totale della rettifica, calcolato come *Importo originario* – *Importo programma*. |
| Data di fine originale | La data di fine originale del programma di differimento. |
| Importo programmazione originale | Il totale del programma di differimento originale. |
