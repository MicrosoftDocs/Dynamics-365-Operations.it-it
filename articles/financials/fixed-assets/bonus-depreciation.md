---
title: ammortamento straordinario
description: "Questo articolo fornisce una panoramica delle funzionalità di ammortamento straordinario."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 414440332d313cfef72ce65ac3cd842d19390aad
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="bonus-depreciation"></a>ammortamento straordinario

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica delle funzionalità di ammortamento straordinario.

La funzionalità di ammortamento aggiuntivo consente di applicare importi di ammortamento straordinari durante il primo anno in cui il cespite viene messo in servizio e ammortizzato. L'ammortamento aggiuntivo deve essere applicato prima di qualsiasi altro calcolo dell'ammortamento. Di conseguenza, è preferibile utilizzare l'ammortamento straordinario con i libri in cui la funzionalità Registra nella contabilità generale è disabilitata. È possibile utilizzare l'opzione **Elimina transazioni non registrate nella contabilità generale** per eliminare lo storico transazioni per i libri che non registrano nella contabilità generale. È quindi possibile inserire successivamente l'ammortamento aggiuntivo nel ciclo di vita del cespite eliminando le transazioni di ammortamento precedentemente registrate. 

È possibile calcolare l'ammortamento aggiuntivo utilizzando il processo di proposta o creando transazioni di ammortamento aggiuntivo manuali. Non è possibile creare transazioni di ammortamento straordinario se per un determinato libro cespiti sono presenti transazioni di ammortamento o transazioni di rettifica ammortamento.

Quando si utilizza il processo di proposta per calcolare l'ammortamento aggiuntivo, tutte le transazioni di ammortamento aggiuntivo esistenti saranno incluse nel calcolo della base, compresi eventuali ammortamenti aggiuntivi precedenti immessi manualmente per il cespite. 

La priorità viene considerata quando è necessario applicare più ammortamenti straordinari per un singolo cespite. Ciascun ammortamento aggiuntivo contribuisce alla riduzione della base di ammortamento del cespite per il successivo ammortamento aggiuntivo. Il valore di realizzo non viene considerato nella base di ammortamento per i calcoli di ammortamento straordinario e la convenzione di ammortamento non viene applicata per questo tipo di ammortamento. 

Attualmente negli Stati Uniti alcune proprietà sono classificate come proprietà regolamentate dalla sezione 179. Per sezione 179 si intende la facoltà di recuperare totalmente o parzialmente il costo di determinate proprietà, fino a un certo limite, detraendo tale costo nell'anno in cui la proprietà viene messa in servizio.

## <a name="example"></a>Esempio
Si supponga che i seguenti ammortamenti aggiuntivi siano associati a un libro cespiti:

-   **Sezione 179:** 1.000,00, priorità 1
-   **Zona A:** 30%, priorità 2

Il costo dell'acquisizione cespiti è di 5.000. Quando viene calcolato l'ammortamento aggiuntivo, il primo importo sarà di 1.000 per l'ammortamento come da sezione 179. 

Il successivo importo di ammortamento aggiuntivo, per l'ammortamento relativo alla Zona A, viene calcolato come segue: 

Costo di acquisizione: 1.000 (ammortamento come da sezione 179) x 30% = 1.200 

Se l'importo di ammortamento aggiuntivo è maggiore del costo di acquisizione rimanente, tale importo corrisponderà al calcolo dell'ammortamento aggiuntivo o al costo di acquisizione rimanente, a seconda dell'importo inferiore. 

Se il costo di acquisizione rimanente è uguale o inferiore a 0 (zero), non verranno generate transazioni di ammortamento aggiuntivo. 

Quando l'ammortamento aggiuntivo viene calcolato mediante il processo di proposta, verrà creata una transazione di ammortamento aggiuntivo per tutti i record di ammortamento aggiuntivo applicabili associati al libro cespiti. 

È possibile creare un numero illimitato di record di ammortamento aggiuntivo. Una volta assegnati tali record al libro gruppo cespite, questi record vengono applicati al libro cespiti. 

L'ammortamento aggiuntivo viene immesso sotto forma di percentuale o di importo fisso. Quando si registrano le proposte di ammortamento, le transazioni relative a questo tipo di ammortamento vengono registrate nel libro come transazioni distinte dalle altre.




