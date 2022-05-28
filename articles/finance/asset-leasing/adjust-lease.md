---
title: Rettificare leasing
description: L'argomento spiega come rettificare un leasing. Potrebbe essere necessario una rettifica se i termini del leasing vengono modificati, il leasing viene prolungato o altre circostanze cambiano.
author: moaamer
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 89ec876c9bd967107635eb2955209a4dcb95cde5
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712176"
---
# <a name="adjust-leases"></a>Rettificare leasing

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

L'argomento spiega come rettificare un leasing. Potrebbe essere necessario una rettifica se i termini del leasing vengono modificati, il leasing viene prolungato o altre circostanze cambiano. Il leasing di cespiti è conforme alle linee guida fornite dagli standard Accounting Standards Codification Topic 842 (ASC 842) e International Financial Reporting Standard 16 (IFRS 16) sulle modifiche del leasing. ASC 842-20-15-1 definisce una modifica del leasing come qualsiasi modifica ai termini e alle condizioni di un contratto che causa una modifica dell'ambito o nella considerazione di un leasing. Il paragrafo 39 dell'IFRS 16 stabilisce che un conduttore deve rivalutare l'obbligazione sul leasingin modo che rifletta le modifiche ai canoni di leasing.

Per le organizzazioni che aderiscono ad ASC 842 o IFRS 16, un leasing viene rimisurato per riflettere una variazione del valore attuale dei canoni minimi futuri del leasing (PVFMLP). Se il PVFMLP aumenta, la scrittura contabile creata sarà un addebito sul conto Asset Right of use e un accredito sul conto obbligazione sul leasing per la differenza tra il nuovo PVFMLP e il PVFMLP precedente. Se il PVFMLP diminuisce, la scrittura contabile sarà un addebito sul conto obbligazione sul leasing e un accredito sul conto Asset ROU per la differenza.

Se la rettifica riduce l'Asset ROU oltre 0 (zero), il resto verrà accreditato sul conto di registrazione del guadagno sulla modifica del leasing specificato nella pagina **Conti di registrazione leasing**. Il sistema contabilizza queste transazioni e di altre voci di rettifica, quali modifiche alla classificazione, costi diretti iniziali, incentivi di leasing, pagamenti anticipati e costi di smantellamento derivanti da modifiche del leasing.

Per indicazioni specifiche sulle transazioni di rettifica del leasing, si consiglia di consultare IFRS 16 e l'ASC 842.

## <a name="lease-adjustment-wizard"></a>Rettifica guidata leasing

Per rettificare un leasing, completa i passaggi seguenti. I dati modificati aggiorneranno le pianificazioni di leasing dopo la pubblicazione dalla procedura guidata **Rettifica leasing**. Puoi salvare il tuo lavoro e chiudere la procedura guidata in qualsiasi momento, quindi tornare più tardi per riprendere il lavoro.

Per aprire la procedura guidata **Rettifica leasing** dal riepilogo leasing, segui questi passaggi.

1. Vai a **Leasing cespiti \> Leasing \> Riepilogo leasing**. 
2. Seleziona il leasing da modificare, quindi seleziona **Rettifica guidata**.
3. Segui le istruzioni della procedura guidata per inserire le modifiche richieste.

Per aprire la procedura guidata **Rettifica leasing** dalla pagina **Rettifiche leasing** per una rettifica già in corso, segui questi passaggi.

1.  Vai a **Leasing \> Leasing \> Rettifiche leasing**.
2.  Seleziona un leasing con stato rettifica **in corso** e quindi seleziona **Rettifica guidata**.
3.  Nei campi **Data di inizio modifica** e **Data registrazione** immetti le date appropriate.
4.  Selezionare **Avanti**.

    Il leasing è ora aggiunto alla pagina **Rettifiche leasing** dove puoi inserire le nuove informazioni.

    Dopo che il leasing è stato rettificato, ad esso si applicano i campi delle considerazioni right-of-use. Se al leasing modificato non sono associati costi diretti iniziali, incentivi di leasing, pagamenti anticipati o costi di smantellamento, lascia i corrispondenti campi vuoti. Gli importi originali non si applicheranno al leasing aggiornato. 

    Ad esempio, un locatore fornisce un incentivo di $1.000 per accettare un'estensione del leasing. In questo caso, quando modifichi il leasing per contabilizzare l'estensione, immetti **1.000** nel campo **Incentivi di leasing derivanti da rettifica**.

    Le righe dello scadenzario pagamenti ora mostrano tutti i pagamenti del mese e dei mesi successivi nel campo **Data di inizio modifica**. Poiché le modifiche sono potenziali, le righe dello scadenzario pagamenti non possono iniziare prima dell'inizio della modifica. Per visualizzare le righe dello scadenzario pagamenti precedenti alla data di inizio della modifica, vai alla pagina **Cronologia versioni leasing**.

