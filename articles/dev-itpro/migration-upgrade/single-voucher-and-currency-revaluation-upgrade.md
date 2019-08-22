---
title: Aggiornare i giornali di registrazione giustificativi singoli e le rivalutazioni valuta
description: Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b76354d0b8bb89e09e861e013a0c680c36b6537d
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851683"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Aggiornare rivalutazioni valuta e giornali di registrazione a singolo giustificativo

[!include [banner](../includes/banner.md)]

Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori. In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611.

Quando si esegue l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611, attenersi alla seguente procedura.

1.  Prima di eseguire l'aggiornamento a Dynamics 365 for Operations, eseguire i processi di rivalutazione valuta estera per la Contabilità clienti e la Contabilità fornitori. Impostare il campo **Metodo** su **Data fattura**. Viene creata una transazione di rivalutazione che annulla l'ultima rivalutazione valuta estera. Di conseguenza, le transazioni aperte vengono valutate alla valuta di contabilizzazione originale.
2.  Eseguire l'aggiornamento a Dynamics 365 for Operations versione 1611.
3.  Eseguire di nuovo il processo di rivalutazione valuta esterna per la contabilità fornitori e la contabilità clienti. Impostare questa volta il campo **Metodo** su **Standard**. Viene creata una nuova transazione di rivalutazione basata sui tassi di cambio correnti. Questa transazione registra il profitto/la perdita non realizzati e il conto CoGe riepilogativo corretto.




