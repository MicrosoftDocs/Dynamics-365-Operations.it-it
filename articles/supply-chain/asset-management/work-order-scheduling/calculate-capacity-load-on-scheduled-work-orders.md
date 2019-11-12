---
title: Calcolare il carico di capacità in ordini di lavoro programmati
description: In questo argomento viene descritto come calcolare il carico di capacità in ordini di lavoro programmati in Gestisci cespite.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d7684d1a4f78c95ebc7fd0a88f1c7dc7fead0303
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652105"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Calcolare il carico di capacità in ordini di lavoro programmati

[!include [banner](../../includes/banner.md)]

 

È possibile calcolare il carico di capacità in ordini di lavoro programmati per ottenere una panoramica del carico di lavoro nelle risorse per un periodo specifico. I calcoli possono essere eseguiti per le risorse seguenti: addetti alla manutenzione, gruppi di lavoratori, strumenti e cespiti.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Programma** > **Carico di capacità**.

2. Nella finestra di dialogo **Calcolare carico di capacità** > nel campo **Mostra**, selezionare il tipo di carico che si desidera calcolare: **Capacità**, **Prenotato**, or **Residuo**.

3. Impostare l'interruttore **Ignora lo zero** su **Sì** se non si desidera visualizzare i risultati contenenti zero.

4. Selezionare i tipi di risorsa per i quali si desidera calcolare il carico di capacità impostando gli interruttori pertinenti su **Sì**: **Lavoratore**, **Gruppo di addetti alla manutenzione**, **Strumento** e **Cespite**.

5. Selezionare la data di inizio per il calcolo nel campo **Dal**.

6. Nel campo **Tipo di intervallo**, selezionare l'intervallo per il calcolo: **Giorno**, **Settimana**, **Mese** o **Trimestre**.

7. Nel campo **Frequenza periodo**, inserire il numero di intervalli da calcolare. Ad esempio, se è stato selezionato **Giorno** come tipo di intervallo e si inserisce il numero "5 "in questo campo, verrà eseguito un calcolo di cinque giorni a partire dalla data di inizio.

8. Fare clic su **OK** per avviare il calcolo.

Nella figura seguente viene illustrato il risultato di un calcolo relativo a tre settimane per il tipo di carico **Prenotato**.

![Figura 1](media/08-work-order-scheduling.png)

[!NOTE]
Se si selezionano i tipi di carico **Capacità** o **Residuo** per il calcolo, lo stesso risultato sarà visualizzato se non vengono effettuate prenotazioni per le risorse nel periodo selezionato.

Per informazioni sulla modalità di calcolo del carico di capacità nelle righe di programma di manutenzione e ordini di lavoro non programmati, consultare [Calcolare carico di capacità](../capacity-planning/calculate-capacity-load.md).

