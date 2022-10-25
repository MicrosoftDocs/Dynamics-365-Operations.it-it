---
title: Area di lavoro della soluzione Invoice Capture
description: In questo articolo vengono fornite informazioni sull'area di lavoro della soluzione Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4f3af7abf94542437be6132344d6bb7ffaf33d07
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691196"
---
# <a name="invoice-capture-solution-workspace"></a>Area di lavoro della soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="side-by-side-viewer-for-the-invoice-capture-solution"></a>Visualizzazione affiancata per la soluzione Invoice Capture

L'inserimento delle fatture nel sistema è in genere un processo dispendioso in termini di tempo e soggetto a errori, poiché gli impiegati devono spostarsi tra più file allegati e finestre per raccogliere le informazioni corrette. La visualizzazione affiancata dei documenti contribuisce a migliorare la tua esperienza quando lavori sulle fatture, rendendo il processo più semplice, più efficiente e più accurato.

Il visualizzatore di documenti affiancati consente agli utenti di avere il documento originale e la fattura aperti fianco a fianco nella stessa finestra. La pagina della fattura è riempita con le informazioni che provengono dal documento di fattura originale. Il visualizzatore crea la connessione tra i campi della pagina della fattura e il documento di fattura originale. Il visualizzatore aiuta anche gli utenti a trovare eventuali errori presenti nella pagina della fattura.

### <a name="open-the-side-by-side-viewer"></a>Aprire la visualizzazione affiancata

In Microsoft Dynamics 365 Finance, è possibile aprire il visualizzatore affiancato dall'elenco nella pagina di riepilogo o dalla pagina elenco fatture. Puoi anche aprirlo toccando due volte (o facendo doppio clic) un record o selezionando il numero di fattura.

### <a name="using-the-side-by-side-viewer"></a>Utilizzo della visualizzazione affiancata

#### <a name="manually-review-an-invoice"></a>Esaminare manualmente una fattura

Un documento di fattura che è stato importato potrebbe richiedere la revisione manuale a causa di errori o avvisi. Nella visualizzazione affiancata, l'intestazione del documento mostrerà lo stato di **Importato** e la versione corrente sarà **Versione originale**.

Per iniziare a rivedere la fattura, seleziona **Inizia revisione**. Tutti i campi diventano modificabili. Il campo **Stato** è aggiornato a **In revisione** e il campo **Versione corrente** viene aggiornato a **Versione modificata**.

#### <a name="view-and-work-with-messages"></a>Visualizzare e utilizzare i messaggi

Gli utenti devono avviare il processo di revisione dal riquadro dei messaggi. I messaggi di errore sono indicati da una X rossa, i messaggi di avviso sono indicati da un triangolo e i messaggi informativi sono indicati da un cerchio. I messaggi relativi al punteggio di attendibilità possono essere classificati come avvisi o errori, a seconda della soglia impostata dal gruppo di configurazione. Per ulteriori informazioni, vedi [Gruppi di configurazione della soluzione Invoice Capture](invoice-capture-config-group.md).

I messaggi di avviso e di errore possono essere ignorati dal riquadro dei messaggi, dall'intestazione della fattura o dalle righe della fattura. Dopo che un messaggio è stato ignorato, non viene più visualizzato come errore o avviso e la convalida della fattura non viene completata.

- Per ignorare i messaggi dal riquadro dei messaggi, seleziona **Ignora**. Per reimpostare un messaggio che è stato ignorato, seleziona ancora **Ignora**. Il suo tipo viene quindi modificato da errore o avviso a informazione.
- Per ignorare i messaggi dall'intestazione della fattura o dalla riga della fattura, seleziona **Ignora** sul campo. Il simbolo del messaggio scompare. Tuttavia, riapparirà se il messaggio viene reimpostato dal riquadro dei messaggi.

Per i messaggi correlati ai campi dell'intestazione della fattura, quando si seleziona il messaggio nel riquadro dei messaggi, il cursore viene spostato sul campo corrispondente nella sezione dell'intestazione.

#### <a name="proofread-and-edit-fields"></a>Rivedi e modifica i campi

Se il valore di un campo viene letto dalla fattura originale tramite il riconoscimento ottico dei caratteri (OCR), sul campo viene visualizzato un simbolo. Se selezioni il simbolo, il visualizzatore di documenti ingrandisce ed evidenzia il punto da cui viene letto il valore del campo, per aiutarti a verificare i dati della fattura.

Per reimpostare l'ingrandimento originale del visualizzatore di documenti, procedi con uno di questi passaggi:

- Seleziona lo stesso simbolo che hai selezionato in precedenza.
- Selezionare il pulsante nell'angolo superiore destro del visualizzatore documenti.

