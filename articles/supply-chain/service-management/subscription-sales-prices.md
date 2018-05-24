---
title: Prezzi di vendita sottoscrizione
description: Quando si crea una sottoscrizione, il prezzo di vendita deriva dall'impostazione del prezzo di vendita creata nel modulo Sottoscrizione prezzo di vendita.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d9d462121915ce3f800581a9540dc1ef8f6e785f
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="subscription-sales-prices"></a>Prezzi di vendita sottoscrizione   

[!include [banner](../includes/banner.md)]


Quando si crea una sottoscrizione, il prezzo di vendita deriva dall'impostazione del prezzo di vendita creata nel modulo **Sottoscrizione prezzo di vendita**.

Nel modulo **Sottoscrizione prezzo di vendita** è possibile creare prezzi di vendita per una sottoscrizione specifica o prezzi di vendita da applicare su più larga scala. Per applicare un prezzo di vendita a una sottoscrizione, il codice periodo e la valuta della sottoscrizione e del prezzo di vendita devono essere identici.

Se il codice periodo e la valuta sono identici per la sottoscrizione e per il prezzo di vendita, i prezzi di vendita di sottoscrizione verranno selezionati sulla base delle priorità elencate nella seguente tabella. Una cella vuota nella tabella indica un campo vuoto e la X indica un valore uguale al valore nella sottoscrizione da cui viene generata la transazione.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Priorità </p></th>
<th><p><strong>Categoria</strong></p></th>
<th><p><strong>ID progetto</strong></p></th>
<th><p><strong>Sottoscrizione</strong></p></th>
<th><p><strong>Valuta di vendita</strong></p></th>
<th><p><strong>Codice periodo</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


Quando viene creata una commissione di sottoscrizione, viene selezionato come prezzo di vendita di sottoscrizione il prezzo di vendita con il livello massimo di dettagli, come indicato nella tabella sopra riportata.

## <a name="update-and-index-subscription-sales-prices"></a>Aggiornare e indicizzare i prezzi di vendita di sottoscrizione

È possibile aggiornare il prezzo di vendita di sottoscrizione aggiornando l'indice o il prezzo di base. L'aggiornamento può essere eseguito in base a un valore percentuale o a un nuovo valore.

## <a name="subscription-fee-sales-prices"></a>Prezzi di vendita di commissioni di sottoscrizione

Quando si crea una commissione di sottoscrizione, il prezzo di vendita è basato sull'impostazione del prezzo di vendita della sottoscrizione. È possibile utilizzare il prezzo di base dell'impostazione del prezzo di sottoscrizione oppure creare prezzi di vendita indicizzati.

## <a name="example"></a>Esempio

Si desidera impostare prezzi di vendita di sottoscrizione di 500 EUR per un nuovo progetto 9030. Nel modulo **Sottoscrizione prezzo di vendita** creare una riga del prezzo di vendita di sottoscrizione come indicato nella tabella seguente:

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valido dal</p></th>
<th><p>Categoria</p></th>
<th><p>Progetto</p></th>
<th><p>Sottoscrizione</p></th>
<th><p>Codice periodo</p></th>
<th><p>Valuta di vendita</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mese</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Si noti che i campi **Categoria** e **Sottoscrizione** sono vuoti.

Creare a questo punto le seguenti sottoscrizioni.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Sottoscrizione assistenza</p></th>
<th><p>Progetto</p></th>
<th><p>Gruppo di sottoscrizioni</p></th>
<th><p>Categoria</p></th>
<th><p>Valuta</p></th>
<th><p>Codice periodo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat1</p></td>
<td><p>EUR</p></td>
<td><p>Mensile</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>Mensile</p></td>
</tr>
</tbody>
</table>


Creare ora commissioni di sottoscrizione per entrambe le sottoscrizioni del gruppo di sottoscrizioni Sub1:

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.

2.  Nel modulo **Gruppi di sottoscrizioni**, fare clic su **Funzione** \> **Crea commissione sottoscrizione**.

3.  Nel modulo **Crea commissione sottoscrizione**, immettere le informazioni appropriate. Per ulteriori informazioni, vedere [Creare transazioni di commissione di sottoscrizione](create-subscription-fee-transactions.md).

Verranno create commissioni di sottoscrizione con prezzo di vendita di 500 EUR per entrambe le sottoscrizioni, come illustrato nella tabella seguente.

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
<th><p>Data progetto</p></th>
<th><p>Sottoscrizione assistenza</p></th>
<th><p>Progetto</p></th>
<th><p>Categoria</p></th>
<th><p>Data di inizio</p></th>
<th><p>Data di fine</p></th>
<th><p>Valuta di vendita</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01/01/2007</p></td>
<td><p>31/03/2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28/08/2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01/01/2007</p></td>
<td><p>31/03/2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Si decide successivamente che si desidera specificare i prezzi di vendita per la categoria SubCat1 del progetto 9030. Viene creata pertanto una nuova riga con prezzo di vendita di 550 EUR per la combinazione del progetto 9030 e della categoria di commissione SubCat1. Per il progetto 9030 ora sono presenti due righe di prezzo di vendita di sottoscrizione, come illustrato nella tabella seguente.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valido dal</p></th>
<th><p>Categoria</p></th>
<th><p>Progetto</p></th>
<th><p>Sottoscrizione</p></th>
<th><p>Codice periodo</p></th>
<th><p>Valuta</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/08/2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mese</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28/08/2007</p></td>
<td><p>SubCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mese</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Ripetere la procedura sopra descritta per creare commissioni di sottoscrizione per entrambe le sottoscrizioni del gruppo di sottoscrizioni Sub1. Nella tabella seguente vengono illustrate le transazioni create per ogni sottoscrizione collegata al gruppo di sottoscrizioni.

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
<th><p>Data progetto</p></th>
<th><p>Sottoscrizione</p></th>
<th><p>Progetto</p></th>
<th><p>Categoria</p></th>
<th><p>Data di inizio</p></th>
<th><p>Data di fine</p></th>
<th><p>Valuta di vendita</p></th>
<th><p>Prezzo di vendita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28/07/2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01/01/2008</p></td>
<td><p>31/03/2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28/07/2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01/01/2008</p></td>
<td><p>31/03/2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Nella prima transazione della sottoscrizione 00020\_135 il prezzo di vendita di 550 EUR deriva dal prezzo di vendita di sottoscrizione impostato per la combinazione di progetto e categoria specifici. Nella seconda transazione della sottoscrizione 00021\_135 il prezzo di vendita di 500 EUR viene utilizzato come prezzo di vendita di sottoscrizione del progetto, poiché per la combinazione del progetto 9030 e della categoria SubCat2 non è impostato alcun prezzo.

## <a name="see-also"></a>Vedere anche

[Aggiornare e indicizzare i prezzi di vendita di sottoscrizione](update-and-index-subscription-sales-prices.md)

  



