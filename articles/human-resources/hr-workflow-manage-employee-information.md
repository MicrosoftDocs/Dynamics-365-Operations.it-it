---
title: Utilizzare flussi di lavoro per gestire le informazioni del dipendente
description: In questo articolo viene descritto come utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750736"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utilizzare flussi di lavoro per gestire le informazioni del dipendente

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo articolo viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record.

La funzionalità del flusso di lavoro per le risorse umane fornisce numerosi flussi di lavoro per la gestione delle attività delle risorse umane. Sono inoltre disponibili numerose opzioni per poter modificare flussi di lavoro specifici e associarli a una gerarchia di reporting. I flussi di lavoro sono disponibili per agevolare la gestione delle modifiche a vari tipi di informazioni sui dipendenti. È possibile associare un flusso di lavoro a una posizione. Quindi, se i dipendenti modificano i propri record dipendente, viene avviato un flusso di lavoro che richiede l'approvazione prima che le nuove informazioni vengano salvate. I flussi di lavoro sono predefiniti per i seguenti tipi di informazioni per consentire di gestire le modifiche in modo efficiente e garantire la precisione dei dati dei dipendenti.

-   Numeri di identificazione
-   Corsi
-   Formazione
-   Immagine
-   Articoli prestati
-   Esperienza professionale
-   Esperienza nel progetto
-   Competenze
-   Posizioni di fiducia
-   Azioni Risorse umane
-   Registrazione di corsi

Quando i dipendenti vengono assunti, trasferiti o licenziati, il flusso di lavoro può includere un processo di revisione. In questo modo, un documento può essere rivisto o i termini di un'azione possono essere definiti come parte del flusso di lavoro. Una volta completato il processo di revisione, l'azione o il documento viene completato e il flusso di lavoro passa a una fase di approvazione finale.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associare un flusso di lavoro a una gerarchia posizioni

È possibile associare un flusso di lavoro con qualsiasi gerarchia di posizione che si configura. Per l'instradamento del flusso di lavoro vengono utilizzati due tipi di gerarchia: **Manageriale** e **Configurabile**.

