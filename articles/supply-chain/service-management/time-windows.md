---
title: Intervalli di tempo
description: È possibile utilizzare gli intervalli di tempo per ottimizzare la programmazione delle righe di ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f64718e6a96cacc005644cbf4286e743111c02f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996503"
---
# <a name="time-windows"></a>Intervalli di tempo  

[!include [banner](../includes/banner.md)]

È possibile utilizzare gli intervalli di tempo per ottimizzare la programmazione delle righe di ordine di assistenza. È possibile impostare il sistema in modo da creare automaticamente gli ordini di assistenza. In base ai criteri specificati da un intervallo di tempo, è possibile collegare qualsiasi numero possibile di righe di ordine di assistenza al minor numero possibile di pochi ordini di assistenza.

Gli intervalli di tempo definiscono il numero massimo di giorni di cui una riga di un ordine di assistenza può essere spostata rispetto alla data calcolata. La data calcolata è la data in cui è stata programmata la riga ordine di assistenza. La data è basata sulla relativa impostazione di intervallo e sul periodo di assistenza definiti nella pagina **Crea ordini di assistenza**. Per definire un intervallo di tempo utilizzando i valori nella seguente tabella.

| Metodo | descrizione                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Settimana   | La data in cui la riga dell'ordine di assistenza può essere spostata in qualsiasi giorno lavorativo nella stessa settimana della data calcolata in origine.                                                                                                                                                                                    |
| Mese  | La data in cui la riga dell'ordine di assistenza può essere spostata in qualsiasi giorno lavorativo nello stesso mese della data calcolata in origine. Ad esempio, la data calcolata per una riga dell'ordine di assistenza è il 15 febbraio 2017. La riga di ordine di assistenza può essere programmata per qualsiasi giorno della settimana tra il 1 febbraio e il 28 febbraio 2017. |
| Manuale | Definire il numero massimo di giorni di cui la riga dell'ordine di assistenza può essere spostata prima o dopo la data calcolata in origine.                                                                                                                                                                           |

Se per una riga di un contratto di assistenza non è stato specificato un intervallo di tempo, la riga dell'ordine di assistenza risultante dal contratto di assistenza dovrà essere eseguita nella data esatta programmata inizialmente.

## <a name="related-topics"></a>Argomenti correlati

[Creare intervalli di tempo](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]