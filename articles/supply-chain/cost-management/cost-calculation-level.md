---
title: Livello di calcolo costi
description: Questo articolo descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e63a868696e36c1d4f5d19ea87bdf4d682c39f8c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334957"
---
# <a name="cost-calculation-level"></a>Livello di calcolo costi

[!include [banner](../includes/banner.md)]

Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli. Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi. In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.

## <a name="turn-the-cost-calculation-level-feature-on-or-off"></a>Attivare o disattivare la funzionalità Livello di calcolo costi

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Livello di calcolo costi* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="example-scenario"></a>Scenario di esempio

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