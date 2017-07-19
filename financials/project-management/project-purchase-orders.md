---
title: Ordini fornitore per un progetto
description: Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 9715d33598c0749ff1ad2523f2fa8834987998ed
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="purchase-orders-for-a-project"></a>Ordini fornitore per un progetto

[!include[banner](../includes/banner.md)]


Questo articolo descrive i vari metodi da utilizzare per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.

In Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, è possibile utilizzare più metodi per creare ordini fornitore per un progetto. Il metodo utilizzato dipende dallo scopo dell'ordine fornitore, da quando gli articoli acquistati vengono consumati e da quando vengono addebitati a un progetto.

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




