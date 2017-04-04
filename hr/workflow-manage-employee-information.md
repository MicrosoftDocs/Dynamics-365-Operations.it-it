---
title: Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti
description: "In questo argomento viene descritto come utilizzare la capacità del flusso di lavoro per le risorse umane gestire le informazioni del dipendente. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti vengono modificati i relativi record."
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
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti

In questo argomento viene descritto come utilizzare la capacità del flusso di lavoro per le risorse umane gestire le informazioni del dipendente. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti vengono modificati i relativi record.

Capacità del flusso di lavoro per le risorse umane sono disponibili numerosi flussi di lavoro per la gestione delle attività di Risorse umane. Inoltre, numerose opzioni sono disponibili in modo da poter modificare i flussi di lavoro specifici e associarli è a una gerarchia di reporting. I flussi di lavoro sono disponibili per la gestione delle modifiche a vari tipi di informazioni dipendente. È possibile associare un flusso di lavoro con una posizione. Quindi, se i dipendenti vengono modificati i relativi record dipendente, un flusso di lavoro viene avviato cui è richiesta l'approvazione prima che le informazioni nuove salvate. I flussi di lavoro predefiniti per i seguenti tipi di informazioni per facilitare la gestione efficiente le modifiche e gestire i dati dei dipendenti con precisione:

-   Numeri di identificazione
-   Corsi
-   Percorso formativo
-   Immagine
-   Articoli prestati
-   Esperienza professionale
-   Esperienza nel progetto
-   Competenze
-   Posizioni di fiducia
-   Azioni di Risorse umane
-   Registrazione del corso

Quando i dipendenti vengono trasferiti i dipendenti, o vengono terminati, il flusso di lavoro può includere un processo di revisione. In questo modo, un documento può essere rettificate o i concetti di un'azione possono essere definiti come parte del flusso di lavoro. Quando il processo di revisione è stato completato, il documento oppure l'azione viene completato e i movimenti del flusso di lavoro in un approvazione deve essere a una fase.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associare un flusso di lavoro con una gerarchia posizioni
È possibile associare un flusso di lavoro con qualsiasi gerarchia che si configura. Ad esempio, se una posizione è associata una gerarchia di reporting a matrice, è possibile configurare un flusso di lavoro che indirizza le spese per un progetto specifico per il cliente potenziale di progetto anziché il manager del dipendente associato alla posizione. Per creare un nuovo flusso di lavoro o modificare un flusso di lavoro esistente, ** flusso di lavoro delle risorse umane ** nella pagina, fare clic su ** nuovo **. Selezionare un flusso di lavoro nell'elenco per avviare la finestra di progettazione del flusso di lavoro. È possibile utilizzare la finestra di progettazione per creare un nuovo flusso di lavoro o per modificare i passaggi in un flusso di lavoro esistente. Quando si modifica un flusso di lavoro esistente, le modifiche vengono salvate come nuova versione. Di conseguenza, è possibile tornare sempre alla versione precedente se necessario.

## <a name="configure-a-human-resources-workflow"></a>Configurare un flusso di lavoro di Risorse umane
Per configurare un flusso di lavoro di base che viene avviato quando i dipendenti è necessario apportare modifiche alla propria identificazione personale, effettuare le seguenti operazioni.

1.  ** Flussi di lavoro delle risorse umane ** alla pagina, fare clic su ** nuovo **.
2.  Nell'elenco di flussi di lavoro disponibili, selezionare ** numeri di identificazione **.
3.  Fare clic su ** esecuzione ** per avviare la finestra di progettazione del flusso di lavoro e quindi per il nome utente e password quando verrà richiesto.
4.  Trascinare ** approvare il numero di identificazione ** l'elemento dall'elenco degli elementi del flusso di lavoro nella canvas di progettazione.
5.  Collegare l'elemento di approvazione a ** ** inizio e fine ** **.
6.  Fare doppio clic ** approvare l'elemento ** quindi fare clic con il pulsante destro del mouse e scegliere ** proprietà **.
7.  Seguire questi passaggi per aggiungere istruzioni dell'elemento di lavoro:
    1.  Selezionare ** assegnazione ** quindi selezionare ** gerarchia ** nel tipo di assegnazione.
    2.  In ** gerarchia ** di selezione, selezionare ** gerarchia configurabile **.
    3.  Aggiungere una condizione di interruzione e chiudere la pagina.

8.  Eseguire tutte le istruzioni aggiuntive (avvisi non aggiuntiva devono esistere).
9.  Fare clic su **Salva e chiudi**. Attivare il nuovo flusso di lavoro quando Verrà visualizzata la finestra di dialogo e selezionare ** di intrattenere rapporti ** attivo.
10. Vanno ** Risorse umane ** &gt; ** le ubicazioni ** &gt; ** posizioni i tipi di gerarchie **.
11. Selezionare ** ** matrice.
12. Aggiungere ** numero di identificazione del lavoratore ** il flusso di lavoro all'elenco.



