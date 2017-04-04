---
title: Aggiornamento da rivalutazione valuta e del singolo giustificativo per Microsoft Dynamics 365 per la versione 1611 di operazioni
description: "In alcune organizzazioni o immettono i giornali di registrazione contengono un singolo giustificativo con più di un cliente o fornitore e di eseguire il processo di rivalutazione valuta estera della contabilità fornitori o Contabilità clienti. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando l&quot;aggiornamento a Microsoft Dynamics 365 per la versione 1611 delle operazioni."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Aggiornamento da rivalutazione valuta e del singolo giustificativo per Microsoft Dynamics 365 per la versione 1611 di operazioni

In alcune organizzazioni o immettono i giornali di registrazione contengono un singolo giustificativo con più di un cliente o fornitore e di eseguire il processo di rivalutazione valuta estera della contabilità fornitori o Contabilità clienti. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando l'aggiornamento a Microsoft Dynamics 365 per la versione 1611 delle operazioni.

Attenersi alle procedure quando si esegue l'aggiornamento a Microsoft Dynamics 365 per la versione 1611 delle operazioni.

1.  Prima di eseguire l'aggiornamento a Dynamics 365 per le operazioni, eseguire i processi di rivalutazione valuta estera in Contabilità clienti e Contabilità fornitori. Impostare ** metodo ** il campo su ** data della fattura **. Una transazione di rivalutazione viene creato il segno l'ultima rivalutazione valuta estera. Di conseguenza, le transazioni aperte vengono valutate alla valuta di contabilizzazione originale.
2.  Aggiornare in Dynamics 365 per la versione 1611 delle operazioni.
3.  Eseguire la contabilità clienti e la rivalutazione valuta estera della contabilità fornitori vengono nuovamente. Questa volta, è impostato ** metodo ** il campo su ** ** standard. Una nuova transazione di rivalutazione vengono create in base ai tassi di cambio correnti. Questa transazione viene registrato il profitto non realizzato/perdite e il conto CoGe riepilogativo corretto.



