---
title: Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti
description: "In questo argomento viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a03b9aa61d754b47905d86114e0da29f1da64b81
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti

[!include[banner](includes/banner.md)]


In questo argomento viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record.

La funzionalità del flusso di lavoro per le risorse umane fornisce numerosi flussi di lavoro per la gestione delle attività delle risorse umane. Sono inoltre disponibili numerose opzioni per poter modificare flussi di lavoro specifici e associarli a una gerarchia di reporting. I flussi di lavoro sono disponibili per agevolare la gestione delle modifiche a vari tipi standard di informazioni sui dipendenti. È possibile associare un flusso di lavoro a una posizione. Quindi, se i dipendenti modificano i propri record dipendente, viene avviato un flusso di lavoro che richiede l'approvazione prima che le nuove informazioni vengano salvate. I flussi di lavoro sono predefiniti per i seguenti tipi di informazioni per consentire di gestire le modifiche in modo efficiente e garantire la precisione dei dati dei dipendenti.

-   Numeri di identificazione
-   Corsi
-   Percorso formativo
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
È possibile associare un flusso di lavoro con qualsiasi gerarchia che si configura. Ad esempio, se una posizione è associata una gerarchia di report di matrice, è possibile configurare un flusso di lavoro che indirizza le spese per un progetto specifico a un responsabile di progetto anziché al responsabile del dipendente associato alla posizione. Per creare un nuovo flusso di lavoro o modificare un flusso di lavoro esistente, nella pagina **Flusso di lavoro risorse umane**, fare clic su **Nuovo**. Selezionare un flusso di lavoro nell'elenco per avviare la finestra di progettazione del flusso di lavoro. È possibile utilizzare la finestra di progettazione per creare un nuovo flusso di lavoro o per modificare i passaggi in un flusso di lavoro esistente. Quando si modifica un flusso di lavoro esistente, le modifiche vengono salvate come una nuova versione. Di conseguenza, è possibile tornare sempre alla versione precedente, se necessario.

## <a name="configure-a-human-resources-workflow"></a>Configurare un flusso di lavoro delle risorse umane
Per configurare un flusso di lavoro di base che viene avviato quando i dipendenti richiedono modifiche alla propria identificazione personale, effettuare le seguenti operazioni.

1.  Nella pagina **Flussi di lavoro risorse umane**, fare clic su **Nuovo**.
2.  Nell'elenco di flussi di lavoro disponibili, selezionare **Numeri di identificazione**.
3.  Fare clic su **Esegui** per avviare la finestra di progettazione del flusso di lavoro, quindi immettere il nome utente e la password quando richiesto.
4.  Trascinare l'elemento **Approva numero di identificazione** dall'elenco degli elementi del flusso di lavoro nella canvas della finestra di progettazione.
5.  Collegare l'elemento di approvazione a **Inizio** e **Fine**.
6.  Fare doppio clic su **Approva elemento**, quindi fare clic con il pulsante destro del mouse e scegliere **Proprietà**.
7.  Per aggiungere istruzioni dell'elemento di lavoro, effettuare le operazioni indicate di seguito:
    1.  Selezionare **Assegnazione**, quindi selezionare **Gerarchia** nel tipo di assegnazione.
    2.  Nella selezione **Gerarchia**, selezionare **Gerarchia configurabile**.
    3.  Aggiungere una condizione di interruzione, quindi chiudere la pagina.

8.  Completare le eventuali istruzioni aggiuntive (non deve essere presente alcun avviso aggiuntivo).
9.  Fare clic su **Salva e chiudi**. Attivare il nuovo flusso di lavoro quando verrà visualizzata la finestra di dialogo, quindi selezionare **Rendi attivo**.
10. Passare a **Risorse umane** &gt; **Posizioni** &gt; **Tipi di gerarchia posizioni**.
11. Selezionare **Matrice**.
12. Aggiungere il flusso di lavoro **Numero di identificazione lavoratore** all'elenco.





