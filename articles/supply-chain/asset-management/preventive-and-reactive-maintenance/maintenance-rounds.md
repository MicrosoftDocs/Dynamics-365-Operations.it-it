---
title: Cicli di manutenzione
description: In questo argomento vengono descritti i cicli di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97f1984b71ab60519f81bb1f6ab38278a0e5aa43
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206106"
---
# <a name="maintenance-rounds"></a>Cicli di manutenzione

[!include [banner](../../includes/banner.md)]

 

In **Gestione cespiti**, è possibile creare cicli di manutenzione per vari cespiti in cui è necessario eseguire un'attività simile a intervalli regolari. Ad esempio, le lubrificazioni o le ispezioni di sicurezza da eseguire su una serie di macchine entro gli stessi intervalli. Il primo passo è di creare un ciclo di manutenzione per i cespiti che richiedono lo stesso tipo di manutenzione. Successivamente, si programmano i cicli di manutenzione. Una volta completata la programmazione dei cicli di manutenzione, è possibile visualizzare tutti i record relativi al ciclo in **Tutti i programmi di manutenzione** e **Apri righe di programma di manutenzione**.

>[!NOTE]
>I cicli di manutenzione possono anche essere impostati nelle unità funzionali per essere completati nei cespiti installati nell'unità funzionale al momento della creazione dell'ordine di lavoro basato sul ciclo. Per ulteriori informazioni sull'impostazione dei cicli di manutenzione nelle unità funzionali, vedere [Creare unità funzionali](../functional-locations/create-functional-locations.md).

## <a name="set-up-a-maintenance-round"></a>Impostare un ciclo di manutenzione

1. Fare clic su **Gestione cespiti** > **Impostazione** > **Manutenzione preventiva** > **Cicli di manutenzione**.

2. Fare clic su **Nuovo** per creare un nuovo ciclo di manutenzione.

3. Immettere un ID nel campo **Ciclo di manutenzione** e un nome per il ciclo nel campo **Nome**.

4. Selezionare una data di inizio per il ciclo nel campo **Data di inizio**.

5. Nei campi **Termina entro giorni** e **Termina entro ore**, è possibile immettere la data di fine prevista in giorni o ore. La data di fine prevista viene calcolata in relazione alla data di inizio, che viene calcolata alla creazione delle righe di programma di manutenzione. Ad esempio, è possibile immettere "7 "nel campo **Termina entro giorni** per indicare che il processo correlato deve essere completato entro una settimana dalla data di inizio.

6. Impostare l'interruttore **Crea automaticamente** su "Sì" se gli ordini di lavoro devono essere creati automaticamente dalle righe di programma di manutenzione generate sulla base di questo ciclo di manutenzione.

7. Nel campo **Tipo di ordine di lavoro**, selezionare il tipo di ordine di lavoro da utilizzare negli ordini di lavoro creati da questo ciclo di manutenzione.

8. Nel campo **Livello servizio**, selezionare il livello di servizio di ordine di lavoro da utilizzare negli ordini di lavoro creati da questo ciclo di manutenzione.

9. Nella Scheda dettaglio **Righe cespite**, fare clic su **Aggiungi** per aggiungere un cespite al ciclo di manutenzione.

10. Un numero di riga viene automaticamente inserito nel campo **Numero riga** per indicare la sequenza dei cespiti nel ciclo di manutenzione.

11. Selezionare il cespite nel campo **Cespite**.

12. Selezionare il tipo di processo di manutenzione per il cespite nel campo **Tipo di processo di manutenzione**.

13. Se necessario, selezionare la **Variante di tipo di processo di manutenzione** e il **Settore** associati al tipo di processo di manutenzione.

14. Selezionare la ricorrenza (giorno, settimana e così via.) nel campo **Tipo di periodo**.

15. Nel campo **Frequenza periodo**, immettere il numero di ricorrenze per il ciclo di manutenzione. Esempio: se è stato selezionato "Giorno" nel campo **Tipo di periodo** e si immette "7" in questo campo, le righe del ciclo di manutenzione vengono create una volta alla settimana durante la programmazione della manutenzione preventiva.

16. Selezionare una data di inizio per il cespite da includere nel ciclo di manutenzione nel campo **Data di inizio**. Questa data può differire da quella impostata nel ciclo di manutenzione.

17. Ripetere i passaggi da 9 a 16 per aggiungere ulteriori cespiti al ciclo di manutenzione.

