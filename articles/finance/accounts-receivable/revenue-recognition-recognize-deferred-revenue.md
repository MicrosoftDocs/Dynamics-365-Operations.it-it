---
title: Riconoscimento dei ricavi differiti
description: In questo argomento vengono fornite informazioni su come riconoscere i ricavi utilizzando la funzionalità di riconoscimento ricavi.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f6b221104d7012d82a0021b6d8f9cc10fe44cb7b8f3473ab8e7ae7a89be0a5e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726112"
---
# <a name="recognize-deferred-revenue"></a>Riconoscimento dei ricavi differiti

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Il riconoscimento ricavi non può essere attivato tramite Gestione funzionalità. Per attivarlo, attualmente è necessario utilizzare le chiavi di configurazione.

In questo argomento viene descritto il processo di riconoscimento ricavi nella programmazione per il riconoscimento ricavi. Dopo la registrazione di una fattura per un ordine cliente, viene creata una programmazione per il riconoscimento ricavi per ciascuna riga dell'ordine cliente in cui è presente una programmazione dei ricavi. La programmazione dei ricavi in una riga viene utilizzata per determinare se i ricavi della riga devono essere differiti.

## <a name="view-revenue-recognition-schedule-details"></a>Visualizzare i dettagli di programmazione per il riconoscimento ricavi

Sono disponibili due modi per accedere ai dettagli della programmazione per il riconoscimento ricavi.

- È possibile aprire la programmazione per il riconoscimento ricavi direttamente da un ordine cliente fatturato. In questo caso, le informazioni nella programmazione dei ricavi vengono filtrate per visualizzare solo i dettagli relativi all'ordine cliente selezionato. Questo metodo è utile per convalidare i dettagli di programmazione per un ordine cliente.
- È possibile aprire la programmazione per il riconoscimento ricavi dalla pagina **Riconoscimento ricavi \> Attività periodiche**. Questo metodo è spesso utilizzato quando i ricavi vengono riconosciuti alla fine di un periodo. Quando la pagina viene aperta per la prima volta, non viene visualizzata alcuna informazione. Utilizzare i filtri sopra la griglia per definire i criteri dei dettagli di programmazione che devono essere visualizzati. È possibile filtrare le date di fatturazione immettendo un intervallo di date, un ordine cliente, un cliente, un ID progetto o uno stato.

[![Illustrazione della pagina Programmazioni ricavi.](./media/revenue-recognition-schedule-page.png)](./media/revenue-recognition-schedule-page.png)

La Scheda dettaglio **Dimensione finanziaria** sotto alla griglia mostra le dimensioni finanziarie della riga ordine cliente. Queste dimensioni sono state considerate durante la registrazione dei ricavi differiti. Sono anche considerate durante il riconoscimento ricavi. I valori di dimensione utilizzati dipendono dalla struttura dei conti assegnata ai conti principali dei ricavi e dei ricavi differiti.

## <a name="recognize-revenue"></a>Riconoscere ricavi

Per riconoscere i ricavi, eseguire il processo **Crea giornale di registrazione** dalla pagina **Riconosci ricavi**. È possibile aprire questa pagina dall'ordine cliente o da **Attività periodiche**. Se il processo viene eseguito dall'ordine cliente, i ricavi vengono riconosciuti solo per l'ordine cliente selezionato. In genere, il processo viene invece eseguito da **Attività periodiche**, in modo da riconoscere i ricavi per tutte le fatture degli ordini cliente registrate.

Per definire i criteri per la selezione e registrazione dei ricavi, selezionare **Crea giornale di registrazione** per aprire la finestra di dialogo **Crea giornale di registrazione**.