Modifica i campi in base alle esigenze. Le modifiche vengono salvate automaticamente quando il cursore lascia un campo. Un simbolo a destra di un campo indica che il campo è stato aggiornato manualmente. Quando la pagina viene aggiornata, il simbolo verrà rimosso.

#### <a name="check-an-invoice-to-get-up-to-date-messages"></a>Controllare una fattura per ricevere messaggi aggiornati

Quando modifichi un campo, il valore del campo viene aggiornato, ma non vengono generati nuovi messaggi di convalida. Per ricevere messaggi di convalida aggiornati, seleziona **Controlla**. I messaggi nel riquadro dei messaggi, nell'intestazione della fattura e nelle righe della fattura vengono aggiornati.

#### <a name="complete-the-review"></a>Completare la revisione

Per completare la revisione, seleziona **Completa revisione**. Le fatture vengono convalidate. Se vengono rilevati errori, lo stato del documento rimane **In revisione** e viene visualizzata una barra dei messaggi. Tutti i messaggi nel riquadro dei messaggi e nell'intestazione e nelle righe della fattura vengono aggiornati automaticamente per fornire informazioni sulle cause della mancata convalida.

Dopo che tutti gli errori di blocco sono stati corretti, la revisione può essere completata. Lo stato del documento viene aggiornato a **Rivisto** e i campi non possono più essere modificati. È possibile riavviare la revisione selezionando ancora **Inizia revisione**.

#### <a name="generate-a-pending-vendor-invoice-in-finance"></a>Generare una fattura fornitore in sospeso in Finance

Per inviare il documento di fattura all'ambiente Finance connesso, seleziona **Genera**. Se la generazione della fattura non riesce, viene visualizzato un messaggio di errore in una barra dei messaggi.

#### <a name="void-an-invoice"></a>Annullare una fattura

Per annullare una fattura, seleziona **Annulla**. Le fatture annullate non possono essere esaminate e non vengono visualizzate nell'elenco **Fatture che necessitano di revisione manuale**.

### <a name="validation-logic"></a>Logica di convalida

Alcuni campi chiave nel visualizzatore affiancato non esistono nei dati di gestione temporanea delle fatture ma sono necessari per generare fatture in sospeso in Finance. Questi campi derivano da una combinazione dei dati di gestione temporanea delle fatture correnti e dei dati master di Finance.

I campi che devono essere derivati sono **Persona giuridica**, **Conto fornitore** e **Numero articolo**. Devono essere derivati nel seguente ordine. Se la derivazione di un campo non riesce, il processo si interrompe.

1. **Persona giuridica** – Viene prima derivata la persona giuridica. Se viene trovata una regola di mapping attiva per la persona giuridica, la persona giuridica viene derivata in base al nome e all'indirizzo della società.
2. **Conto fornitore** – Successivamente, il conto fornitore viene derivato in base a una regola di mapping attiva e a una combinazione della persona giuridica derivata e del nome e dell'indirizzo del fornitore.
3. **Numero articolo** – Infine, il nome dell'articolo è derivato dallo staging, sulla base dei seguenti tre tipi di informazioni:

    - Una regola di mapping configurata
    - Persona giuridica derivata
    - Conto fornitore derivato

Per eseguire una convalida, seleziona **Controlla** nel visualizzatore affiancato. Attualmente la convalida effettua i seguenti controlli:

- **Controllo obbligatorio** – Questo controllo convalida i campi obbligatori per il visualizzatore affiancato. Gli utenti possono selezionare quali campi devono essere obbligatori nella pagina **Impostazione di configurazione**.
- **Punteggio di attendibilità** – Gli utenti possono impostare la soglia di avviso e la soglia di errore per il punteggio di attendibilità. Questo controllo si concentra sul punteggio di attendibilità dell'OCR che è al di sotto di tali soglie. I messaggi di errore o di avviso verranno visualizzati in base al risultato della convalida.
- **Persona giuridica** – Questo controllo convalida che una persona giuridica sia in Finance. Se la persona giuridica non esiste nell'ambiente Finance, la convalida ha esito negativo.

Quando il visualizzatore affiancato viene utilizzato per la prima volta e l'utente seleziona **Controlla**, vengono eseguiti i processi di derivazione e convalida. Se le fatture sono accurate, il processo di convalida viene eseguito quando l'utente seleziona **Completa revisione**. Viene anche eseguito quando l'utente seleziona **Genera fattura fornitore**.

Il processo di derivazione si verifica prima del processo di convalida e tutti gli avvisi o gli errori provengono dal processo di convalida. Gli avvisi e gli errori verranno registrati in Finance.