- Una gerarchia **Manageriale** rappresenta la struttura di creazione di report dell'azienda o dell'organizzazione. Per altre informazioni su questo tipo di gerarchia, vedi [Posizione Subordinato a](hr-personnel-positions.md#reports-to-position).
- Una gerarchia **Configurabile** rappresenta una matrice o una gerarchia personalizzata. Per altre informazioni su questo tipo di gerarchia, vedi [Relazioni](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Esempio di gerarchia manageriale

È consigliabile configurare un flusso di lavoro in modo che, quando un dipendente invia una richiesta di acquisto per un nuovo computer, la richiesta venga instradata al responsabile del dipendente e al responsabile di livello non direttamente superiore . Quando configuri il passaggio del flusso di lavoro, imposta il campo **Tipo di assegnazione** su **Gerarchia**. La scheda **Tipo di gerarchia** diventa quindi disponibile. Per questo esempio, seleziona la gerarchia **Manageriale**.

### <a name="configurable-hierarchy-example"></a>Esempio di gerarchia configurabile

Se una posizione è associata una gerarchia di report di matrice, puoi configurare un flusso di lavoro che indirizza le spese per un progetto specifico al capo del progetto anziché al responsabile del dipendente. In questo caso, imposta il campo **Tipo di assegnazione** su **Gerarchia**. Quindi, nella scheda **Tipo di gerarchia**, seleziona la gerarchia **Configurabile**. Dopo aver configurato il flusso di lavoro, seleziona la gerarchia **Associa** nella pagina **Impostazione flusso di lavoro** per selezionare la gerarchia da utilizzare per l'instradamento del flusso di lavoro.

> [!IMPORTANT]
> Quando un documento, una transazione o un record anagrafico viene inviato per l'approvazione del flusso di lavoro, la posizione principale dell'autore dell'invio verrà utilizzata per determinare a chi deve essere successivamente inoltrato il documento.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Impostazione della gerarchia nei parametri del flusso di lavoro

1. Nella pagina **Parametri del flusso di lavoro**, vai a **Percorsi di trasferimento della gerarchia**.
2. Per impostazione predefinita, l'opzione **Utilizza la gerarchia di posizioni** è impostata su **No**. In questo caso, il flusso di lavoro utilizzerà la posizione principale del lavoratore quando si sposta nella gerarchia. Imposta l'opzione su **Sì** per fare in modo che il flusso di lavoro utilizzi l'elemento padre della posizione quando si sposta nella gerarchia.

### <a name="additional-example"></a>Esempio aggiuntivo 

La dipendente Grace Sturman ha due posizioni: consulente e formatore. La posizione principale di Graces è quella di responsabile della formazione. Quando non sta formando nuovi dipendenti, è disponibile per lavori di consulenza. Attraverso la sua posizione principale, Grace fa capo a Claire, la direttrice delle risorse umane. Claire fa rapporto a Charlie. Per la sua posizione di consulente, Grace ha più relazioni tratteggiate, a seconda del progetto.

L'azienda di Grace crea regole di instradamento del flusso di lavoro basate su una gerarchia **Configurabile** (gerarchie basate su matrice/progetto). Questa gerarchia usa la posizione di consulente di Grace. Se l'opzione **Usa la gerarchia delle posizioni** è impostata su **No**, quando un documento viene inoltrato a Grace per la sua approvazione, il flusso di lavoro esaminerà la sua posizione principale (responsabile della formazione) per determinare dove il documento deve essere inviato successivamente. In questo caso, verrà indirizzato prima a Claire e poi a Charlie. Se l'opzione è impostata su **Sì** e il flusso di lavoro utilizza una gerarchia **Configurabile**, il flusso di lavoro esaminerà la posizione di consulente di Grace e la relazione di creazione di report per determinare dove il documento deve essere instradato successivamente.

### <a name="configure-a-human-resources-workflow"></a>Configurare un flusso di lavoro delle risorse umane
Per configurare un flusso di lavoro di base che viene avviato quando i dipendenti richiedono modifiche alla propria identificazione personale, effettuare le seguenti operazioni.

1.  Nella pagina **Flussi di lavoro risorse umane**, selezionare **Nuovo**.
2.  Nell'elenco di flussi di lavoro disponibili, selezionare **Numeri di identificazione**.
3.  Seleziona **Esegui** per aprire la finestra di progettazione del flusso di lavoro, quindi immettere il nome utente e la password.
4.  Sposta l'elemento **Approva numero di identificazione** dall'elenco degli elementi del flusso di lavoro nella canvas della finestra di progettazione.
5.  Collegare l'elemento di approvazione a **Inizio** e **Fine**.
6.  Toccare due volte (o fare doppio clic) **Approva elemento**, selezionare e tenere premuto (o fare clic con il pulsante destro del mouse), quindi selezionare **Proprietà**.
7.  Per aggiungere istruzioni dell'elemento di lavoro, effettuare le operazioni indicate di seguito:

    1.  Selezionare **Assegnazione**, quindi selezionare **Gerarchia** nel tipo di assegnazione.
    2.  Nella selezione **Gerarchia**, selezionare **Gerarchia configurabile**.
    3.  Aggiungere una condizione di interruzione, quindi chiudere la pagina.

8.  Completa tutte le istruzioni aggiuntive.
9.  Seleziona **Salva e chiudi**. Attivare il nuovo flusso di lavoro quando verrà visualizzata la finestra di dialogo, quindi selezionare **Rendi attivo**.
10. Passare a **Risorse umane** &gt; **Posizioni** &gt; **Tipi di gerarchia posizioni**.
11. Selezionare **Matrice**.
12. Aggiungere il flusso di lavoro **Numero di identificazione lavoratore** all'elenco.

## <a name="additional-resources"></a>Risorse aggiuntive

[Visualizzare e gestire le modifiche agli indirizzi](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