8.  Selezionare **Avanti**.

    La pagina successiva mostra i dettagli chiave sulla rettifica del leasing prevista, come i valori di riporto dell'obbligazione sul leasing prima della modifica e la nuova obbligazione sul leasing dopo la modifica. La pagina mostra anche un'anteprima della scrittura contabile per la rettifica del leasing prevista.

9.  Seleziona **Invia a flusso di lavoro** per inviare la rettifica del leasing al sistema del flusso di lavoro se il flusso di lavoro della rettifica del leasing è attivo e la rettifica non è stata ancora approvata. Per ulteriori informazioni su come utilizzare il flusso di lavoro di rettifica del leasing, vedi [Utilizzare flussi di lavoro di rettifica del leasing](use-create-lease-wrkflw.md).

    > [!NOTE]
    > A questo punto, il sistema ricalcola le variabili di rettifica per verificare che non siano state registrate transazioni a fronte del leasing da quando sono stati calcolati per la prima volta la panoramica della rettifica e la scrittura contabile della rettifica. Se i valori cambiano, la griglia della panoramica delle rettifiche viene aggiornata ed è possibile rivedere le informazioni prima di inviare nuovamente le rettifiche del leasing al sistema del flusso di lavoro.

10. Se un flusso di lavoro non è attivo o se la rettifica del leasing è stata approvata, seleziona **Fine** per elaborare le modifiche e registrare la scrittura contabile di rettifica.

    > [!NOTE] 
    > A questo punto, il sistema ricalcola le variabili di rettifica per verificare che non siano state registrate transazioni a fronte del leasing da quando sono stati calcolati per la prima volta la panoramica della rettifica e la scrittura contabile della rettifica. Se i valori cambiano, la griglia della panoramica della rettifica viene aggiornata ed è possibile rivedere le modifiche prima di selezionare **Fine**. Se il flusso di lavoro è attivo e la rettifica del leasing è stata approvata, qualsiasi modifica alla panoramica della rettifica provocherà il ripristino dello stato di approvazione su **Non inviato**. In questo caso, è necessario inviare nuovamente la rettifica del leasing al sistema del flusso di lavoro.

    Nella pagina **Rettifiche leasing**, lo stato della rettifica è ora impostato su **Completato**.

    Nella pagina **Rettifiche leasing** è ancora possibile vedere le schede dettaglio **Panoramica rettifica** e **Anteprima voce di rettifica**. I dettagli del leasing e le informazioni sulla data vengono visualizzati nella cronologia delle versioni del leasing.

    Una nuova versione di leasing e un nuovo set di pianificazioni vengono ora creati utilizzando le informazioni modificate. 

13. Per visualizzare le nuove pianificazioni, vai al leasing, quindi seleziona **Libri**.
14. Per visualizzare lo scadenzario pagamenti appena generato, seleziona **Scadenzario pagamenti**.
15. Per visualizzare il nuovo piano di ammortamento dell'obbligazione sul leasing generato dalle nuove informazioni, chiudi la pagina **Scadenziario pagamenti** e apri il la pagina **Piano di ammortamento dell'obbligazione**.
16. Per visualizzare il piano di ammortamento dei cespiti appena generato, apri la pagina **Piano di ammortamento dei cespiti** dalla pagina **Dettagli libro**.
17. Per visualizzare la scrittura contabile di rettifica, seleziona **Giornali di registrazione \> Giornale di registrazione leasing cespiti**.

## <a name="cancel-a-lease-adjustment"></a>Annullare una rettifica del leasing

Per eliminare una rettifica del leasing in corso, attieniti alla seguente procedura.

1.  Vai a **Leasing \> Leasing \> Rettifiche leasing**.
2.  Seleziona la rettifica del leasing in corso da annullare.
3.  Seleziona **Annulla rettifica**. 
4.  Selezionare **OK**.

    > [!NOTE] 
    > Se selezioni **Annulla** nella procedura guidata **Rettifica leasing** ripristini la modifica più recente completata nella procedura guidata, ma non rimuovi una rettifica in corso.

## <a name="use-the-lease-adjustment-workflow"></a>Utilizzare il flusso di lavoro di rettifica del leasing