18. Nella Scheda dettaglio **Righe unità funzionale**, fare clic su **Aggiungi** per aggiungere un'unità funzionale al ciclo di manutenzione. Fare riferimento alla descrizione dei campi correlati visti nei passaggi precedenti. Gli stessi campi sono disponibili per la creazione di una riga di cespite, ma è anche possibile selezionare **Produttore** e **Modello** per un'unità funzionale, se necessario. Se si seleziona solo un'unità funzionale in una riga, ma non si effettuano selezioni in **Tipo di cespite**, **Produttore**, **Modello**, **Tipo di processo di manutenzione**, **Variante tipi di processo di manutenzione** e **Settore**, tutti i cespiti associati a quell'unità funzionale al momento della programmazione di manutenzione verranno inclusi nel ciclo di manutenzione.

19. Nella Scheda dettaglio **Pool**, fare clic su **Aggiungi** per selezionare un pool di ordini di da includere nel ciclo di manutenzione. È possibile collegare vari pool di ordini di lavoro a un ciclo di manutenzione.

20. Salvare l'impostazione.

>[!NOTE]
>I campi **Cespiti** e **Righe** nel gruppo **Dettagli** della Scheda dettaglio **Intestazione** indicano il numero totale di cespiti e righe associati al ciclo di manutenzione selezionato.

L'illustrazione seguente mostra ed esempio di un ciclo di manutenzione contenente tre cespiti.

![Figura 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Programma cicli di manutenzione

Dopo l'impostazione di un ciclo di manutenzione, si esegue un processo di programmazione per programmare tutti i processi correlati al ciclo di manutenzione.

1. Fare clic su **Gestione cespiti** > **Periodico** > **Manutenzione preventiva** > ,**Programma cicli di manutenzione** o **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apro pool di programmi di manutenzione** > selezionare la riga di programma di manutenzione nell'elenco > pulsante **Cicli di manutenzione**.

2. Nel campo **Periodo**, selezionare il tipo di periodo da utilizzare per il processo di programmazione.

3. Nel campo **Frequenza periodo**, inserire il numero di periodi da includere nel processo di programmazione. L'inizio della programmazione è la data corrente.

4. Impostare l'interruttore **Crea automaticamente** su "Sì" se un ordine di lavoro deve essere creato automaticamente in base al ciclo di manutenzione.

>[!NOTE]
>Se questo interruttore è impostato su "Sì" e anche l'interruttore **Crea automaticamente** è impostato su "Sì" nel ciclo di manutenzione nel modulo **Cicli di manutenzione**, gli ordini di lavoro sono creati in base alle righe del ciclo di manutenzione e vengono create anche le righe di programma di manutenzione con lo stato "Ordine di lavoro creato". Se solo uno degli interruttori **Crea automaticamente** è impostato su "Sì", in questo elenco a discesa o in **Cicli di manutenzione**, solo le righe di programma di manutenzione vengono create con lo stato "Creata". In tal caso, non viene creato alcun ordine di lavoro.

5. Se necessario, è possibile selezionare specifici cicli o un'altra data di inizio per il processo di programmazione. Fare clic su **Filtro** e aggiungere i cicli da includere.

6. Fare clic su **OK**.

7. A questo punto è possibile visualizzare i processi dei cicli di manutenzione in **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione**. Se i cicli di manutenzione sono collegati a un pool di ordini di lavoro, vengono visualizzate anche le righe di programma di manutenzione in **Apri pool di programmazione di manutenzione**. Le righe di programma di manutenzione create da un ciclo hanno il tipo di riferimento "Cicli di manutenzione".

Le due illustrazioni di seguito illustrano un processo di programmazione nella finestra di dialogo **Cicli di programmazione della manutenzione** e le righe del programma di manutenzione create in **Tutto il programma di manutenzione** in base al processo di programmazione.

![Figura 2](media/14-preventive-maintenance.png)

![Figura 3](media/15-preventive-maintenance.png)

- Quando gli ordini di lavoro vengono creati manualmente nei cespiti coperti da un garanzia fornitore, viene visualizzata una finestra di dialogo per informare l'utente della garanzia. La creazione dell'ordine di lavoro può quindi essere annullata. La verifica di una relazione di garanzia viene omessa per gli ordini di lavoro creati automaticamente.  
- È possibile impostare un processo batch nella Scheda dettaglio **Esecuzione in background** per programmare i cicli a intervalli regolari.  
- Se un ciclo è incluso in vari pool di ordini di lavoro (vedere [Pool di ordini di lavoro](../work-orders/work-order-pools.md)), un record viene visualizzato per ogni pool in **Apri pool di programmi di manutenzione**. Questa operazione viene eseguita per ottimizzare le opzioni di filtro per i pool di ordini di lavoro.

