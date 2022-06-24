---
title: Livello di calcolo costi
description: Questo articolo descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: JennySong-SH
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 647ef4b13b864cfdbb7905fe7a0d340e85f6c1e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850875"
---
# <a name="cost-calculation-level"></a>Livello di calcolo costi

[!include [banner](../includes/banner.md)]

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