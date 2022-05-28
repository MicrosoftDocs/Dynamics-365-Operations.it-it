---
title: Esempio di giorni di riduzione
description: Esempio di giorni di riduzione.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85e588273244c88ffa208e88b66800dc7ce20d68
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674815"
---
# <a name="reduction-days-example"></a>Esempio di giorni di riduzione

[!include [banner](../includes/banner.md)]

È stata creata una transazione di sottoscrizione per la sottoscrizione di manutenzione di un cliente come descritto nella seguente tabella.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
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
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]