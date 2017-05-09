---
title: Aggiornamento relativo a rivalutazione valuta e singolo giustificativo per Microsoft Dynamics 365 for Operations versione 1611
description: "Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l&quot;aggiornamento a Microsoft Dynamics 365 for Operations versione 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Aggiornamento relativo a rivalutazione valuta e singolo giustificativo per Microsoft Dynamics 365 for Operations versione 1611

Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611.

Quando si esegue l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611, attenersi alla seguente procedura.

1.  Prima di eseguire l'aggiornamento a Dynamics 365 for Operations, eseguire i processi di rivalutazione valuta estera per la Contabilità clienti e la Contabilità fornitori. Impostare il campo **Metodo** su **Data fattura**. Viene creata una transazione di rivalutazione che annulla l'ultima rivalutazione valuta estera. Di conseguenza, le transazioni aperte vengono valutate alla valuta di contabilizzazione originale.
2.  Eseguire l'aggiornamento a Dynamics 365 for Operations versione 1611.
3.  Eseguire di nuovo il processo di rivalutazione valuta esterna per la contabilità fornitori e la contabilità clienti. Impostare questa volta il campo **Metodo** su **Standard**. Viene creata una nuova transazione di rivalutazione basata sui tassi di cambio correnti. Questa transazione registra il profitto/la perdita non realizzati e il conto CoGe riepilogativo corretto.



