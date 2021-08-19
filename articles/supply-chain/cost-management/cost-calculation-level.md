---
title: Livello di calcolo dei costi
description: Questo argomento descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 41f2550ff22b838aa5d85022582fd9715917fe462aa34dbfc833941f5ada3325
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717392"
---
# <a name="cost-calculation-level"></a>Livello di calcolo costi

Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli. Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi. In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.

Il seguente semplice scenario mostra le differenze tra il livello DBS **Livello di calcolo dei costi** e il livello DBS **Livello di determinazione costi** Livello DBA.

Sono disponibili tre prodotti: A, B e C. Il prodotto C è il componente del prodotto B e il prodotto B è il componente del prodotto A.

- **Livello di detyerminazione costi** assegna i seguenti livelli DBA:

    - **Prodotto A:** 0
    - **Prodotto B:** 1
    - **Prodotto C:** 2

- **Livello di detyerminazione costi** assegna i seguenti livelli DBA:

    - **Prodotto A:** 0
    - **Prodotto B:** 1
    - **Prodotto C:** 2

Un ordine di produzione per il prodotto C viene quindi creato e il prodotto A è aggiunto alla DBA dell'ordine di produzione. Dopo la stima dell'ordine, i livelli DBA vengono aggiornati nel modo seguente:

- **Livello di detyerminazione costi** assegna i seguenti livelli DBA:

    - **Prodotto B:** 1
    - **Prodotto C:** 2
    - **Prodotto A:** 3

- **Livello di detyerminazione costi** assegna i seguenti livelli DBA:

    - **Prodotto A:** 0
    - **Prodotto B:** 1
    - **Prodotto C:** 2

Questo comportamento garantisce che le modifiche alle DBA dell'ordine di produzione non influiscano sui calcoli dei costi successivi.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]