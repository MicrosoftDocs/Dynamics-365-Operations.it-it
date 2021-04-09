---
title: Articoli di reso per più fatture e ordini cliente
description: In questo argomento viene descritta la funzionalità che consente di eseguire resi per più fatture e ordini cliente in Dynamics 365 Commerce.
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
ms.openlocfilehash: 4a64794a0e04516441fab628d441640e4d154b8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796897"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Articoli di reso per più fatture e ordini cliente

[!include [banner](includes/banner.md)]


Questo articolo descrive due funzionalità che ottimizzano i resi degli ordini cliente su più fatture. 

## <a name="enable-refunds-over-multiple-captures"></a>Abilita rimborsi per più acquisizioni

Questa funzione consente più rimborsi collegati sullo stesso ordine cliente. 

1. Accedere all'area di lavoro **Gestione funzionalità** e cercare **Abilita rimborsi su più acquisizioni**.
2. Selezionare **Abilita rimborsi su più ordini** e quindi fare clic su **Abilita**. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Abilita il calcolo delle imposte corretto per i resi con quantità parziale

Questa funzione garantisce che quando un ordine viene restituito utilizzando più fatture, le imposte saranno pari all'importo delle imposte addebitato in origine. 

1. Accedere all'area di lavoro **Gestione funzionalità** e cercare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale**.
2. Selezionare **Abilita il calcolo delle imposte corretto per i resi con quantità parziale** e quindi fare clic su **Abilita**. 


## <a name="process-returns"></a>Elaborare i resi

Dopo che queste funzionalità sono attivate e le modifiche vengono sincronizzate nei punti vendita, il cassiere nel punto vendita può selezionare più ordini cliente relativi a un cliente per il reso.

Quando gli ordini sono selezionati, verrà visualizzato un elenco di tutti i prodotti restituibili in tutte le fatture per gli ordini. A questo punto il cassiere può selezionare i prodotti da restituire. Un unico ordine di reso verrà creato per tutti i prodotti selezionati.

Se l'ordine viene reso integralmente, l'importo delle imposte restituite al cliente sarà pari all'importo delle imposte addebitare in origine.



[!INCLUDE[footer-include](../includes/footer-banner.md)]