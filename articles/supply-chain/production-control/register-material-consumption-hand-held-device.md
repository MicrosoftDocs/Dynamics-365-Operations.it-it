---
title: Registrare il consumo dei materiali usando un dispositivo mobile
description: In questo argomento viene descritto un flusso di lavoro che consente la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67fbb8eebb637a96638c574373441213c66e9ddc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431429"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Registrare il consumo dei materiali usando un dispositivo mobile

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto un flusso di lavoro che consente la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile.

<a name="introduction"></a>Introduzione
------------

Questo flusso di lavoro è rilevante in presenza di in requisito vincolate per la tracciabilità de materiale. In questi casi, per gestire la tracciabilità dei materiali, l'ora e la quantità esatti devono essere dichiarati per il consumo. Questo processo è l'opposto delle operazioni di pre o backflush, in cui è presente uno scostamento tra l'ora di registrazione e l'ora in cui ha luogo il consumo effettivo. Questo spiega perché una strategia di consumo automatico non può essere utilizzata per alcuni materiali con requisiti di tracciabilità. Esaminiamo uno scenario semplice che spiega come configurare un flusso di lavoro per consentire la registrazione del consumo di materie prime nella produzione tramite un dispositivo portatile. [![Configurare un flusso di lavoro per consentire la registrazione del consumo di materie prime tramite un dispositivo portatile](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Dettagli dello scenario

Un processo di produzione continua (5) utilizza la materia prima RM-100 controllata per lotto. Il materiale è disponibile nell'ubicazione Bulk-001 (1) sulla targa PL -1 con due lotti, B1 e B2, entrambi con una quantità di 100 chilogrammi. Il lavoro di magazzino (2) viene emesso e elaborato per RM-100 e il materiale viene prelevato da Bulk-001 presso l'ubicazione di entrata produzione PIL-01 (3), definita come controllato senza targa. L'operatore pesa il materiale rispetto al materiale dell'ubicazione di entrata produzione (3) e registra il peso e il numero di lotto come consumato (4). Dall'ubicazione di entrata produzione, parte del materiale viene aggiunta manualmente al processo di produzione in intervalli di tempo definiti. Quando l'operatore aggiunge il materiale, viene pesato su una scala e il numero di lotto viene registrato.

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a>Configurare il flusso di lavoro per registrare il consumo utilizzando un dispositivo portatile
Creare un prodotto finito, FG-100, con una distinta base che include la materia prima controllata per lotto RM-100. Aggiungere due lotti, B1 e B2, di RM-100 in una quantità pari a 100 nell'ubicazione: Bulk-001 su targa: PL-1. Il principio di registrazione del consumo di materiali in entrata sulla riga distinta base per RM-100 è impostato su **Manuale**. Impostare l'ubicazione entrata produzione su PIL-01. È possibile farlo selezionando questa ubicazione come ubicazione di entrata produzione predefinita nel magazzino 51.

1.  Creare una nuova voce di menu per dispositivo mobile: 

-    **Nome voce di menu** - Registra consumo materiali. 
-    **Titolo** - Registra consumo materiali. 
-    **Modalità** - Indiretta. 
-    **Codice attività** - Registra consumo materiali.

2.  Aggiungere la voce di menu al menu per dispositivo mobile **Produzione mobile**.
3.  Creare un ordine di produzione per il prodotto finito: 

-    **Numero articolo** - FG-100 
-    **Sito** - 5 
-    **Magazzino** - 51 
-    **Quantità** - 150

L'ordine di produzione è **Stimato** e **Rilasciato** e il lavoro di magazzino viene creato.

4.  Completare il lavoro tramite il flusso di lavoro per il prelievo di materie prime per il dispositivo portatile.

Questo porterà il materiale dall'ubicazione di stoccaggio all'ubicazione di entrata produzione PIL-01. Dopo che il lavoro è stato completato, il materiale avrà lo stato **Prelevato nell'ubicazione di entrata produzione**. Lo stato dopo che il lavoro è stato elaborato può essere **Prelevato** o **Fisico prenotato**. Ciò viene configurata con il parametro **Stato di emissione dopo aggiunto al modulo di magazzino**.

5.  Avviare l'ordine di produzione dal client o da dispositivo portatile utilizzando la voce di menu **Inizio di produzione**.

Dopo che l'ordine di produzione è stato avviato, è possibile registrare il consumo di materiali con il flusso di lavoro per un dispositivo portatile. Iniziamo la registrazione di un consumo di 25 chilogrammi del lotto B1.

6.  Selezionare la voce di menu  **Registra materiale** **consumo** dal menu per il dispositivo portatile, immettere i seguenti dati: 

-    Numero dell'ordine di produzione. 
-    Ubicazione in cui il materiale dovrà essere consumato, in questo caso PIL-01. 
-    Numero articolo RM-100. 
-    Numero lotto B1. 
-    Quantità di 25.

7.  Selezionare **OK**.

Si noti che viene visualizzato sullo schermo il messaggio "Riga giornale di registrazione creata". Nell'ordine di produzione è presente giornale di registrazione aperto di tipo **Distinta di prelievo produzione** per il numero di articolo RM-100 e il numero di lotto B1. 

È ora possibile scegliere di continuare la registrazione, ad esempio sul numero lotto B2, e ogni volta che si seleziona **OK,** una nuova riga del giornale di registrazione viene aggiunta al giornale di registrazione aperto. 

Al termine della registrazione, selezionare **Fatto** per registrare il giornale e terminare il flusso di lavoro.

### <a name="additional-comments"></a>Commenti aggiuntivi 

-   Se un utente annulla il flusso di lavoro dopo la creazione di una riga del giornale di registrazione, il giornale di registrazione è nello stato non registrato ma se l'utente in un momento successivo utilizza il flusso di lavoro per lo stesso ordine di produzione, le righe verranno aggiunte al giornale di registrazione aperto anziché in un nuovo giornale.
-   Il nuovo flusso di lavoro supporta anche la registrazione dei numeri di serie.
-   È possibile registrare solo un numero di articolo definito nella distinta base o nella formula per l'ordine di produzione o l'ordine lotto selezionato.
-   Il materiale può essere consumato in quantità eccessiva. Ad esempio, se si stima una quantità consumata di materiale pari a 100 kg, è possibile che si verifichi un consumo eccessivo pari a una quantità, ad esempio, di 105 chilogrammi.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]