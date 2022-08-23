---
title: Registrazione fatture con importo zero
description: Questo articolo spiega come registrare transazioni finanziarie per fatture che hanno un importo pari a 0 (zero).
author: mrolecki
ms.date: 11/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.search.form: ''
ms.openlocfilehash: 7f2cd9f91c4d50571620b387f4dd14bacb1210fd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280705"
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
