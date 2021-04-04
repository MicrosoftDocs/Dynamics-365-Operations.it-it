---
title: Registrazione fatture con importo zero
description: Questo argomento spiega come registrare transazioni finanziarie per fatture che hanno un importo pari a 0 (zero).
author: ilkond
manager: AnnBe
ms.date: 11/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 1df0de631b8278ba7a9a3fa2d85061f6ab963de8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244436"
---
# <a name="posting-invoices-with-zero-amount"></a>Registrazione fatture con importo zero

[!include [banner](../includes/banner.md)]

In Italia, devono essere registrate transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero).

## <a name="prerequisites"></a>Prerequisiti

Prima di poter registrare transazioni finanziarie per fatture che hanno un importo totale pari a 0 (zero), devono essere soddisfatti i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Registrazione fatture con importo pari a zero**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="posting-invoices-that-have-an-amount-of-0-zero"></a>Registrazione di fatture con un importo pari a 0 (zero)

La funzione Registrazione fatture con importo pari a zero si applica alle fatture create nei moduli **Contabilità clienti** e **Contabilità fornitori**.

Quando vengono registrate fatture con un importo pari a 0 (zero), il sistema crea transazioni cliente/fornitore e transazioni giustificativo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]