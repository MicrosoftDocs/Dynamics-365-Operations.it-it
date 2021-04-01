---
title: Report Aging clienti
description: Nel report Aging clienti vengono visualizzati i saldi esigibili dai clienti ordinati per intervallo di date o per periodo di aging.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236988"
---
# <a name="customer-aging-report"></a>Report di aging clienti 

Nel report **Aging clienti** vengono visualizzati i saldi esigibili dai clienti ordinati per intervallo di date o per periodo di aging.

Quando si genera questo report, vengono visualizzati i seguenti parametri predefiniti. È possibile utilizzare tali parametri per filtrare i dati che verranno visualizzati nel report. Per ulteriori informazioni, vedere [Impostare la riscossione](set-up-collections.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Campo</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classificazione della priorità di pagamento</strong></p></td>
<td><p>Selezionare una o più classificazioni della priorità di pagamento da includere nel report.</p>
<div class="alert">

**Nota:** questo controllo è disponibile solo se è stata selezionata la chiave di configurazione <STRONG>Settore pubblico</STRONG>.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Includi transazioni senza una classificazione della priorità di pagamento</strong></p></td>
<td><p>Se questa casella di controllo è selezionata, verranno incluse nel report tutte le transazioni alle quali non è assegnata una classificazione della priorità di pagamento.</p>
<div class="alert">

**Nota:** questo controllo è disponibile solo se è stata selezionata la chiave di configurazione <STRONG>Settore pubblico</STRONG>.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Aging a partire dal</strong></p></td>
<td><p>Immettere la data utilizzata nel bucket di aging corrente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo a partire da</strong></p></td>
<td><p>Immettere la data per cui si desidera visualizzare i saldi dei clienti, nota anche come data limite per le transazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data di inizio</strong></p></td>
<td><p>Immettere una data compresa nel primo intervallo periodico o periodo di aging da includere nel report.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Criteri</strong></p></td>
<td><p>Selezionare il tipo di data su cui basare il report.</p>
<ul>
<li><p><strong>Data della transazione</strong>: la data di registrazione della transazione selezionata. Ad esempio potrebbe essere la data di una fattura su cui è basato il calcolo della data di scadenza.</p></li>
<li><p><strong>Data di scadenza</strong>: la data di scadenza delle transazioni basata sui termini di pagamento.</p></li>
<li><p><strong>Data documento</strong>: la data del documento definita dall'utente su cui è basato il calcolo della data di scadenza.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Definizione periodo di aging</strong></p></td>
<td><p>Consente di selezionare una definizione del periodo di aging. Se si seleziona una definizione del periodo di aging, il campo <strong>Intervallo</strong> non viene utilizzato.</p>
<p>Per la stampa del report non è possibile utilizzare definizioni del periodo di aging con più di sei periodi di aging.</p>
<div class="alert">

**Nota:** è possibile impostare periodi di aging nella pagina <STRONG>Definizioni periodo di aging</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Stampa descrizione periodo di aging</strong></p></td>
<td><p>Selezionare <strong>Sì</strong> per includere nel report le descrizioni dei periodi di aging nella parte superiore di ciascuna colonna del periodo di aging. Selezionare <strong>No</strong> per stampare il report senza le intestazioni di colonna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Definire il periodo da utilizzare immettendo il numero di unità, espresso in giorni o mesi, per ciascun periodo. Ad esempio, per visualizzare le informazioni di aging per settimana, immettere 7 in questo campo e selezionare <strong>Giorno</strong> nel campo <strong>Giorni/Mese</strong>.</p>
<div class="alert">

**Nota:** le informazioni immesse in questo campo vengono utilizzate solo se non è stata selezionata una definizione del periodo di aging. In caso contrario, la direzione di stampa viene definita nella definizione del periodo di aging.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Giorno/mese</strong></p></td>
<td><p>Selezionare l'unità, <strong>Giorno</strong> o <strong>Mese</strong>, utilizzata per definire il periodo nel campo <strong>Intervallo</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Direzione di stampa</strong></p></td>
<td><p>Specificare se calcolare i saldi e stampare il report di aging per periodi trascorsi o futuri. Le date vengono valutate rispetto alla data selezionata nel campo <strong>Saldo a partire da</strong>. Per visualizzare le informazioni relative ai periodi trascorsi, selezionare <strong>Indietro</strong>. Per visualizzare le informazioni relative ai periodi futuri, selezionare <strong>Avanti</strong>.</p>
<div class="alert">
  
<STRONG>Nota:</STRONG> le informazioni immesse in questo campo vengono utilizzate solo se non è stata selezionata una definizione del periodo di aging.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Dettagli</strong></p></td>
<td><p>Selezionare questo campo per elencare le transazioni incluse nei saldi visualizzati nel report.</p></td>
</tr>
<tr class="even">
<td><p><strong>Includi importi in valuta della transazione</strong></p></td>
<td><p>Selezionare questo campo per includere gli importi nella valuta della transazione oltre agli importi nella valuta di contabilizzazione. Se questa casella di controllo non è selezionata, gli importi nel report vengono visualizzati solo nella valuta di contabilizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo negativo</strong></p></td>
<td><p>Selezionare questo campo per includere i conti cliente con saldi negativi.</p></td>
</tr>
<tr class="even">
<td><p><strong>Escludi conti con saldo zero</strong></p></td>
<td><p>Selezionare questo campo per escludere i conti cliente con saldo zero.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Posizionamento pagamento</strong></p></td>
<td><p>Seleziona questo campo per visualizzare i pagamenti non liquidati. Vengono visualizzati nella prima colonna del report.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]