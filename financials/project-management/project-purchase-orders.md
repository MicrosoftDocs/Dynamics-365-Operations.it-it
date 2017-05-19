---
title: Ordini fornitore per un progetto
description: Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell&quot;ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2a0c21c2937600d1e31f9326970e52e3bdcff90c
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="purchase-orders-for-a-project"></a>Ordini fornitore per un progetto

[!include[banner](../includes/banner.md)]


Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.

In Microsoft Dynamics 365 for Operations, è possibile utilizzare più metodi per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.

### <a name="methods-for-creating-a-purchase-order"></a>Metodi per la creazione di un ordine fornitore

Per creare un ordine fornitore nel modulo Gestione progetti e contabilità, è possibile utilizzare uno dei seguenti metodi. Lo scopo dell'ordine fornitore determina quando verrà consumato l'ordine e, di conseguenza, quando gli articoli verranno addebitati a un progetto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metodo</th>
<th>Scopo</th>
<th>Consumo articoli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Creare un ordine fornitore direttamente da un progetto.</td>
<td>Utilizzare questo metodo per acquistare articoli da un fornitore esterno per il consumo nell'ambito di un progetto. È possibile creare l'ordine fornitore in due modi:
<ul>
<li>Dal progetto stesso. In questo caso il progetto è già definito per l'ordine fornitore.</li>
<li>Accedendo all'ordine fornitore del progetto. È necessario selezionare sia il fornitore sia il progetto per cui viene creato l'ordine fornitore.</li>
</ul></td>
<td>Gli articoli vengono consumati quando viene aggiornata la fattura fornitore.</td>
</tr>
<tr class="even">
<td>Creare un ordine fornitore da un ordine cliente.</td>
<td>Utilizzare questo metodo per acquistare articoli quando si crea un ordine cliente da un progetto.</td>
<td>Gli articoli vengono consumati quando l'ordine cliente viene fatturato al cliente.</td>
</tr>
<tr class="odd">
<td>Creare un ordine fornitore da una richiesta articolo.</td>
<td>Utilizzare questo metodo per acquistare articoli quando si crea una richiesta articolo da un progetto.</td>
<td>Gli articoli vengono consumati quando viene aggiornato il documento di trasporto relativo alla richiesta articolo.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Quando si aggiorna la fattura fornitore o il documento di trasporto, verrà chiesto di aggiornare il documento di trasporto per la richiesta articolo.




