---
title: Dimensioni finanziarie e conti principali in una lingua da destra a sinistra
description: "In questo argomento vengono descritte alcune decisioni di implementazione che è opportuno considerare quando si utilizza una lingua da destra a sinistra in Microsoft Dynamics 365 for Operations e è necessario impostare le dimensioni finanziarie e i conti principali."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b1f196d2a13bba49647dd4f008cd39b7417940f1
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a>Dimensioni finanziarie e conti principali in una lingua da destra a sinistra

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritte alcune decisioni di implementazione che è opportuno considerare quando si utilizza una lingua da destra a sinistra in Microsoft Dynamics 365 for Operations e è necessario impostare le dimensioni finanziarie e i conti principali.

Le dimensioni finanziarie e i conti principali sono componenti chiave della fase di pianificazione di un'implementazione. Dopo che le dimensioni finanziarie e i conti principali vengono creati nel sistema, questi vengono usati nelle pagine **Configura strutture dei conti** **Strutture regole avanzate** e **Configurazione dimensione finanziaria per integrazione applicazioni**. L'ordine definito in queste pagine viene utilizzato nel sistema per l'immissione e l'utilizzo dei dati. In alcuni aree del sistema, dimensioni finanziarie e i conti principali vengono visualizzati in campi separati. Tuttavia, in altre aree, ad esempio i giornali di registrazione, le dimensioni finanziarie e i conti principali vengono visualizzate come singola stringa.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Procedure consigliate per impostare le dimensioni finanziarie e i conti principali in un sistema destra-sinistra

-   Quando si seleziona il delimitatore per i piani dei conti, selezionare una delle opzioni di doppio delimitatore: doppio trattino (--), doppia barra (||) o doppio punto (..) o doppio carattere di sottolineatura (\_\_).
-   Quando si creano i valori delle dimensioni finanziarie e dei conti principali, utilizzare solo numeri e caratteri di lingue da destra a sinistra.
-   Evitare di utilizzare il delimitatore di piano dei conti selezionato nei valori delle dimensioni finanziarie e dei conti principali.

Seguendo queste procedure consigliate, contribuite a garantire la rappresentazione coerente dell'ordine definito dall'utente in ogni parte del sistema.




