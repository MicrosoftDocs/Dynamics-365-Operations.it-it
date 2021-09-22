---
title: Impossibile impostare la quantità dell'articolo di tipo Assistenza in una riga dell'offerta di vendita
description: Quando si utilizzano le offerte di vendita, non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza, perché non sono presenti articoli fisici da conteggiare.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476809"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Impossibile modificare la quantità di vendita di un articolo di tipo Assistenza in una riga di offerta di vendita

## <a name="symptoms"></a>Sintomi

Se provi a impostare una quantità di vendita (campo **SalesQty**) per un elemento di tipo *Servizio*, in una riga dell'offerta di vendita, verrà visualizzato il seguente messaggio:

> Aggiornamento non consentito per il campo Quantità.

## <a name="cause"></a>Causa

Questo comportamento è predefinito. Non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza. Ad esempio, se offri un servizio per installare un articolo, non ha senso registrare una quantità, perché non esiste un articolo fisico da conteggiare. Esiste solo un servizio.
