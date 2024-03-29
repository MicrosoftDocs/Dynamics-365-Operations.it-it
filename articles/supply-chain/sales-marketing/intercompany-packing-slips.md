---
title: Documenti di trasporto interaziendali
description: Questo articolo descrive come generare e stampare documenti di trasporto per le transazioni interaziendali
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3516058bbf925df4b0a0c75286a3d97457cc1e69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900856"
---
# <a name="intercompany-packing-slips"></a>Documenti di trasporto interaziendali

## <a name="generate-intercompany-packing-slips"></a>Generare documenti di trasporto interaziendali

[!include [banner](../../includes/banner.md)]

Se si utilizza la consegna diretta, quando il documento di trasporto viene generato nell'ordine cliente interaziendale, viene sempre generato automaticamente anche nell'ordine fornitore interaziendale e nell'ordine cliente originario. La fattura ordine fornitore interaziendale si basa sul documento di trasporto relativo generato in precedenza.

Gli eventuali aggiornamenti apportati al documento di trasporto nell'ordine cliente interaziendale vengono riportati nell'ordine fornitore interaziendale e nell'ordine cliente originario.

Se non si utilizza la consegna diretta, è necessario generare manualmente il documento di trasporto nell'ordine cliente interaziendale, nell'ordine fornitore interaziendale e nell'ordine cliente originario.

## <a name="print-intercompany-packing-slips"></a>Stampare documenti di trasporto interaziendali

[!include [banner](../../includes/banner.md)]

Se si utilizza la consegna diretta, è possibile stampare automaticamente un documento di trasporto per l'ordine fornitore interaziendale e l'ordine cliente originario quando il documento di trasporto viene registrato nell'ordine cliente interaziendale.

Per stampare automaticamente i documenti di trasporto, nella pagina **Interaziendale** per gli ordini fornitore, selezionare entrambi i campi **Stampa documento di trasporto automaticamente**.

Se si aggiorna il documento di trasporto nell'ordine cliente interaziendale, le modifiche vengono riportate automaticamente nell'ordine fornitore interaziendale e nell'ordine cliente originario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
