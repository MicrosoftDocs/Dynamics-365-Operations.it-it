---
title: Risolvere i problemi relativi alle offerte di vendita
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 92b77c1b7de1f5c946e677c810c0d0e43427473e7ba26679df23f7663946dbc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765396"
---
# <a name="troubleshoot-sales-quotations"></a>Risolvere i problemi relativi alle offerte di vendita

Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con le offerte di vendita.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Non riesco a modificare la quantità di vendita di un'offerta di vendita per un articolo di tipo Assistenza.

### <a name="issue-description"></a>Descrizione del problema

Se provi a impostare una quantità di vendita (campo **SalesQty**) per un elemento di tipo *Servizio*, in una riga dell'offerta di vendita, verrà visualizzato il seguente messaggio: "Aggiornamento non consentito per il campo Quantità".

### <a name="issue-resolution"></a>Risoluzione dei problemi

Non è possibile impostare una quantità di vendita per i prodotti che sono articoli di tipo Assistenza. Ad esempio, se offri un servizio per installare un articolo, non ha senso registrare una quantità, perché non esiste un articolo fisico. Esiste solo un servizio.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]