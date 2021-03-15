---
title: Risolvere i problemi relativi alle offerte di vendita
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 98011dbf22ff55b7651ce63557fa4a360130b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974762"
---
# <a name="troubleshoot-sales-quotations"></a>Risolvere i problemi relativi alle offerte di vendita

Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Non riesco a modificare la quantità di vendita di un'offerta di vendita per un articolo di tipo Assistenza.

### <a name="issue-description"></a>Descrizione del problema

Se provi a impostare una quantità di vendita (campo **SalesQty**) per un elemento di tipo *Servizio*, in una riga dell'offerta di vendita, verrà visualizzato il seguente messaggio: "Aggiornamento non consentito per il campo Quantità".

### <a name="issue-resolution"></a>Risoluzione dei problemi

Non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza. Ad esempio, se offri un servizio per installare un articolo, non ha senso registrare una quantità, perché non esiste un articolo fisico. Esiste solo un servizio.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]