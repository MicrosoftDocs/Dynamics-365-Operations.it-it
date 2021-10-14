---
title: Documenti di trasporto interaziendali
description: Questo argomento descrive come generare e stampare documenti di trasporto per le transazioni interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 72d052d2daba90d49ba372fb3fb480bdd0877398
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548362"
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
