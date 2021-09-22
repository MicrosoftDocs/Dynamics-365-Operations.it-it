---
title: I processi in corso terminano quando si dichiara la quantità parziale sull'ultimo processo
description: Quando si utilizza il dispositivo scheda processo per dichiarare una quantità parziale sull'ultimo processo in un ordine di produzione, tutti i processi precedenti che hanno lo stato In corso vengono terminati.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476810"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>I processi in corso precedenti vengono terminati quando si dichiara la quantità parziale sull'ultimo processo

## <a name="symptoms"></a>Sintomi

Quando si utilizza il dispositivo scheda processo per dichiarare una quantità parziale sull'ultimo processo in un ordine di produzione, tutti i processi precedenti su quell'ordine che hanno lo stato In corso vengono automaticamente terminati.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. Nella pagina **Impostazioni predefinite ordine di produzione**, nella scheda **Dichiarazione di finito**, è presente un'opzione denominata **Ciclo di lavorazione con contrassegno di fine**. Se questo argomento è impostato su *Sì*, viene registrato un giornale di registrazione delle schede cicli di lavorazione quando un lavoratore utilizza il dispositivo scheda processo o il terminale scheda processo per dichiarare l'ultima operazione. Questo giornale contrassegna tutte le operazioni come completate e termina tutti i processi di produzione. Quando l'opzione **Ciclo di lavorazione con contrassegno di fine** è impostata su *Sì*, il sistema non considera lo stato del processo che il lavoratore ha selezionato quando ha dichiarato l'ultima operazione. Il sistema inoltre non considera se il lavoratore sta dichiarando una quantità totale o parziale.
