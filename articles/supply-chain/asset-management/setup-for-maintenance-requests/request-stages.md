---
title: Stati del ciclo di vita delle richieste di intervento di manutenzione
description: In questo argomento viene descritto come impostare gli stati del ciclo di vita delle richieste di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 151db9ca8a121759e39b690ec296b36a18dc1729
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571164"
---
# <a name="maintenance-request-lifecycle-states"></a>Stati del ciclo di vita delle richieste di intervento di manutenzione

[!include [banner](../../includes/banner.md)]

 


Gli stato del ciclo di vita delle richieste di intervento di manutenzione definiscono le fasi in cui può trovarsi una richiesta. Esempi includono **Creato**, **Attivo** e **Finito**. Quando una richiesta di intervento di manutenzione viene convertita in ordine di lavoro, lo stato del ciclo di vita della richiesta deve essere aggiornato a **Finito** o **Chiuso** per indicare che la richiesta non è più attiva. Nella pagina elenco **Tutte le richieste di intervento di manutenzione**, vengono visualizzate tutte le richieste di intervento di manutenzione, indipendentemente dallo stato del ciclo di vita.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Imposta gli stati del ciclo di vita della richiesta di intervento di manutenzione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Stati del ciclo di vita**.
2. Selezionare **Nuovo** per creare un nuovo stato del ciclo di vita delle richieste di intervento di manutenzione.
3. Nel campo **Stato del ciclo di vita**, immettere l'ID dello stato del ciclo di vita.
4. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Dettagli** il campo **Modelli del ciclo di vita** mostra il numero di modelli del ciclo di vita delle richieste di intervento di manutenzione che utilizzano lo stato del ciclo di vita del cespite.

5. Nella Scheda dettaglio **Generale**, impostare **Attivo** su **Sì** se la richiesta di intervento di manutenzione deve essere attiva mentre si trova in questo stato del ciclo di vita.
6. Impostare **Imposta fine effettiva** su **Sì** se la data e ora di fine effettive devono essere immesse automaticamente in una richiesta di intervento di manutenzione che si trova in questo stato del ciclo di vita.
7. Impostare **Crea ordine di lavoro** su **Sì** se un ordine di lavoro può essere creato da una richiesta di intervento di manutenzione che si trova in questo stato del ciclo di vita.
8. Impostare **Elimina** su **Sì** se la richiesta di intervento di manutenzione può essere eliminata mentre si trova in questo stato del ciclo di vita.
9. Nella Scheda dettaglio **Aggiorna**, le opzioni **In entrata** e **In uscita** nella sezione **Cespite** sono pertinenti se si utilizza la riparazione in deposito. Impostare l'opzione appropriata su **Sì** se lo stato del ciclo di vita dei cespiti selezionati in una richiesta di intervento di manutenzione deve essere aggiornato automaticamente su **In entrata** o **In uscita** quando lo stato del ciclo di vita di quella richiesta di intervento di manutenzione è impostato su **In entrata** o **In uscita**.

Nella figura seguente è illustrato un esempio della pagina **Stati del ciclo di vita delle richieste di intervento di manutenzione**.

![Pagina Stati del ciclo di vita delle richieste di intervento di manutenzione](media/02-setup-for-requests.png)

> [!NOTE]
> Gli stati del ciclo di vita , i gruppi di stati del ciclo di vita e i tipi delle richieste di intervento di manutenzione sono correlati a vengono utilizzati allo stesso modo degli stati del ciclo di vita , gruppi di stati del ciclo di vita e i tipi degli ordini di lavoro. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Impostare i modelli del ciclo di vita della richiesta di intervento di manutenzione

Dopo aver creato gli stati del ciclo di vita necessari per le richieste di intervento di manutenzione, possono essere divisi in gruppi di stati del ciclo di vita, o modelli del ciclo di vita. I modelli del ciclo di vita delle richieste di intervento di manutenzione vengono utilizzati per creare il flusso che può essere utilizzato per i diversi tipi di richieste di intervento di manutenzione. Come minimo, un modello standard del ciclo di vita delle richieste di intervento di manutenzione deve essere creato.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Modelli del ciclo di vita**.
2. Selezionare **Nuovo** per creare un modello del ciclo di vita delle richieste di intervento di manutenzione.
3. Nel campo **Modello del ciclo di vita**, immettere un ID del modello del ciclo di vita.
4. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Dettagli**, **Stati del ciclo di vita** mostra il numero di stati del ciclo di vita del cespite selezionati in questo modello del ciclo di vita. Nel campo **Tipi di richieste di intervento di manutenzione** viene visualizzato il numero di tipi di richieste di intervento di manutenzione che utilizzano questo modello del ciclo di vita.

5. Nella Scheda dettaglio **Stati del ciclo di vita**, selezionare gli stati del ciclo di vita che devono essere inclusi nel modello:

    - Per includere uno stato del ciclo di vita nel modello, selezionarlo nella sezione **Stati del ciclo di vita rimanenti** e quindi fare clic sul pulsante freccia destra ![Freccia destra](media/03-setup-for-requests.png) per spostarlo nella sezione **Stati del ciclo di vita selezionati**.
    - Per includere tutti gli stati del ciclo di vita disponibili nel modello, selezionare il pulsante **Seleziona tutti gli stati disponibili** ![Seleziona tutti gli stati disponibili](media/04-setup-for-requests.png). Tutti gli stati del ciclo di vita verranno spostati nella sezione **Stati del ciclo di vita selezionati**.
    - Per rimuovere uno stato del ciclo di vita dal modello, selezionarlo nella sezione **Stati del ciclo di vita selezionati** e quindi fare clic sul pulsante freccia sinistra ![Freccia sinistra](media/05-setup-for-requests.png) per spostarlo nella sezione **Stati del ciclo di vita rimanenti**.

6. Nella Scheda dettaglio **Generale**, i campi della sezione **Aggiornamenti** sono pertinenti se si utilizza la riparazione in deposito.

    - Nel campo **Stato del ciclo di vita per cespite ricevuto**, selezionare lo stato del ciclo di vita del cespite a cui i cespiti selezionati in una richiesta di intervento di manutenzione devono essere aggiornati automaticamente quando vengono ricevuti per la riparazione in deposito.
    - Nel campo **Stato del ciclo di vita per cespite consegnato**, selezionare lo stato del ciclo di vita del cespite a cui i cespiti selezionati in una richiesta di intervento di manutenzione devono essere aggiornati automaticamente quando vengono restituiti dopo la riparazione.

Nella figura seguente è illustrato un esempio della pagina **Modelli del ciclo di vita delle richieste di intervento di manutenzione**.

![Pagina Modelli del ciclo di vita delle richieste di intervento di manutenzione](media/06-setup-for-requests.png)
