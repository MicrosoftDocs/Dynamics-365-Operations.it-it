---
title: Registrazione fatture con importo zero
description: Questo argomento spiega come registrare transazioni finanziarie per fatture che hanno un importo pari a 0 (zero).
author: ilkond
ms.date: 11/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: a664a31b18c1943f668762722061bc2b72060b1a6e5a4829a6486807b4585643
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764220"
---
# <a name="posting-invoices-with-zero-amount"></a>Registrazione fatture con importo zero

[!include [banner](../includes/banner.md)]

In Italia, devono essere registrate transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero).

## <a name="prerequisites"></a>Prerequisiti

Prima di poter registrare transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero), devono essere soddisfatti i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Registrazione fatture con importo pari a zero**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="posting-invoices-that-have-an-amount-of-0-zero"></a>Registrazione di fatture con un importo pari a 0 (zero)

La funzione Registrazione fatture con importo pari a zero si applica alle fatture create nei moduli **Contabilità clienti** e **Contabilità fornitori**.

Quando vengono registrate fatture con un importo pari a 0 (zero), il sistema crea transazioni cliente/fornitore e transazioni giustificativo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]