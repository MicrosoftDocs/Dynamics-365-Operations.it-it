---
title: Articoli di reso in più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi in più fatture e ordini cliente in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 1/08/2019
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
ms.openlocfilehash: d2cf6f92e90ef196827abb599c65c732615ec7bb
ms.sourcegitcommit: e72eae546d48d41d4b07ff78cfc0242c32b793e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2019
ms.locfileid: "373070"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Articoli di reso in più fatture e ordini cliente

[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

Nella versione 10.0 di Dynamics 365 for Finance and Operations, i resi possono essere eseguiti in più ordini e fatture, mentre nelle versioni precedenti alla 10.0 era possibile elaborare i resi solo per un'unica fattura alla volta. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurare Retail per supportare i resi in più fatture e ordini cliente

1. Andare a **Parametri Retail \> Ordini cliente**.
1. Attivare il parametro **Consenti resi per più ordini**. 

## <a name="process-returns"></a>Elaborare i resi

Dopo che il parametro è attivato e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.

Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini. A questo punto il cassiere può selezionare i prodotti da restituire. Un unico ordine di reso verrà creato per tutti i prodotti selezionati.