Questa sezione spiega come utilizzare il flusso di lavoro di rettifica del leasing. Il flusso di lavoro della rettifica del leasing consente di gestire le rettifiche del leasing in modo coerente fornendo una serie di passaggi di approvazione e assegnandoli a utenti specifici che approvano una rettifica del leasing prima che diventi definitiva. Dopo che la rettifica del leasing è stata approvata nel flusso di lavoro, è possibile utilizzare la procedura guidata **Rettifica leasing** per completare la rettifica del leasing.

1.  Per inviare una rettifica del leasing per l'approvazione, vai a **Leasing \> Leasing \> Rettifiche leasing**.
2.  Seleziona l'ID leasing della rettifica del leasing quindi seleziona **Rettifica guidata**.
3.  Nell'ultima pagina della procedura guidata, seleziona **Invia per approvazione**.
4.  Immetti un commento sulla rettifica quindi seleziona **OK**.

    Lo stato del flusso di lavoro diventa **In attesa di approvazione** e tutti i campi della procedura guidata sono bloccati per la modifica.

5.  Per approvare la rettifica del leasing, vai a **Leasing \> Leasing \> Rettifiche leasing**.
6.  Seleziona l'ID leasing della rettifica del leasing e rivedi le schede dettaglio **Panoramica rettifica** e **Anteprima voce di rettifica**.
7.  Seleziona **Flusso di lavoro \> Approvato**.

    Nella pagina **Rettifiche leasing**, lo stato del flusso di lavoro è ora impostato su **Approvato**. A questo punto, la rettifica del leasing è pronta per essere registrata tramite la scrittura contabile di rettifica.

8.  Per continuare a elaborare la rettifica del leasing e registrare la voce di rettifica, vai a **Leasing \> Leasing \> Rettifiche leasing**.
9.  Seleziona l'ID leasing della rettifica del leasing quindi seleziona **Rettifica guidata**.
10. Seleziona **Avanti** fino a raggiungere l'ultima pagina della procedura guidata, quindi seleziona **Fine**.

Il sistema ricalcola i valori di riporto del leasing per garantire che le variabili di rettifica approvate siano aggiornate. In caso di modifiche, lo stato di approvazione viene reimpostato su **Bozza** e dovresti inviare nuovamente la rettifica del leasing al sistema del flusso di lavoro.

## <a name="view-lease-versions"></a>Visualizzare le versioni del leasing

Se un leasing è stato rettificato, puoi visualizzarne le diverse versioni. Puoi inoltre visualizzare le pianificazioni storiche e i dettagli dei leasing precedenti.

1. Nella pagina **Riepilogo leasing**, seleziona il leasing, quindi, nel riquadro azioni, seleziona **Cronologia versioni leasing**.

    Se il leasing selezionato è stato rettificato, la pagina **Cronologia versioni leasing** mostra le diverse versioni. Il leasing originale è etichettato **1** e le versioni successive hanno un ordine numerico crescente.

    Per una versione di leasing selezionata, puoi visualizzare le dimensioni finanziarie, i dettagli del contratto, la posizione e le righe dello scadenzario pagamenti.

2. Per visualizzare i programmi storici, apri il leasing modificato dalla pagina **Riepilogo leasing**, seleziona il libro desiderato, quindi, nel riquadro azioni, seleziona **Cronologia versioni libro**.
3. Nella pagina **Versione libro** seleziona una versione e una programmazione da visualizzare.

## <a name="adjust-a-lease-book"></a>Rettificare un libro di leasing

Per rettificare solo un libro di leasing, segui questi passaggi.

1. Vai a **Leasing cespiti** \> **Leasing** \> **Riepilogo leasing**.
2. Seleziona e apri un leasing.
3. Nella pagina **Dettagli leasing**, seleziona **Libri**.
4. Nella pagina **Dettagli libri** del riquadro azioni, nel gruppo **Gestisci**, seleziona **Rettifica libro**. 
5. Rimuovi le righe di scadenzario pagamenti.
6. Nel campo **Data modifica leasing** immetti la data di modifica. Quindi prendi in considerazione la rimozione di tutte le considerazioni aggiuntive relative all'attività/passività (costo diretto iniziale, incentivo del leasing, pagamento anticipato del leasing, costo di smantellamento e garanzia del valore residuo), se presenti. 
7. Per evitare calcoli imprecisi per la rettifica del leasing, aggiungi nuove righe programma pagamenti per le nuove date di pagamento che corrispondono alla data di modifica. 

> [!NOTE] 
> Ti consigliamo di utilizzare la procedura guidata **Rettifica leasing** per rettificare un leasing. La procedura guidata riduce il numero di passaggi manuali, fornisce un'anteprima dei saldi dopo la rettifica e consente di modificare gli importi prima della registrazione.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
