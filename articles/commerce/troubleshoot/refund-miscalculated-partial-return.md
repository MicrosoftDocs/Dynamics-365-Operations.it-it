---
title: Le spese rimborsabili sono calcolate erroneamente in base alla quantità restituita
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i cassieri vedono addebiti rimborsabili errati nel punto vendita (POS) per la quantità di articoli restituiti.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c8ecaa0cb73d06ac66b57cce815264e841a2259b
ms.sourcegitcommit: 94ebdaae6dc996b205ac78ed546e38f91f4f46ed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2022
ms.locfileid: "8490215"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Le spese rimborsabili sono calcolate erroneamente in base alla quantità restituita

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i cassieri vedono addebiti rimborsabili errati nel punto vendita (POS) per la quantità di articoli restituiti.

## <a name="description"></a>Description

Un cliente restituisce una quantità parziale degli articoli acquistati per un ordine cliente con addebiti rimborsabili a livello di riga. Tuttavia, invece di mostrare un rimborso parziale, il POS mostra tutti gli addebiti come rimborsabili.

Ad esempio, un cliente acquista una quantità di cinque articoli a 5 USD per articolo, per un addebito totale di 25 USD. Il cliente restituisce quindi tre dei cinque articoli. Tuttavia, al cassiere viene mostrato un addebito rimborsabile 25 USD nel POS, invece dell'addebito rimborsabile 15 USD previsto per i tre articoli che sono stati restituiti.

## <a name="resolution"></a>Risoluzione

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Attivare la funzionalità Abilita spese di rimborso in base alla quantità rimborsata

A partire da Microsoft Dynamics 365 Commerce versione 10.0.26, la funzione **Abilita spese di rimborso in base alla quantità rimborsata** consente di calcolare gli addebiti rimborsabili a livello di riga in base alla quantità di articoli restituiti.

Per abilitare la funzionalità **Abilita spese di rimborso in base alla quantità rimborsata** in Commerce headquarters, attieniti alla seguente procedura.

1. Apri l'area di lavoro **Gestione funzionalità** (**Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**).
1. Nell'elenco delle funzioni disponibili, cerca e seleziona la funzionalità **Abilita spese di rimborso in base alla quantità rimborsata**.
1. Nel riquadro di destra, seleziona **Abilita ora**.
