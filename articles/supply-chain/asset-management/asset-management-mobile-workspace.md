---
title: Area di lavoro mobile Gestione cespiti
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 525f21d076027f1bf339e59fd0e346706044839c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430976"
---
# <a name="asset-management-mobile-workspace"></a>Area di lavoro mobile Gestione cespiti

[!include [banner](../../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'area di lavoro mobile Gestione cespiti. Questa area di lavoro consente agli utenti di visualizzare e creare richieste di manutenzione e ordini di lavoro. Gli utenti possono inoltre visualizzare i processi di ordine di lavoro assegnati in una visualizzazione elenco o del calendario. È inoltre possibile visualizzare e eseguire ricerche di cespiti e unità funzionali.


## <a name="overview"></a>Panoramica

Gestione cespiti è un modulo avanzato per gestire i cespiti e i processi di ordine di lavoro in Dynamics 365 Supply Chain Management. L'area di lavoro mobile **Gestione cespiti** consente agli utenti di visualizzare rapidamente i processi di ordini di lavoro assegnati sul dispositivo mobile desiderato. Gli utenti possono inoltre creare e gestire richieste di intervento di manutenzione, aggiornare lo stato del ciclo di vita e visualizzare dettagli relativi all'unità funzionale e ai cespiti utilizzando il proprio dispositivo mobile.

Nello specifico, l'area di lavoro mobile **Gestione cespiti** consente agli utenti di eseguire queste attività:

- Creare, visualizzare e modificare richiesta di intervento di manutenzione, scattare una foto o associare un'immagine esistente alla richiesta di intervento di manutenzione, modificare lo stato del ciclo di vita della richiesta di intervento di manutenzione. 
- Creare, visualizzare e modificare ordini di lavoro, scattare una foto o associare un'immagine esistente all'ordine di lavoro, modificare lo stato del ciclo di vita dell'ordine di lavoro, visualizzare i processi di ordine di lavoro.
- Visualizzare processi di ordine di lavoro assegnati in una visualizzazione calendario.
- Creare, visualizzare e modificare processi di ordini di lavoro, aggiornare contatori di cespiti, visualizzare l'elenco di controllo di manutenzione, visualizzare e modificare note relative ai processi di ordine di lavoro, visualizzare gli strumenti necessari per il processo di ordine di lavoro.
- Visualizzare o cercare uno specifico cespite o unità funzionale.


## <a name="prerequisites"></a>Prerequisiti

I prerequisiti variano a seconda della versione di Dynamics 365 Supply Chain Management distribuita per l'organizzazione.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-supply-chain-management"></a>Prerequisiti se si utilizza Microsoft Dynamics 365 Supply Chain Management 
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 Supply Chain Management, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Gestione cespiti**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili
Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:

- [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile
1. Avviare l'app sul dispositivo mobile.

2. Immettere il proprio URL Dynamics 365.

3. La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.

4. Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

![Figura 1](media/am-mobile-01.png)


## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Visualizzare processi di ordine di lavoro assegnati in una visualizzazione calendario

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Calendario processi ordine di lavoro personali**.

3. Selezionare la data per la quale visualizzare processi di ordine di lavoro. Nell'elenco, verrà visualizzato l'ID cespite e l'ID unità funzionale per ogni processo di ordine di lavoro.

4. Selezionare un processo di ordine di lavoro nell'elenco per visualizzare dettagli sui processi: informazioni su cespiti e unità funzionale nonché altri collegamenti di navigazione per visualizzare **Allegati**, **Liste di controllo**, **Strumenti**, **Contatori cespiti**, **Note**, **Giornali di registrazione**.

![Figura 2](media/am-mobile-02.png)


## <a name="create-a-work-order-job"></a>Creare un processo di ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro per cui creare un nuovo processo di ordine di lavoro.

4. Selezionare il pulsante **Aggiungi riga**.

5. Selezionare il **cespite** per cui si desidera creare un nuovo processo di ordine di lavoro.

6. Selezionare **Tipo di processo di manutenzione**, **Variante tipo di processo di manutenzione** e **Settore**.

7. Selezionare **Fine**.

![Figura 3](media/am-mobile-03.png)


## <a name="add-attachment-to-a-work-order-job"></a>Aggiungere un allegato a un processo di ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro > il processo di ordine di lavoro a cui si desidera aggiungere un allegato.
    - In alternativa, è anche possibile selezionare **Calendario processi ordine di lavoro personale** o **Elenco processi ordine di lavoro personale** nella home page **Dettagli processo di ordine di lavoro**.

4. Selezionare **Allegati** nella pagina **Dettagli processo di ordine di lavoro**.

5. Gli allegati esistenti saranno visualizzati nel processo di ordine di lavoro. Selezionare **Aggiungi allegato**.

6. Immettere **Nome** e **Note** per l'allegato.

7. Selezionare **Scegli immagine** per selezionare una foto dalla gallery nel dispositivo mobile o **Scatta foto** per scattare una foto.

8. Selezionare **Fine**.

![Figura 4](media/am-mobile-04.png)


## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Visualizzare l'elenco di controllo di manutenzione in un processo di ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro > il processo di ordine di lavoro per il quale si intende visualizzare gli elenchi di controllo.
    - In alternativa, è anche possibile selezionare **Calendario processi ordine di lavoro personale** o **Elenco processi ordine di lavoro personale** nella home page **Dettagli processo di ordine di lavoro**.

4. Selezionare **Elenchi di controllo** nella pagina **Dettagli processo di ordine di lavoro**.

5. Viene visualizzato un elenco delle righe dell'elenco di controllo correlate al processo di ordine di lavoro. Selezionare una riga dell'elenco di controllo per visualizzare **Istruzioni** e aggiungere **Note**.

6. Selezionare il pulsante Indietro (**<**) per tornare alla pagina precedente.

![Figura 5](media/am-mobile-05.png)


## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Visualizzare e aggiornare contatori di cespiti in un processo di ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro > il processo di ordine di lavoro per il quale si intende visualizzare contatori di cespiti.
    - In alternativa, è anche possibile selezionare **Calendario processi ordine di lavoro personale** o **Elenco processi ordine di lavoro personale** nella home page **Dettagli processo di ordine di lavoro**.

4. Selezionare **Contatori cespiti** nella pagina **Dettagli processo di ordine di lavoro**.

5. Viene visualizzato un elenco di contatori di cespiti correlati al processo di ordine di lavoro. Selezionare l'icona matita in una riga del contatore di cespiti per aggiornare il valore del contatore.

6. Immettere un nuovo valore per il contatore e selezionare **Fatto**.

![Figura 6](media/am-mobile-06.png)


## <a name="register-consumption-on-a-work-order-job"></a>Registrare il consumo di un processo di ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro > il processo di ordine di lavoro per il quale si intende aggiungere registrazioni del consumo.
    - In alternativa, è anche possibile selezionare **Calendario processi ordine di lavoro personale** o **Elenco processi ordine di lavoro personale** nella home page **Dettagli processo di ordine di lavoro**.

4. Selezionare **Giornali di registrazione** nella pagina **Dettagli processo di ordine di lavoro**.

5. Selezionare **Aggiungi ore** per creare registrazioni delle ore di lavoro.
    1. Selezionare la **categoria** nella ricerca.
    2. Nel campo **Ore**, immettere il numero di ore lavorative dedicate al processo di ordine di lavoro.
    3. Selezionare la **proprietà di riga** appropriata.
    4. Selezionare **Fine**.

6. Selezionare **Aggiungi articoli** per creare registrazioni di articoli.
    1. Selezionare **Numero articolo** nella ricerca.
    2. Selezionare il **sito** nella ricerca.
    3. Immettere la **quantità** di articoli consumati.
    4. Selezionare **Fine**.

7. Selezionare **Aggiungi spesa** per creare registrazioni di spese.
    1. Selezionare la **categoria** nella ricerca.
    2. Immettere la quantità per la registrazione di spese.
    3. Selezionare la **valuta di vendita** nella ricerca
    4. Immettere il **prezzo di costo** per la registrazione delle spese.
    5. Selezionare **Fine**.

![Figura 7](media/am-mobile-07.png)


## <a name="update-lifecycle-state-on-a-work-order"></a>Aggiornare lo stato del ciclo di vita di un ordine di lavoro

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutti gli ordini di lavoro di manutenzione**.

3. Selezionare l'ordine di lavoro per il quale si desidera aggiornare lo stato del ciclo di vita.

4. Selezionare il pulsante **Aggiorna stato** nella parte inferiore dello schermo.

5. Selezionare un nuovo stato del ciclo di vita dall'elenco.

6. Selezionare **Fine**.

![Figura 8](media/am-mobile-08.png)


## <a name="create-a-maintenance-request"></a>Creare una nuova richiesta di intervento di manutenzione

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutte le richieste di intervento di manutenzione**.

3. Selezionare **Azioni** nella parte inferiore della schermata e quindi **Creare richieste di intervento di manutenzione**.

4. Se la sequenza numerica è attivata per le richieste di intervento di manutenzione in **Gestione cespiti**, il campo **Richiesta di intervento di manutenzione** è nascosto in quanto viene compilato automaticamente. Se il campo **Richiesta di intervento di manutenzione** è visibile, immettere un ID richiesta di intervento di manutenzione.

5. Selezionare un **tipo di richiesta di intervento di manutenzione**.

6. Immettere una **descrizione** per la richiesta di intervento di manutenzione.

7. Selezionare il **cespite** per il quale si desidera creare la richiesta.

8. Selezionare il **livello di servizio** per la richiesta di intervento di manutenzione.

9. Selezionare **Fine**.

![Figura 9](media/am-mobile-09.png)


## <a name="add-attachment-to-a-maintenance-request"></a>Aggiungere un allegato a una richiesta di intervento di manutenzione

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione cespiti**.

2. Selezionare **Tutte le richieste di intervento di manutenzione**.

3. Selezionare la richiesta di intervento di manutenzione a cui si desidera aggiungere un allegato.

4. Selezionare **Allegati** nella parte inferiore della schermata.

5. Selezionare **Aggiungi allegati**.

6. Immettere **Nome** e **Note** per l'allegato.

7. Selezionare **Scegli immagine** per selezionare una foto dalla gallery nel dispositivo mobile o **Scatta foto** per scattare una foto.

8. Selezionare **Fine**.

![Figura 10](media/am-mobile-10.png)