[![Creare opzioni per i parametri del giornale di registrazione.](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

Nella finestra di dialogo, utilizzare le opzioni del gruppo di campi **Data di elaborazione** per definire la data di registrazione utilizzata durante il riconoscimento ricavi. Se si seleziona **Data selezionata**, è possibile immettere una data di registrazione nel campo **Data della transazione**. Se si seleziona **Data di programmazione ricavi**, la data della transazione non viene utilizzata. In tal caso, il valore del campo **Data di riconoscimento** in ciascuna riga della programmazione viene utilizzato come data di registrazione.

A questo punto, nel campo **In data**, immettere la data di inizio per il riconoscimento ricavi. Verranno riconosciute tutte le righe della programmazione in cui la data di riconoscimento è anteriore o coincide con la data di inizio, purché non siano in attesa.

Dopo aver definito le date, selezionare **OK** nella finestra di dialogo per creare il giornale di registrazione. Viene visualizzato un messaggio informativo che mostra il numero di transazioni create e il giornale di registrazione in cui sono state create. Il giornale di registrazione non viene registrato automaticamente. Di conseguenza, il responsabile del riconoscimento ricavi ha la possibilità di verificare che le righe della programmazione vengano riconosciute.

Dopo aver eseguito il processo, le righe della programmazione che erano state trasferite nel giornale di registrazione vengono contrassegnate con lo stato **Elaborato**. Il flag **Elaborato** indica che le righe sono state trasferite nel giornale di registrazione, ma che possono essere registrate o non registrate. Dopo aver registrato il giornale di registrazione per il riconoscimento ricavi, continua a essere visualizzato il flag **Elaborato**. Se il giornale di registrazione per il riconoscimento ricavi viene eliminato o se una riga viene eliminata, il flag **Elaborato** viene rimosso. In questo modo, quando il processo **Crea giornale di registrazione** viene eseguito nuovamente, la riga può essere riconosciuta.

[![Pagina di programmazione del riconoscimento ricavi.](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Nella pagina **Giornale di registrazione per riconoscimento ricavi** (**Riconoscimento ricavi \> Scritture contabili \> Giornale di registrazione per riconoscimento ricavi**), aprire **Righe** per visualizzare i dettagli degli elementi riconosciuti. Per ogni riga della programmazione riconosciuta viene sempre creata una transazione separata, anche se tutte le righe sono registrate nella stessa data utilizzando gli stessi conti CoGe.

[![Pagina del giustificativo giornale di registrazione.](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

Nella colonna **Conto** viene visualizzato il conto CoGe dei ricavi differiti. Il conto CoGe non può essere modificato. Questa restrizione garantisce che il conto CoGe dei ricavi differiti venga sbloccato correttamente. Il conto CoGe non viene convalidato rispetto alla struttura dei conti perché può essere stato modificato in seguito all'ultima registrazione nel conto CoGe dei ricavi differiti.

Nella colonna **Conto di contropartita** viene visualizzato il conto CoGe dei ricavi. Per impostazione predefinita, il conto CoGe dei ricavi viene ottenuto dai profili di registrazione scorte e le dimensioni finanziarie vengono recuperate dalla riga ordine cliente. Il conto CoGe è convalidato rispetto alla struttura dei conti corrente. Tuttavia, può subire variazioni se la struttura dei conti è stata modificata e richiede dimensioni finanziarie aggiuntive.

L'Importo predefinito viene ottenuto dalla riga della programmazione corrispondente e non può essere modificato.

Per impostazione predefinita, se l'ordine cliente è multivaluta, viene impostato il tasso di cambio della fattura. In questo modo si garantisce che gli importi della valuta di contabilizzazione e della valuta di dichiarazione siano completamente sbloccati. Per motivi di arrotondamento, il tasso di cambio dell'ultima riga della programmazione può variare leggermente da quello della fattura.

Dopo aver registrato il giornale di registrazione per il riconoscimento ricavi, il giustificativo viene inserito nella programmazione. Se sono presenti più giustificativi per la stessa riga della programmazione, nella riga viene visualizzato un asterisco (\*). Per visualizzare i giustificativi registrati per quella riga, selezionare **Transazioni giustificativo**.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Modificare i dettagli di programmazione per il riconoscimento ricavi

La maggior parte dei dati contenuti nei dettagli di programmazione ricavi non possono essere modificati. Le nuove righe non possono essere aggiunte alla programmazione e le righe esistenti non possono essere eliminate. I dettagli di programmazione ricavi per ciascuna riga ordine cliente devono essere gestiti in modo tale da garantire che nel corso del tempo un'organizzazione possa riconoscere lo stesso importo che era stato differito.

### <a name="edit-schedule-lines"></a>Modificare righe programmazione

Nelle righe della programmazione sono consentite alcune modifiche. Nelle righe possono essere modificati i seguenti campi:

- **In attesa**: questo flag può essere impostato o rimosso prima che la riga venga elaborata. Per rimuovere il flag, selezionare la riga e fare clic su **Rimuovi sospensione**. I ricavi nelle linea in attesa non possono essere riconosciuti. È possibile mettere le righe automaticamente in attesa se nella programmazione dei ricavi vengono impostate le sospensioni automatiche.

    [![Programmazioni ricavi - modificare righe della programmazione.](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Data di riconoscimento**: la data di riconoscimento può essere modificata prima che la riga venga elaborata. Quando si esegue il processo che crea il giornale di registrazione per il riconoscimento ricavi, viene inserita una data nel campo **Riconosci ricavi a partire da**. Tale data viene confrontata con quella riportata nel campo **Data di riconoscimento** per determinare quali righe devono essere riconosciute.
- **Importo da rilasciare**: l'importo che verrà rilasciato può essere modificato prima che la riga venga elaborata. È possibile ridurre, ma non aumentare, l'importo dei ricavi riconosciuti. Questo campo consente a un'organizzazione di riconoscere una parte dei ricavi alla data di riconoscimento. Se l'importo viene modificato, l'importo nel campo **Importo rimanente** indica quanti ricavi devono essere ancora riconosciuti.
- **Quantità da rilasciare**: se la programmazione dei ricavi viene impostata per un'occorrenza o un mese, il campo **Quantità da rilasciare** indica la quantità per la riga ordine cliente. Questo campo può anche essere modificato e fornisce un altro metodo per riconoscere una parte dei ricavi. Ad esempio, se la quantità della riga è 5, è possibile sostituirla in modo che sia inferiore a 5. L'Importo nel campo **Importo da rilasciare** viene aggiornato proporzionalmente.

### <a name="update-contract-terms"></a>Aggiornare i termini del contratto

I dettagli della programmazione dei ricavi vengono creati in base alla programmazione dei ricavi assegnata alla riga ordine cliente quando viene registrata la fattura. Se la programmazione dei ricavi nella riga ordine cliente non è corretta, non può essere modificata nell'ordine cliente dopo che questo è stato fatturato. In tal caso, è necessario utilizzare il pulsante **Aggiorna termini del contratto** per modificare la programmazione dei ricavi. La programmazione dei ricavi può essere modificata prima o dopo il riconoscimento ricavi.

Per modificare la programmazione, selezionare una riga della programmazione per l'articolo che si intende modificare. Nella figura seguente viene selezionata la riga corrispondente all'articolo S0008, registrato utilizzando una programmazione dei ricavi di 12 mesi. Quando si seleziona **Aggiorna termini del contratto**, in una finestra di dialogo vengono visualizzate le date di inizio e fine del contratto e la programmazione dei ricavi.

[![Data di inizio e fine del contratto.](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Modificare la data di inizio e fine del contratto per riflettere l'intervallo di date corretto. Quando si modifica l'intervallo di date, il valore nel campo **Numero di occorrenze** deve corrispondere a una programmazione dei ricavi definita nel sistema. In questo esempio, poiché il contratto è stato modificato in un contratto di 24 mesi, occorre impostare una programmazione dei ricavi di 24 mesi. Poiché la programmazione dei ricavi di 24 mesi è disponibile, viene inserita per impostazione predefinita e il contratto può essere modificato. Se la programmazione dei ricavi con un numero corrispondente di occorrenze non è disponibile, il contratto non può essere modificato. Dopo aver aggiornato i termini del contratto e la programmazione dei ricavi in base alle esigenze, selezionare **OK** nella finestra di dialogo per salvare le modifiche.

[![Intervallo di date contratto aggiornato.](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

Modificare il contratto produce i seguenti effetti sui dettagli della programmazione dei ricavi:

- Se i ricavi del prodotto non sono stati riconosciuti, tutti i dettagli della programmazione precedente vengono rimossi e sostituiti con i dettagli della nuova programmazione. Ad esempio, inizialmente l'articolo S0008 aveva 12 righe nei dettagli della programmazione. Le 12 righe vengono rimosse e sostituite con 24 righe, in base alla nuova programmazione dei ricavi.
- Se i ricavi del prodotto sono stati riconosciuti, in alcuni casi il riconoscimento non è corretto poiché basato su una programmazione dei ricavi errata. Le righe devono essere stornate e riconosciute nuovamente, in base alla nuova programmazione. In questo scenario vengono create nuove righe di programmazione dei ricavi, con importi negativi alla data di riconoscimento originale. Le nuove righe vengono create per riconoscere gli importi basati sulla nuova programmazione dei ricavi. Ad esempio, l'8 agosto 2019 è stato riconosciuto un importo ricavi di $10,53. L'8 settembre 2019 è stato riconosciuto un importo ricavi di $13,16. Di conseguenza, vengono create due nuove righe nelle stesse date. Una riga per -$10,53 e l'altra per -$13,16. Vengono quindi create ventiquattro nuove righe, tra le quali allocare l'importo totale di $160,61 corrispondente ai ricavi differiti. È possibile registrare le righe di storno eseguendo il processo **Crea giornale di registrazione**.

[![Programmazione di riconoscimento ricavi.](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]