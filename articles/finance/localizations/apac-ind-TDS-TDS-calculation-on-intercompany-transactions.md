---
title: Calcolo della TDS sulle transazioni interaziendali
description: In questo argomento viene descritto il processo utilizzato per calcolare l'imposta dedotta all'origine (TDS) sulle transazioni interaziendali in fasi.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023361"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>Calcolo della TDS sulle transazioni interaziendali

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto il processo utilizzato per calcolare l'imposta dedotta all'origine (TDS) sulle transazioni interaziendali in fasi.

Quando viene creato un ordine fornitore o un ordine cliente interaziendale, il gruppo TDS predefinito definito per il cliente o il fornitore viene utilizzato per calcolare l'importo TDS. L'importo TDS viene registrato nei conti fornitori o clienti dopo la registrazione della fattura.

Un ordine cliente o un ordine fornitore interaziendale viene creato automaticamente per l'ordine fornitore o l'ordine cliente originale. Il gruppo TDS predefinito viene visualizzato nell'ordine interaziendale, in modo che sia possibile calcolare la TDS. Puoi modificare il gruppo TDS. La fattura può essere registrata solo se l'importo netto della fattura nell'ordine interaziendale creato automaticamente corrisponde all'importo netto della fattura nell'ordine originale (l'importo netto è l'importo della fattura al netto della TDS).

Ad esempio, viene creata una fattura di vendita per 50.000 a cui viene associato il gruppo TDS del **10%**. L'importo della fattura registrato è 45.000 e l'importo TDS registrato per la fattura di vendita è 5.000. Viene creato automaticamente un ordine di acquisto per l'ordine di vendita interaziendale a cui viene associato il gruppo TDS del **10%**. Se selezioni il gruppo TDS del **15%**, non puoi registrare la fattura, poiché l'importo netto della fattura dell'ordine cliente interaziendale creato automaticamente non corrisponde all'importo netto della fattura dell'ordine cliente originale.

Un giornale di registrazione pagamenti creato per una fattura interaziendale viene registrato automaticamente. Il giornale di registrazione pagamenti può essere registrato solo se il relativo importo del pagamento netto corrisponde all'importo del pagamento netto nel giornale di registrazione pagamenti originale.
