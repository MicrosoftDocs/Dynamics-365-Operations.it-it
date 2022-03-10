---
title: Utilizzare flussi di lavoro per gestire le informazioni del dipendente
description: In questo argomento viene descritto come utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d80ed49a4f423179997ac35562284a4e28af803f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068087"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utilizzare flussi di lavoro per gestire le informazioni del dipendente


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo argomento viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record.

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
È possibile associare un flusso di lavoro con qualsiasi gerarchia che si configura. Ad esempio, se una posizione è associata una gerarchia di report di matrice, è possibile configurare un flusso di lavoro che indirizza le spese per un progetto specifico a un responsabile di progetto anziché al responsabile del dipendente associato alla posizione. Per creare un nuovo flusso di lavoro o modificare un flusso di lavoro esistente, nella pagina **Flusso di lavoro risorse umane**, selezionare **Nuovo**. Selezionare un flusso di lavoro nell'elenco per aprire la finestra di progettazione del flusso di lavoro. È possibile utilizzare la finestra di progettazione per creare un nuovo flusso di lavoro o per modificare i passaggi in un flusso di lavoro esistente. Quando si modifica un flusso di lavoro esistente, le modifiche vengono salvate come una nuova versione. Di conseguenza, è possibile tornare sempre alla versione precedente, se necessario.

## <a name="configure-a-human-resources-workflow"></a>Configurare un flusso di lavoro delle risorse umane
Per configurare un flusso di lavoro di base che viene avviato quando i dipendenti richiedono modifiche alla propria identificazione personale, effettuare le seguenti operazioni.

1.  Nella pagina **Flussi di lavoro risorse umane**, selezionare **Nuovo**.
2.  Nell'elenco di flussi di lavoro disponibili, selezionare **Numeri di identificazione**.
3.  Selezionare **Esegui** per aprire la finestra di progettazione del flusso di lavoro, quindi immettere il nome utente e la password quando richiesto.
4.  Trascinare l'elemento **Approva numero di identificazione** dall'elenco degli elementi del flusso di lavoro nella canvas della finestra di progettazione.
5.  Collegare l'elemento di approvazione a **Inizio** e **Fine**.
6.  Toccare due volte (o fare doppio clic) **Approva elemento**, selezionare e tenere premuto (o fare clic con il pulsante destro del mouse), quindi selezionare **Proprietà**.
7.  Per aggiungere istruzioni dell'elemento di lavoro, effettuare le operazioni indicate di seguito:

    1.  Selezionare **Assegnazione**, quindi selezionare **Gerarchia** nel tipo di assegnazione.
    2.  Nella selezione **Gerarchia**, selezionare **Gerarchia configurabile**.
    3.  Aggiungere una condizione di interruzione, quindi chiudere la pagina.

8.  Completare le eventuali istruzioni aggiuntive (non deve essere presente alcun avviso aggiuntivo).
9.  Seleziona **Salva e chiudi**. Attivare il nuovo flusso di lavoro quando verrà visualizzata la finestra di dialogo, quindi selezionare **Rendi attivo**.
10. Passare a **Risorse umane** &gt; **Posizioni** &gt; **Tipi di gerarchia posizioni**.
11. Selezionare **Matrice**.
12. Aggiungere il flusso di lavoro **Numero di identificazione lavoratore** all'elenco.

## <a name="additional-resources"></a>Risorse aggiuntive

[Visualizzare e gestire le modifiche agli indirizzi](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
