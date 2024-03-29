---
title: Articoli di reso per più fatture e ordini cliente
description: In questo articolo viene descritta la funzionalità che consente di eseguire resi per più fatture e ordini cliente in Dynamics 365 Commerce.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890323"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Articoli di reso per più fatture e ordini cliente

[!include [banner](includes/banner.md)]


I resi possono essere effettuati per più fatture e ordini cliente. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>Configurare Commerce per supportare i resi per più fatture e ordini cliente

1. Andare a **Parametri di commercio \> Ordini cliente**.
1. Attivare il parametro **Consenti resi per più ordini**. 

## <a name="process-returns"></a>Elaborare i resi

Dopo che il parametro è attivato e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.

Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini. A questo punto il cassiere può selezionare i prodotti da restituire. Un unico ordine di reso verrà creato per tutti i prodotti selezionati.
