---
title: Utilizzare la funzionalità Messaggi elettronici
description: Questo articolo fornisce informazioni su come utilizzare la funzionalità dei messaggi elettronici (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b61c119a06e1a7281d3adb67e043d2f7002cbea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880703"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Utilizzo della funzionalità Messaggi elettronici

[!include [banner](../includes/banner.md)]

Se si lavora a livello del messaggio, la pagina **Messaggi elettronici** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Messaggi elettronici**) è più utile. Se si lavora a livello della raccolta di dati o dell'elemento del messaggio, la pagina **Elementi del messaggio elettronico** (**Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Elementi del messaggio elettronico**) è più utile.

## <a name="electronic-messages"></a>Messaggi elettronici

La pagina **Messaggi elettronici** presenta l'elaborazione disponibile, in base al ruolo. I ruoli di sicurezza sono associati all'elaborazione nella configurazione dell'elaborazione. Per ogni elaborazione disponibile, la pagina mostra i messaggi elettronici e le informazioni ad essi correlate.

La scheda Dettaglio **Messaggi** visualizza i messaggi elettronici per l'elaborazione selezionata. A seconda dello stato del messaggio selezionato e dell'elaborazione predefinita, è possibile eseguire alcune azioni utilizzando i pulsanti sopra la griglia:

- **Nuovo** - Questo pulsante è associato alle azioni **Crea messaggio**.
- **Elimina** - Questo pulsante è disponibile se la casella di controllo **Consenti eliminazione** è selezionata per lo stato corrente del messaggio selezionato.
- **Raccogli dati** - Questo pulsante è associato alle azioni di tipo **Popola record**.
- **Genera report** - Questo pulsante è associato alle azioni **Messaggio esportazione creazione di report elettronici**.
- **Invia report** - Questo pulsante è associato alle azioni **Servizio Web**.
- **Importa risposta** - Questo pulsante è associato alle azioni di tipo **Importazione creazione di report elettronici**.
- **Aggiorna stato** - Questo pulsante è associato alle azioni **Elaborazione utente livello del messaggio**.
- **Elementi del messaggio** - Apre la pagina **Elementi del messaggio elettronico**.

La scheda Dettaglio **Registro azioni** visualizza le informazioni su tutte le azioni eseguite per il messaggio selezionato. Se un'azione ha causato un errore, le informazioni sull'errore sono associate alla riga correlata nella griglia. Per esaminare le informazioni sull'errore, selezionare la riga nella griglia, quindi il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

La scheda Dettaglio **Campi aggiuntivi del messaggio** visualizza tutti i campi aggiuntivi definiti per i messaggi nella configurazione dell'elaborazione. La Scheda dettagli include inoltre i valori di quei campi aggiuntivi.

La scheda Dettaglio **Elementi del messaggio** visualizza tutti gli elementi del messaggio correlati al messaggio selezionato. A seconda dello stato dell'elemento del messaggio selezionato, è possibile eseguire alcune azioni utilizzando i pulsanti sopra la griglia:

- **Elimina** - Questo pulsante è disponibile se la casella di controllo **Consenti eliminazione** è selezionata per lo stato corrente dell'elemento del messaggio selezionato.
- **Aggiorna stato** - Questo pulsante è associato alle azioni di tipo **Elaborazione utente**.
- **Documento originale** - Aprire una pagina che visualizza il documento originale per l'elemento del messaggio selezionato.

I report che sono già stati generati e ricevuti per un messaggio sono collegati a tale messaggio. Per esaminare gli allegati correlati a un messaggio, selezionare il messaggio e quindi selezionare il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

![Pulsante Allegato](media/attachment-icon.png)

La pagina **Allegati** visualizza gli allegati correlati al messaggio selezionato. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro Azioni.

![Pulsante Apri](media/open-button.png)

È inoltre possibile esaminare gli allegati correlati a un'azione specifica eseguita in precedenza per un messaggio. Nella Scheda dettaglio **Messaggi** della pagina **Messaggi elettronici** selezionare il messaggio. Nella Scheda dettaglio **Registro azioni** selezionare l'azione, quindi il pulsante **Allegato** (simbolo della graffetta) nell'angolo in alto a destra della pagina.

È possibile eseguire l'intera elaborazione o solo una specifica azione selezionando **Esegui elaborazione** nel riquadro Azioni.

## <a name="electronic-message-items"></a>Elementi del messaggio elettronico

La pagina **Elementi del messaggio elettronico** mostra tutti gli elementi del messaggio e un registro delle azioni che sono state eseguite per ogni elemento del messaggio. La pagina mostra inoltre i campi aggiuntivi definiti per gli elementi del messaggio, nonché i valori di questi campi aggiuntivi.

