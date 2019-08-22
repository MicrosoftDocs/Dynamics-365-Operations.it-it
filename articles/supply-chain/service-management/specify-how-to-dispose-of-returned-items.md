---
title: Specificare la modalità di smaltimento dei resi
description: Specificare la modalità di smaltimento dei resi.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6991fc04f5015fc3d604306e9327a5e551e728db
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743074"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Specificare la modalità di smaltimento dei resi 

[!include [banner](../includes/banner.md)]


Quando si gestisce un ordine di reso, è necessario specificare un codice motivo reso per identificare poiché il prodotto viene restituito. È inoltre necessario specificare un codice smaltimento e un'azione di smaltimento per determinare cosa deve essere effettuato con il prodotto restituito.

È possibile applicare un codice smaltimento quando si crea l'ordine di reso, si registra l'arrivo dell'articolo, si aggiorna il documento di trasporto specificando che l'articolo è arrivato oppure quando si termina un ordine di quarantena.

È possibile definire tutti i codici smaltimento necessari per il processo aziendale. Nella tabella riportata di seguito è disponibile l'insieme dei codici più comunemente utilizzati per specificare la modalità di smaltimento dei resi.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo di smaltimento</p></th>
<th><p>Codice comune</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dismissione</p></td>
<td><p>SC</p></td>
<td><p>Scarto/distruzione</p></td>
</tr>
<tr class="even">
<td><p>Dismissione</p></td>
<td><p>Controller di dominio</p></td>
<td><p>Donazione in beneficenza</p></td>
</tr>
<tr class="odd">
<td><p>Dismissione</p></td>
<td><p>TD</p></td>
<td><p>Dismissione effettuata da terzi</p></td>
</tr>
<tr class="even">
<td><p>Dismissione</p></td>
<td><p>SL</p></td>
<td><p>Realizzo</p></td>
</tr>
<tr class="odd">
<td><p>Dismissione</p></td>
<td><p>TS</p></td>
<td><p>Vendita a terzi (mercati secondari)</p></td>
</tr>
<tr class="even">
<td><p>Riparazione/Modifica</p></td>
<td><p>RW</p></td>
<td><p>Rilavorazione</p></td>
</tr>
<tr class="odd">
<td><p>Riparazione/Modifica</p></td>
<td><p>RF</p></td>
<td><p>Rifabbricazione/rinnovamento</p></td>
</tr>
<tr class="even">
<td><p>Riparazione/Modifica</p></td>
<td><p>MD</p></td>
<td><p>Modifica</p></td>
</tr>
<tr class="odd">
<td><p>Riparazione/Modifica</p></td>
<td><p>RP</p></td>
<td><p>Riparazione</p></td>
</tr>
<tr class="even">
<td><p>Riparazione/Modifica</p></td>
<td><p>RV</p></td>
<td><p>Restituzione al fornitore</p></td>
</tr>
<tr class="odd">
<td><p>Altro</p></td>
<td><p>AI</p></td>
<td><p>Utilizzo degli articoli così come sono</p></td>
</tr>
<tr class="even">
<td><p>Altro</p></td>
<td><p>RS</p></td>
<td><p>Rivendita</p></td>
</tr>
<tr class="odd">
<td><p>Altro</p></td>
<td><p>EX</p></td>
<td><p>Scambia</p></td>
</tr>
<tr class="even">
<td><p>Altro</p></td>
<td><p>MS</p></td>
<td><p>Varie</p></td>
</tr>
</tbody>
</table>


Per ogni codice smaltimento definito, è necessario selezionare un'azione di smaltimento. L'azione di smaltimento determina le implicazioni fisiche e finanziarie dei codici smaltimento. Ad esempio, l'azione di smaltimento determina la gestione fisica dell'articolo reso, il relativo effetto finanziario e se è richiesto l'invio al cliente di un articolo sostitutivo. È possibile definire un numero illimitato di codici smaltimento in base alle proprie esigenze, ma è possibile scegliere solo tra sei azioni di smaltimento predefinite. Nella tabella seguente vengono illustrate le azioni di smaltimento e le relative definizioni.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Azione di smaltimento</p></th>
<th><p>descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Avere</strong></p></td>
<td><p>Restituire l'articolo al magazzino ed effettuare l'accredito al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Solo credito</strong></p></td>
<td><p>Effettuare l'accredito al cliente senza richiedere o prevedere la restituzione dell'articolo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Scarti</strong></p></td>
<td><p>Scartare l'articolo ed effettuare l'accredito al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sostituzione e credito</strong></p></td>
<td><p>Restituire l'articolo al magazzino, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sostituzione e scarto</strong></p></td>
<td><p>Scartare l'articolo, creare un ordine sostitutivo ed effettuare l'accredito al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Reso a cliente</strong></p></td>
<td><p>Rifiutare l'articolo reso e restituirlo al cliente.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Selezionare un codice smaltimento per un ordine di quarantena

1.  Fare clic su **Gestione articoli** \> **Periodico** \> **Gestione qualità** \> **Ordini di quarantena**.

2.  In caso di ordini di quarantena esistenti, selezionare un'azione nel campo **Codice smaltimento** della scheda **Panoramica**.



## <a name="see-also"></a>Vedere anche

[Ordine di quarantena (modulo)](https://technet.microsoft.com/library/aa554073(v=ax.60))

[Codici smaltimento (modulo)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

  


