---
title: Esempio di giorni di riduzione
description: Esempio di giorni di riduzione.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a>Esempio di giorni di riduzione 

[!include [banner](../includes/banner.md)]


È stata creata una transazione di sottoscrizione per la sottoscrizione di manutenzione di un cliente come descritto nella seguente tabella.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Dal</p></th>
<th><p>Al</p></th>
<th><p>Sottoscrizione</p></th>
<th><p>Tipo di sottoscrizione</p></th>
<th><p>Progetto</p></th>
<th><p>Categoria</p></th>
<th><p>Valuta di vendita</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>01 marzo 2011</p></td>
<td><p>31 marzo 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Regolare</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>200,00</p></td>
</tr>
</tbody>
</table>


Il cliente segnala che la copertura del servizio non è necessaria per due giorni (10 marzo e 11 marzo). Si concorda quindi di applicare una riduzione della sottoscrizione per i due giorni citati.

Viene quindi creata una nuova transazione di tipo **Giorni riduzione** come descritto nella seguente tabella.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Dal</p></th>
<th><p>Al</p></th>
<th><p>Sottoscrizione</p></th>
<th><p>Tipo di sottoscrizione</p></th>
<th><p>Progetto</p></th>
<th><p>Categoria</p></th>
<th><p>Valuta di vendita</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>10 marzo 2011</p></td>
<td><p>11 marzo 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Giorni riduzione</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12,90</p></td>
</tr>
</tbody>
</table>


Quando le transazioni per marzo 2011 vengono fatturate, il prezzo di vendita di EUR 200 viene ridotto a EUR 12,90. L'importo addebitabile per la transazione di sottoscrizione è pertanto EUR 187,10 e vengono fatturate due transazioni per un totale di EUR 187,10.

## <a name="see-also"></a>Vedere anche

[Ridurre i giorni delle commissioni di sottoscrizione](reduce-the-days-on-subscription-fees.md)

  



