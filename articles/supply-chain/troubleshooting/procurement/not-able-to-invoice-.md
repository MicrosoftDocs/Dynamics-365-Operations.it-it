---
title: Impossibile fatturare un ordine cliente visualizzabile dal cliente
description: Non è più possibile fatturare l'ordine cliente originale e l'ordine fornitore con consegna diretta originale dopo aver abilitato l'opzione Registra fattura automaticamente.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30c485be79be5ebbec8b51272b8bbe6e0c7df9d81bbaaaef316dbfede03abf68
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756753"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Impossibile fatturare un ordine cliente visualizzabile dal cliente

Numero KB: 4611793

## <a name="symptoms"></a>Sintomi

Non è più possibile fatturare l'ordine cliente originale e l'ordine fornitore con consegna diretta originale dopo aver abilitato l'opzione **Registra fattura automaticamente** nella pagina **Interaziendale** di un fornitore.

## <a name="resolution"></a>Risoluzione

Il comportamento di sincronizzazione per le fatture degli ordini di consegna diretta e interaziendali è controllato e forzato dai parametri descritti in [Impostare i parametri per la registrazione di un ordine interaziendale](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

Dopo aver impostato tali parametri, devi dapprima fatturare l'ordine cliente interaziendale. Gli ordini cliente e gli ordini fornitore originali verranno quindi sincronizzati.
