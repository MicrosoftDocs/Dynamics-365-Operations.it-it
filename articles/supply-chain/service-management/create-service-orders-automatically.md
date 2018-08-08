---
title: Creare ordini di assistenza automaticamente
description: "È possibile creare ordini di assistenza per uno o più contratti di assistenza."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c39e5b5eb79859b0a76c357edfee953ca90c0c4a
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-automatically"></a>Creare ordini di assistenza automaticamente    

[!include [banner](../includes/banner.md)]


È possibile creare ordini di assistenza per uno o più contratti di assistenza. Dopo la creazione è possibile visualizzare gli ordini di assistenza nel modulo **Ordini di assistenza**.

Gli ordini di assistenza vengono creati solo per il periodo di validità del contratto di assistenza. Se l'intervallo specificato nel modulo **Crea ordini di assistenza** inizia prima della data di inizio o termina dopo la data di fine del contratto di assistenza, gli ordini di assistenza verranno creati solo per la parte dell'intervallo compresa nel periodo del contratto.

Quando si creano manualmente o automaticamente ordini di assistenza dalla riga del contratto di assistenza, l'ordine di assistenza deve rientrare nell'intervallo di tempo definito dalle date di inizio e fine relative alla riga, a meno che la data di fine nella riga non sia specificata.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Creare ordini di assistenza automaticamente per un contratto di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.

2.  Selezionare un contratto di assistenza.

3.  Fare clic sulla scheda **Consegna**, quindi fare clic su **Ordini di assistenza pianificati**.

4.  Specificare una data nei campi **Dal** e **Al** per definire il periodo di assistenza.

5.  Selezionare la casella di controllo **Mostra Registro informazioni** per visualizzare l'elenco degli ordini di assistenza creati.

6.  Selezionare i tipi di transazioni nel gruppo di campi **Includi tipi di transazioni**. I tipi di transazione rappresentano le righe create nel contratto di assistenza e ciascun tipo di transazione selezionato determina la generazione di più ordini di assistenza, a seconda dell'intervallo di assistenza specificato nella riga del contratto.

7.  Selezionare la casella di controllo **Continua** per creare gli eventuali ordini di assistenza mancanti all'interno di una serie di ordini continua.

8.  Fare clic su **OK**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Creare ordini di assistenza automaticamente per più contratti di assistenza

1.  Fare clic su **Gestione assistenza** \> **Periodico** \> **Ordini di assistenza** \> **Crea ordini di assistenza**.

2.  Fare clic su **Seleziona** per operare le selezioni di aggiunta o rimozione dei criteri utilizzati per creare gli ordini di assistenza.

3.  Fare clic su **OK**.

## <a name="see-also"></a>Vedere anche

[Ordini di assistenza](service-orders.md)

[Creare ordini di assistenza automaticamente](auto-create-service-orders.md)

  



