---
title: Articoli di reso in più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi in più fatture e ordini cliente in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565302"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Articoli di reso in più fatture e ordini cliente

[!include [banner](includes/banner.md)]


Nella versione 10.0 di Dynamics 365 for Finance and Operations, i resi possono essere eseguiti in più ordini e fatture, mentre nelle versioni precedenti alla 10.0 era possibile elaborare i resi solo per un'unica fattura alla volta. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurare Retail per supportare i resi in più fatture e ordini cliente

1. Andare a **Parametri di vendita al dettaglio \> Ordini cliente**.
1. Attivare il parametro **Consenti resi per più ordini**. 

## <a name="process-returns"></a>Elaborare i resi

Dopo che il parametro è attivato e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.

Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini. A questo punto il cassiere può selezionare i prodotti da restituire. Un unico ordine di reso verrà creato per tutti i prodotti selezionati.