Nella tabella seguente sono descritti i campi della scheda **Elementi del messaggio**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Elaborazione in corso</td>
<td>Il nome dell'elaborazione utilizzata per creare l'elemento del messaggio.</td>
</tr>
<tr>
<td>Elemento del messaggio</td>
<td>L'ID dell'elemento del messaggio. Questo ID viene assegnato automaticamente in base alla sequenza numerica <b>Elemento del messaggio</b> definita nella pagina <b>Parametri di contabilità generale</b>.</td>
</tr>
<tr>
<td>Data elemento del messaggio</td>
<td>La data di creazione dell'elemento del messaggio.</td>
</tr>
<tr>
<td>Tipo di elemento del messaggio</td>
<td>Il tipo di elemento del messaggio. Diversi tipi di elementi del messaggio possono essere configurati per la stessa elaborazione (ad esempio, <b>Fatture in entrata</b> e <b>Fatture in uscita</b>). Questo campo può essere impostato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Stato elemento del messaggio</td>
<td><p>Lo stato effettivo dell'elemento del messaggio. Gli stati disponibili variano a seconda del tipo di elemento del messaggio. Di seguito sono riportati alcuni esempi.</p>
<ul>
<li><b>Popolato</b> - Un record è stato aggiunto alla tabella Elementi del messaggio.</li>
<li><b>Valutato</b> - Ulteriori attributi sono stati calcolati per l'elemento del messaggio.</li>
<li><b>Dichiarato</b> - L'elemento del messaggio è stato aggiunto correttamente a un report.</li>
<li><b>Escluso</b> - Questo stato è utile se è necessario escludere alcuni elementi del messaggio da un report prima che venga esportato.</li>
</ul>
</td>
</tr>
<tr>
<td>Data di trasmissione</td>
<td>Per l'elaborazione che trasmette automaticamente un report generato al di fuori del sistema, la data in cui l'elemento del messaggio è stato trasmesso.</td>
</tr>
<tr>
<td>Numero documento</td>
<td>Questo campo viene impostato automaticamente in base alla configurazione dell'azione di popolamento record. Questo campo può essere impostato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Numero conto</td>
<td>Numero di conto di un cliente o di un fornitore oppure un altro valore del campo, a seconda del campo specificato nell'azione di popolamento di record. Questo campo può essere impostato automaticamente solo quando una fattura viene aggiunta alla tabella Elementi del messaggio.</td>
</tr>
<tr>
<td>Messaggio</td>
<td>Il numero del messaggio. Questo numero viene assegnato automaticamente in base alla sequenza numerica <b>Messaggio</b> definita nella pagina <b>Parametri di contabilità generale</b>.</td>
</tr>
<tr>
<td>Stato messaggio</td>
<td>Lo stato effettivo del messaggio elettronico.</td>
</tr>
<tr>
<td>Azione successiva</td>
<td>Le azioni successive che possono essere avviate per lo stato corrente dell'elemento del messaggio.</td>
</tr>
</tbody>
</table>

Nella scheda **Campi aggiuntivi** sono visualizzati i campi aggiuntivi per l'elemento del messaggio selezionato e i relativi valori.

### <a name="run-processing"></a>Esegui elaborazione

Nel riquadro Azione selezionare **Esegui elaborazione** per eseguire l'elaborazione per gli elementi del messaggio. Per eseguire un'azione specifica, nella finestra di dialogo **Esegui elaborazione**, impostare l'opzione **Scegli azione** su **Sì**, quindi selezionare un'azione. Per eseguire l'intera elaborazione, lasciare l'opzione **Scegli azione** su **No**.

### <a name="generate-report"></a>Genera report

Nel riquadro Azioni selezionare **Genera report**. Questo pulsante è associato alle azioni **Esportazione creazione di report elettronici**.

### <a name="update-status"></a>Aggiorna stato

Nel riquadro Azione selezionare **Aggiorna stato** per aggiornare lo stato di uno o più degli elementi del messaggio. Nella finestra di dialogo **Aggiorna stato**, utilizzare la scheda dettaglio **Record da includere** per selezionare gli elementi del messaggio da aggiornare. Assicurarsi di definire correttamente i criteri di selezione, poiché gli stati dell'elemento del messaggio verranno aggiornati in base a questi criteri, lo stato iniziale dell'azione selezionata e il valore specificato nel campo **Nuovo stato**. Dopo il completamento di un aggiornamento dello stato, risulterà difficile determinare quali elementi sono stati aggiornati. Di conseguenza, sarà difficile eseguire il rollback dell'aggiornamento dello stato.

### <a name="electronic-messages"></a>Messaggi elettronici

Nel riquadro Azioni scegliere **Messaggi elettronici** per esaminare un messaggio elettronico correlato all'elemento del messaggio selezionato.

È anche possibile esaminare tutti i file correlati a uno specifico elemento del messaggio. Selezionare il campo **Messaggio** per l'elemento del messaggio o nel riquadro Azione selezionare **Messaggi elettronici**. Nella pagina **Messaggio elettronico** selezionare il messaggio per esaminare i file e il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

La pagina **Allegati** visualizza gli allegati correlati al messaggio. Per visualizzare un file, selezionarlo nell'elenco a sinistra, quindi selezionare **Apri** nel riquadro azioni.

### <a name="original-document"></a>Documento originale

Nel riquadro Azioni selezionare **Documento originale** per aprire il documento originale per l'elemento del messaggio selezionato.
