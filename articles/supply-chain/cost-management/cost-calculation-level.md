---
title: Livello di calcolo dei costi
description: Questo argomento descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: a3cd2783ae120ac6681431c010b9b126a9ca7d94
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3410960"
---
# <a name="cost-calculation-level"></a>Livello di calcolo costi

Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli. Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi. In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.

Il seguente semplice scenario mostra le differenze tra il livello DBS **Livello di calcolo dei costi** e il livello DBS **Livello di determinazione costi**Livello DBA.

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
