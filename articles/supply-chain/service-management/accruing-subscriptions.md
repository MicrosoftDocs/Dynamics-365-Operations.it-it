---
title: Accumulo delle sottoscrizioni
description: Con le sottoscrizioni di assistenza è possibile accumulare ricavi manualmente nei periodi successivi alla data in cui è stata fatturata una transazione sbilanciata.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ebd65655db56ee1169f24dbc79fbfb5130f06a5
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978823"
---
# <a name="accruing-subscriptions"></a>Accumulo delle sottoscrizioni 

[!include [banner](../includes/banner.md)]


Con le sottoscrizioni di assistenza è possibile accumulare ricavi manualmente nei periodi successivi alla data in cui è stata fatturata una transazione sbilanciata.

Per il periodo di fatturazione impostato per la commissione di sottoscrizione vengono creati periodi di attribuzione per competenza basati sul codice periodo della sottoscrizione.

È possibile accumulare e stornare i ricavi sospesi.

## <a name="reverse-accruals-of-credit-amounts"></a>Stornare i ricavi degli importi in Avere

Se si accreditano gli importi delle sottoscrizioni fatturate, è possibile utilizzare due metodi per stornare gli importi di attribuzione per competenza:

  - È possibile stornare ciascuna transazione relativa ai ricavi sospesi separatamente, prima di creare la proposta di nota di accredito per la transazione. Si tratta del metodo manuale. (manuale)

  - È possibile fare in modo che gli importi accumulati vengano stornati automaticamente nella data in cui la nota di accredito viene registrata o nella data di registrazione originaria dell'attribuzione per competenza.

Per ulteriori informazioni, vedere [Parametri sottoscrizione (modulo)](https://technet.microsoft.com/library/aa619615.aspx).

## <a name="setup-requirements"></a>Imposta requisiti

Per accumulare ricavi, assicurarsi che vengano soddisfatti i seguenti requisiti per i dati:

## <a name="account-setup"></a>Impostazione dei conti

I conti **WIP - Sottoscrizione** e **Ricavi sospesi - Sottoscrizione** devono essere impostati nel modulo **Gestione progetti**.

Quando si registrano i ricavi sospesi, l'importo di attribuzione per competenza viene addebitato sul conto **WIP - Sottoscrizione**. Tale importo viene invece accreditato sul conto **Ricavi sospesi - Sottoscrizione**.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Impostare i conti per l'attribuzione per competenza dei ricavi delle sottoscrizioni

1.  Fare clic su **Gestione progetti e contabilità** \> **Impostazioni** \> **Registrazione** \> **Impostazioni registrazione contabile**.

2.  Fare clic sulla scheda **Conti ricavi** e selezionare **WIP - Sottoscrizione** o **Ricavi sospesi - Sottoscrizione** per impostare i conti.

## <a name="subscription-group-setup"></a>Impostazione dei gruppi di sottoscrizioni

Per poter accumulare ricavi per le sottoscrizioni, è necessario che la casella di controllo **Accumula ricavi** sia selezionata. La casella di controllo si trova nel modulo **Gruppi di sottoscrizioni** per il gruppo associato alla sottoscrizione. Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Attivare l'attribuzione per competenza dei ricavi per un gruppo di sottoscrizioni

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Sottoscrizioni assistenza** \> **Gruppo di sottoscrizioni**.

## <a name="periods"></a>Periodi

È necessario impostare un codice periodo di fatturazione. È inoltre necessario impostare un periodo di attribuzione per competenza, a meno che non si desideri che i ricavi vengano accumulati entro gli stessi intervalli di tempo utilizzati per la fatturazione.

Nella seguente tabella viene fornita una panoramica dei periodi di attribuzione per competenza che è possibile impostare per ogni periodo di fatturazione.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Periodo di fatturazione</p></th>
<th><p>Periodo di attribuzione per competenza</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anni</strong></p></td>
<td><ul>
<li><p><strong>Anni</strong></p></li>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mese</strong></p></li>
<li><p><strong>Giorno</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Trimestre</strong></p></td>
<td><ul>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mese</strong></p></li>
<li><p><strong>Giorno</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Mese</strong></p></td>
<td><ul>
<li><p><strong>Mese</strong></p></li>
<li><p><strong>Giorno</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Settimana</strong></p></td>
<td><ul>
<li><p><strong>Giorno</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Giorno</strong></p></td>
<td><ul>
<li><p><strong>Giorno</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

L'impostazione del periodo di fatturazione rappresenta una parte obbligatoria dell'impostazione generale dei gruppi di sottoscrizioni. È possibile decidere se impostare anche un periodo di attribuzione per competenza per il gruppo di sottoscrizioni. Se si imposta, il periodo di attribuzione per competenza per il gruppo di sottoscrizioni viene suggerito nel campo **Codice periodo**, che si trova nel modulo **Accumula ricavi sottoscrizione** quando vengono accumulati i ricavi della sottoscrizione. Tale informazione relativa al gruppo di sottoscrizioni è comunque facoltativa.


> [!NOTE]
> <P>Utilizzare il seguente percorso per aprire il modulo <STRONG>Accumula ricavi sottoscrizione</STRONG>. Fare clic su <STRONG>Gestione assistenza</STRONG> &gt; <STRONG>Periodico</STRONG> &gt; <STRONG>Sottoscrizioni assistenza</STRONG> &gt; <STRONG>Accumula ricavi sottoscrizione</STRONG>.</P>


## <a name="transactions"></a>Transazioni

È possibile controllare il numero di transazioni contabili create quando si registrano i ricavi sospesi. Nelle sottoscrizioni definire se le transazioni contabili devono essere create come totale o per riga.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Specificare il livello di dettagli di registrazione da visualizzare per le transazioni di attribuzione per competenza

1.  Fare clic su **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.

2.  Nel campo **Fattura** disponibile nella scheda **Finanziario** selezionare **Totale** o **Riga**.


## <a name="see-also"></a>Vedere anche

[Accumula ricavi sottoscrizione](accrue-subscription-revenue.md)

  


