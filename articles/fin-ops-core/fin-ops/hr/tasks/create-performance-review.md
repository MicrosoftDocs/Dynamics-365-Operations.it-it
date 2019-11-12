---
title: Creare revisioni delle prestazioni
description: In questo argomento viene illustrato come creare una revisione delle prestazioni e descritto lo scopo per ogni sezione di revisione.
author: andreabichsel
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3583f974d1768e0efefb80f0ad8aa011669c1301
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178579"
---
# <a name="create-performance-reviews"></a>Creare revisioni delle prestazioni

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene illustrato come creare una revisione delle prestazioni e descritto lo scopo per ogni sezione di revisione. Questa procedura è stata creata utilizzando la società di dati dimostrativi USMF.

1. Nella home page, selezionare l'area di lavoro **Dipendente self-service**.
2. Selezionare **Nuova revisione** per creare una nuova revisione.
3. Nel campo **Tipo di revisione** immettere o selezionare un valore.
4. Nel campo **Periodo prestazioni** immettere o selezionare un valore.
5. Immettere una data nel campo **Data di fine**.
6. Selezionare **OK**. È inoltre possibile creare una revisione a partire da un modello. Si tratta del modo migliore per creare una revisione perché ogni sezione conterrà le informazioni necessarie per avviare una revisione.  
7. È possibile visualizzare o nascondere le schede come la scheda Allegati:

    1. Nel riquadro azioni, selezionare **Mostra sezioni** per aprire la finestra di dialogo a discesa.
    1. Selezionare **Sì** o **No** nel campo **Mostra allegati** per visualizzare o nascondere la scheda Allegati.
    1. Selezionare **Salva**.

8. Selezionare **Aggiungi obiettivo a revisione** per aggiungere un obiettivo. Al termine, selezionare **OK**.
9. Fare clic su **Aggiungi competenza** per aprire la finestra di dialogo a discesa.
10. Digitare un valore nel campo **Titolo**.
11. Nel campo **Descrizione**, immettere `Increase customer skills by working with the support team`.
12. Selezionare **OK**.
13. Selezionare **Comprimi tutto**.
14. Selezionare **Espandi tutto**.
15. Selezionare **Aggiungi commento**.
16. Selezionare **Registra**.
17. Selezionare la scheda **Misurazioni**.
18. Selezionare **Aggiungi misura** per aprire la finestra di dialogo a discesa.
19. Nel campo **Misura** immettere o selezionare un valore.
26. Nel campo **Importo di destinazione** immettere un numero.
20. Selezionare **OK**.
21. Selezionare la scheda **Attività**.
22. Selezionare **Aggiungi**.
23. Digitare un valore nel campo **Titolo**.
24. Digitare un valore nel campo **Descrizione**
25. Nel campo **Data di inizio**, immettere una data.
26. Immettere una data nel campo **Data di completamento**.
27. Selezionare **Sì** nel campo **Piano di sviluppo**.
28. Nel campo **Parole chiave** digitare un valore.
29. Selezionare **Salva**.
30. Selezionare la scheda **Valutazioni**.  

    - La Scheda dettaglio **Dettagli valutazione** consente ai dipendenti di valutare se stessi e il responsabile di valutare il dipendente. Se i pesi vengono utilizzati, il valore del peso dei punteggi verrà calcolato automaticamente.  
    - Per visualizzare questa sezione, è necessario abilitare le impostazioni dei parametri per la visualizzazione delle valutazioni del dipendente.  

31. Selezionare la scheda **Conferme**. Se la revisione utilizza il flusso di lavoro, le conferme verranno visualizzate solo dopo il flusso di lavoro viene completato. Se nessun flusso di lavoro è utilizzato, sia il lavoratore che il responsabile sono elencati qui. La casella di controllo richiesta viene selezionata in base alle impostazioni del tipo di revisione.  
32. Selezionare la scheda **Generale**.

    - Il periodo di prestazioni crea le date di inizio e fine predefinite. Quelle date sono modificabili.  
    - Gli stati consentono di controllare l'accesso alla revisione. Lo stato **Non avviato** consente a ognuno di modificare la revisione. Lo stato **In corso** consente solo al dipendente di visualizzare e modificare la revisione. Pronto per revisione consente solo al responsabile di visualizzare e modificare la revisione. Stato Revisione finale consente sia al dipendente che al responsabile di visualizzare e anche modificare la revisione se impostato nel tipo di revisione. Gli stati **Completato**, **Rifiutato** e **Annullato** rendono la revisione di sola lettura.  

33. Nel campo **Panoramica** digitare un valore.
34. Selezionare la scheda **Revisione**. Quando la revisione passa da uno stato all'altro, il dipendente e il responsabile possono aggiungere commenti per ciascun obiettivo o competenza.  
35. Selezionare la scheda **Conferme**. Il lavoratore e il responsabile possono confermare la revisione. Quando tutte le conferme necessarie sono state completate, lo stato diventa **Completato** e non è possibile apportare altre modifiche.  
