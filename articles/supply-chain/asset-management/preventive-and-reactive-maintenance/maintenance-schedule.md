---
title: Programma di manutenzione
description: In questo argomento viene descritto il programma di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 351e088ece0512fee1bb5f9dad020f32f7728fe4
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889003"
---
# <a name="maintenance-schedule"></a>Programma di manutenzione

[!include [banner](../../includes/banner.md)]

 

Il processo di manutenzione contiene un elenco di tutti i piani di manutenzione preventiva previsti, le richiesta di intervento di manutenzione e i cicli di manutenzione da eseguire. Alcune righe di programmazione possono essere state convertite in ordini di lavoro.

Le quattro visualizzazioni del programma di manutenzione sono leggermente differenti, a seconda delle righe di programma di manutenzione che si desidera visualizzare.

| Voce di menu                  | Descrizione del contenuto                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tutto il programma di manutenzione       | Sono visualizzate tutte le righe di programma di manutenzione.     |
| Programmazione del cespite personale        | Tutte le righe di programma di manutenzione contenenti cespiti installati in unità funzionali a cui si è correlati in quanto lavoratore (impostazione in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md)) sono visualizzate in questo elenco. |
| Apri le righe di programma di manutenzione | Le righe di programma di manutenzione il cui stato è "Creata", a indicare che non sono ancora state convertite in un ordine di lavoro o sono state eliminate, sono visualizzate in questo elenco.                                            |
| Apri i pool di programmi di manutenzione | Le righe di programma di manutenzione correlate a un pool di ordini di lavoro sono visualizzate in questo elenco.                                                                                                                  |

>[!NOTE]
>Se una riga di programma di manutenzione è inclusa in vari pool di ordini di lavoro (vedere [Pool di ordini di lavoro](../work-orders/work-order-pools.md)), un record viene visualizzato per ogni pool in **Apri pool di programmi di manutenzione**. Questa operazione viene eseguita per ottimizzare le opzioni di filtro per i pool di ordini di lavoro.

Per aprire un programma di manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione**.

2. Per aggiornare il programma di manutenzione, fare clic su **Piano di manutenzione** o **Cicli di manutenzione**. 

3. È possibile modificare una riga di programma di manutenzione selezionandola e facendo clic su **Modifica**. Ad esempio, è possibile aggiornare facilmente il livello del servizio o il lavoratore responsabile del processo. È possibile modificare solo le righe di programma di manutenzione che non sono ancora state associate a un ordine di lavoro.

4. È possibile eliminare una riga di programma di manutenzione selezionandola nella pagina elenco e facendo clic su **Elimina**.

5. È possibile eliminare una riga di programma di manutenzione selezionandola nella pagina elenco e facendo clic su **Rimuovi**. Questa funzione è utile se, ad esempio, un cespite ha un piano di manutenzione di 2.000 chilometri e un piano di manutenzione di 10.000 chilometri. Quindi, è possibile che si intenda rimuovere la riga creata dal piano di manutenzione di 2.000 chilometri quando coincide con 10.000 km, 20.000 km, 30.000 km e così via. Se si rimuove una riga di programma di manutenzione associata a un piano di manutenzione, quella riga non sarà più visualizzata quando il piano di manutenzione viene programmato.

6. È possibile selezionare un numero di righe di programma di manutenzione in **Tutti i programmi di manutenzione** e fare clic su **Pool di ordini di lavoro**, se tutte le righe selezionate devono essere incluse nello stesso pool di ordini di lavoro.

7. È possibile selezionare un numero di righe di programma di manutenzione in **Tutti i programmi di manutenzione**, **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione** e fare clic su **Rettifica le programmazioni** se si intende eseguire le stesse rettifiche su più righe. È possibile modificare le date di inizio e fine previste, il livello del servizio e il gruppo di addetti alla manutenzione responsabile o l'addetto alla manutenzione responsabile associato alle righe di programma di manutenzione selezionate.

- Quando una riga di programma di manutenzione è associata a un ordine di lavoro, l'ID ordine di lavoro viene visualizzato nel campo **Ordine di lavoro**.  
- Nella visualizzazione dettagli **Tutti i cespiti** > Scheda dettaglio **Piani di manutenzione cespiti**, è possibile selezionare piani di manutenzione per il cespite. Successivamente, se si elimina una riga di piano di manutenzione associata a un cespite in **Tutti i cespiti**, si eliminano automaticamente anche tutte le righe di programma di manutenzione con stato "Creata" che sono state create in base a quel piano di manutenzione. Vedere anche [Creare un cespite](../objects/create-an-object.md).

L'illustrazione seguente mostra la pagina di elenco **Tutti i programmi di manutenzione**.

![Figura 1](media/16-preventive-maintenance.png)

