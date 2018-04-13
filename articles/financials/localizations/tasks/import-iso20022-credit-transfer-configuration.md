--- 
title: Importare la configurazione di bonifico ISO20022
description: In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore.
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 71c0175178203006e297466c4a37cd3e6319b6ea
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importare la configurazione di bonifico ISO20022

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore. Viene usato il formato di bonifico tedesco ISO 20022 come esempio. Questa procedura può essere utilizzata per un altro formato di creazione di report elettronici disponibile. 

Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF ma è possibile utilizzare qualsiasi società di dati dimostrativi per completare l'attività.

Si tratta della prima attività di cinque, tale set illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Nell'elenco di provider di configurazioni disponibili selezionare Microsoft.
3. Fare clic su Imposta attivo.
4. Fare clic su Archivi.
5. Fare clic su Apri.
6. Fare clic su Mostra filtri.
7. Applicare i filtri seguenti: immettere un valore di filtro "Bonifico ISO20022 (DE)" nel campo "Nome configurazione" utilizzando l'operatore di filtro "inizia con".
    * In alternativa, individuare la configurazione nell'elenco, selezionarla e spostarla nell'attività di importazione.  
8. Fare clic su Importa.
    * Se il pulsante di importazione non è disponibile, significa che la configurazione è già stata importata.  
9. Fare clic su Sì.


