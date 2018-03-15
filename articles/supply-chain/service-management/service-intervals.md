---
title: Intervalli assistenza
description: L'intervallo di assistenza indica la frequenza con cui vengono create righe di ordine di assistenza per le righe di contratto di assistenza in caso di creazione degli ordini di assistenza.
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4ea10e4c0fbfd21538bba16d2b01deb3e4b3a10d
ms.openlocfilehash: 4a51a3c3483e81cefdaf3d8e62a4f1f47fcd706b
ms.contentlocale: it-it
ms.lasthandoff: 02/20/2018

---

# <a name="service-intervals"></a>Intervalli assistenza

[!include[banner](../includes/banner.md)]


L'intervallo del contratto di assistenza indica la frequenza con cui vengono create righe di ordine di assistenza per le righe di contratto di assistenza nel caso di creazione automatica degli ordini di assistenza.

Quando gli ordini di assistenza vengono creati automaticamente, le righe di ordine di assistenza vengono create in base all'intervallo specificato per la riga di contratto di assistenza dalla data di inizio della riga di contratto.

Se il campo **Intervallo** di una riga di contratto di assistenza nella pagina **Contratti di assistenza** è vuoto, la riga rappresenta un evento occasionale e non viene utilizzata per creare ripetutamente ordini di assistenza.

## <a name="example"></a>Esempio

In questo esempio, viene illustrato il modo in cui un intervallo di assistenza influisce sulle righe di contratto di assistenza e sulle righe di ordine di assistenza in un ordine di assistenza.

### <a name="create-a-service-agreement"></a>Creare un contratto di assistenza

Innanzitutto, creare un contratto di assistenza e impostare l'opzione **Combina ordini di assistenza** su **In base al contratto di assistenza**.

1. Fare clic su **Contratti di assistenza**.
2. Nel **riquadro azioni**, nel gruppo **Nuovo** della scheda **Contratto di assistenza** fare clic su **Contratto di assistenza** per creare un nuovo contratto di assistenza.
3. Immettere una descrizione, selezionare un progetto nel campo **ID progetto** e immettere una data nel campo **Data di inizio**.
4. Nel campo **Combina ordini di assistenza** selezionare **In base al contratto di assistenza**.

È stato così creato il seguente contratto di assistenza:

| Project      | Data di inizio                                                                         |
|--------------|------------------------------------------------------------------------------------|
| Progetto selezionato | La data specificata per il progetto. In questo esempio viene utilizzata la data corrente. |

### <a name="create-a-service-agreement-line"></a>Creare una riga di contratto di assistenza

Creare successivamente una riga di contratto di assistenza con **Ora** come tipo di transazione.

Per completare questa parte dell'esempio, è necessario creare un intervallo di assistenza di 10 giorni nella pagina **Intervalli assistenza**. 

1. Selezionare il contratto di assistenza appena creato. 
2. Nella scheda dettaglio **Righe** fare clic sul pulsante **Aggiungi** per creare una nuova riga nel riquadro inferiore della pagina **Contratti di assistenza** .
3. Nel campo **Tipo di transazione** selezionare **Ora**.
4. Nel campo **Lavoratore** selezionare il lavoratore che fornirà il servizio.
5. Nel campo **Intervallo di assistenza** selezionare l'intervallo di 10 giorni.

È stata così creata una riga di contratto di assistenza con le seguenti informazioni:

| Tipo di transazione | Data di inizio                               | Intervallo di assistenza |
|------------------|------------------------------------------|------------------|
| Ore             | Data corrente.                        | Ogni 10 giorni    |
| Lavoro           | Il lavoratore che fornirà il servizio. |                  |

Per la riga non è stato specificato un intervallo di tempo. 

### <a name="create-planned-service-orders"></a>Creare ordini di assistenza pianificati

È possibile creare ora gli ordini di assistenza pianificati e le righe di ordine di assistenza per il mese prossimo.

1. Nella pagina **Contratti di assistenza**, nel **Riquadro azioni** della scheda **Fornisci**, fare clic su **Ordini di assistenza pianificati**.
2. Nella pagina **Crea ordini di assistenza** immettere la data corrente nel campo **Dal** e la data che corrisponde a un mese a partire dalla data corrente nel campo **Al**.
3. Impostare il dispositivo di scorrimento **Ora** su **Sì**. 
4. Fare clic su **OK**.

Poiché non è presente un raggruppamento nell'ordine di assistenza, definito dall'opzione **In base al contratto di assistenza** nel campo **Combina ordini di assistenza**, viene creata una riga di ordine di assistenza per ogni ordine di assistenza.

### <a name="service-orders-created"></a>Ordini di assistenza creati

Sono state create tre righe di ordine di assistenza nell'intervallo di tempo specificato nella finestra di dialogo **Crea ordini di assistenza**. È possibile visualizzare le righe di assistenza nella pagina **Contratti di assistenza** (**riquadro azioni** \> scheda **Fornisci** \>pulsante **Visualizza**).

## <a name="related-topics"></a>Argomenti correlati

[Impostare gli intervalli di assistenza](set-up-service-intervals.md)  


