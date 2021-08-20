---
title: Interazione dei campi Stato e Avanzamento relativi agli ordini di assistenza
description: Nel modulo Ordini di assistenza il campo Avanzamento nell'intestazione dell'ordine di assistenza riflette lo stato dell'intero ordine di assistenza, mentre nel campo Stato è indicato lo stato delle singole righe dell'ordine di assistenza.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 210ff82a904e9657d9808a0994c70683e9126622d279aae94e946be0c4f484c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756054"
---
# <a name="service-status-and-progress-field-interaction"></a>Interazione dei campi Stato e Avanzamento relativi agli ordini di assistenza 

[!include [banner](../includes/banner.md)]


Nel modulo **Ordini di assistenza** il campo **Avanzamento** nell'intestazione dell'ordine di assistenza riflette lo stato dell'intero ordine di assistenza, mentre nel campo **Stato** è indicato lo stato delle singole righe dell'ordine di assistenza.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Avanzamento</p></th>
<th><p>Stato riga 1</p></th>
<th><p>Stato riga 2</p></th>
<th><p>Stato riga 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>In corso</strong></p></td>
<td><p><strong>Creato</strong></p></td>
<td><p><strong>Creato</strong></p></td>
<td><p><strong>Creato</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>In corso</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Creato</strong></p></td>
<td><p><strong>Creato</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>In corso</strong></p></td>
<td><p><strong>Creato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Contabilizzato</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Contabilizzato</strong></p></td>
<td><p><strong>Contabilizzato</strong></p></td>
<td><p><strong>Contabilizzato</strong></p></td>
<td><p><strong>Contabilizzato</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Contabilizzato</strong></p></td>
<td><p><strong>Contabilizzato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
<td><p><strong>Annullato</strong></p></td>
</tr>
</tbody>
</table>


L'avanzamento di un ordine di assistenza è In corso se in tutte le righe è presente lo stato **Creato** e anche se in alcune righe è presente lo stato **Annullato** o **Contabilizzato**.

Se tutte le righe in un ordine di assistenza sono contrassegnate dallo stato **Contabilizzato**, l'avanzamento dell'ordine di assistenza è **Contabilizzato**. Se lo stato di alcune righe è **Contabilizzato** e di altre è **Annullato**, l'avanzamento è ancora **Contabilizzato**.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]